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
TQID: 'https://experienceleague.adobe.com/Z7fXMSiDxpF6LXWMV2aYc71UvOYWlUzyOv8TS6ogS7k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 1%
---
# Rapporto notifiche push{#push-notification-report}

>[!CAUTION]
>
>Tieni presente che devi trascinare e rilasciare le metriche **[!UICONTROL Message type]** nelle tabelle per suddividere i dati in base ai tipi di consegna, in questo caso le consegne di notifiche push.

Il report **Notifica push** fornisce dettagli sulle prestazioni di marketing delle notifiche push in Adobe Campaign. Questo rapporto predefinito consente di comprendere come gli utenti interagiscono con le notifiche push, le app mobili e le consegne.

Per implementare il tracciamento push è necessaria una certa configurazione nell&#39;app mobile. Per i passaggi dettagliati, consulta questa [pagina](../../administration/using/push-tracking.md).

![](assets/dynamic_report_push.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

La prima tabella **Riepilogo coinvolgimento notifiche push** è suddivisa in tre categorie: per giorno, per app mobile e per consegna. Contiene i dati disponibili per la reattività del destinatario alla consegna:

* **[!UICONTROL Processed/sent]**: numero totale di notifiche push inviate.
* **[!UICONTROL Delivered]**: numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.
* **[!UICONTROL Impressions]**: numero di volte in cui una notifica push è stata recapitata al dispositivo e lasciata intatta nel centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e invia nuovamente tali informazioni al server.
* **[!UICONTROL Unique impressions]**: numero di impression per destinatario.
* **[!UICONTROL Click through rate]**: percentuale di utenti che hanno interagito con la notifica push.
* **[!UICONTROL Open rate]**: percentuale di notifiche push aperte.

![](assets/dynamic_report_push_2.png)

La seconda tabella **Clic e aperture per notifiche push** è suddivisa in tre categorie: per giorno, per app mobile e per consegna. Contiene i dati disponibili per il comportamento del destinatario per consegna:

* **[!UICONTROL Impressions]**: totale delle notifiche push visualizzate dai destinatari.
* **[!UICONTROL Unique impressions]**: numero di impression per destinatario.
* **[!UICONTROL Click]**: numero di volte in cui una notifica push è stata recapitata al dispositivo e cliccata dall&#39;utente. L’utente desidera visualizzare la notifica, che verrà quindi spostata nel tracciamento push aperto, oppure ignorarla.
* **[!UICONTROL Unique clicks]**: numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio facendo clic sulla notifica o sul pulsante.
* **[!UICONTROL Open]**: numero totale di notifiche push recapitate al dispositivo e su cui gli utenti hanno fatto clic, aprendo in tal modo l&#39;app. È simile al Clic push, tranne per il fatto che l’apertura push non viene attivata se la notifica viene chiusa.
* **[!UICONTROL Unique Opens]**: numero di destinatari che hanno aperto la consegna.
