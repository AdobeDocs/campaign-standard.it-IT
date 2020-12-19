---
solution: Campaign Standard
product: campaign
title: Report notifiche push
description: Grazie al rapporto out-of-the-box delle notifiche push, scopri il successo delle notifiche push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# Report notifiche push{#push-notification-report}

>[!CAUTION]
>
>Nota: devi trascinare le metriche **[!UICONTROL Message type]** nelle tabelle per suddividere i dati in base ai tipi di consegna, in questo caso le consegne di notifiche push.

Il rapporto **Notifica push** fornisce dettagli sulle prestazioni di marketing delle notifiche push in  Adobe Campaign. Questo report out-of-the-box ti aiuterà a capire in che modo gli utenti interagiscono con le notifiche push, le applicazioni mobili e le consegne.

Per implementare il tracciamento push è necessaria una certa configurazione nell&#39;applicazione mobile. Per i passaggi dettagliati, fai riferimento a questa [pagina](../../administration/using/push-tracking.md).

![](assets/dynamic_report_push.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

La prima tabella **Riepilogo coinvolgimento notifica push** è suddivisa in tre categorie: per giorno, per app mobile e per consegna. Contiene i dati disponibili per la reattività del destinatario alla consegna:

* **[!UICONTROL Processed/sent]**: Numero totale di notifiche push inviate.
* **[!UICONTROL Delivered]**: Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.
* **[!UICONTROL Impressions]**: Numero di volte in cui una notifica push viene inviata al dispositivo e lasciata inalterata nel Centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e le ritorna al server.
* **[!UICONTROL Unique impressions]**: Numero di impression per destinatario.
* **[!UICONTROL Click through rate]**: Percentuale di utenti che hanno interagito con la notifica push.
* **[!UICONTROL Open rate]**: Percentuale delle notifiche push aperte.

![](assets/dynamic_report_push_2.png)

La seconda tabella **Notifica push Click &amp; open** è suddivisa in tre categorie: per giorno, per app mobile e per consegna. Contiene i dati disponibili per il comportamento del destinatario per consegna:

* **[!UICONTROL Impressions]**: Totale delle notifiche push visualizzate dai destinatari.
* **[!UICONTROL Unique impressions]**: Numero di impression per destinatario.
* **[!UICONTROL Click]**: Numero di volte in cui una notifica push è stata inviata al dispositivo e l&#39;utente ha fatto clic su di essa. L&#39;utente desidera visualizzare la notifica, che verrà quindi spostata nel tracciamento dell&#39;apertura push, o chiusa.
* **[!UICONTROL Unique clicks]**: Numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio facendo clic sulla notifica o sul pulsante.
* **[!UICONTROL Open]**: Numero totale di notifiche push inviate al dispositivo e fate clic su di esse dagli utenti per aprire l&#39;app. Questo è simile al clic push, tranne per il fatto che l&#39;apertura push non viene attivata se la notifica è stata chiusa.
* **[!UICONTROL Unique Opens]**: Numero di destinatari che hanno aperto la consegna.

