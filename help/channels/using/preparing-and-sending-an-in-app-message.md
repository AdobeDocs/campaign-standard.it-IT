---
title: Preparazione e invio di un messaggio in-app
description: Crea un messaggio in-app per eseguire il targeting con contenuto specifico per gli abbonati alla tua applicazione.
page-status-flag: never-activated
uuid: a79b0466-8641-46cc-a70f-e4e839587bb2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: 18bf5297-a688-4302-abe4-e2fbcafdb515
context-tags: delivery,triggers,back;deliveryCreation,wizard
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1274'
ht-degree: 98%

---


# Preparazione e invio di un messaggio in-app{#preparing-and-sending-an-in-app-message}

>[!NOTE]
>
>La personalizzazione in-app si basa su un campo di collegamento che in genere è un ID di gestione delle relazioni con i clienti e/o un ID di accesso all’app mobile. Sei l’unico responsabile della protezione di questo campo di collegamento quando è utilizzato in connessione con Adobe Campaign. Se non riesci a proteggere i campi di collegamento, il messaggio personalizzato potrebbe essere vulnerabile. Se non segui procedure sicure di composizione, gestione e protezione del campo di collegamento, Adobe non sarà responsabile dei danni derivanti dall’accesso o dall’utilizzo non autorizzati di dati di profilo.

In Adobe Campaign sono disponibili tre tipi di messaggi in-app:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: questo tipo di messaggio ti consente di eseguire il targeting dei profili Adobe Campaign (profili di gestione delle relazioni con i clienti) che sono abbonati alla tua app mobile. Questo tipo di messaggio può essere personalizzato con tutti gli attributi di profilo disponibili in Adobe Campaign, ma richiede un handshake sicuro tra l’SDK mobile e il servizio di messaggistica in-app di Campaign per garantire che i messaggi con informazioni personali e riservate siano utilizzati solo da utenti autorizzati.

   Per scaricare questo tipo di messaggio sui dispositivi degli utenti, l’SDK mobile deve inviare i campi di collegamento utilizzati per connettere un profilo mobile a un profilo di gestione delle relazioni con i clienti in Adobe Campaign. Per ulteriori informazioni sulle API SDK necessarie per supportare i messaggi in-app, consulta questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: questo tipo di messaggio ti consente di inviare messaggi a tutti gli utenti (correnti o futuri) della tua app mobile anche se non dispongono di un profilo esistente in Adobe Campaign. La personalizzazione non è quindi possibile quando si personalizzano i messaggi in quanto il profilo utente potrebbe non esistere in Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: questo tipo di messaggio ti consente di eseguire il targeting per tutti gli utenti noti o anonimi di un’app mobile con un profilo mobile in Adobe Campaign. Questo tipo di messaggi può essere personalizzato utilizzando solo attributi non personali e non riservati e non richiede un handshake sicuro tra l’SDK di mobile e il servizio di messaggistica in-app di Adobe Campaign.

   Per ulteriori informazioni su come gestire dati personali e riservati, consulta [Gestione dei campi del profilo mobile con dati personali e sensibili](#handling-mobile-profile-fields-with-personal-and-sensitive-data).

![](assets/diagram_inapp.png)

## Gestione dei campi del profilo mobile con dati personali e sensibili {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, i dati degli attributi del profilo mobile inviati da dispositivi mobili sono memorizzati nella risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** che ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni.

Questa risorsa deve essere estesa per raccogliere i dati che intendi inviare dal dispositivo mobile ad Adobe Campaign. A tale scopo, consulta questa [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) per i passaggi dettagliati.

Per abilitare la personalizzazione dei messaggi in-app in modo più sicuro, i campi del profilo mobile di questa risorsa devono essere configurati di conseguenza. In **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, quando crei i nuovi campi dei profili mobili, seleziona **[!UICONTROL Personal and Sensitive]** per renderli non disponibili durante la personalizzazione dei messaggi in-app.

>[!NOTE]
>
>Se disponi di un’implementazione esistente con estensione di risorse personalizzata in questa tabella, è consigliabile etichettare i campi in modo appropriato prima di sfruttarli per la personalizzazione dei messaggi in-app.

![](assets/in_app_personal_data_2.png)

Una volta configurata e pubblicata la risorsa personalizzata **[!UICONTROL Subscriptions to an application]**, puoi iniziare a preparare la consegna in-app utilizzando il modello **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Solo i campi non personali e non riservati della risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** saranno disponibili per la personalizzazione.

Se desideri poter personalizzare i campi **Personali e riservati**, è consigliabile utilizzare il modello **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** che offre un meccanismo di sicurezza aggiuntivo per garantire la protezione dei dati PII degli utenti.

## Preparazione del messaggio in-app {#preparing-your-in-app-message}

I passaggi per la creazione di un messaggio in-app autonomo con Adobe Campaign sono i seguenti:

1. Dalla pagina Home di Adobe Campaign, fai clic sulla scheda **[!UICONTROL In-App messaging]**.

   Puoi creare un messaggio in-app anche dalla scheda **Marketing activities** facendo clic sul pulsante **[!UICONTROL Create]**.

   Puoi creare un messaggio in-app anche da una campagna, dalla pagina Home di Adobe Campaign o in un flusso di lavoro.

1. Seleziona **Messaggio in-app**.

   ![](assets/inapp_creating.png)

1. Seleziona un modello appropriato in base alle tue esigenze di definizione del pubblico di destinazione.

   ![](assets/inapp_creating_2.png)

   Per impostazione predefinita, puoi selezionare uno dei seguenti tre modelli preconfigurati:

   * **[!UICONTROL Target users based on their Campaign CRM profile (inAppProfile)]**
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**

1. Immetti le proprietà del messaggio in-app e seleziona la tua app mobile nel campo **[!UICONTROL Associate a Mobile App to a delivery]**. Tieni presente che se non hai configurato la tua app mobile con Adobe Campaign Standard, non verrà visualizzata nell’elenco. Per ulteriori informazioni sulla configurazione dell’app mobile, consulta questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/inapp_creating_3.png)

