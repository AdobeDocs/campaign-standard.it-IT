---
solution: Campaign Standard
product: campaign
title: Report notifiche push
description: Con il rapporto preconfigurato sulle notifiche push, scopri il successo delle notifiche push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Generazione rapporti
role: Leader
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---


# Report notifiche push{#push-notification-report}

>[!CAUTION]
>
>Tieni presente che devi trascinare e rilasciare le metriche **[!UICONTROL Message type]** nelle tabelle per suddividere i dati in base ai tipi di consegna, in questo caso le consegne di notifiche push.

Il rapporto **Notifica push** fornisce dettagli sulle prestazioni di marketing delle notifiche push in Adobe Campaign. Questo rapporto pronto all’uso ti aiuterà a comprendere come gli utenti interagiscono con le notifiche push, le applicazioni mobili e le consegne.

Per implementare il tracciamento push è necessaria una certa configurazione nell’app mobile. Per i passaggi dettagliati, fai riferimento a questa [pagina](../../administration/using/push-tracking.md) .

![](assets/dynamic_report_push.png)

Ogni tabella è rappresentata da numeri di riepilogo e grafici. Puoi modificare il modo in cui i dettagli vengono visualizzati nelle rispettive impostazioni di visualizzazione.

La prima tabella **Riepilogo del coinvolgimento nelle notifiche push** è suddivisa in tre categorie: di giorno, per app mobile e per consegna. Contiene i dati disponibili per la reattività del destinatario alla consegna:

* **[!UICONTROL Processed/sent]**: Numero totale di notifiche push inviate.
* **[!UICONTROL Delivered]**: Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.
* **[!UICONTROL Impressions]**: Numero di volte in cui una notifica push è stata recapitata al dispositivo e lasciata intatta nel centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e ritrasmette le informazioni al server.
* **[!UICONTROL Unique impressions]**: Numero di impression per destinatario.
* **[!UICONTROL Click through rate]**: Percentuale di utenti che hanno interagito con la notifica push.
* **[!UICONTROL Open rate]**: Percentuale di notifiche push aperte.

![](assets/dynamic_report_push_2.png)

La seconda tabella **Notifiche push Clic e apre** è suddivisa in tre categorie: di giorno, per app mobile e per consegna. Contiene i dati disponibili per il comportamento del destinatario per consegna:

* **[!UICONTROL Impressions]**: Totale delle notifiche push visualizzate dai destinatari.
* **[!UICONTROL Unique impressions]**: Numero di impression per destinatario.
* **[!UICONTROL Click]**: Numero di volte in cui l’utente ha fatto clic su e inviato una notifica push al dispositivo. L’utente voleva visualizzare la notifica, che verrà quindi spostata nel tracciamento Push Open (Apri push), oppure ignorarla.
* **[!UICONTROL Unique clicks]**: Numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio clic sulla notifica o sul pulsante.
* **[!UICONTROL Open]**: Numero totale di notifiche push inviate al dispositivo e su cui gli utenti hanno fatto clic per aprire l’app. È simile al clic push, tranne per il fatto che l’apertura push non viene attivata se la notifica è stata ignorata.
* **[!UICONTROL Unique Opens]**: Numero di destinatari che hanno aperto la consegna.

