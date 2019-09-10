---
title: Carica file
seo-title: Carica file
description: Carica file
seo-description: L'attività Carica file consente di importare dati in un modulo strutturato per utilizzare tali dati in Adobe Campaign.
page-status-flag: never-activated
uuid: 69 af 12 cc -6 f 82-4977-9 f 53-aa 7 bc 26 f 5 d 7 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: gestione dati-attività
discoiquuid: 584 ff 893-9 b 1 b -46 c 9-9628-714 ab 349 ab 88
context-tags: Fileimport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fc3c687328c5a460b442b8b2497965ccab3be50b

---


# Carica file{#load-file}

## Descrizione {#description}

![](assets/data_loading.png)

L' **[!UICONTROL Load file]** attività consente di importare dati in un modulo strutturato per utilizzare tali dati in Adobe Campaign. I dati vengono importati temporaneamente e un'altra attività è necessaria per integrarla definitivamente nel database di Adobe Campaign.

## Contesto di utilizzo {#context-of-use}

Il modo in cui i dati vengono estratti viene definito quando l'attività è configurata. Ad esempio, il file da caricare può essere un elenco di contatti.

>[!CAUTION]
>
>Sono inclusi solo i file di struttura «flat», ad esempio i file.txt. csv, ecc., i file.

Potete:

