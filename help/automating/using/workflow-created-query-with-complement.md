---
title: Creazione di consegne con un complemento
description: Questo caso di utilizzo mostra come creare consegne con un complemento.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,segmentation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Creazione di consegne con un complemento {#deliveries-with-complement}

Potete inviare un messaggio e-mail ai clienti: uno per i clienti creati meno di un anno fa, uno per i clienti creati più di un anno fa.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Creazione di un&#39;attività Query {#create-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascinate e rilasciate un&#39;attività [Query](../../automating/using/query.md) .
1. Fate doppio clic sull&#39;attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL email]** con l&#39;operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Clic **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di un&#39;attività di segmentazione {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia un&#39;attività di [segmentazione](../../automating/using/segmentation.md) e fai doppio clic su di essa.
1. Passa il cursore del mouse sul segmento e fai clic ![](assets/edit_darkgrey-24px.png) per individuare i clienti aggiunti quest&#39;anno nel database.
1. Trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL Created]** con il tipo di filtro **[!UICONTROL Relative]**.
1. Modificate **[!UICONTROL Level of precision]** in **[!UICONTROL Year]** e selezionate **[!UICONTROL This year]**.
1. Fate clic **[!UICONTROL Confirm]** due volte.
1. In **[!UICONTROL Advanced Options]**, selezionate **[!UICONTROL Generate complement]** per creare un segmento con targeting per i destinatari rimanenti.
1. Clic **[!UICONTROL Confirm]**.
1. Clic **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Per osservare la struttura della regola, fare clic su **[!UICONTROL Advanced Mode]**.

## Creazione di una consegna tramite e-mail {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascina e rilascia un&#39;attività di consegna [](../../automating/using/email-delivery.md) e-mail dopo ogni segmento.
1. Fate clic sull&#39;attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Single send email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizza la tua e-mail con offerte specifiche per ogni consegna.
1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Clic **[!UICONTROL Save]**.

Per ulteriori informazioni, consultate [progettare un&#39;e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
