---
title: Targeting dei tipi di pubblico di Adobe Experience Platform
description: Scopri come eseguire il targeting delle audience Adobe Experience Platform all'interno dei flussi di lavoro.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# Targeting dei tipi di pubblico di Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Il servizio Destinazioni audience è attualmente in versione beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.

Dopo aver creato un&#39;audience [](../../audiences/using/aep-about-audience-destinations-service.md) Adobe Experience Platform utilizzando Segment Builder (Generatore di segmenti), puoi utilizzarla come faresti per un&#39;audience di Campaign all&#39;interno dei flussi di lavoro per personalizzare e inviare messaggi.

Per attivare un pubblico Adobe Experience Platform nei flussi di lavoro, attenetevi alla seguente procedura:

1. Aggiungete un&#39; **[!UICONTROL Read audience]** attività nel flusso di lavoro, quindi apritela.

1. Selezionate l&#39; **[!UICONTROL Adobe Experience Platform]** opzione in **[!UICONTROL Type of audience]**, quindi aggiungete il pubblico desiderato.

   ![](assets/aep_wkf_readaudience.png)

1. (Facoltativo) Una volta selezionato il pubblico, potete fare clic sul pulsante occhio per rivedere e/o modificare la definizione del segmento (accertatevi di salvare di nuovo le modifiche).

   Facendo clic sul pulsante occhio, potrai semplicemente accedere al Segment Builder (in un&#39;altra scheda) associato all&#39;audience selezionata all&#39;interno di Campaign.

1. Selezionate un **[!UICONTROL Platform data mapping]** elemento per specificare la dimensione di targeting desiderata per il pubblico Adobe Experience Platform selezionato.

   Per impostazione predefinita, la chiave primaria (ad esempio, iRecipientID per la tabella Profilo, iAppSubscriptionID per la tabella AppSubscription) utilizzata per la riconciliazione sarà automaticamente disponibile dall’elenco a discesa. Per eseguire il targeting all&#39;esterno della chiave primaria, è necessario creare uno **spazio dei nomi** personalizzato.

   >[!NOTE]
   >
   >Per i target esterni alla chiave primaria, è inoltre necessario creare un mapping di destinazione personalizzato che corrisponda allo spazio dei nomi personalizzato. For more information on Target Mapping, refer to [this section](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Questo elenco contiene tutte le mappature XDM (Experience Data Model) configurate nell&#39;istanza. Per ulteriori informazioni su Adobe Experience Platform Data Connector, consultare [questo documento](../../developing/using/aep-about-data-connector.md)dedicato.

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una volta configurate correttamente le dimensioni di pubblico e di destinazione, fate clic sul **[!UICONTROL Confirm]** pulsante per salvare le modifiche.

Ora puoi configurare il flusso di lavoro con altre attività. Ad esempio, potete collegare un&#39; **[!UICONTROL Email delivery]** attività per inviare un&#39;e-mail all&#39;audience selezionata.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard consente di eseguire il targeting del pubblico Adobe Experience Platform all&#39;interno di tutti i canali di distribuzione: E-mail, messaggi SMS, messaggi di posta diretta, notifiche push e messaggi in-app.
>
>*Nota: Per tutti i messaggi push e in-app, i Campaign Standard supportano solo le consegne per i soli profili noti.

Per ulteriori informazioni sull&#39;utilizzo dei flussi di lavoro e delle consegne, consulta le sezioni seguenti:

* [Esplorazione dei flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esplorazione dei canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Informazioni sulle attività dei canali](../../automating/using/about-channel-activities.md)
