---
title: Creazione di modelli di flusso di lavoro per l’importazione di dati
description: Scopri come creare modelli di flusso di lavoro per importare i dati.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 5974a52c-8721-4575-b452-2982d6497235
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1176'
ht-degree: 1%

---

# Creazione di modelli di flusso di lavoro per l’importazione di dati {#import-workflow-template}

L’utilizzo di un modello di importazione è una best practice se devi importare regolarmente file con la stessa struttura.

Questo esempio mostra come preimpostare un flusso di lavoro che può essere riutilizzato per importare nel database Adobe Campaign i profili provenienti da un sistema di gestione delle relazioni con i clienti.

1. Crea un nuovo modello di workflow da **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Aggiungi le seguenti attività:

   * **[!UICONTROL Load file]**: definire la struttura prevista del file contenente i dati da importare.

     >[!NOTE]
     >
     >È possibile importare dati solo da un singolo file. Se il flusso di lavoro include più attività **[!UICONTROL Load file]**, verrà utilizzato ogni volta lo stesso file.

   * **[!UICONTROL Reconciliation]**: riconciliare i dati importati con i dati del database.
   * **[!UICONTROL Segmentation]**: creare filtri per elaborare i record in modo diverso a seconda che siano stati riconciliati o meno.
   * **[!UICONTROL Deduplication]**: deduplicare i dati dal file in ingresso prima che vengano inseriti nel database.
   * **[!UICONTROL Update data]**: aggiornare il database con i profili importati.

   ![](assets/import_template_example0.png)

1. Configurare l&#39;attività **[!UICONTROL Load file]**:

   * Definisci la struttura prevista caricando un file di esempio. Il file di esempio deve contenere solo poche righe, ma tutte le colonne necessarie per l’importazione. Controlla e modifica il formato del file per assicurarti che il tipo di ciascuna colonna sia impostato correttamente: testo, data, numero intero, ecc. Ad esempio:

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * Nella sezione **[!UICONTROL File to load]**, selezionare **[!UICONTROL Upload a new file from the local machine]** e lasciare vuoto il campo. Ogni volta che viene creato un nuovo flusso di lavoro da questo modello, è possibile specificare il file desiderato, purché corrisponda alla struttura definita.

     Puoi utilizzare una qualsiasi delle opzioni, ma devi modificare il modello di conseguenza. Ad esempio, se selezioni **[!UICONTROL Use the file specified in the inbound transition]**, puoi aggiungere un&#39;attività **[!UICONTROL Transfer file]** prima di recuperare il file da importare da un server FTP/SFTP.

     Se si desidera consentire agli utenti di scaricare un file contenente errori verificatisi durante un&#39;importazione, selezionare l&#39;opzione **[!UICONTROL Keep the rejects in a file]** e specificare **[!UICONTROL File name]**.

     ![](assets/import_template_example1.png)

1. Configurare l&#39;attività **[!UICONTROL Reconciliation]**. Lo scopo di questa attività in questo contesto è identificare i dati in arrivo.

   * Nella scheda **[!UICONTROL Relations]**, seleziona **[!UICONTROL Create element]** e definisci un collegamento tra i dati importati e la dimensione di targeting dei destinatari (vedi [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources)). In questo esempio, per creare la condizione di unione viene utilizzato il campo personalizzato **ID CRM**. Utilizzare il campo o la combinazione di campi necessari per identificare record univoci.
   * Nella scheda **[!UICONTROL Identification]**, lasciare deselezionata l&#39;opzione **[!UICONTROL Identify the document from the working data]**.

   ![](assets/import_template_example2.png)

1. Configurare l&#39;attività **[!UICONTROL Segmentation]** per recuperare i destinatari riconciliati in una transizione e i destinatari che non è stato possibile riconciliare ma che dispongono di un numero sufficiente di dati in una seconda transizione.

   La transizione con i destinatari riconciliati può quindi essere utilizzata per aggiornare il database. La transizione con destinatari sconosciuti può quindi essere utilizzata per creare nuove voci di destinatari nel database, se nel file è disponibile un set minimo di informazioni.

   I destinatari che non possono essere riconciliati e che non dispongono di un numero sufficiente di dati vengono selezionati in una transizione in uscita complementare e possono essere esportati in un file separato o semplicemente ignorati.

   * Nella scheda **[!UICONTROL General]** dell&#39;attività, impostare **[!UICONTROL Resource type]** su **[!UICONTROL Temporary resource]** e selezionare **[!UICONTROL Reconciliation]** come set di destinazione.
   * Nella scheda **[!UICONTROL Advanced options]**, selezionare l&#39;opzione **[!UICONTROL Generate complement]** per verificare se non è possibile inserire un record nel database. Se necessario, puoi applicare ulteriori elaborazioni ai dati complementari: esportazione di file, aggiornamento di elenchi, ecc.
   * Nel primo segmento della scheda **[!UICONTROL Segments]**, aggiungi una condizione di filtro al gruppo in entrata per selezionare solo i record per i quali l&#39;ID CRM del profilo non è uguale a 0. In questo modo, i dati del file riconciliati con i profili del database vengono selezionati in tale sottoinsieme.

     ![](assets/import_template_example3.png)

   * Aggiungere un secondo segmento per selezionare record non riconciliati con un numero di dati sufficiente per essere inseriti nel database. Ad esempio: indirizzo e-mail, nome e cognome. Il valore ID CRM dei record non riconciliati è uguale a 0.

     ![](assets/import_template_example3_2.png)

   * Tutti i record non selezionati nei primi due sottoinsiemi vengono selezionati in **[!UICONTROL Complement]**.

