---
title: Rapporto notifiche push
seo-title: Rapporto notifiche push
description: Rapporto notifiche push
seo-description: Con il rapporto push out-of-the-box, scopri il successo delle notifiche push.
page-status-flag: never-activated
uuid: 5 b 121 a 37-1 c 09-4749-a 409-6989978 ddc 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: list-of-reports
discoiquuid: a 425 cd 59-edfd -42 c 5-a 6 bd -38773 c 353 ff 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7102ed308f94985f8924a13aab2583e50b6c68e4

---


# Push notification report{#push-notification-report}

>[!CAUTION]
>
>Please note that you have to drag and drop the **[!UICONTROL Message type]** metrics to your tables to split your data depending on your delivery types, in this case push notification deliveries.

The **Push notification** report provides details of marketing performance of push notifications in Adobe Campaign. Questo rapporto aggiornato ti aiuterà a capire in che modo gli utenti interagiscono con notifiche push, applicazioni mobili e consegne.

Some configuration is required in the mobile application to implement push tracking, refer to this [page](https://helpx.adobe.com/campaign/kb/push-tracking.html) for the detailed steps.

![](assets/dynamic_report_push.png)

Ogni tabella è rappresentata da numeri di riepilogo e diagrammi. Puoi modificare il modo in cui i dettagli vengono visualizzati nelle rispettive impostazioni di visualizzazione.

The first table **Push notification Engagement Summary** is split into three categories: by day, by mobile app and by delivery. Contiene i dati disponibili per la reattività dei destinatari alla distribuzione:

* **[!UICONTROL Processed/sent]**: Numero totale di notifiche push inviate.
* **[!UICONTROL Delivered]**: Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.
* **[!UICONTROL Impressions]**: Numero di volte in cui una notifica push è stata distribuita sul dispositivo e lasciata invariata nel Centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. Questo assicura che il dispositivo abbia ricevuto il messaggio e che le informazioni vengano trasmesse nuovamente al server.
* **[!UICONTROL Unique impressions]**: Numero di impression da parte del destinatario.
* **[!UICONTROL Click through rate]**: Percentuale di utenti che hanno interagito con la notifica push.
* **[!UICONTROL Open rate]**: Percentuale delle notifiche push aperte.

![](assets/dynamic_report_push_2.png)

The second table **Push notification Clicks &amp; opens** is split into three categories: by day, by mobile app and by delivery. Contiene i dati disponibili per il comportamento dei destinatari per distribuzione:

* **[!UICONTROL Impressions]**: Totale delle notifiche push visualizzate dai destinatari.
* **[!UICONTROL Unique impressions]**: Numero di impression da parte del destinatario.
* **[!UICONTROL Click]**: Numero di volte in cui una notifica push è stata trasmessa al dispositivo e fa clic su di essa. L'utente desidera visualizzare la notifica, che verrà quindi spostata in Push Open tracking (Sposta tracciamento aperto) o dismiss.
* **[!UICONTROL Unique clicks]**: Numero di volte in cui un utente univoco interagisce con la notifica push, ad es. clic sulla notifica o sul pulsante.
* **[!UICONTROL Open]**: Numero totale delle notifiche push distribuite sul dispositivo e su cui è stato fatto clic dagli utenti aprendo l'app. Questo è simile a Click Click (Clic push) eccetto a Push Open (Apri push), se la notifica è stata chiusa.
* **[!UICONTROL Unique Opens]**: Numero di destinatari che hanno aperto la consegna.

