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

1. Crea un nuovo modello di flusso di lavoro da **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Aggiungi le seguenti attività:

   * **[!UICONTROL Load file]**: definisci la struttura prevista del file contenente i dati da importare.

     >[!NOTE]
     >
     >È possibile importare dati solo da un singolo file. Se il flusso di lavoro ha più **[!UICONTROL Load file]** attività, verrà utilizzato ogni volta lo stesso file.

   * **[!UICONTROL Reconciliation]**: riconciliare i dati importati con i dati del database.
   * **[!UICONTROL Segmentation]**: crea filtri per elaborare i record in modo diverso a seconda che possano essere riconciliati o meno.
   * **[!UICONTROL Deduplication]**: deduplica i dati dal file in arrivo prima che vengano inseriti nel database.
   * **[!UICONTROL Update data]**: aggiorna il database con i profili importati.

   ![](assets/import_template_example0.png)

1. Configurare **[!UICONTROL Load file]** attività:

   * Definisci la struttura prevista caricando un file di esempio. Il file di esempio deve contenere solo poche righe, ma tutte le colonne necessarie per l’importazione. Controlla e modifica il formato del file per assicurarti che il tipo di ciascuna colonna sia impostato correttamente: testo, data, numero intero, ecc. Ad esempio:

     ```
     lastname;firstname;birthdate;email;crmID
     Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
     ```

   * In **[!UICONTROL File to load]** sezione, seleziona **[!UICONTROL Upload a new file from the local machine]** e lasciare vuoto il campo. Ogni volta che viene creato un nuovo flusso di lavoro da questo modello, è possibile specificare il file desiderato, purché corrisponda alla struttura definita.

     Puoi utilizzare una qualsiasi delle opzioni, ma devi modificare il modello di conseguenza. Ad esempio, se selezioni **[!UICONTROL Use the file specified in the inbound transition]**, è possibile aggiungere una **[!UICONTROL Transfer file]** prima di recuperare il file da importare da un server FTP/SFTP.

     Se desideri che gli utenti possano scaricare un file contenente errori verificatisi durante un’importazione, seleziona la **[!UICONTROL Keep the rejects in a file]** e specificare **[!UICONTROL File name]**.

     ![](assets/import_template_example1.png)

1. Configurare **[!UICONTROL Reconciliation]** attività. Lo scopo di questa attività in questo contesto è identificare i dati in arrivo.

   * In **[!UICONTROL Relations]** , seleziona **[!UICONTROL Create element]** e definire un collegamento tra i dati importati e la dimensione di targeting dei destinatari (vedi [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources)). In questo esempio, la proprietà **ID CRM** per creare la condizione di unione viene utilizzato un campo personalizzato. Utilizzare il campo o la combinazione di campi necessari per identificare record univoci.
   * In **[!UICONTROL Identification]** , lasciare **[!UICONTROL Identify the document from the working data]** deselezionata.

   ![](assets/import_template_example2.png)

1. Configurare **[!UICONTROL Segmentation]** attività per recuperare i destinatari riconciliati in una transizione e i destinatari che non è stato possibile riconciliare ma che dispongono di un numero sufficiente di dati in una seconda transizione.

   La transizione con i destinatari riconciliati può quindi essere utilizzata per aggiornare il database. La transizione con destinatari sconosciuti può quindi essere utilizzata per creare nuove voci di destinatari nel database, se nel file è disponibile un set minimo di informazioni.

   I destinatari che non possono essere riconciliati e che non dispongono di un numero sufficiente di dati vengono selezionati in una transizione in uscita complementare e possono essere esportati in un file separato o semplicemente ignorati.

   * In **[!UICONTROL General]** dell’attività, imposta la scheda **[!UICONTROL Resource type]** a **[!UICONTROL Temporary resource]** e seleziona **[!UICONTROL Reconciliation]** come set di destinazione.
   * In **[!UICONTROL Advanced options]** , selezionare la scheda **[!UICONTROL Generate complement]** per verificare se non è possibile inserire un record nel database. Se necessario, puoi applicare ulteriori elaborazioni ai dati complementari: esportazione di file, aggiornamento di elenchi, ecc.
   * Nel primo segmento del **[!UICONTROL Segments]** , aggiungi una condizione di filtro sul gruppo in entrata per selezionare solo i record per i quali l’ID CRM del profilo non è uguale a 0. In questo modo, i dati del file riconciliati con i profili del database vengono selezionati in tale sottoinsieme.

     ![](assets/import_template_example3.png)

   * Aggiungere un secondo segmento per selezionare record non riconciliati con un numero di dati sufficiente per essere inseriti nel database. Ad esempio: indirizzo e-mail, nome e cognome. Il valore ID CRM dei record non riconciliati è uguale a 0.

     ![](assets/import_template_example3_2.png)

   * Tutti i record non selezionati nei primi due sottoinsiemi vengono selezionati nel **[!UICONTROL Complement]**.

