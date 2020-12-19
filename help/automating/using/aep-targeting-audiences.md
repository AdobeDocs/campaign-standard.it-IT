---
solution: Campaign Standard
product: campaign
title: Targeting dei tipi di pubblico di Adobe Experience Platform
description: Scopri come eseguire il targeting delle audience Adobe Experience Platform all'interno dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---


# Targeting dei tipi di pubblico di Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Il servizio Destinazioni audience è attualmente in versione beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.

Dopo aver creato un [pubblico Adobe Experience Platform](../../audiences/using/aep-about-audience-destinations-service.md) utilizzando Segment Builder (Generatore di segmenti), puoi utilizzarlo nello stesso modo in cui lo faresti per un pubblico di Campaign all&#39;interno dei flussi di lavoro per personalizzare e inviare messaggi.

Per attivare un pubblico Adobe Experience Platform nei flussi di lavoro, attenetevi alla seguente procedura:

1. Aggiungete un&#39;attività **[!UICONTROL Read audience]** nel flusso di lavoro, quindi apritela.

1. Selezionare l&#39;opzione **[!UICONTROL Adobe Experience Platform]** in **[!UICONTROL Type of audience]**, quindi aggiungere il pubblico desiderato.

   ![](assets/aep_wkf_readaudience.png)

1. (Facoltativo) Una volta selezionato il pubblico, potete fare clic sul pulsante occhio per rivedere e/o modificare la definizione del segmento (accertatevi di salvare di nuovo le modifiche).

   Facendo clic sul pulsante occhio, potrai semplicemente accedere al Segment Builder (in un&#39;altra scheda) associato all&#39;audience selezionata all&#39;interno di Campaign.

1. Selezionate un elemento **[!UICONTROL Platform data mapping]** per specificare la dimensione di targeting desiderata per il pubblico Adobe Experience Platform selezionato.

   Per impostazione predefinita, la chiave primaria (ad esempio, iRecipientID per la tabella Profilo, iAppSubscriptionID per la tabella AppSubscription) utilizzata per la riconciliazione sarà automaticamente disponibile dall’elenco a discesa. Per eseguire il targeting all&#39;esterno della chiave primaria, è necessario creare un **Namespace** personalizzato.

   >[!NOTE]
   >
   >Per i target esterni alla chiave primaria, è inoltre necessario creare un mapping di destinazione personalizzato che corrisponda allo spazio dei nomi personalizzato. Per ulteriori informazioni sulla mappatura di Target, consultare [questa sezione](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Questo elenco contiene tutte le mappature XDM (Experience Data Model) configurate nell&#39;istanza. Per ulteriori informazioni su Adobe Experience Platform Data Connector, consultare [questo documento dedicato](../../developing/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una volta configurate correttamente le dimensioni di pubblico e di destinazione, fate clic sul pulsante **[!UICONTROL Confirm]** per salvare le modifiche.

Ora puoi configurare il flusso di lavoro con altre attività. Ad esempio, potete collegare un&#39;attività **[!UICONTROL Email delivery]** per inviare un&#39;e-mail all&#39;audience selezionata.

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