1. Configurare l&#39;attività **[!UICONTROL Update data]** che si trova dopo la prima transizione in uscita dell&#39;attività **[!UICONTROL Segmentation]** configurata in precedenza.

   * Selezionare **[!UICONTROL Update]** come **[!UICONTROL Operation type]** poiché la transizione in entrata contiene solo i destinatari già presenti nel database.
   * Nella scheda **[!UICONTROL Identification]**, seleziona **[!UICONTROL Using reconciliation criteria]** e definisci una chiave tra **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato nell&#39;attività **[!UICONTROL Reconciliation]**. In questo esempio viene utilizzato il campo personalizzato **ID CRM**.

     ![](assets/import_template_example6.png)

   * Nella scheda **[!UICONTROL Fields to update]**, indica i campi della dimensione Profili da aggiornare con il valore della colonna corrispondente del file. Se i nomi delle colonne dei file sono identici o quasi identici ai nomi dei campi dimensione dei destinatari, puoi utilizzare il pulsante bacchetta magica per far corrispondere automaticamente i diversi campi.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Se prevedi di inviare direct mailing a questi profili, assicurati di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il provider di direct mailing. Assicurarsi inoltre che la casella **[!UICONTROL Address specified]** nelle informazioni dei profili sia selezionata. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare, specificare **1** come **[!UICONTROL Source]** e selezionare il campo `postalAddress/@addrDefined` come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla direct mailing e sull&#39;utilizzo dell&#39;opzione **[!UICONTROL Address specified]**, vedere [questo documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configura l&#39;attività **[!UICONTROL Deduplication]** che si trova dopo la transizione contenente i profili non riconciliati:

   * Nella scheda **[!UICONTROL Properties]**, impostare **[!UICONTROL Resource type]** sulla risorsa temporanea generata dall&#39;attività **[!UICONTROL Reconciliation]** del flusso di lavoro.

     ![](assets/import_template_example4.png)

   * In questo esempio, il campo e-mail viene utilizzato per trovare profili univoci. Puoi utilizzare qualsiasi campo che sei sicuro di avere compilato e che fa parte di una combinazione univoca.
   * Scegli un **[!UICONTROL Deduplication method]**. In questo caso, l’applicazione decide automaticamente quali record vengono conservati in caso di duplicati.

   ![](assets/import_template_example7.png)

1. Configurare l&#39;attività **[!UICONTROL Update data]** che si trova dopo l&#39;attività **[!UICONTROL Deduplication]** configurata in precedenza.

   * Selezionare **[!UICONTROL Insert only]** come **[!UICONTROL Operation type]** poiché la transizione in entrata contiene solo profili non presenti nel database.
   * Nella scheda **[!UICONTROL Identification]**, seleziona **[!UICONTROL Using reconciliation criteria]** e definisci una chiave tra **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato nell&#39;attività **[!UICONTROL Reconciliation]**. In questo esempio viene utilizzato il campo personalizzato **ID CRM**.

     ![](assets/import_template_example6.png)

   * Nella scheda **[!UICONTROL Fields to update]**, indica i campi della dimensione Profili da aggiornare con il valore della colonna corrispondente del file. Se i nomi delle colonne dei file sono identici o quasi identici ai nomi dei campi dimensione dei destinatari, puoi utilizzare il pulsante bacchetta magica per far corrispondere automaticamente i diversi campi.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Se prevedi di inviare direct mailing a questi profili, assicurati di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il provider di direct mailing. Assicurarsi inoltre che la casella **[!UICONTROL Address specified]** nelle informazioni dei profili sia selezionata. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare, specificare **1** come **[!UICONTROL Source]** e selezionare il campo **[postalAddress/@addrDefined]** come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla direct mailing e sull&#39;utilizzo dell&#39;opzione **[!UICONTROL Address specified]**, vedere [questo documento](../../channels/using/about-direct-mail.md#recommendations).

1. Dopo la terza transizione dell&#39;attività **[!UICONTROL Segmentation]**, aggiungere un&#39;attività **[!UICONTROL Extract file]** e un&#39;attività **[!UICONTROL Transfer file]** per tenere traccia dei dati non inseriti nel database. Configura queste attività per esportare la colonna necessaria e trasferire il file su un server FTP o SFTP dove puoi recuperarlo.
1. Aggiungi un&#39;attività **[!UICONTROL End]** e salva il modello di flusso di lavoro.

Ora è possibile utilizzare il modello, disponibile per ogni nuovo flusso di lavoro. È sufficiente quindi specificare il file contenente i dati da importare nell&#39;attività **[!UICONTROL Load file]**.

![](assets/import_template_example9.png)
