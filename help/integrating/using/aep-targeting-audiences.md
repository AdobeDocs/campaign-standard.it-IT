---
title: Targeting dei tipi di pubblico di Adobe Experience Platform
description: Scopri come eseguire il targeting dei tipi di pubblico di Adobe Experience Platform all’interno dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 11e2cd7e-99b7-45cc-a0c2-41049128fe49
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 3%

---

# Targeting dei tipi di pubblico di Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta, e potrebbe essere soggetto ad aggiornamenti frequenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Contatta l’Assistenza clienti di Adobe se desideri accedervi.

Dopo aver creato un’ [Pubblico Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md) puoi utilizzare il Generatore di segmenti come se fosse un pubblico di Campaign all’interno dei flussi di lavoro, per personalizzare e inviare messaggi.

Per attivare un pubblico di Adobe Experience Platform nei flussi di lavoro, effettua le seguenti operazioni:

1. Aggiungi un **[!UICONTROL Read audience]** attività nel flusso di lavoro, quindi aprirlo.

1. Seleziona la **[!UICONTROL Adobe Experience Platform]** opzione in **[!UICONTROL Type of audience]**, quindi aggiungi il pubblico desiderato.

   ![](assets/aep_wkf_readaudience.png)

1. (Facoltativo) Una volta selezionato il pubblico, puoi fare clic sul pulsante con l’occhio per rivedere e/o modificare la definizione del segmento (assicurati di salvare di nuovo le modifiche).

   Facendo clic sul pulsante con l’icona a forma di occhio, accedi al Generatore di segmenti (in un’altra scheda) associato al pubblico selezionato all’interno di Campaign.

1. Seleziona un **[!UICONTROL Platform data mapping]** per specificare la dimensione di targeting desiderata per il pubblico Adobe Experience Platform selezionato.

   Per impostazione predefinita, la chiave primaria (ad esempio, iRecipientID per la tabella Profilo, iAppSubscriptionID per la tabella AppSubscription) utilizzata per la riconciliazione sarà automaticamente disponibile dall’elenco a discesa. Per eseguire il targeting all&#39;esterno della chiave primaria, è necessario creare un **Namespace**.

   >[!NOTE]
   >
   >Per le destinazioni che non rientrano nella chiave primaria, è inoltre necessario creare una mappatura di destinazione personalizzata corrispondente allo spazio dei nomi personalizzato. Per ulteriori informazioni sulla mappatura di Target, consulta [questa sezione](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Questo elenco contiene tutte le mappature Experience Data Model (XDM) configurate nell’istanza. Per ulteriori informazioni su Connettore dati di Adobe Experience Platform, consulta [questo documento dedicato](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una volta configurate correttamente le dimensioni di pubblico e di targeting, fai clic sul pulsante **[!UICONTROL Confirm]** per salvare le modifiche.

Ora puoi configurare il flusso di lavoro con altre attività. Ad esempio, puoi collegare un **[!UICONTROL Email delivery]** per inviare un’e-mail al pubblico selezionato.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard consente di rivolgerti al pubblico di Adobe Experience Platform all’interno di tutti i canali di consegna: e-mail, messaggi SMS, messaggi direct mail, notifiche push e messaggi in-app.
>
>*Nota: per tutti i messaggi push e in-app, Campaign Standard supporta solo le consegne per i profili noti.

Per ulteriori informazioni su come utilizzare flussi di lavoro e consegne, consulta queste sezioni:

* [Esplorazione dei flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esplorazione dei canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Informazioni sulle attività del canale](../../automating/using/about-channel-activities.md)
