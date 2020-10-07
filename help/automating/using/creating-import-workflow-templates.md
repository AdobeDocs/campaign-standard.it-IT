---
title: Creazione di modelli di flusso di lavoro per l’importazione di dati
description: Scopri come creare modelli di workflow per importare dati.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1172'
ht-degree: 1%

---


# Creazione di modelli di flusso di lavoro per l’importazione di dati {#import-workflow-template}

L’utilizzo di un modello di importazione è una procedura consigliata se è necessario importare regolarmente file con la stessa struttura.

Questo esempio mostra come impostare un flusso di lavoro che può essere riutilizzato per importare profili provenienti da un CRM nel database Adobe Campaign .

1. Crea un nuovo modello di workflow da **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Aggiungete le seguenti attività:

   * **[!UICONTROL Load file]**: Definire la struttura prevista del file contenente i dati da importare.

      >[!NOTE]
      >
      >È possibile importare solo dati da un singolo file. Se il flusso di lavoro ha più **[!UICONTROL Load file]** attività, lo stesso file verrà utilizzato ogni volta.

   * **[!UICONTROL Reconciliation]**: Riconciliare i dati importati con i dati del database.
   * **[!UICONTROL Segmentation]**: Creare filtri per elaborare i record in modo diverso a seconda che possano essere riconciliati o meno.
   * **[!UICONTROL Deduplication]**: Deduplicare i dati dal file in entrata prima di essere inseriti nel database.
   * **[!UICONTROL Update data]**: Aggiornate il database con i profili importati.

   ![](assets/import_template_example0.png)

