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
source-wordcount: '1172'
ht-degree: 1%

---

# Creazione di modelli di flusso di lavoro per l’importazione di dati {#import-workflow-template}

L’utilizzo di un modello di importazione è una best practice per importare regolarmente file con la stessa struttura.

Questo esempio mostra come impostare un flusso di lavoro che può essere riutilizzato per importare profili provenienti da un sistema di gestione delle relazioni con i clienti nel database Adobe Campaign.

1. Crea un nuovo modello di flusso di lavoro da **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Aggiungi le seguenti attività:

   * **[!UICONTROL Load file]**: Definisci la struttura prevista del file contenente i dati da importare.

      >[!NOTE]
      >
      >È possibile importare dati da un solo file. Se il flusso di lavoro ha più **[!UICONTROL Load file]** attività, lo stesso file verrà utilizzato ogni volta.

   * **[!UICONTROL Reconciliation]**: Riconciliare i dati importati con i dati del database.
   * **[!UICONTROL Segmentation]**: Crea filtri per elaborare i record in modo diverso a seconda che possano essere riconciliati o meno.
   * **[!UICONTROL Deduplication]**: Deduplica i dati dal file in arrivo prima di inserirli nel database.
   * **[!UICONTROL Update data]**: Aggiorna il database con i profili importati.

   ![](assets/import_template_example0.png)

1. Configura le **[!UICONTROL Load file]** attività:

   * Definisci la struttura prevista caricando un file di esempio. Il file di esempio deve contenere solo poche righe ma tutte le colonne necessarie per l’importazione. Controlla e modifica il formato del file per assicurarti che il tipo di ogni colonna sia impostato correttamente: testo, data, numero intero, ecc. Ad esempio:

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * In **[!UICONTROL File to load]** sezione , seleziona **[!UICONTROL Upload a new file from the local machine]** e lasciare il campo vuoto. Ogni volta che viene creato un nuovo flusso di lavoro da questo modello, puoi specificare qui il file desiderato, purché corrisponda alla struttura definita.

      Puoi utilizzare una qualsiasi delle opzioni ma devi modificare di conseguenza il modello. Ad esempio, se selezioni **[!UICONTROL Use the file specified in the inbound transition]**, puoi aggiungere una **[!UICONTROL Transfer file]** prima di recuperare il file da importare da un server FTP/SFTP.

      Se desideri che gli utenti siano in grado di scaricare un file contenente errori verificatisi durante un&#39;importazione, controlla il **[!UICONTROL Keep the rejects in a file]** e specifica la **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configura le **[!UICONTROL Reconciliation]** attività. Lo scopo di questa attività in questo contesto è quello di identificare i dati in arrivo.

   * In **[!UICONTROL Relations]** scheda , seleziona **[!UICONTROL Create element]** e definire un collegamento tra i dati importati e la dimensione di targeting dei destinatari (consulta [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources)). In questo esempio, la **ID CRM** il campo personalizzato viene utilizzato per creare la condizione di unione. Utilizzare il campo o la combinazione di campi necessari, purché sia possibile identificare record univoci.
   * In **[!UICONTROL Identification]** , lascia **[!UICONTROL Identify the document from the working data]** deselezionata.

   ![](assets/import_template_example2.png)

1. Configura le **[!UICONTROL Segmentation]** attività per recuperare i destinatari riconciliati in una transizione e i destinatari che non potevano essere riconciliati ma che disponevano di dati sufficienti in una seconda transizione.

   La transizione con i destinatari riconciliati può quindi essere utilizzata per aggiornare il database. La transizione con destinatari sconosciuti può quindi essere utilizzata per creare nuove voci dei destinatari nel database se nel file è disponibile un set minimo di informazioni.

   I destinatari che non possono essere riconciliati e che non dispongono di abbastanza dati vengono selezionati in una transizione in uscita di complemento e possono essere esportati in un file separato o semplicemente ignorati.

   * In **[!UICONTROL General]** , imposta la **[!UICONTROL Resource type]** a **[!UICONTROL Temporary resource]** e seleziona **[!UICONTROL Reconciliation]** come set di destinazione.
   * In **[!UICONTROL Advanced options]** controlla la **[!UICONTROL Generate complement]** per poter vedere se non è possibile inserire alcun record nel database. Se necessario, puoi quindi applicare un ulteriore trattamento ai dati complementari: esportazione di file, aggiornamento di elenchi, ecc.
   * Nel primo segmento della **[!UICONTROL Segments]** aggiungi una condizione di filtro nel gruppo in entrata per selezionare solo i record per i quali l’ID CRM del profilo non è uguale a 0. In questo modo, i dati del file riconciliati con i profili del database vengono selezionati in quel sottoinsieme.

      ![](assets/import_template_example3.png)

   * Aggiungi un secondo segmento che seleziona record non riconciliati con dati sufficienti per essere inseriti nel database. Ad esempio: indirizzo e-mail, nome e cognome. Per i record non riconciliati il valore ID CRM del profilo è uguale a 0.

      ![](assets/import_template_example3_2.png)

   * Tutti i record non selezionati nei primi due sottoinsiemi sono selezionati nella **[!UICONTROL Complement]**.

