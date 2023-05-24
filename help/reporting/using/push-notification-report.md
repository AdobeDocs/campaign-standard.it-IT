---
title: Rapporto notifiche push
description: Con il rapporto preconfigurato Notifica push, scopri come le notifiche push hanno avuto esito positivo.
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
>Tieni presente che devi trascinare la **[!UICONTROL Message type]** metriche alle tabelle per suddividere i dati in base ai tipi di consegna, in questo caso le consegne di notifiche push.

Il **Notifica push** Il rapporto fornisce dettagli sulle prestazioni di marketing delle notifiche push in Adobe Campaign. Questo rapporto predefinito consente di comprendere come gli utenti interagiscono con le notifiche push, le app mobili e le consegne.

Per implementare il tracciamento push è necessaria una certa configurazione nell’app mobile. Fai riferimento a questo [pagina](../../administration/using/push-tracking.md) per i passaggi dettagliati.

![](assets/dynamic_report_push.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

Prima tabella **Riepilogo coinvolgimento notifiche push** è suddiviso in tre categorie: per giorno, per app mobile e per consegna. Contiene i dati disponibili per la reattività del destinatario alla consegna:

* **[!UICONTROL Processed/sent]**: numero totale di notifiche push inviate.
* **[!UICONTROL Delivered]**: numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.
* **[!UICONTROL Impressions]**: numero di volte in cui una notifica push è stata recapitata al dispositivo e lasciata intatta nel centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e invia nuovamente tali informazioni al server.
* **[!UICONTROL Unique impressions]**: numero di impression per destinatario.
* **[!UICONTROL Click through rate]**: percentuale di utenti che hanno interagito con la notifica push.
* **[!UICONTROL Open rate]**: percentuale di notifiche push aperte.

![](assets/dynamic_report_push_2.png)

La seconda tabella **Notifica push Clic e aperture** è suddiviso in tre categorie: per giorno, per app mobile e per consegna. Contiene i dati disponibili per il comportamento del destinatario per consegna:

* **[!UICONTROL Impressions]**: totale delle notifiche push visualizzate dai destinatari.
* **[!UICONTROL Unique impressions]**: numero di impression per destinatario.
* **[!UICONTROL Click]**: numero di volte in cui una notifica push è stata recapitata al dispositivo e su cui l’utente ha fatto clic. L’utente desidera visualizzare la notifica, che verrà quindi spostata nel tracciamento push aperto, oppure ignorarla.
* **[!UICONTROL Unique clicks]**: numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio facendo clic sulla notifica o sul pulsante.
* **[!UICONTROL Open]**: numero totale di notifiche push inviate al dispositivo e su cui gli utenti hanno fatto clic, con conseguente apertura dell’app. È simile al Clic push, tranne per il fatto che l’apertura push non viene attivata se la notifica viene chiusa.
* **[!UICONTROL Unique Opens]**: numero di destinatari che hanno aperto la consegna.
