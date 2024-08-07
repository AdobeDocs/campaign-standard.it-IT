---
title: Transfer file
description: L’attività Transfer file ti consente di ricevere o inviare file, verificare se sono presenti o elencarli in Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileTransfer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 736bf3dc-96c4-4518-96f8-d9aaa46d7f84
source-git-commit: 53852538ac1e092dc9376119f29d969ed4b02952
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 75%

---

# Trasferimento file{#transfer-file}

## Descrizione {#description}

![](assets/file_transfer.png)

L’attività **[!UICONTROL Transfer file]** ti consente di ricevere o inviare file, verificare se sono presenti o elencarli in Adobe Campaign.

## Contesto di utilizzo {#context-of-use}

La modalità di estrazione dei dati viene definita durante la configurazione dell’attività. Il file da caricare può rappresentare un elenco di contatti, ad esempio.

Puoi utilizzare questa attività per recuperare dati che sono quindi strutturati con l’attività **[!UICONTROL Load file]**.

**Argomenti correlati:**

* [Caso di utilizzo: aggiornamento dei dati in base a un download automatico del file](../../automating/using/update-data-automatic-download.md)

## Configurazione {#configuration}

1. Rilascia un’attività **[!UICONTROL Transfer file]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Utilizza l’elenco a discesa nel campo **[!UICONTROL Action]** per selezionare una delle seguenti azioni dell’attività:

   ![](assets/wkf_file_transfer_01.png)

   * **File download**: ti consente di scaricare un file.
   * **File upload**: ti consente di caricare un file. Il caricamento di un file da un file di Adobe Campaign genera una voce di registro nel menu **[!UICONTROL Export audits]**. Per ulteriori informazioni sui controlli delle esportazioni, consulta la sezione [Controllo delle esportazioni](../../administration/using/auditing-export-logs.md).
   * **Test to see if file exists**: ti consente di verificare se è presente un file.
   * **File listing**: ti consente di elencare i file presenti sul server definito nella scheda **[!UICONTROL Protocol]**. Puoi utilizzare questa azione principalmente a scopo di debug, per verificare se l’attività è configurata in base alle tue esigenze prima di scaricare i file dal server remoto.