1. Configurare **[!UICONTROL Update data]** attività situata dopo la prima transizione in uscita del **[!UICONTROL Segmentation]** attività configurata in precedenza.

   * Seleziona **[!UICONTROL Update]** as **[!UICONTROL Operation type]** poiché la transizione in entrata contiene solo i destinatari già presenti nel database.
   * In **[!UICONTROL Identification]** , seleziona **[!UICONTROL Using reconciliation criteria]** e definisci una chiave tra **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato in **[!UICONTROL Reconciliation]** attività. In questo esempio, la proprietà **ID CRM** viene utilizzato un campo personalizzato.

     ![](assets/import_template_example6.png)

   * In **[!UICONTROL Fields to update]** , indica i campi della dimensione Profili da aggiornare con il valore della colonna corrispondente del file. Se i nomi delle colonne dei file sono identici o quasi identici ai nomi dei campi dimensione dei destinatari, puoi utilizzare il pulsante bacchetta magica per far corrispondere automaticamente i diversi campi.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Se prevedi di inviare direct mailing a questi profili, assicurati di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il provider di direct mailing. Assicurati inoltre che il **[!UICONTROL Address specified]** nelle informazioni dei profili è selezionata. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare e specificare **1** as **[!UICONTROL Source]** e seleziona la `postalAddress/@addrDefined` campo come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla direct mailing e sull&#39;utilizzo del **[!UICONTROL Address specified]** , vedere [questo documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configurare **[!UICONTROL Deduplication]** attività che si trova dopo la transizione contenente profili non riconciliati:

   * In **[!UICONTROL Properties]** , impostare **[!UICONTROL Resource type]** alla risorsa temporanea generata da **[!UICONTROL Reconciliation]** attività del flusso di lavoro.

     ![](assets/import_template_example4.png)

   * In questo esempio, il campo e-mail viene utilizzato per trovare profili univoci. Puoi utilizzare qualsiasi campo che sei sicuro di avere compilato e che fa parte di una combinazione univoca.
   * Scegli un **[!UICONTROL Deduplication method]**. In questo caso, l’applicazione decide automaticamente quali record vengono conservati in caso di duplicati.

   ![](assets/import_template_example7.png)

1. Configurare **[!UICONTROL Update data]** attività situata dopo il **[!UICONTROL Deduplication]** attività configurata in precedenza.

   * Seleziona **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** poiché la transizione in entrata contiene solo profili non presenti nel database.
   * In **[!UICONTROL Identification]** , seleziona **[!UICONTROL Using reconciliation criteria]** e definisci una chiave tra **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato in **[!UICONTROL Reconciliation]** attività. In questo esempio, la proprietà **ID CRM** viene utilizzato un campo personalizzato.

     ![](assets/import_template_example6.png)

   * In **[!UICONTROL Fields to update]** , indica i campi della dimensione Profili da aggiornare con il valore della colonna corrispondente del file. Se i nomi delle colonne dei file sono identici o quasi identici ai nomi dei campi dimensione dei destinatari, puoi utilizzare il pulsante bacchetta magica per far corrispondere automaticamente i diversi campi.

     ![](assets/import_template_example6_2.png)

     >[!NOTE]
     >
     >Se prevedi di inviare direct mailing a questi profili, assicurati di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il provider di direct mailing. Assicurati inoltre che il **[!UICONTROL Address specified]** nelle informazioni dei profili è selezionata. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare e specificare **1** as **[!UICONTROL Source]** e seleziona la **[postalAddress/@addrDefined]** campo come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla direct mailing e sull&#39;utilizzo del **[!UICONTROL Address specified]** , vedere [questo documento](../../channels/using/about-direct-mail.md#recommendations).

1. Dopo la terza transizione del **[!UICONTROL Segmentation]** attività, aggiungi un **[!UICONTROL Extract file]** attività e un **[!UICONTROL Transfer file]** se desideri tenere traccia dei dati non inseriti nel database. Configura queste attività per esportare la colonna necessaria e trasferire il file su un server FTP o SFTP dove puoi recuperarlo.
1. Aggiungi un **[!UICONTROL End]** e salva il modello di workflow.

Ora è possibile utilizzare il modello, disponibile per ogni nuovo flusso di lavoro. È sufficiente quindi specificare il file contenente i dati da importare nel **[!UICONTROL Load file]** attività.

![](assets/import_template_example9.png)
