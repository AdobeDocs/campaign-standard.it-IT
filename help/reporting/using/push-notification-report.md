---
title: Rapporto notifiche push
description: Con il rapporto preconfigurato sulle notifiche push, scopri il successo delle notifiche push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 1%

---

# Rapporto notifiche push{#push-notification-report}

>[!CAUTION]
>
>Tieni presente che devi trascinare e rilasciare la **[!UICONTROL Message type]** metriche alle tabelle per suddividere i dati in base ai tipi di consegna, in questo caso consegne di notifiche push.

La **Notifica push** Il rapporto fornisce dettagli sulle prestazioni di marketing delle notifiche push in Adobe Campaign. Questo rapporto pronto all’uso ti aiuta a capire come gli utenti interagiscono con le notifiche push, le applicazioni mobili e le consegne.

È necessaria una certa configurazione nell’app mobile per implementare il tracciamento push, consulta questo [page](../../administration/using/push-tracking.md) per i passaggi dettagliati.

![](assets/dynamic_report_push.png)

Ogni tabella è rappresentata da numeri di riepilogo e grafici. Puoi modificare il modo in cui i dettagli vengono visualizzati nelle rispettive impostazioni di visualizzazione.

La prima tabella **Riepilogo del coinvolgimento nella notifica push** è suddiviso in tre categorie: di giorno, per app mobile e per consegna. Contiene i dati disponibili per la reattività del destinatario alla consegna:

* **[!UICONTROL Processed/sent]**: Numero totale di notifiche push inviate.
* **[!UICONTROL Delivered]**: Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.
* **[!UICONTROL Impressions]**: Numero di volte in cui una notifica push è stata recapitata al dispositivo e lasciata intatta nel centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e ritrasmette le informazioni al server.
* **[!UICONTROL Unique impressions]**: Numero di impression per destinatario.
* **[!UICONTROL Click through rate]**: Percentuale di utenti che hanno interagito con la notifica push.
* **[!UICONTROL Open rate]**: Percentuale di notifiche push aperte.

![](assets/dynamic_report_push_2.png)

La seconda tabella **Clic e aperture delle notifiche push** è suddiviso in tre categorie: di giorno, per app mobile e per consegna. Contiene i dati disponibili per il comportamento del destinatario per consegna:

* **[!UICONTROL Impressions]**: Totale delle notifiche push visualizzate dai destinatari.
* **[!UICONTROL Unique impressions]**: Numero di impression per destinatario.
* **[!UICONTROL Click]**: Numero di volte in cui l’utente ha fatto clic su e inviato una notifica push al dispositivo. L’utente voleva visualizzare la notifica, che verrà quindi spostata nel tracciamento Push Open (Apri push), oppure ignorarla.
* **[!UICONTROL Unique clicks]**: Numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio clic sulla notifica o sul pulsante.
* **[!UICONTROL Open]**: Numero totale di notifiche push inviate al dispositivo e su cui gli utenti hanno fatto clic per aprire l’app. È simile al clic push, tranne per il fatto che l’apertura push non viene attivata se la notifica è stata ignorata.
* **[!UICONTROL Unique Opens]**: Numero di destinatari che hanno aperto la consegna.