1. Seleziona il protocollo da utilizzare:
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Archiviazione BLOB di Microsoft Azure](#azure-blob-configuration-wf)
   * [File presenti sul server Adobe Campaign](#files-server-configuration-wf)

1. La sezione **[!UICONTROL Additional options]**, disponibile a seconda del protocollo selezionato, consente di aggiungere parametri al protocollo.

   Puoi eseguire le seguenti azioni:

   * **[!UICONTROL Delete the source files after transfer]**: cancella i file sul server remoto. Se lasci questa opzione deselezionata, assicurati di monitorare manualmente le dimensioni del contenuto archiviato nella directory SFTP.

   * **[!UICONTROL Sorting files]**: consente di ordinare i file in ordine alfanumerico. Questa opzione è disabilitata per impostazione predefinita.

     <!--**[!UICONTROL Disable passive mode]**: allows you to specify the connection port to be used for data transfer.-->

   * **[!UICONTROL List all files]**: opzione disponibile quando si seleziona l&#39;azione **[!UICONTROL File listing]** nella scheda **[!UICONTROL General]**. Ti consente di indicizzare tutti i file presenti sul server nella variabile dell’evento **vars.filenames**, in cui i nomi dei file sono separati da **“n”** caratteri.

1. La sezione **[!UICONTROL If no files are found]** della scheda **[!UICONTROL Advanced options]** ti permette di configurare azioni specifiche in caso di errori o file inesistenti rilevati all’avvio dell’attività.

   Puoi anche definire il numero dei tentativi. I diversi tentativi vengono visualizzati nel log di esecuzione del flusso di lavoro.

   ![](assets/wkf_file_transfer_09.png)

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

### Configurazione con HTTP {#HTTP-configuration-wf}

Il protocollo HTTP ti consente di iniziare a scaricare un file da un account esterno o da un URL.

Con questo protocollo, è possibile scegliere l&#39;opzione **[!UICONTROL Use connection parameters defined in an external account]**. In questo caso, seleziona l’account desiderato e specifica il percorso del file da scaricare.

![](assets/wkf_file_transfer_03.png)

Puoi anche scegliere l’opzione **[!UICONTROL Quick configuration]**. Devi solo inserire l’URL nel relativo campo.
![](assets/wkf_file_transfer_04.png)

**[!UICONTROL Follow redirections]**, **[!UICONTROL Ignore the HTTP return code]** e **[!UICONTROL Add received HTTP headers to the file]** sono le opzioni aggiuntive disponibili quando si seleziona il protocollo HTTP.

### Configurazione con SFTP {#SFTP-configuration-wf}

Il protocollo SFTP ti consente di iniziare a scaricare un file da un URL o da un account esterno.

Con questo protocollo, puoi scegliere l&#39;opzione **[!UICONTROL Use connection parameters defined in an external account]**, quindi selezionare l&#39;account desiderato e specificare il percorso del file da scaricare.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>I caratteri jolly sono supportati.

Puoi anche scegliere l’opzione **[!UICONTROL Quick configuration]**. Devi solo inserire l’URL nel relativo campo.

### Configurazione con Amazon S3 {#S3-configuration-wf}

Il protocollo Amazon S3 ti consente di iniziare a scaricare un file da un URL o da un account esterno tramite Amazon Simple Storage Service (S3).

1. Seleziona un account esterno di Amazon S3. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. Scegli se vuoi **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**.

3. Specifica il percorso del file da scaricare.

   ![](assets/wkf_file_transfer_08.png)

   >[!CAUTION]
   >
   > I caratteri jolly non sono supportati in Amazon S3.
   >
   > Per eseguire il targeting di più file come `my_file_02` e `my _file_3433`, è possibile utilizzare la seguente sintassi: `acs-myawsbucket.s3.amazonaws.com/object-path/my_file_`.

4. Se desideri eliminare i file sorgente al termine del trasferimento, seleziona la casella **[!UICONTROL Delete the source files after transfer]**.

### Configurazione con l’archiviazione BLOB di Microsoft Azure {#azure-blob-configuration-wf}

Il protocollo BLOB di Microsoft Azure ti consente di accedere a BLOB che si trovano in un account di archiviazione BLOB di Microsoft Azure.

1. Seleziona un account esterno **[!UICONTROL Microsoft Azure Blob]**. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. Scegli se vuoi **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Specifica il percorso del file da scaricare, che può corrispondere a più BLOB. In questo caso, l’attività **[!UICONTROL File transfer]** attiva la transizione in uscita ogni volta che viene trovato un BLOB. Vengono quindi elaborati in ordine alfabetico.

   >[!CAUTION]
   >
   >I caratteri jolly non sono supportati nel caso vengano riscontrati gli stessi nomi per più file. Invece, devi immettere un prefisso. Tutti i nomi dei BLOB che corrispondono a quel prefisso risultano idonei.

   Di seguito trovi alcuni esempi di percorsi di file:

   * **&quot;campaign/&quot;**: rileva tutti i BLOB nella cartella Campaign che si trova nella directory principale del contenitore.
   * **&quot;campaign/new-&quot;**: rileva tutti i BLOB con un nome di file che inizia con &quot;new-&quot; e si trova nella cartella Campaign.
   * **&quot;&quot;**: l’aggiunta di un percorso vuoto ti consente di far coincidere tutti i BLOB disponibili nel contenitore.

### Configurazione con file presenti sul server Adobe Campaign {#files-server-configuration-wf}

Il protocollo **[!UICONTROL File(s) present on the Adobe Campaign server]** corrisponde all’archivio contenente i file da recuperare.
Metacaratteri o caratteri jolly (ad esempio &#42; o ?) può essere utilizzato per filtrare i file.

Scegli se desideri **[!UICONTROL Define a file path]** o **[!UICONTROL Use a dynamic file path]**. L’opzione **[!UICONTROL Use a dynamic file path]** ti consente di utilizzare un’espressione standard e variabili di eventi per personalizzare il nome del file da trasferire. Per ulteriori informazioni, consulta [questa pagina](../../automating/using/customizing-workflow-external-parameters.md).

Il percorso deve essere relativo alla directory dello spazio di archiviazione del server di Adobe Campaign. I file si trovano nella directory **sftp&lt;nomeistanza>/**. Inoltre, non è possibile sfogliare le directory al di sopra dello spazio di archiviazione.

Ad esempio:

`user&lt;yourinstancename>/my_recipients.csv` è corretto.

`../hello/my_recipients.csv` non è corretto.

`//myserver/hello/myrecipients.csv` non è corretto.

## Impostazioni di storicizzazione {#historization-settings}

Tutte le volte che esegui un’attività **[!UICONTROL Transfer file]**, memorizzi i file caricati o scaricati in una cartella dedicata. Viene creata una cartella per ogni attività **[!UICONTROL Transfer file]** di un flusso di lavoro. Pertanto, è importante poter limitare le dimensioni di questa cartella per preservare lo spazio fisico sul server.

A questo scopo, puoi definire le **[!UICONTROL Historization settings]** nelle **[!UICONTROL Advanced options]** dell’attività **[!UICONTROL Transfer File]**.

**[!UICONTROL Historization settings]** ti consentono di definire un numero massimo di file o una dimensione totale per la cartella dell’attività. Per impostazione predefinita sono autorizzati 100 file e 50 MB.

Tutte le volte che l’attività viene eseguita, la cartella viene controllata come segue:

* Vengono presi in considerazione solo file creati più di 24 ore prima dell’esecuzione dell’attività.
* Se il numero di file considerati è maggiore del valore del parametro **[!UICONTROL Maximum number of files]**, i file meno recenti vengono eliminati finché non viene raggiunto il **[!UICONTROL Maximum number of files]** consentito.
* Se la dimensione totale dei file considerati è maggiore del valore del parametro **[!UICONTROL Maximum size (in MB)]**, i file meno recenti vengono eliminati finché non viene raggiunta la **[!UICONTROL Maximum size (in MB)]** consentita.

>[!NOTE]
>
>Se l’attività non viene eseguita nuovamente, la relativa cartella non viene né controllata né eliminata. In quest’ottica, fai attenzione durante il trasferimento di file di grandi dimensioni.

## Variabili di output {#output-variables}

L&#39;attività **[!UICONTROL Transfer file]** genera variabili evento come output, che è possibile sfruttare in altre attività, ad esempio per verificare il numero di file scaricati utilizzando un&#39;attività [Test](../../automating/using/test.md).

Si noti che le variabili di evento possono essere passate anche a un altro flusso di lavoro utilizzando un segnale esterno (vedere [Personalizzazione di un flusso di lavoro con parametri esterni](../../automating/using/customizing-workflow-external-parameters.md)).

Le variabili di output disponibili sono:

* **[!UICONTROL fileName]**: nome dei file trasferiti.
* **[!UICONTROL filesCount]**: numero di file trasferiti.
