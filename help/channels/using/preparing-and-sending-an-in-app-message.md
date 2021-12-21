---
title: Preparazione e invio di un messaggio in-app
description: Crea un messaggio in-app per eseguire il targeting con contenuto specifico per gli abbonati alla tua applicazione.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back;deliveryCreation,wizard
feature: In App
role: User
exl-id: ef83d991-302b-491e-9cdb-07f5da7a5971
source-git-commit: 0523c7cc68661a5593ae2c58382f839c2379f2db
workflow-type: tm+mt
source-wordcount: '1170'
ht-degree: 95%

---

# Preparazione e invio di un messaggio in-app{#preparing-and-sending-an-in-app-message}

In Adobe Campaign sono disponibili tre tipi di messaggi in-app:

* **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: questo tipo di messaggio ti consente di eseguire il targeting dei profili Adobe Campaign (profili di gestione delle relazioni con i clienti) che sono abbonati alla tua app mobile. Questo tipo di messaggio può essere personalizzato con tutti gli attributi di profilo disponibili in Adobe Campaign, ma richiede un handshake sicuro tra l’SDK mobile e il servizio di messaggistica in-app di Campaign per garantire che i messaggi con informazioni personali e riservate siano utilizzati solo da utenti autorizzati.

   Per scaricare questo tipo di messaggio sui dispositivi degli utenti, l’SDK mobile deve inviare i campi di collegamento utilizzati per connettere un profilo mobile a un profilo di gestione delle relazioni con i clienti in Adobe Campaign. Per ulteriori informazioni sulle API SDK necessarie per supportare i messaggi in-app, consulta questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference).

