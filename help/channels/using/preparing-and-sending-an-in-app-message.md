---
title: Preparazione e invio di un messaggio in-app
seo-title: Preparazione e invio di un messaggio in-app
description: Preparazione e invio di un messaggio in-app
seo-description: Create un messaggio in-app per indirizzare gli utenti iscritti all'applicazione con contenuto specifico.
page-status-flag: mai attivato
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: messaggi in-app
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: consegna,trigger,back;deliveryCreation,procedura guidata
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Preparazione e invio di un messaggio in-app{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>La personalizzazione in-app si basa su un campo di collegamento che in genere è un ID CRM e/o un ID di accesso app mobile. Sei l'unico responsabile della protezione di questo campo di collegamento quando utilizzato in connessione con Adobe Campaign. Se non riesci a proteggere i campi di collegamento, il messaggio personalizzato potrebbe essere vulnerabile. Adobe non sarà responsabile dei danni derivanti dall'accesso o dall'uso non autorizzati di dati di profilo se non segui le procedure di composizione, gestione e protezione del campo di collegamento sicuro.

In Adobe Campaign sono disponibili tre tipi di messaggi in-app:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Questo tipo di messaggio ti consente di eseguire il targeting dei profili Adobe Campaign (profili CRM) che hanno effettuato la sottoscrizione all'applicazione mobile. Questo tipo di messaggio può essere personalizzato con tutti gli attributi di profilo disponibili in Adobe Campaign, ma richiede una stretta di mano sicura tra l'SDK di Mobile e il servizio di messaggistica in-app di Campaign per garantire che i messaggi con informazioni personali e riservate siano utilizzati solo da utenti autorizzati.

   Per scaricare questo tipo di messaggio sui dispositivi degli utenti, Mobile SDK deve inviare i campi di collegamento utilizzati per connettere un profilo mobile a un profilo CRM in Adobe Campaign. Per ulteriori informazioni sulle API SDK necessarie per supportare In-App, consulta questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Questo tipo di messaggio consente di inviare messaggi a tutti gli utenti (correnti o futuri) dell'applicazione mobile anche se non dispongono di un profilo esistente in Adobe Campaign. La personalizzazione non è quindi possibile quando si personalizzano i messaggi in quanto il profilo utente potrebbe non esistere nemmeno in Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Questo tipo di messaggio consente di eseguire il targeting di tutti gli utenti noti o anonimi di un'app mobile con un profilo mobile in Adobe Campaign. Questo tipo di messaggi può essere personalizzato utilizzando solo attributi non personali e non sensibili e non richiede una stretta di mano sicura tra l'SDK di Mobile e il servizio di messaggistica in-app di Adobe Campaign.

   Per ulteriori informazioni su come gestire i dati personali e riservati, consulta [Gestione dei campi del profilo mobile con dati](#handling-mobile-profile-fields-with-personal-and-sensitive-data)personali e sensibili.

![](assets/diagram_inapp.png)

## Gestione dei campi del profilo mobile con dati personali e sensibili {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

Questa risorsa deve essere estesa per raccogliere i dati che si intende inviare dal dispositivo mobile ad Adobe Campaign. A tale scopo, fare riferimento a questa [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) per i passaggi dettagliati.

Per abilitare la personalizzazione dei messaggi in-app in modo più sicuro, i campi del profilo mobile da questa risorsa devono essere configurati di conseguenza. In your **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, when creating your new mobile profiles fields, check **[!UICONTROL Personal and Sensitive]** to make them unavailable during In-App messages personalization.

>[!NOTE]
>
>Se disponi di un'implementazione esistente con estensione di risorse personalizzata in questa tabella, ti consigliamo di etichettare i campi in modo appropriato prima di sfruttarli per la personalizzazione dei messaggi in-app.

![](assets/in_app_personal_data_2.png)

Once your **[!UICONTROL Subscriptions to an application]** custom resource is configured and published, you can start preparing your In-App delivery using the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template. Only non-personal and non-sensitive fields will be available from **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource for personalization.

If you require personalization with **Personal and Sensitive** fields, we recommend using the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template which has additional security mechanism to ensure that your users' PII data remains secure.

## Preparazione del messaggio in-app {#preparing-your-in-app-message}

I passaggi per creare un messaggio in-app standalone con Adobe Campaign sono:

1. Dalla home page di Adobe Campaign, fai clic sulla **[!UICONTROL In-App messaging]** scheda.

   Puoi anche creare un'app in-app dalla scheda Attività **** marketing, facendo clic sul **[!UICONTROL Create]** pulsante.

   Puoi anche creare un messaggio in-app da una campagna, dalla home page di Adobe Campaign o in un flusso di lavoro.

1. Seleziona messaggio **** in-app.

   ![](assets/inapp_creating.png)

1. Selezionate un modello appropriato in base alle esigenze di targeting delle audience.

   ![](assets/inapp_creating_2.png)

   Per impostazione predefinita, potete selezionare uno dei seguenti tre modelli out-of-the-box:

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Immettete le proprietà del messaggio in-app e selezionate l'app mobile nel **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   ![](assets/inapp_creating_3.png)

1. Seleziona l'audience di cui vuoi eseguire il targeting per il messaggio in-app. Il pubblico viene previamente filtrato in base all'applicazione mobile associata a questa distribuzione.

   Si noti che questo passaggio non è necessario con l’applicazione **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** in quanto riguarda tutti gli utenti di un’applicazione mobile.

   ![](assets/inapp_creating_8.png)

1. Nella **[!UICONTROL Triggers]** scheda, trascina e rilascia l’evento che attiverà il messaggio. Scegliendo un attivatore, scegliete un’azione eseguita dagli utenti che causerà la visualizzazione del messaggio in-app.

   Sono disponibili quattro categorie di eventi:

   * **[!UICONTROL Mobile Application events]**: Eventi personalizzati implementati nell'applicazione mobile.

      Per ulteriori informazioni sulle creazioni degli eventi, consultate questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

   * **[!UICONTROL Life Cycle events]**: Eventi del ciclo di vita pronti supportati dall’SDK di Adobe Mobile.

      Per ulteriori informazioni sugli eventi del ciclo di vita, consultare questa [pagina](https://marketing.adobe.com/resources/help/en_US/mobile/android/metrics.html).

   * **[!UICONTROL Analytics Events]**: Le tre categorie seguenti sono supportate a seconda degli strumenti utilizzati nell’app mobile: Adobe Analytics, dati contestuali o stato di visualizzazione.

      Questi eventi sono disponibili solo se disponete di una licenza Adobe Analytics.

   * **[!UICONTROL Places]**: Le tre categorie seguenti sfruttano i dati sulla posizione in tempo reale per fornire esperienze mobili pertinenti in termini di contesto: Posiziona i dati contestuali, i metadati personalizzati Luoghi o il tipo di evento Luoghi.

      Per ulteriori informazioni su Adobe Places, consulta la documentazione relativa a [Places](https://placesdocs.com/).
   ![](assets/inapp_creating_4.png)

1. Se utilizzi un evento **[!UICONTROL Analytics Events]**, gli eventi di stato Adobe Analytics e View verranno popolati automaticamente in base alle suite di rapporti configurate nell'estensione Analytics in Adobe Experience Platform Launch, mentre gli eventi di dati Context devono essere aggiunti manualmente.

   Questi eventi sono disponibili solo se disponete di una licenza Adobe Analytics.

   ![](assets/inapp_creating_7.png)

1. Se si utilizza un **[!UICONTROL Places]** attivatore, i dati contestuali Luoghi, i metadati personalizzati Luoghi o il tipo di evento Luoghi verranno popolati automaticamente in base a tutte le librerie e ai relativi punti di interesse creati in Adobe Places.

   Tieni presente che questo attivatore verrà applicato sul dispositivo solo per i punti di interesse dalle librerie selezionate nell'estensione Luoghi in Experience Platform Launch. Per ulteriori informazioni sull'estensione Places e su come installarla, consulta questa [documentazione](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/places-extension-1/places-extension).

1. Nella **[!UICONTROL Frequency & duration]** scheda, scegli la frequenza dell'attivatore, la data di inizio e di fine, il giorno della settimana e l'ora del giorno in cui sarà attivo il messaggio in-app.

   ![](assets/inapp_creating_5.png)

1. Modificate il contenuto del messaggio e definite le opzioni avanzate. Consultate [Personalizzazione di un messaggio](https://helpx.adobe.com/campaign/standard/channels/using/customizing-a-push-notification.html)in-app.

   ![](assets/inapp_creating_6.png)

1. Click **[!UICONTROL Create]**.

Il messaggio in-app ora è pronto per essere inviato al pubblico di destinazione.

**Argomenti correlati:**

* [Personalizzazione di un messaggio in-app](../../channels/using/customizing-an-in-app-message.md)
* [Rapporto in-app](../../reporting/using/in-app-report.md)
* [Invio di un messaggio in-app in un flusso di lavoro](../../automating/using/in-app-delivery.md)

## Invio del messaggio in-app {#sending-your-in-app-message}

Una volta completata la preparazione della consegna e che sono state eseguite le fasi di approvazione, potete inviare il messaggio.

1. Fare clic **[!UICONTROL Prepare]** per calcolare la destinazione e generare i messaggi.

   ![](assets/inapp_sending_4.png)

1. Una volta completata la preparazione, la finestra **Deployment** presenta i KPI seguenti: **Target** e **To deliver**.

   Per controllare la finestra Distribuzione, fai clic sul ![](assets/lp_link_properties.png) pulsante per individuare eventuali esclusioni o errori nella distribuzione.

   ![](assets/inapp_sending_5.png)

1. Fate clic **[!UICONTROL Confirm]** per iniziare a inviare il messaggio in-app.

   ![](assets/inapp_sending_6.png)

1. Controlla lo stato della distribuzione tramite il dashboard e i registri dei messaggi. For more on this, refer to this [section](../../sending/using/monitoring-a-delivery.md).

   **[!UICONTROL Delivered]** e **[!UICONTROL Sent]** i conteggi dei KPI si basano su quanto è stato inviato con successo dal servizio di distribuzione di Campaign a Message. Questi KPI non rappresentano un'indicazione del numero di dispositivi mobili che hanno ricevuto o scaricato correttamente il messaggio dal servizio di distribuzione dei messaggi.

   ![](assets/inapp_sending_7.png)

1. Misura l'impatto dei messaggi in-app con i rapporti di consegna. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

**Argomenti correlati:**

* [Rapporto in-app](../../reporting/using/in-app-report.md)
* [Invio di un messaggio in-app in un flusso di lavoro](../../automating/using/in-app-delivery.md)