* Utilizzate la struttura del file per applicarla ai dati di un altro file (recuperati utilizzando l **[!UICONTROL Transfer file]** 'attività) o,
* Utilizza la struttura e i dati del file per importarli in Adobe Campaign.

## Configurazione {#configuration}

La configurazione dell'attività prevede due passaggi. Innanzitutto, è necessario definire la struttura del file prevista caricando un file di esempio. Una volta effettuata questa operazione, potete specificare l'origine del file i cui dati verranno importati.

>[!NOTE]
>
>I dati del file di esempio vengono utilizzati per configurare l'attività ma non vengono importati. È consigliabile utilizzare un file di esempio contenente piccoli dati.

1. Trascina un **[!UICONTROL Load file]** 'attività nel tuo flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante dalle azioni rapide visualizzate.
1. Caricate il file di esempio che vi consentirà di definire la struttura prevista durante l'importazione del file finale.

   ![](assets/wkf_file_loading.png)

   Una volta caricato il file di dati, nell'attività vengono visualizzate due nuove schede: **[!UICONTROL File structure]** e **[!UICONTROL Column definition]**.

1. Passate alla **[!UICONTROL File structure]** scheda per visualizzare la struttura rilevata automaticamente dal file di esempio.

   Se la struttura del file è stata rilevata in modo errato, è possibile correggere eventuali errori possibili:

   * Potete scegliere di utilizzare la struttura di un altro file selezionando **[!UICONTROL Detect structure from a new file]** l'opzione.
   * Potete modificare i parametri di rilevamento predefiniti per adattarli al file. **[!UICONTROL File type]** Il campo consente di specificare se il file da importare è composto da colonne con lunghezza fissa. In tal caso, è necessario specificare anche il numero massimo di caratteri per ogni colonna della **[!UICONTROL Column definition]** scheda.

      Tutte le opzioni di rilevamento necessarie per recuperare correttamente i dati dal file vengono ridisposte in **[!UICONTROL File format]**. Potete modificarle e quindi ririlevare la struttura dell'ultimo file caricato nell'attività tenendo conto di queste nuove impostazioni. A tal fine, utilizzate il **[!UICONTROL Apply configuration]** pulsante. Ad esempio, è possibile specificare un separatore di colonna diverso.

      >[!NOTE]
      >
      >Questa operazione prende in considerazione l'ultimo file caricato nell'attività. Se il file rilevato è di grandi dimensioni, l'anteprima dati mostrerà solo le prime 30 righe.

      ![](assets/wkf_file_loading3.png)

      Nella **[!UICONTROL File format]** sezione, l' **[!UICONTROL Check columns from file against column definitions]** opzione consente di verificare che le colonne del file che state caricando corrispondano alla definizione della colonna.

      Se il numero e/o il nome delle colonne non corrisponde alla definizione della colonna, durante l'esecuzione del flusso di lavoro viene visualizzato un messaggio di errore. Se l'opzione non è attivata, gli avvisi vengono visualizzati nel file di registro.

      ![](assets/wkf_file_loading_check.png)

1. Passate alla **[!UICONTROL Column definition]** scheda per controllare il formato di dati di ciascuna colonna e regolare i parametri, se necessario.

   La **[!UICONTROL Column definition]** scheda consente di specificare con precisione la struttura dati di ciascuna colonna per importare dati che non contengono errori (ad esempio, utilizzando la gestione null) e farli corrispondere ai tipi già presenti nel database Adobe Campaign per operazioni future.

   Ad esempio, è possibile modificare l'etichetta di una colonna, selezionandone il tipo (stringa, numero intero, data, ecc.) oppure specifica anche l'elaborazione degli errori.

   Per ulteriori informazioni, consulta [la sezione Formato](../../automating/using/load-file.md#column-format) colonna.

   ![](assets/wkf_file_loading4.png)

1. Nella **[!UICONTROL Execution]** scheda specificare se il file deve essere elaborato per il caricamento dei dati:

   * Deriva da una transizione in ingresso nel flusso di lavoro.
   * È quello caricato durante il passaggio precedente.
   * È un nuovo file da caricare dal computer locale. L' **[!UICONTROL Upload a new file from local machine]** opzione viene visualizzata se nel flusso di lavoro è già stato definito un primo file. Questo consente di caricare un altro file da elaborare se il file corrente non è adatto alle vostre esigenze.

      ![](assets/wkf_file_loading1.png)

1. Se il file da cui si desidera caricare i dati viene compresso in un file GZIP (.gz), selezionare l **[!UICONTROL Decompression]** 'opzione nel **[!UICONTROL Add a pre-processing step]** campo. Questo consente di decomprimere il file prima di caricare i dati. Questa opzione è disponibile solo se il file proviene dalla transizione in entrata dell'attività.
1. L' **[!UICONTROL Keep the rejects in a file]** opzione consente di scaricare un file contenente errori che si sono verificati durante l'importazione e di applicarlo a un fase di post-elaborazione.

   >[!NOTE]
   >
   >L **[!UICONTROL Add date and time to the file name]** 'opzione consente di aggiungere un timestamp al nome del file contenente gli rifiuta.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Formato colonna {#column-format}

Quando si carica un file di esempio, il formato della colonna viene rilevato automaticamente con i parametri predefiniti per ogni tipo di dati. Potete modificare questi parametri predefiniti per specificare i processi particolari da applicare ai dati, in particolare in presenza di un errore o di un valore vuoto.

A tal fine, selezionate **[!UICONTROL Edit properties]** tra le azioni rapide della colonna di cui desiderate definire il formato. Viene aperta la finestra dei dettagli del formato colonna.

![](assets/wkf_file_loading4.png)

È quindi possibile modificare la formattazione di ogni colonna.

La formattazione delle colonne consente di definire l'elaborazione dei valori di ciascuna colonna:

* **[!UICONTROL Ignore column]**: non elabora questa colonna durante il caricamento dei dati.
* **[!UICONTROL Data type]**: specifica il tipo di dati previsto per ogni colonna.
* **[!UICONTROL Format and separators]**, **Proprietà**: specificare le proprietà di un testo, l'ora, la data e il formato numerico, nonché il separatore specificato dal contesto della colonna.

   * **[!UICONTROL Maximum number of characters]**: specifica il numero massimo di caratteri per le colonne del tipo di stringa.

      Questo campo deve essere compilato quando si caricano i file composti da colonne con lunghezza fissa.

   * **[!UICONTROL Letter case management]**: definisce se è necessario applicare un processo maiuscolo/minuscolo ai **dati Testo** .
   * **[!UICONTROL White space management]**: specifica se alcuni spazi devono essere ignorati in una stringa per **i dati Testo** .
   * **[!UICONTROL Time format]****[!UICONTROL Date format]**: specificare il formato per **Data**, **Ora** e **Data e ora** .
   * **[!UICONTROL Format]**: consente di definire il formato dei valori numerici per **Integer** e **i dati Numero** mobile.
   * **[!UICONTROL Separator]**: definisce il separatore specificato dal contesto della colonna (separatore delle migliaia o separatore decimale per valori numerici, separatore per date e ora) per **Data**, **Ora**, **Data e ora**, **Integer** e Numero **di numeri** Mobile.

* **[!UICONTROL Remapping of values]**: questo campo è disponibile solo nella configurazione dei dettagli delle colonne. Consente di trasformare alcuni valori durante l'importazione. Ad esempio, potete trasformare «tre» in «3».
* **[!UICONTROL Error processing]**: definisce il comportamento se viene rilevato un errore.

   * **[!UICONTROL Ignore the value]**: il valore viene ignorato. Un avviso viene generato nel registro dell'esecuzione del flusso di lavoro.
   * **[!UICONTROL Reject the line]**: l'intera riga non viene elaborata.
   * **[!UICONTROL Use a default value]**: sostituisce il valore che causava l'errore con un valore predefinito, definito nel **[!UICONTROL Default value]** campo.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: sostituisce il valore che causava l'errore con un valore predefinito definito nel **[!UICONTROL Default value]** campo, a meno che non sia stata definita una mappatura per il valore errato (consultate **[!UICONTROL Remapping of values]** l'opzione sopra).
   * **[!UICONTROL Reject the line when there is no remapping value]**: l'intera riga non viene elaborata a meno che non sia stata definita una mappatura per il valore errato (consultate **[!UICONTROL Remapping of values]** l'opzione sopra).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** problemi relativi ai valori nel file importato. Ad esempio, un tipo di dati difettoso rilevato («quattro» in lettere per una colonna «Integer»), una stringa contenente più caratteri del numero massimo consentito, una data con separatori difettosi e così via. Tuttavia, questa opzione non riguarda gli errori generati dalla gestione dei valori vuota.

* **[!UICONTROL Default value]**: specifica il valore predefinito in base all'elaborazione degli errori scelta.
* **[!UICONTROL Empty value management]**: specifica come gestire valori vuoti durante il caricamento dei dati.

   * **[!UICONTROL Generate an error for numerical fields]**: genera un errore solo per i campi numerici, in caso contrario inserisce un valore NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autorizza valori vuoti. Il valore NULL viene quindi inserito.
   * **[!UICONTROL Generate an error]**: genera un errore se un valore è vuoto.

## Esempio 1: Aggiornamento del database {#example-1-update-the-database}

L'attività dei file di caricamento struttura principalmente i dati recuperati da un'attività del file di trasferimento per integrarlo nei dati esistenti.

L'esempio seguente mostra il risultato di un'attività di caricamento caricato automaticamente tramite un'attività di trasferimento di file, seguita da un'attività di dati update. Questo flusso di lavoro intende arricchire il database Adobe Campaign con nuovi profili o aggiornare i profili esistenti utilizzando i dati recuperati dal file importato.

![](assets/load_file_workflow_ex1.png)

1. Trascina un **[!UICONTROL Transfer file]** 'attività nel tuo flusso di lavoro e la configura in modo che recuperi il file desiderato.
1. Trascinate un **[!UICONTROL Load file]** 'attività nel flusso di lavoro e inseritela dopo l' **[!UICONTROL Transfer file]** attività.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante dalle azioni rapide visualizzate.
1. Nella **[!UICONTROL File to load]** sezione della **[!UICONTROL Execution]** scheda, selezionare l **[!UICONTROL Use the file specified in the inbound transition]** 'opzione.

   ![](assets/wkf_file_loading8.png)

1. Configurate l'attività come specificato precedentemente.
1. Trascinate un **[!UICONTROL Update data]** 'attività nel flusso di lavoro e inseritela dopo l' **[!UICONTROL Load file]** attività, quindi configuratela. Fare riferimento ai dati [Aggiorna](../../automating/using/update-data.md).

Una volta iniziato il flusso di lavoro, i dati del file caricato vengono estratti e utilizzati per arricchire il database Adobe Campaign.

## Esempio 2: Invio di un'e-mail con campi arricchiti {#example-2-email-with-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](../../automating/using/load-file.md#example-2-email-with-enriched-fields)-->

L'attività del file di caricamento consente anche di inviare un'e-mail con dati aggiuntivi da un file esterno nello stesso flusso di lavoro.

L'esempio seguente mostra come inviare un'e-mail utilizzando dati aggiuntivi recuperati da un file esterno tramite l'attività del file di caricamento. In questo esempio, il file esterno contiene un elenco di profili con il numero di account associato. Vuoi importare questi dati per inviare un messaggio e-mail a ciascun profilo con il relativo numero account.

![](assets/load_file_workflow_ex2.png)

1. Trascinate un **[!UICONTROL Query]** 'attività nel flusso di lavoro e apritela per definire la destinazione principale.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Trascina un **[!UICONTROL Load file]** 'attività per assegnare alcuni dati a un profilo. In questo esempio, caricate un file contenente numeri di account corrispondenti ad alcuni profili del database.

   ![](assets/load_file_activity.png)

1. Trascinate un **[!UICONTROL Enrichment]** 'attività nel flusso di lavoro e collegate ad essa il file e le attività di query.

1. Nella **[!UICONTROL Advanced relations]** scheda dell'attività di arricchimento, selezionate e **[!UICONTROL 0 or 1 cardinality simple link]** definite i campi da usare per la riconciliazione. Qui si usa il cognome per riconciliare i dati con i profili del database.

   ![](assets/load_file_enrichment_relation.png)

1. Nella **[!UICONTROL Additional data]** scheda, selezionate gli elementi che desiderate utilizzare nell'e-mail. Qui selezionate Numero account (colonna dal file recuperato tramite l'attività del file di caricamento).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Per ulteriori informazioni, consulta la [sezione Arricchimento](../../automating/using/enrichment.md) .

1. Trascinate un **[!UICONTROL Segmentation]** 'attività nel flusso di lavoro e apritela per perfezionare la destinazione principale.

   ![](assets/load_file_segmentation.png)

   Per ulteriori informazioni, consulta la sezione [Segmentazione](../../automating/using/segmentation.md) .

1. Trascinate un **[!UICONTROL Email delivery]** 'attività nel flusso di lavoro e apritela.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Aggiungi un campo personalizzato e seleziona i dati aggiuntivi definiti nell'attività di arricchimento (qui Numero account) dal **[!UICONTROL Additional data (targetData)]** nodo. Questo consente di recuperare in modo dinamico il numero di account di ogni profilo nel contenuto e-mail.

   ![](assets/load_file_perso_field.png)

1. Salva l'e-mail e avvia il flusso di lavoro.

Il messaggio e-mail viene inviato alla destinazione. Ogni profilo riceve l'e-mail con il numero di account corrispondente.

![](assets/load_file_email.png)
