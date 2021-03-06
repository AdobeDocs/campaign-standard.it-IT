---
title: Creare e inviare una notifica push
description: Segui questi passaggi per creare una notifica push a invio singolo in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 7%

---

# Preparazione e invio di una notifica push{#preparing-and-sending-a-push-notification}

## Preparazione della notifica {#preparing-the-notification}

I passaggi per creare una notifica push con Adobe Campaign sono i seguenti:

1. Da **[!UICONTROL Marketing activities]** finestra, [creare una nuova attività di marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Puoi creare una singola notifica push anche da un [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity) o da Adobe Campaign [home page](../../start/using/interface-description.md#home-page).

   Puoi anche utilizzare un’attività di consegna delle notifiche push in un flusso di lavoro. Questa attività viene presentata nel [Consegna notifiche push](../../automating/using/push-notification-delivery.md) sezione .

1. Seleziona **[!UICONTROL Push notification]**.
1. Seleziona un modello.

   ![](assets/push_notif_type.png)

   Per impostazione predefinita, è possibile selezionare uno dei due modelli seguenti:

   * **[!UICONTROL Send push to Campaign profiles]**: utilizza questo modello per eseguire il targeting dei profili Adobe Campaign CRM che si sono abbonati alla tua app mobile e hanno acconsentito alla ricezione di notifiche push. È possibile inserire [personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) campi nella notifica push, ad esempio il nome del destinatario.
   * **[!UICONTROL Send push to app subscribers]**: utilizza questo modello per inviare una notifica push a tutti gli utenti noti e anonimi di applicazioni mobili che hanno acconsentito alla ricezione di notifiche dalla tua applicazione. Puoi personalizzare questi messaggi con i dati raccolti dalla tua app mobile.

   Puoi anche selezionare modelli multilingue. Per ulteriori informazioni, consulta [Creazione di una notifica push multilingue](../../channels/using/creating-a-multilingual-push-notification.md).

   Per ulteriori informazioni sui modelli, consulta la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md) sezione .

1. Immetti le proprietà di notifica push e seleziona la tua app mobile nella **[!UICONTROL Associate a Mobile App to a delivery]** campo .

   L’elenco a discesa mostrerà le applicazioni SDK V4 e Experience Platform SDK.

   ![](assets/push_notif_properties.png)

   Puoi collegare la notifica push a una campagna. A questo scopo, selezionala dalle campagne già create.

1. Nella schermata seguente, puoi specificare un pubblico, ad esempio tutti i clienti VIP che si sono abbonati a una specifica app mobile. Per ulteriori informazioni, consulta [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).

   Il pubblico verrà filtrato automaticamente in base all’app mobile selezionata nel passaggio precedente.

   ![](assets/push_notif_audience.png)

1. Ora puoi personalizzare la notifica push. Innanzitutto, scegli lo stile del messaggio: **[!UICONTROL Alert/Message/Badge]** o **[!UICONTROL Silent push]**. I tipi di notifica push sono descritti nella sezione [Informazioni sulle notifiche push](../../channels/using/about-push-notifications.md) sezione .

   Modifica il contenuto della notifica push e definisci le opzioni avanzate. Vedi [Personalizzazione di una notifica push](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   Il contenuto e le opzioni di notifica push configurati qui vengono passati alla tua app mobile sotto forma di payload. La struttura dettagliata del carico utile è descritta nel [Struttura del payload per le notifiche push di Campaign Standard](../../administration/using/push-payload.md) nota tecnica.

1. Fai clic su **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Prima di inviare la notifica, puoi testarla con i profili di test e quindi visualizzare esattamente ciò che i destinatari vedranno prima di inviare la consegna. Seleziona **[!UICONTROL Audiences]** dal riepilogo della consegna e fai clic su **[!UICONTROL Test profiles]** scheda .

   Per ulteriori informazioni sull’invio dei test, consulta [Profili di test](../../sending/using/sending-proofs.md).

1. Seleziona i profili di test e fai clic su **[!UICONTROL Preview]** per visualizzare la notifica: il contenuto viene personalizzato con i dati del profilo di test.
1. Controlla il layout della notifica push su diversi dispositivi: seleziona iPhone, telefono Android, iPad o tablet Android per visualizzare l&#39;anteprima del rendering.

   ![](assets/push_notif_preview.png)

1. La **[!UICONTROL Estimated Payload Size]** è una stima basata sui dati del profilo di test. La dimensione effettiva del payload può variare. Il limite del messaggio è di 4 KB.

   >[!CAUTION]
   >
   >Se la dimensione del payload supera il limite di 4 KB, il messaggio non verrà recapitato.

I dati di personalizzazione hanno un impatto sulla dimensione del messaggio.

## Invio della notifica {#sending-the-notification}

Le notifiche push possono essere inviate a un pubblico selezionato in Adobe Campaign definendo i criteri di pubblico. Per l’esempio seguente, il pubblico selezionato è composto da 4 abbonati a app mobili mirate.

1. Fai clic su **[!UICONTROL Prepare]** per calcolare il target e generare le notifiche.

   ![](assets/push_send_1.png)

1. Una volta completata la preparazione, la **[!UICONTROL Deployment]** window presenta i KPI seguenti: **[!UICONTROL Target]** e **[!UICONTROL To deliver]**. Tieni presente che il conteggio **[!UICONTROL To deliver]** è inferiore a quello di **[!UICONTROL Targeted]** a causa di esclusioni che possono essere visualizzate facendo clic sul pulsante ![](assets/lp_link_properties.png) nella parte inferiore della finestra **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. In **[!UICONTROL Exclusion logs]** È possibile trovare l’elenco di tutti i messaggi esclusi dal target inviato e il motivo di questa esclusione.

   Qui, possiamo vedere che uno dei nostri abbonati all’app mobile è stato escluso perché l’indirizzo era sul elenco Bloccati e gli altri abbonati perché il profilo era un duplicato.

   ![](assets/push_send_5.png)

1. Fai clic sul pulsante **[!UICONTROL Exclusion causes]** per visualizzare il volume dei messaggi esclusi.

   ![](assets/push_send_7.png)

1. Ora puoi fare clic su **[!UICONTROL Confirm]** per iniziare a inviare notifiche push.
1. Controlla lo stato della consegna attraverso il dashboard messaggi e i registri. Per ulteriori informazioni, consulta [Invio di messaggi](../../sending/using/confirming-the-send.md) e [Log di consegna](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   In questo esempio, il dashboard dei messaggi visualizza il tentativo di Adobe Campaign di inviare due notifiche push: uno è stato consegnato correttamente al dispositivo e un altro non è riuscito. Per sapere perché la consegna contiene errori, fai clic sul pulsante ![](assets/lp_link_properties.png) nella parte inferiore del **[!UICONTROL Deployment]** finestra.

   ![](assets/push_send_4.png)

1. Da **[!UICONTROL Deployment]** fai clic su **[!UICONTROL Sending logs]** per accedere all’elenco delle notifiche push inviate e i relativi stati. Per questa consegna, una notifica push è stata inviata correttamente mentre l’altra non è riuscita a causa di un token dispositivo non valido. Questo utente iscritto verrà quindi aggiunto al  elenco Bloccati da ulteriori consegne.

   >[!NOTE]
   >
   >I motivi possono essere qualsiasi errore a valle di Adobe Campaign. In caso di errori da parte di provider come apns e fcm, il motivo rifletterà anche questo. Per ulteriori informazioni sugli errori del provider, consulta [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentazione.

   ![](assets/push_send_6.png)

Ora puoi misurare l’impatto della consegna delle notifiche push con report dinamici.

**Argomenti correlati:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all’interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)
