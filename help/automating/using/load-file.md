---
title: Caricare file
description: L'attività Carica file consente di importare dati in un modulo strutturato per utilizzarli in Adobe Campaign.
page-status-flag: mai attivato
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: gestione dei dati
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caricare file{#load-file}

## Descrizione {#description}

![](assets/data_loading.png)

L' **[!UICONTROL Load file]** attività consente di importare i dati in un modulo strutturato per utilizzarli in Adobe Campaign. I dati vengono importati temporaneamente e un'altra attività è necessaria per integrarli definitivamente nel database Adobe Campaign.

## Contesto di utilizzo {#context-of-use}

Il modo in cui i dati verranno estratti viene definito quando l'attività viene configurata. Il file da caricare può essere un elenco di contatti, ad esempio.

>[!CAUTION]
>
>Vengono presi in considerazione solo i file di struttura "flat", ad esempio i file .txt, .csv e così via.

È possibile:

* Utilizzare la struttura del file per applicarla ai dati di un altro file (recuperati utilizzando l' **[!UICONTROL Transfer file]** attività) o,
* Usa la struttura e i dati del file per importarlo in Adobe Campaign.

## Configurazione {#configuration}

La configurazione dell'attività prevede due passaggi. Innanzitutto, occorre definire la struttura del file prevista caricando un file di esempio. Al termine, è possibile specificare l'origine del file i cui dati verranno importati.

>[!NOTE]
>
>I dati del file di esempio vengono utilizzati per configurare l'attività, ma non vengono importati. È consigliabile utilizzare un file di esempio contenente dati limitati.

1. Trascinate e rilasciate un' **[!UICONTROL Load file]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Caricate il file di esempio che vi consentirà di definire la struttura prevista al momento dell'importazione del file finale.

   ![](assets/wkf_file_loading.png)

   Una volta caricato il file di dati, nell'attività vengono visualizzate due nuove schede: **[!UICONTROL File structure]** e **[!UICONTROL Column definition]**.

1. Passate alla **[!UICONTROL File structure]** scheda per visualizzare la struttura rilevata automaticamente dal file di esempio.

   Se la struttura del file non è stata rilevata correttamente, sono disponibili diverse opzioni per correggere eventuali errori:

   * Potete scegliere di utilizzare la struttura di un altro file selezionando l’ **[!UICONTROL Detect structure from a new file]** opzione.
   * Potete modificare i parametri di rilevamento predefiniti per adattarli al file. Il **[!UICONTROL File type]** campo consente di specificare se il file da importare è costituito da colonne con lunghezza fissa. In tal caso, è inoltre necessario specificare il numero massimo di caratteri per ciascuna colonna della **[!UICONTROL Column definition]** scheda.

      Tutte le opzioni di rilevamento necessarie per recuperare correttamente i dati dal file sono raggruppate in **[!UICONTROL File format]**. Potete modificarle e quindi rilevare nuovamente la struttura dell'ultimo file caricato nell'attività tenendo conto di queste nuove impostazioni. A questo scopo, utilizzare il **[!UICONTROL Apply configuration]** pulsante. Ad esempio, è possibile specificare un separatore di colonna diverso.

      >[!NOTE]
      >
      >Questa operazione prende in considerazione l'ultimo file caricato nell'attività. Se il file rilevato è grande, l'anteprima dati mostrerà solo le prime 30 righe.

      ![](assets/wkf_file_loading3.png)

      Nella **[!UICONTROL File format]** sezione, l' **[!UICONTROL Check columns from file against column definitions]** opzione consente di verificare che le colonne del file che si sta caricando corrispondano alla definizione della colonna.

      Se il numero e/o il nome delle colonne non corrisponde alla definizione della colonna, durante l'esecuzione del flusso di lavoro verrà visualizzato un messaggio di errore. Se l'opzione non è attivata, nel file di registro verranno visualizzati degli avvisi.

      ![](assets/wkf_file_loading_check.png)

1. Vai alla **[!UICONTROL Column definition]** scheda per controllare il formato dei dati per ogni colonna e regolare i parametri se necessario.

   La **[!UICONTROL Column definition]** scheda consente di specificare con precisione la struttura dati di ciascuna colonna al fine di importare dati che non contengono errori (ad esempio, utilizzando la gestione null) e di farli corrispondere ai tipi già presenti nel database Adobe Campaign per le operazioni future.

   Ad esempio, è possibile modificare l'etichetta di una colonna, selezionarne il tipo (stringa, numero intero, data, ecc.)  oppure specificare l'elaborazione degli errori.

   Per ulteriori informazioni, consultare la sezione Formato [](#column-format) colonna.

   ![](assets/wkf_file_loading4.png)

1. Nella **[!UICONTROL Execution]** scheda, specificare se il file deve essere elaborato per il caricamento dei dati:

   * Proviene da una transizione in entrata nel flusso di lavoro.
   * È quello caricato durante il passaggio precedente.
   * È un nuovo file da caricare dal computer locale. L' **[!UICONTROL Upload a new file from local machine]** opzione viene visualizzata se il caricamento di un primo file era già stato definito nel flusso di lavoro. Questo consente di caricare un altro file da elaborare se il file corrente non soddisfa le vostre esigenze.

      ![](assets/wkf_file_loading1.png)

1. Se il file da cui si desidera caricare i dati è compresso in un file GZIP (.gz), selezionare l' **[!UICONTROL Decompression]** opzione nel **[!UICONTROL Add a pre-processing step]** campo. Questo consente di decomprimere il file prima di caricare i dati. Questa opzione è disponibile solo se il file proviene dalla transizione in entrata dell'attività.
1. L’ **[!UICONTROL Keep the rejects in a file]** opzione consente di scaricare un file contenente errori verificatisi durante l’importazione e di applicarvi una fase di post-elaborazione. Quando l’opzione è attivata, la transizione in uscita viene rinominata come "Rifiuti".

   >[!NOTE]
   >
   >L' **[!UICONTROL Add date and time to the file name]** opzione consente di aggiungere una marca temporale al nome del file contenente i rifiuti.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Se si verifica un errore con l'attività dopo l'esecuzione del flusso di lavoro, fare riferimento ai registri per ottenere ulteriori dettagli sui valori errati nel file. For more on workflows logs, refer to [this section](../../automating/using/executing-a-workflow.md#monitoring)

## Formato colonna {#column-format}

Quando si carica un file di esempio, il formato della colonna viene rilevato automaticamente con i parametri predefiniti per ciascun tipo di dati. È possibile modificare questi parametri predefiniti per specificare i processi specifici da applicare ai dati, in particolare in caso di errore o di valore vuoto.

A questo scopo, selezionate **[!UICONTROL Edit properties]** dalle azioni rapide della colonna il cui formato desiderate definire. Viene aperta la finestra di dettaglio del formato della colonna.

![](assets/wkf_file_loading4.png)

È quindi possibile modificare la formattazione di ciascuna colonna.

La formattazione delle colonne consente di definire il valore di elaborazione di ogni colonna:

* **[!UICONTROL Ignore column]**: non elabora questa colonna durante il caricamento dei dati.
* **[!UICONTROL Data type]**: specifica il tipo di dati previsto per ogni colonna.
* **[!UICONTROL Format and separators]**, **Proprietà**: specificare le proprietà di un testo, il formato di ora, data e valore numerico, nonché il separatore specificato dal contesto della colonna.

   * **[!UICONTROL Maximum number of characters]**: specifica il numero massimo di caratteri per le colonne del tipo di stringa.

      Questo campo deve essere compilato quando si caricano file composti da colonne con lunghezza fissa.

   * **[!UICONTROL Letter case management]**: Definisce se è necessario applicare un processo di maiuscole e minuscole ai dati **Testo** .
   * **[!UICONTROL White space management]**: specifica se alcuni spazi devono essere ignorati in una stringa per i dati **Testo** .
   * **[!UICONTROL Time format]**, **[!UICONTROL Date format]**: specifica il formato per i dati **Data**, **Ora** e **Data e ora** .
   * **[!UICONTROL Format]**: consente di definire il formato dei valori numerici per i dati relativi a numeri **interi** e numeri **** mobili.
   * **[!UICONTROL Separator]**: definisce il separatore specificato dal contesto della colonna (separatore delle migliaia o separatore decimale per i valori numerici, separatore per le date e l'ora) per i dati **Data**, **Ora**, **Data e ora**, **Intero** e Numero **** mobile.

* **[!UICONTROL Remapping of values]**: questo campo è disponibile solo nella configurazione dei dettagli delle colonne. Consente di trasformare alcuni valori al momento dell’importazione. Ad esempio, potete trasformare "tre" in "3".
* **[!UICONTROL Error processing]**: definisce il comportamento in caso di errore.

   * **[!UICONTROL Ignore the value]**: il valore viene ignorato. Nel registro di esecuzione del flusso di lavoro viene generato un avviso.
   * **[!UICONTROL Reject the line]**: l'intera linea non viene elaborata.
   * **[!UICONTROL Use a default value]**: sostituisce il valore che causava l'errore con un valore predefinito, definito nel **[!UICONTROL Default value]** campo.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: sostituisce il valore che causava l'errore con un valore predefinito, definito nel **[!UICONTROL Default value]** campo, a meno che non sia stata definita una mappatura per il valore errato (vedere l' **[!UICONTROL Remapping of values]** opzione precedente).
   * **[!UICONTROL Reject the line when there is no remapping value]**: l'intera linea viene elaborata solo se è stata definita una mappatura per il valore errato (vedere l' **[!UICONTROL Remapping of values]** opzione precedente).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** si verificano errori relativi ai valori nel file importato. Ad esempio, è stato rilevato un tipo di dati errato ("quattro" in lettere per una colonna "Intero"), una stringa contenente più caratteri del numero massimo autorizzato, una data con separatori difettosi, ecc. Tuttavia, questa opzione non riguarda gli errori generati dalla gestione dei valori vuoti.

* **[!UICONTROL Default value]**: specifica il valore predefinito in base all'elaborazione degli errori scelta.
* **[!UICONTROL Empty value management]**: specifica come gestire i valori vuoti durante il caricamento dei dati.

   * **[!UICONTROL Generate an error for numerical fields]**: genera un errore solo per i campi numerici, altrimenti inserisce un valore NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autorizza valori vuoti. Il valore NULL viene quindi inserito.
   * **[!UICONTROL Generate an error]**: genera un errore se un valore è vuoto.

## Esempio 1: Aggiornamento del database {#example-1-update-the-database}

L'attività del file di caricamento struttura principalmente i dati provenienti da un'attività del file di trasferimento per integrarlo nei dati esistenti.

L'esempio seguente mostra il risultato di un'attività di caricamento del file scaricata automaticamente tramite un'attività di trasferimento, seguita da un'attività di aggiornamento dei dati. Questo flusso di lavoro mira ad arricchire il database di Adobe Campaign con nuovi profili o ad aggiornare i profili esistenti utilizzando i dati recuperati dal file importato.

![](assets/load_file_workflow_ex1.png)

1. Trascinate e rilasciate un' **[!UICONTROL Transfer file]** attività nel flusso di lavoro e configuratela in modo da ripristinare il file desiderato.
1. Trascinate e rilasciate un' **[!UICONTROL Load file]** attività nel flusso di lavoro e inseritela dopo l' **[!UICONTROL Transfer file]** attività.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Nella **[!UICONTROL File to load]** sezione della **[!UICONTROL Execution]** scheda, selezionare l' **[!UICONTROL Use the file specified in the inbound transition]** opzione.

   ![](assets/wkf_file_loading8.png)

1. Configura l'attività come specificato in precedenza.
1. Trascinate e rilasciate un' **[!UICONTROL Update data]** attività nel flusso di lavoro, inseritela dopo l' **[!UICONTROL Load file]** attività, quindi configuratela. Fare riferimento a [Dati](../../automating/using/update-data.md)di aggiornamento.

Una volta avviato il flusso di lavoro, i dati del file caricato vengono estratti e quindi utilizzati per arricchire il database di Adobe Campaign.

## Esempio 2: Invio di un’e-mail con campi arricchiti {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

L'attività del file di caricamento consente inoltre di inviare un'e-mail arricchita di dati aggiuntivi da un file esterno nello stesso flusso di lavoro.

L'esempio seguente mostra come inviare un'e-mail utilizzando dati aggiuntivi recuperati da un file esterno tramite l'attività del file di caricamento. In questo esempio, il file esterno contiene un elenco di profili con il relativo numero di account associato. Desiderate importare questi dati per inviare un messaggio e-mail a ogni profilo con il relativo numero di account.

![](assets/load_file_workflow_ex2.png)

1. Trascinate e rilasciate un' **[!UICONTROL Query]** attività nel flusso di lavoro e apritela per definire la destinazione principale.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Trascinare un' **[!UICONTROL Load file]** attività per assegnare alcuni dati a un profilo. In questo esempio, caricate un file contenente i numeri di account corrispondenti ad alcuni profili del database.

   ![](assets/load_file_activity.png)

1. Trascinate e rilasciate un' **[!UICONTROL Enrichment]** attività nel flusso di lavoro, quindi collegate il file di caricamento e le attività di query ad esso.

1. Nella **[!UICONTROL Advanced relations]** scheda dell'attività di arricchimento, selezionare i campi **[!UICONTROL 0 or 1 cardinality simple link]** e definirli per la riconciliazione. Qui usiamo il cognome per riconciliare i dati con i profili del database.

   ![](assets/load_file_enrichment_relation.png)

1. Nella **[!UICONTROL Additional data]** scheda, selezionate gli elementi che desiderate utilizzare nel messaggio e-mail. Qui selezionate il numero di account (colonna dal file recuperato tramite l'attività del file di caricamento).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Per ulteriori informazioni, vedere la sezione [Arricchimento](../../automating/using/enrichment.md) .

1. Trascinate e rilasciate un' **[!UICONTROL Segmentation]** attività nel flusso di lavoro e apritela per perfezionare la destinazione principale.

   ![](assets/load_file_segmentation.png)

   Per ulteriori informazioni, consulta la sezione [Segmentazione](../../automating/using/segmentation.md) .

1. Trascinate e rilasciate un' **[!UICONTROL Email delivery]** attività nel flusso di lavoro per aprirla.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Aggiungi un campo di personalizzazione e seleziona dal **[!UICONTROL Additional data (targetData)]** nodo i dati aggiuntivi definiti nell'attività di arricchimento (qui Numero account). Questo consente di recuperare in modo dinamico il numero di account di ciascun profilo presente nel contenuto dell'e-mail.

   ![](assets/load_file_perso_field.png)

1. Salvate il messaggio e-mail e avviate il flusso di lavoro.

L'e-mail viene inviata alla destinazione. Ogni profilo riceve l’e-mail con il numero di account corrispondente.

![](assets/load_file_email.png)