1. Configurare l&#39; **[!UICONTROL Load file]** attività:

   * Definite la struttura prevista caricando un file di esempio. Il file di esempio deve contenere solo poche righe, ma tutte le colonne necessarie per l&#39;importazione. Controllare e modificare il formato del file per essere certi che il tipo di ogni colonna sia impostato correttamente: testo, data, numero intero, ecc. Ad esempio:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Nella **[!UICONTROL File to load]** sezione, selezionare **[!UICONTROL Upload a new file from the local machine]** e lasciare il campo vuoto. Ogni volta che viene creato un nuovo flusso di lavoro da questo modello, potete specificare qui il file desiderato, purché corrisponda alla struttura definita.

      Potete utilizzare una qualsiasi delle opzioni, ma dovete modificare di conseguenza il modello. Ad esempio, se selezionate **[!UICONTROL Use the file specified in the inbound transition]**, potete aggiungere un&#39; **[!UICONTROL Transfer file]** attività prima di recuperare il file da importare da un server FTP/SFTP.

      Se desiderate che gli utenti possano scaricare un file contenente errori verificatisi durante un&#39;importazione, verificate l&#39; **[!UICONTROL Keep the rejects in a file]** opzione e specificate il **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configurare l&#39; **[!UICONTROL Reconciliation]** attività. Lo scopo di questa attività in questo contesto è identificare i dati in arrivo.

   * Nella **[!UICONTROL Relations]** scheda, selezionare **[!UICONTROL Create element]** e definire un collegamento tra i dati importati e la dimensione di targeting dei destinatari (vedere Dimensioni e risorse [di](../../automating/using/query.md#targeting-dimensions-and-resources)targeting). In questo esempio, il campo personalizzato ID **** CRM viene utilizzato per creare la condizione di partecipazione. Utilizzare il campo o la combinazione di campi necessari, purché sia possibile identificare record univoci.
   * Nella **[!UICONTROL Identification]** scheda, lasciate l&#39; **[!UICONTROL Identify the document from the working data]** opzione deselezionata.

   ![](assets/import_template_example2.png)

1. Configurare l&#39; **[!UICONTROL Segmentation]** attività per recuperare i destinatari riconciliati in una transizione e i destinatari che non possono essere riconciliati ma che dispongono di dati sufficienti in una seconda transizione.

   La transizione con destinatari riconciliati può quindi essere utilizzata per aggiornare il database. La transizione con destinatari sconosciuti può quindi essere utilizzata per creare nuove voci di destinatari nel database se nel file è disponibile un insieme minimo di informazioni.

   I destinatari che non possono essere riconciliati e che non dispongono di dati sufficienti vengono selezionati in una transizione in uscita complementare e possono essere esportati in un file separato o semplicemente ignorati.

   * Nella **[!UICONTROL General]** scheda dell&#39;attività, impostate l&#39; **[!UICONTROL Resource type]** opzione su **[!UICONTROL Temporary resource]** e selezionate **[!UICONTROL Reconciliation]** come set di destinazione.
   * Nella **[!UICONTROL Advanced options]** scheda, selezionare l&#39; **[!UICONTROL Generate complement]** opzione per verificare se non è possibile inserire alcun record nel database. Se necessario, è possibile applicare ulteriore elaborazione ai dati complementari: esportazione di file, aggiornamento di elenchi, ecc.
   * Nel primo segmento della **[!UICONTROL Segments]** scheda, aggiungi una condizione di filtro nella popolazione in entrata per selezionare solo i record per i quali l&#39;ID CRM del profilo non è uguale a 0. In questo modo, i dati del file riconciliati con i profili del database vengono selezionati in tale sottoinsieme.

      ![](assets/import_template_example3.png)

   * Aggiungere un secondo segmento che selezioni record non riconciliati con dati sufficienti per essere inseriti nel database. Ad esempio: indirizzo e-mail, nome e cognome. Per i record che non sono riconciliati il valore dell&#39;ID CRM del profilo è uguale a 0.

      ![](assets/import_template_example3_2.png)

   * Tutti i record non selezionati nei primi due sottoinsiemi sono selezionati nella **[!UICONTROL Complement]**.

1. Configurate l&#39; **[!UICONTROL Update data]** attività che si trova dopo la prima transizione in uscita dell&#39; **[!UICONTROL Segmentation]** attività configurata in precedenza.

   * Selezionate **[!UICONTROL Update]** come **[!UICONTROL Operation type]** perché la transizione in entrata contiene solo i destinatari già presenti nel database.
   * Nella **[!UICONTROL Identification]** scheda, selezionate **[!UICONTROL Using reconciliation criteria]** e definite una chiave tra il **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato nell&#39; **[!UICONTROL Reconciliation]** attività. In questo esempio, viene utilizzato il campo personalizzato ID **** CRM.

      ![](assets/import_template_example6.png)

   * Nella **[!UICONTROL Fields to update]** scheda, indicare i campi dalla dimensione Profili da aggiornare con il valore della colonna corrispondente dal file. Se i nomi delle colonne del file sono identici o quasi identici ai nomi dei campi dimensione destinatari, è possibile utilizzare il pulsante bacchetta magica per far corrispondere automaticamente i diversi campi.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se prevedete di inviare e-mail dirette a questi profili, accertatevi di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il fornitore di posta diretta. Verificate inoltre che sia selezionata la **[!UICONTROL Address specified]** casella delle informazioni del profilo. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare, specificare **1** come **[!UICONTROL Source]** e selezionare il `postalAddress/@addrDefined` campo come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla posta diretta e sull&#39;uso dell&#39; **[!UICONTROL Address specified]** opzione, consulta [questo documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configurate l&#39; **[!UICONTROL Deduplication]** attività che si trova dopo la transizione contenente profili non riconciliati:

   * Nella **[!UICONTROL Properties]** scheda, impostare la risorsa temporanea **[!UICONTROL Resource type]** generata dall&#39; **[!UICONTROL Reconciliation]** attività del flusso di lavoro.

      ![](assets/import_template_example4.png)

   * In questo esempio, il campo e-mail viene utilizzato per trovare profili univoci. Potete utilizzare qualsiasi campo sicuramente compilato e parte di una combinazione univoca.
   * Scegli una **[!UICONTROL Deduplication method]**. In questo caso, l&#39;applicazione decide automaticamente quali record vengono conservati in caso di duplicati.

   ![](assets/import_template_example7.png)

1. Configurate l&#39; **[!UICONTROL Update data]** attività che si trova dopo che l&#39; **[!UICONTROL Deduplication]** attività è stata configurata in precedenza.

   * Selezionate **[!UICONTROL Insert only]** come **[!UICONTROL Operation type]** , poiché la transizione in entrata contiene solo profili non presenti nel database.
   * Nella **[!UICONTROL Identification]** scheda, selezionate **[!UICONTROL Using reconciliation criteria]** e definite una chiave tra il **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato nell&#39; **[!UICONTROL Reconciliation]** attività. In questo esempio, viene utilizzato il campo personalizzato ID **** CRM.

      ![](assets/import_template_example6.png)

   * Nella **[!UICONTROL Fields to update]** scheda, indicare i campi dalla dimensione Profili da aggiornare con il valore della colonna corrispondente dal file. Se i nomi delle colonne del file sono identici o quasi identici ai nomi dei campi dimensione destinatari, è possibile utilizzare il pulsante bacchetta magica per far corrispondere automaticamente i diversi campi.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se prevedete di inviare e-mail dirette a questi profili, accertatevi di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il fornitore di posta diretta. Verificate inoltre che sia selezionata la **[!UICONTROL Address specified]** casella delle informazioni del profilo. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare, specificare **1** come **[!UICONTROL Source]** e selezionare il campo **[postalAddress/@addrDefined]** come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla posta diretta e sull&#39;uso dell&#39; **[!UICONTROL Address specified]** opzione, consulta [questo documento](../../channels/using/about-direct-mail.md#recommendations).

1. Dopo la terza transizione dell&#39; **[!UICONTROL Segmentation]** attività, aggiungete un&#39; **[!UICONTROL Extract file]** attività e un&#39; **[!UICONTROL Transfer file]** attività se desiderate tenere traccia dei dati non inseriti nel database. Configurate queste attività per esportare la colonna desiderata e per trasferire il file su un server FTP o SFTP in cui potete recuperarlo.
1. Aggiungete un&#39; **[!UICONTROL End]** attività e salvate il modello di flusso di lavoro.

Ora è possibile utilizzare il modello ed è disponibile per ogni nuovo flusso di lavoro. È quindi necessario specificare il file contenente i dati da importare nell&#39; **[!UICONTROL Load file]** attività.

![](assets/import_template_example9.png)
