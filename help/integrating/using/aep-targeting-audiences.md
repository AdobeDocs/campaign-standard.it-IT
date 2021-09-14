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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 5%

---

# Targeting dei tipi di pubblico di Adobe Experience Platform {#targeting-aep-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta e potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Dopo aver creato un [pubblico Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md) utilizzando il Generatore di segmenti, puoi utilizzarlo nello stesso modo in cui lo utilizzeresti per personalizzare e inviare messaggi per un pubblico di Campaign all’interno dei flussi di lavoro.

Per attivare un pubblico Adobe Experience Platform nei flussi di lavoro, effettua le seguenti operazioni:

1. Aggiungi un’attività **[!UICONTROL Read audience]** nel flusso di lavoro, quindi aprila.

1. Seleziona l’opzione **[!UICONTROL Adobe Experience Platform]** in **[!UICONTROL Type of audience]**, quindi aggiungi il pubblico desiderato.

   ![](assets/aep_wkf_readaudience.png)

1. (Facoltativo) Una volta selezionato il pubblico, puoi fare clic sul pulsante occhio per rivedere e/o modificare la definizione del segmento (assicurati di salvare nuovamente le modifiche).

   Facendo clic sul pulsante con l’occhio ti indirizzerai semplicemente al Generatore di segmenti (in un’altra scheda) associato al pubblico selezionato all’interno di Campaign.

1. Seleziona un elemento **[!UICONTROL Platform data mapping]** per specificare la dimensione di targeting desiderata per il pubblico Adobe Experience Platform selezionato.

   Per impostazione predefinita, la chiave primaria (ad esempio, iRecipientID per la tabella Profilo, iAppSubscriptionID per la tabella AppSubscription) utilizzata per la riconciliazione sarà automaticamente disponibile dall’elenco a discesa. Per eseguire il targeting al di fuori della chiave primaria, è necessario creare un **Namespace** personalizzato.

   >[!NOTE]
   >
   >Per le destinazioni al di fuori della chiave primaria, devi anche creare una mappatura Target personalizzata che corrisponda allo spazio dei nomi personalizzato. Per ulteriori informazioni sulla mappatura di Target, consulta [questa sezione](../../administration/using/target-mappings-in-campaign.md).

   ![](assets/aep_wkf_readaudience_namespace.png)

   Questo elenco contiene tutte le mappature Experience Data Model (XDM) configurate sull&#39;istanza. Per ulteriori informazioni su Adobe Experience Platform Data Connector, consulta [questo documento dedicato](../../integrating/using/aep-about-data-connector.md).

   ![](assets/aep_wkf_readaudience_namespace2.png)

1. Una volta configurate correttamente le dimensioni di pubblico e targeting, fai clic sul pulsante **[!UICONTROL Confirm]** per salvare le modifiche.

Ora puoi configurare il flusso di lavoro con altre attività. Ad esempio, puoi collegare un’attività **[!UICONTROL Email delivery]** per inviare un’e-mail al pubblico selezionato.

![](assets/aep_wkf_email.png)

>[!NOTE]
>
>Campaign Standard consente di eseguire il targeting del pubblico Adobe Experience Platform all’interno di tutti i canali di consegna: E-mail, messaggi SMS, direct mailing, notifiche push e messaggi in-app.
>
>*Nota: Per tutti i messaggi push e in-app, Campaign Standard supporta solo le consegne per i soli profili noti.

Per ulteriori informazioni su come utilizzare flussi di lavoro e consegne, consulta queste sezioni:

* [Esplorazione dei flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esplorazione dei canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Informazioni sulle attività del canale](../../automating/using/about-channel-activities.md)
