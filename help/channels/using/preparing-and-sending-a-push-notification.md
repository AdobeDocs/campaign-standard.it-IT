---
title: Preparazione e invio di una notifica push
seo-title: Preparazione e invio di una notifica push
description: Preparazione e invio di una notifica push
seo-description: Segui questi passaggi per creare una notifica push singola in Adobe Campaign.
page-status-flag: never-activated
uuid: 01997725-ca 0 a -420 c -9 e 81-5 ea 801652 f 87
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: notifiche push
discoiquuid: ec 930 cd 4-6365-4 e 54-babe -9 dc 2 eed 041 fc
context-tags: delivery, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Preparing and sending a push notification{#preparing-and-sending-a-push-notification}

## Preparing the notification {#preparing-the-notification}

I passaggi per creare una notifica push con Adobe Campaign sono:

1. From the **[!UICONTROL Marketing activities]** window, [create a new marketing activity](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Note that a single push notification can also be created from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page).

   Potete anche utilizzare un'attività di consegna delle notifiche push in un flusso di lavoro. This activity is presented in the [Push notification delivery](../../automating/using/push-notification-delivery.md) section.

1. Select **[!UICONTROL Push notification]**.
1. Selezionate un modello.

   ![](assets/push_notif_type.png)

   Per impostazione predefinita, potete selezionare uno dei due modelli seguenti:

   * **[!UICONTROL Send push to Campaign profiles]**: utilizzate questo modello per impostare come destinazione i profili CRM di Adobe Campaign che hanno effettuato la sottoscrizione all'applicazione mobile e che hanno acconsentito alla ricezione di notifiche push. You can insert [personalization](../../designing/using/inserting-a-personalization-field.md) fields into your push notification, such as the recipient's first name.
   * **[!UICONTROL Send push to app subscribers]**: utilizzare questo modello per inviare una notifica push a tutti gli utenti delle applicazioni mobili noti e anonimi che hanno acconsentito alla ricezione di notifiche dall'applicazione. Puoi personalizzare questi messaggi con i dati raccolti dall'applicazione mobile.
   È inoltre possibile selezionare modelli multilingue. For more information, refer to [Creating a multilingual push notification](../../channels/using/creating-a-multilingual-push-notification.md).

   For more on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tieni presente che il menu a discesa visualizzerà le applicazioni SDK V 4 e Experience Platform SDK.

   ![](assets/push_notif_properties.png)

   Potete collegare la notifica push a una campagna. A tal fine, selezionatela dalle campagne che sono già state create.

1. Nella schermata seguente, potete specificare un pubblico, ad esempio tutti i clienti VIP che hanno effettuato la sottoscrizione a una specifica applicazione mobile. For more on this, see [Creating audiences](../../audiences/using/creating-audiences.md).

   Il pubblico verrà filtrato automaticamente in base all'applicazione per dispositivi mobili selezionata nel passaggio precedente.

   ![](assets/push_notif_audience.png)

1. Ora potete personalizzare la notifica push. First, choose the message style: **[!UICONTROL Alert/Message/Badge]** or **[!UICONTROL Silent push]**. The push notification types are described in the [About push notifications](../../channels/using/about-push-notifications.md) section.

   Modifica il contenuto della notifica push e definisci le opzioni avanzate. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   Il contenuto di notifica push e le opzioni configurate qui vengono passati alla tua app mobile sotto forma di payload. The detailed structure of the payload is described in the [Understanding ACS push notifications payload structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) technote.

1. Click **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Prima di inviare la notifica, potete testarla con i profili di prova e quindi visualizzare esattamente ciò che i destinatari vedranno prima di inviare la distribuzione. Select **[!UICONTROL Audiences]** from your delivery summary and click the **[!UICONTROL Test profiles]** tab.

   For more on sending tests, refer to [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md).

1. Select your test profiles and click **[!UICONTROL Preview]** to display the notification: content is personalized with the test profile data.
1. Controllate il layout delle notifiche push su dispositivi diversi: selezionate iphone, telefoni Android, ipad o tablet Android per effettuare l'anteprima.

   ![](assets/push_notif_preview.png)

1. The **[!UICONTROL Estimated Payload Size]** is an estimate based on test profile data. Le dimensioni effettive del payload possono variare. Il limite del messaggio è di 4 KB.

   >[!CAUTION]
   >
   >Se la dimensione del payload supera i 4 KB, il messaggio non verrà distribuito. I dati di personalizzazione influiscono sulla dimensione del messaggio.

## Sending the notification {#sending-the-notification}

Le notifiche push possono essere inviate a un pubblico selezionato in Adobe Campaign, definendo i criteri di audience. Per l'esempio di seguito, il pubblico selezionato è composto da 4 utenti con sottoscrizione di app mobili.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Tieni presente che il conteggio **[!UICONTROL To deliver]** è inferiore a quello di **[!UICONTROL Targeted]** a causa di esclusioni che possono essere visualizzate facendo clic sul pulsante ![](assets/lp_link_properties.png) nella parte inferiore della finestra **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. In the **[!UICONTROL Exclusion logs]** tab, you can find the list of all the messages excluded from the target sent and the reason behind this exclusion.

   Qui possiamo vedere che uno dei nostri abbonati a un app mobile è stato escluso perché l'indirizzo è stato inserito in blacklist e gli altri abbonati, perché il profilo era un duplicato.

   ![](assets/push_send_5.png)

1. Click the **[!UICONTROL Exclusion causes]** tab to display the volume of excluded messages.

   ![](assets/push_send_7.png)

1. You can now click **[!UICONTROL Confirm]** to start sending push notifications.
1. Controllate lo stato della distribuzione tramite il dashboard messaggio e i registri. For more on this, see [Sending messages](../../sending/using/confirming-the-send.md) and [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   In questo esempio, il pannello del messaggio mostra che Adobe Campaign ha tentato di inviare due notifiche push: una è stata inviata al dispositivo e un'altra non è riuscita. To know why the delivery has errors, click the ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_4.png)

1. From the **[!UICONTROL Deployment]** window, click the **[!UICONTROL Sending logs]** tab to access the list of sent push notifications and their statuses. Per questa consegna, una notifica push è stata inviata correttamente, mentre l'altra non riusciva a causa di un token dispositivo errato. Questo utente verrà inserito in blacklist da ulteriori consegne.

   >[!NOTE]
   >
   >I motivi possono essere qualsiasi errore a valle di Adobe Campaign. In caso di errori da fornitori come apns e fcm, il motivo sarà anche quello. For more information on provider failures, you can refer to the [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) and [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) documentation.

   ![](assets/push_send_6.png)

Ora puoi misurare l'impatto della distribuzione di notifiche push con rapporti dinamici.

**Argomenti correlati:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all'interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)