* **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: questo tipo di messaggio ti consente di inviare messaggi a tutti gli utenti (correnti o futuri) della tua app mobile anche se non dispongono di un profilo esistente in Adobe Campaign. La personalizzazione non è quindi possibile quando si personalizzano i messaggi in quanto il profilo utente potrebbe non esistere in Adobe Campaign.
* **[!UICONTROL Target users based on their Mobile profile (inApp)]**: questo tipo di messaggio ti consente di eseguire il targeting per tutti gli utenti noti o anonimi di un’app mobile con un profilo mobile in Adobe Campaign. Questo tipo di messaggi può essere personalizzato utilizzando solo attributi non personali e non riservati e non richiede un handshake sicuro tra l’SDK di mobile e il servizio di messaggistica in-app di Adobe Campaign.

   Per ulteriori informazioni su come gestire dati personali e riservati, consulta [Gestione dei campi del profilo mobile con dati personali e sensibili](../../channels/using/about-in-app-messaging.md#handling-mobile-profile-fields-with-personal-and-sensitive-data).

![](assets/diagram_inapp.png)

## Preparazione del messaggio in-app {#preparing-your-in-app-message}

>[!CAUTION]
>
>La personalizzazione in-app si basa su un campo di collegamento che in genere è un ID di gestione delle relazioni con i clienti e/o un ID di accesso all’app mobile. Sei l’unico responsabile della protezione di questo campo di collegamento quando è utilizzato in connessione con Adobe Campaign. Se non riesci a proteggere i campi di collegamento, il messaggio personalizzato potrebbe essere vulnerabile. Se non segui procedure sicure di composizione, gestione e protezione del campo di collegamento, Adobe non sarà responsabile dei danni derivanti dall’accesso o dall’utilizzo non autorizzati di dati di profilo.

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

1. Immetti le proprietà del messaggio in-app e seleziona la tua app mobile nel campo **[!UICONTROL Associate a Mobile App to a delivery]**. 

   Se non trovi applicazioni nell’elenco a discesa, assicurati che le tue app mobili siano in una **Configurato** stato. Applicazioni in un **Pronto per la configurazione** lo stato non viene visualizzato nell’elenco. Per ulteriori informazioni sulla configurazione dell’app mobile, consulta questa [pagina](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

   ![](assets/inapp_creating_3.png)

1. Seleziona il tipo di pubblico per il quale vuoi eseguire il targeting per il messaggio in-app. Il pubblico viene filtrato in modo preliminare in base all’app mobile associata a questa consegna.

   Tieni presente che questo passaggio non è necessario con **[!UICONTROL Broadcast an In-App message (inAppBroadcast)]** in quanto esegue il targeting di tutti gli utenti di un’app mobile.

   ![](assets/inapp_creating_8.png)

1. Nella scheda **[!UICONTROL Triggers]**, trascina e rilascia l’evento che attiverà il messaggio. Selezionando un trigger, scegli un’azione eseguita dagli utenti a seguito della quale il messaggio in-app verrà visualizzato.

   Sono disponibili quattro categorie di eventi:

   * **[!UICONTROL Mobile Application events]**: eventi personalizzati implementati nella tua app mobile.

      Per ulteriori informazioni sulle creazioni di eventi, consulta questa [pagina](../../administration/using/configuring-a-mobile-application.md).

   * **[!UICONTROL Life Cycle events]**: eventi del ciclo di vita preconfigurati supportati dall’SDK mobile di Adobe.

      Per ulteriori informazioni sugli eventi del ciclo di vita, consulta questa [pagina](https://experienceleague.adobe.com/docs/mobile-services/android/metrics.html).

   * **[!UICONTROL Analytics Events]**: le tre categorie seguenti sono supportate a seconda degli strumenti utilizzati nella tua app mobile: Adobe Analytics, Dati contestuali o Stato di visualizzazione.

      Tieni presente che tali eventi sono disponibili solo se disponi di una licenza Adobe Analytics.

   * **[!UICONTROL Places]**: le tre categorie seguenti sfruttano i dati sulla posizione in tempo reale per fornire esperienze mobili contestualmente rilevanti: Dati contestuali di Places, Metadati personalizzati di Places o Tipo di evento Places.

      Per ulteriori informazioni su Adobe Places, consulta la [documentazione su Places](https://experienceleague.adobe.com/docs/places/using/home.html).
   ![](assets/inapp_creating_4.png)

1. Se utilizzi un **[!UICONTROL Analytics Events]**, gli eventi Adobe Analytics e Stato di visualizzazione verranno compilati automaticamente in base alle suite di rapporti configurate nell’estensione Analytics in Adobe Experience Platform Launch, mentre gli eventi Dati contestuali devono essere aggiunti manualmente.

   Tieni presente che tali eventi sono disponibili solo se disponi di una licenza Adobe Analytics.

   ![](assets/inapp_creating_7.png)

1. Se utilizzi un trigger **[!UICONTROL Places]**, Dati contestuali di Places, Metadati personalizzati di Places o Tipo di evento Places verranno compilati automaticamente in base a tutte le librerie e ai relativi punti di interesse creati in Adobe Places.

   Tieni presente che questo trigger verrà applicato sul dispositivo solo per i punti di interesse dalle librerie selezionate nell’estensione Places in Experience Platform Launch. Per ulteriori informazioni sull’estensione Places e su come installarla, consulta questa [documentazione](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. Nella scheda **[!UICONTROL Frequency & duration]**, scegli la frequenza del trigger, la data di inizio e di fine, il giorno della settimana e l’ora del giorno in cui il messaggio in-app sarà attivo.

   ![](assets/inapp_creating_5.png)

1. Modifica il contenuto del messaggio e definisci le opzioni avanzate. Consulta [Personalizzazione di un messaggio in-app](../../channels/using/customizing-an-in-app-message.md).

   ![](assets/inapp_creating_6.png)

1. Fai clic su **[!UICONTROL Create]**.

Il messaggio in-app ora è pronto per essere inviato al pubblico di destinazione.

**Argomenti correlati:**

* [Personalizzazione di un messaggio in-app](../../channels/using/customizing-an-in-app-message.md)
* [Rapporto in-app](../../reporting/using/in-app-report.md)
* [Invio di un messaggio in-app all’interno di un flusso di lavoro](../../automating/using/in-app-delivery.md)

## Anteprima del messaggio in-app {#previewing-the-in-app-message}

Prima di inviare il messaggio in-app, puoi eseguirne la verifica tramite i profili di test, così da controllare ciò che verrà visualizzato dal pubblico target quando riceverà la tua consegna.

1. Fai clic sul pulsante **[!UICONTROL Preview]**.

   ![](assets/inapp_sending_2.png)

1. Per iniziare a visualizzare l’anteprima della consegna, fai clic sul pulsante **[!UICONTROL Select a test profile]** e seleziona uno dei profili di test. Per ulteriori informazioni sui profili di test, consulta questa [sezione](../../audiences/using/managing-test-profiles.md).
1. Controlla il messaggio su diversi dispositivi, ad esempio Android, iPhone o persino tablet. Puoi anche verificare se i campi di personalizzazione recuperano i dati corretti.

   ![](assets/inapp_sending_3.png)

1. Ora puoi inviare il messaggio e misurarne l’impatto tramite i rapporti di consegna.

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

* [Rapporto in-app](../../reporting/using/in-app-report.md)
* [Invio di un messaggio in-app all’interno di un flusso di lavoro](../../automating/using/in-app-delivery.md)
