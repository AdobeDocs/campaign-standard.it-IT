---
title: Trasferire file
description: L'attività Trasferisci file consente di ricevere o inviare file, verificare se sono presenti file o elencare file in Adobe Campaign.
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Trasferire file{#transfer-file}

## Descrizione {#description}

![](assets/file_transfer.png)

L&#39; **[!UICONTROL Transfer file]**attività consente di ricevere o inviare file, verificare se sono presenti file o elencare file in Adobe Campaign.

## Contesto di utilizzo {#context-of-use}

Il modo in cui i dati verranno estratti viene definito quando l&#39;attività viene configurata. Il file da caricare può essere un elenco di contatti, ad esempio.

Potete utilizzare questa attività per recuperare i dati che saranno quindi strutturati con l&#39; **[!UICONTROL Load file]**attività.

## Configurazione {#configuration}

1. Rilascia un&#39; **[!UICONTROL Transfer file]**attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Utilizzate l&#39;elenco a discesa nel **[!UICONTROL Action]**campo per selezionare una delle seguenti azioni di attività:

   ![](assets/wkf_file_transfer_01.png)

   * **Download** file: consente di scaricare un file.
   * **Caricamento** file: consente di caricare un file. Il caricamento di un file da un file Adobe Campaign genera una voce di registro nel **[!UICONTROL Export audits]**menu. Per ulteriori informazioni sui controlli delle esportazioni, consultare la sezione[Controllo delle esportazioni](../../administration/using/auditing-export-logs.md).
   * **Verificare se il file esiste**: consente di verificare se è presente un file.
   * **Elenco** file: consente di elencare i file presenti in Adobe Campaign.
   A seconda dell’azione selezionata, sono disponibili uno o più protocolli:

   * **HTTP**: questo protocollo consente di iniziare a scaricare un file da un account esterno o da un URL.

      * Fate clic sull&#39; **[!UICONTROL Use connection parameters defined in an external account]**opzione, quindi selezionate l&#39;account desiderato e specificate il percorso del file da scaricare.

         ![](assets/wkf_file_transfer_03.png)

      * Fate clic sull&#39; **[!UICONTROL Quick configuration]**opzione, quindi immettete l&#39;URL nel campo che viene visualizzato.

         ![](assets/wkf_file_transfer_04.png)
   * **S3**: questo protocollo consente di iniziare a scaricare un file da un URL o un account esterno tramite Amazon Simple Storage Service (S3).

      * Selezionate l’account esterno e specificate il percorso del file da scaricare.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: questo protocollo consente di iniziare a scaricare un file da un URL o da un account esterno.

      * Fate clic sull&#39; **[!UICONTROL Use connection parameters defined in an external account]**opzione, quindi selezionate l&#39;account desiderato e specificate il percorso del file da scaricare.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >I caratteri jolly sono supportati.

      * Fate clic sull&#39; **[!UICONTROL Quick configuration]**opzione, quindi immettete l&#39;URL nel campo che viene visualizzato.
      * Per ordinare i file importati, selezionate l’ **[!UICONTROL Sort alphanumerically]**opzione dalla**[!UICONTROL Additional options]** sezione. I file verranno quindi elaborati in ordine sequenziale.

         ![](assets/wkf_file_transfer_sort.png)
   * **File presenti nel server** Adobe Campaign: questo protocollo corrisponde al repository contenente i file da recuperare.

      Metacaratteri o caratteri jolly (ad esempio * o ?) può essere utilizzato per filtrare i file.

      Compilate questo campo e confermate l&#39;attività per utilizzare questo protocollo.

      >[!NOTE]
      >
      >Il percorso deve essere relativo alla directory dello spazio di archiviazione del server Adobe Campaign. I file si trovano nella directory **sftp&lt;nomeistanza>/** . Non è inoltre possibile scorrere le directory sopra lo spazio di archiviazione. Ad esempio:

      >**user&lt;nomeistanza>/my_recipients.csv** è corretto.
      **../hello/my_recipients.csv** non è corretto.
      **/myserver/hello/myrecipients.csv** non è corretto.
   Seleziona il protocollo e completa i campi associati.

   L&#39; **[!UICONTROL Use a dynamic file path]**opzione, disponibile per ciascun protocollo, consente di utilizzare un&#39;espressione standard e variabili di eventi per personalizzare il nome del file da trasferire. Per ulteriori informazioni, vedere la sezione[Personalizzazione delle attività con variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)di eventi.

1. La **[!UICONTROL Additional options]**sezione, disponibile a seconda del protocollo selezionato, consente di aggiungere parametri al protocollo. È possibile:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: questa opzione è disponibile quando si seleziona l’**[!UICONTROL File listing]** azione. Consente di indicizzare tutti i file presenti sul server nella variabile di evento **vars.filenames** , in cui i nomi dei file sono separati dai **&#39;n&#39;** caratteri.

1. La **[!UICONTROL If no files are found]**sezione della**[!UICONTROL Advanced options]** scheda consente di configurare azioni specifiche in caso di errori o file inesistenti rilevati all&#39;avvio dell&#39;attività.

   È inoltre possibile definire i tentativi. I diversi tentativi vengono visualizzati nel registro di esecuzione del flusso di lavoro.

   ![](assets/wkf_file_transfer_09.png)

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

## Impostazioni di istorizzazione {#historization-settings}

Ogni volta che un&#39; **[!UICONTROL Transfer file]**attività viene eseguita, memorizza i file caricati o scaricati in una cartella dedicata. Viene creata una cartella per ogni**[!UICONTROL Transfer file]** attività di un flusso di lavoro. Pertanto, è importante poter limitare le dimensioni di questa cartella al fine di preservare lo spazio fisico sul server.

Per farlo, potete definire **[!UICONTROL Historization settings]**nel**[!UICONTROL Advanced options]** dell&#39; **[!UICONTROL Transfer File]**attività.

**[!UICONTROL Historization settings]**consente di definire un numero massimo di file o una dimensione totale per la cartella dell&#39;attività. Per impostazione predefinita, sono autorizzati 100 file e 50 MB.

Ogni volta che l&#39;attività viene eseguita, la cartella viene controllata come segue:

* Vengono presi in considerazione solo i file creati più di 24 ore prima dell&#39;esecuzione dell&#39;attività.
* Se il numero di file presi in considerazione è maggiore del valore del **[!UICONTROL Maximum number of files]**parametro, i file meno recenti vengono eliminati finché non viene raggiunto il**[!UICONTROL Maximum number of files]** limite consentito.
* Se la dimensione totale dei file presi in considerazione è maggiore del valore del **[!UICONTROL Maximum size (in MB)]**parametro, i file meno recenti vengono eliminati finché non viene raggiunto il**[!UICONTROL Maximum size (in MB)]** limite consentito.

>[!NOTE]
Se l&#39;attività non viene eseguita di nuovo, la relativa cartella non verrà controllata né eliminata. In questo modo, prestate attenzione quando trasferite file di grandi dimensioni.

## Esempio {#example}

L&#39;esempio seguente mostra la configurazione di un&#39;attività di trasferimento **di** file che sarà seguita da un&#39;attività di file **** Load e quindi da un&#39;attività di dati **** Update. L&#39;obiettivo di questo flusso di lavoro è quello di aggiungere o aggiornare i profili del database Adobe Campaign con i dati recuperati dal flusso di lavoro.

1. Trascina e rilascia un’attività **Trasferisci file** nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Nella **[!UICONTROL Protocol]**scheda, selezionate** SFTP **.
1. Selezionate i parametri di connessione **Usa definiti in un&#39;opzione di account** esterno.
1. Immettete il nome dell’account esterno.
1. Immettere il percorso del **file sul server** remoto.

   ![](assets/wkf_file_transfer_07.png)

1. Confermate l&#39;attività e salvate il flusso di lavoro.