1. Configura le **[!UICONTROL Update data]** attività situata dopo la prima transizione in uscita del **[!UICONTROL Segmentation]** attività configurata in precedenza.

   * Seleziona **[!UICONTROL Update]** come **[!UICONTROL Operation type]** poiché la transizione in entrata contiene solo i destinatari già presenti nel database.
   * In **[!UICONTROL Identification]** scheda , seleziona **[!UICONTROL Using reconciliation criteria]** e definire una chiave tra **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato in **[!UICONTROL Reconciliation]** attività. In questo esempio, la **ID CRM** viene utilizzato il campo personalizzato .

      ![](assets/import_template_example6.png)

   * In **[!UICONTROL Fields to update]** , indica i campi della dimensione Profili da aggiornare con il valore della colonna corrispondente dal file . Se i nomi delle colonne del file sono identici o quasi identici ai nomi dei campi della dimensione destinatari, è possibile utilizzare il pulsante bacchetta magica per associare automaticamente i diversi campi.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se prevedi di inviare direct mailing a questi profili, accertati di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il provider di direct mailing. Assicurati inoltre che il **[!UICONTROL Address specified]** nelle informazioni del profilo è selezionata. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare e specificare **1** come **[!UICONTROL Source]** e seleziona la `postalAddress/@addrDefined` campo come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla direct mailing e sull’utilizzo dei **[!UICONTROL Address specified]** opzione , vedi [presente documento](../../channels/using/about-direct-mail.md#recommendations).

1. Configura le **[!UICONTROL Deduplication]** attività situata dopo la transizione contenente profili non riconciliati:

   * In **[!UICONTROL Properties]** imposta la **[!UICONTROL Resource type]** alla risorsa temporanea generata dal **[!UICONTROL Reconciliation]** attività del flusso di lavoro.

      ![](assets/import_template_example4.png)

   * In questo esempio, il campo e-mail viene utilizzato per trovare profili univoci. Puoi utilizzare qualsiasi campo di cui sei sicuro che sia compilato e parte di una combinazione unica.
   * Scegli un **[!UICONTROL Deduplication method]**. In questo caso, l&#39;applicazione decide automaticamente quali record vengono conservati in caso di duplicati.

   ![](assets/import_template_example7.png)

1. Configura le **[!UICONTROL Update data]** attività situata dopo **[!UICONTROL Deduplication]** attività configurata in precedenza.

   * Seleziona **[!UICONTROL Insert only]** come **[!UICONTROL Operation type]** poiché la transizione in entrata contiene solo profili non presenti nel database.
   * In **[!UICONTROL Identification]** scheda , seleziona **[!UICONTROL Using reconciliation criteria]** e definire una chiave tra **[!UICONTROL Dimension to update]** - Profili in questo caso - e il collegamento creato in **[!UICONTROL Reconciliation]** attività. In questo esempio, la **ID CRM** viene utilizzato il campo personalizzato .

      ![](assets/import_template_example6.png)

   * In **[!UICONTROL Fields to update]** , indica i campi della dimensione Profili da aggiornare con il valore della colonna corrispondente dal file . Se i nomi delle colonne del file sono identici o quasi identici ai nomi dei campi della dimensione destinatari, è possibile utilizzare il pulsante bacchetta magica per associare automaticamente i diversi campi.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Se prevedi di inviare direct mailing a questi profili, accertati di includere un indirizzo postale, in quanto queste informazioni sono essenziali per il provider di direct mailing. Assicurati inoltre che il **[!UICONTROL Address specified]** nelle informazioni del profilo è selezionata. Per aggiornare questa opzione da un flusso di lavoro, è sufficiente aggiungere un elemento ai campi da aggiornare e specificare **1** come **[!UICONTROL Source]** e seleziona la **[postalAddress/@addrDefined]** campo come **[!UICONTROL Destination]**. Per ulteriori informazioni sulla direct mailing e sull’utilizzo dei **[!UICONTROL Address specified]** opzione , vedi [presente documento](../../channels/using/about-direct-mail.md#recommendations).

1. Dopo la terza transizione della **[!UICONTROL Segmentation]** aggiungi un **[!UICONTROL Extract file]** attività e **[!UICONTROL Transfer file]** se desideri tenere traccia dei dati non inseriti nel database. Configura queste attività per esportare la colonna necessaria e per trasferire il file su un server FTP o SFTP in cui puoi recuperarlo.
1. Aggiungi un **[!UICONTROL End]** e salva il modello di flusso di lavoro .

Ora è possibile utilizzare il modello ed è disponibile per ogni nuovo flusso di lavoro. È sufficiente quindi specificare il file contenente i dati da importare nel **[!UICONTROL Load file]** attività.

![](assets/import_template_example9.png)