1. Seleziona il tipo di pubblico per il quale vuoi eseguire il targeting per il messaggio in-app. Il pubblico viene filtrato in modo preliminare in base all’app mobile associata a questa consegna.

   Tieni presente che questo passaggio non è necessario con **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** in quanto esegue il targeting di tutti gli utenti di un’app mobile.

   ![](assets/inapp_creating_8.png)

1. Nella scheda **[!UICONTROL Triggers]**, trascina e rilascia l’evento che attiverà il messaggio. Selezionando un trigger, scegli un’azione eseguita dagli utenti a seguito della quale il messaggio in-app verrà visualizzato.

   Sono disponibili quattro categorie di eventi:

   * **[!UICONTROL Mobile Application events]**: eventi personalizzati implementati nella tua app mobile.

      Per ulteriori informazioni sulle creazioni di eventi, consulta questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

   * **[!UICONTROL Life Cycle events]**: eventi del ciclo di vita preconfigurati supportati dall’SDK mobile di Adobe.

      Per ulteriori informazioni sugli eventi del ciclo di vita, consulta questa [pagina](https://docs.adobe.com/content/help/en/mobile-services/android/metrics.html).

   * **[!UICONTROL Analytics Events]**: le tre categorie seguenti sono supportate a seconda degli strumenti utilizzati nella tua app mobile: Adobe Analytics, Dati contestuali o Stato di visualizzazione.

      Tieni presente che tali eventi sono disponibili solo se disponi di una licenza Adobe Analytics.

   * **[!UICONTROL Places]**: le tre categorie seguenti sfruttano i dati sulla posizione in tempo reale per fornire esperienze mobili contestualmente rilevanti: Dati contestuali di Places, Metadati personalizzati di Places o Tipo di evento Places.

      Per ulteriori informazioni su Adobe Places, consulta la [documentazione su Places](https://placesdocs.com/).
   ![](assets/inapp_creating_4.png)

1. Se utilizzi un **[!UICONTROL Analytics Events]**, gli eventi Adobe Analytics e Stato di visualizzazione verranno compilati automaticamente in base alle suite di rapporti configurate nell’estensione Analytics in Adobe Experience Platform Launch, mentre gli eventi Dati contestuali devono essere aggiunti manualmente.

   Tieni presente che tali eventi sono disponibili solo se disponi di una licenza Adobe Analytics.

   ![](assets/inapp_creating_7.png)

1. Se utilizzi un trigger **[!UICONTROL Places]**, Dati contestuali di Places, Metadati personalizzati di Places o Tipo di evento Places verranno compilati automaticamente in base a tutte le librerie e ai relativi punti di interesse creati in Adobe Places.

   Tieni presente che questo trigger verrà applicato sul dispositivo solo per i punti di interesse dalle librerie selezionate nell’estensione Places in Experience Platform Launch. Per ulteriori informazioni sull’estensione Places e su come installarla, consulta questa [documentazione](https://docs.adobe.com/content/help/it-IT/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. Nella scheda **[!UICONTROL Frequency & duration]**, scegli la frequenza del trigger, la data di inizio e di fine, il giorno della settimana e l’ora del giorno in cui il messaggio in-app sarà attivo.

   ![](assets/inapp_creating_5.png)

1. Modifica il contenuto del messaggio e definisci le opzioni avanzate. Consulta [Personalizzazione di un messaggio in-app](https://helpx.adobe.com/campaign/standard/channels/using/customizing-an-in-app-message.html).

   ![](assets/inapp_creating_6.png)

1. Fai clic su **[!UICONTROL Create]**.

Il messaggio in-app ora è pronto per essere inviato al pubblico di destinazione.

**Argomenti correlati:**

* [Personalizzazione di un messaggio in-app](../../channels/using/customizing-an-in-app-message.md)
* [Report in-app](../../reporting/using/in-app-report.md)
* [Invio di un messaggio in-app all’interno di un flusso di lavoro](../../automating/using/in-app-delivery.md)

## Invio del messaggio in-app {#sending-your-in-app-message}

Una volta completata la preparazione della consegna ed eseguiti i passaggi di approvazione, puoi inviare il messaggio.

1. Fai clic su **[!UICONTROL Prepare]** per calcolare la destinazione e generare i messaggi.

   ![](assets/inapp_sending_4.png)

1. Una volta completata correttamente la preparazione, la finestra **Implementazione** presenta i KPI seguenti: **Destinazione** e **Da consegnare**.

   Puoi controllare la finestra Deployment facendo clic sul pulsante ![](assets/lp_link_properties.png) per eventuali esclusioni o errori nella consegna.

   ![](assets/inapp_sending_5.png)

1. Fai clic su **[!UICONTROL Confirm]** per iniziare a inviare il messaggio in-app.

   ![](assets/inapp_sending_6.png)

1. Controlla lo stato della consegna attraverso il dashboard messaggi e i registri. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/monitoring-a-delivery.md).

   I conteggi dei KPI **[!UICONTROL Delivered]** e **[!UICONTROL Sent]** si basano su quanto è stato inviato correttamente da Campaign al servizio di consegna dei messaggi. Tieni presente che questi KPI non rappresentano un’indicazione del numero di dispositivi mobili che hanno ricevuto o scaricato correttamente il messaggio dal servizio di consegna dei messaggi.

   ![](assets/inapp_sending_7.png)

1. Misura l’impatto dei messaggi in-app con i rapporti di consegna. Per ulteriori informazioni sul reporting, consulta [questa sezione](../../reporting/using/in-app-report.md).

**Argomenti correlati:**

* [Report in-app](../../reporting/using/in-app-report.md)
* [Invio di un messaggio in-app all’interno di un flusso di lavoro](../../automating/using/in-app-delivery.md)
