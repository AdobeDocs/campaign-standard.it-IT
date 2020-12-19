---
solution: Campaign Standard
product: campaign
title: Creazione di consegne con un complemento
description: Questo caso di utilizzo mostra come creare consegne con un complemento.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 41%

---


# Creazione di consegne con un complemento {#deliveries-with-complement}

Potete inviare un messaggio e-mail ai clienti: uno per i clienti creati meno di un anno fa, uno per i clienti creati più di un anno fa.

1. In **[!UICONTROL Marketing Activities]**, fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL Workflow]**.
1. Seleziona **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà del flusso di lavoro e fai clic su **[!UICONTROL Create]**.

## Creazione di un&#39;attività Query {#create-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia un’attività [Query](../../automating/using/query.md) .
1. Fai doppio clic sull’attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL email]** con l&#39;operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Fai clic su **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creare un&#39;attività di segmentazione {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascinare un&#39;attività [Segmentazione](../../automating/using/segmentation.md) e fare doppio clic su di essa.
1. Passate il puntatore del mouse sul segmento, quindi fate clic su ![](assets/edit_darkgrey-24px.png) per eseguire il targeting dei clienti aggiunti quest&#39;anno nel database.
1. Trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL Created]** con il tipo di filtro **[!UICONTROL Relative]**.
1. Modificate **[!UICONTROL Level of precision]** in **[!UICONTROL Year]** e selezionate **[!UICONTROL This year]**.
1. Fai due volte clic su **[!UICONTROL Confirm]**.
1. In **[!UICONTROL Advanced Options]**, selezionare **[!UICONTROL Generate complement]** per creare un segmento per i destinatari rimanenti.
1. Fai clic su **[!UICONTROL Confirm]**.
1. Fai clic su **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Per osservare la struttura della regola, fare clic su **[!UICONTROL Advanced Mode]**.

## Creazione di una consegna e-mail {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascinare e rilasciare un&#39;attività [Email delivery](../../automating/using/email-delivery.md) dopo ogni segmento.
1. Fai clic sull’attività e seleziona ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Seleziona **[!UICONTROL Single send email]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di e-mail e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’e-mail e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’e-mail, fai clic su **[!UICONTROL Email Designer]**.
1. Inserisci elementi o seleziona un modello esistente.
1. Personalizza la tua e-mail con offerte specifiche per ogni consegna.
1. Seleziona **[!UICONTROL Preview]** per controllare il layout.
1. Fai clic su **[!UICONTROL Save]**.

Per ulteriori informazioni, consulta [Progettazione di un’e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
