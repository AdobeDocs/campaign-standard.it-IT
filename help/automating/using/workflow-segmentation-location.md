---
title: Segmentazione sulla posizione"
description: Questo esempio mostra come eseguire la segmentazione sulla posizione.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---


# Segmentazione sulla posizione {#segmentation-on-location}

Potete inviare un&#39;e-mail di targeting ai clienti con offerte sui loro negozi locali.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Selezione dei destinatari contattabili tramite e-mail{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascinate e rilasciate un&#39;attività [Query](../../automating/using/query.md) ![](assets/query.png).
1. Fate doppio clic sull&#39;attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare il campo **[!UICONTROL email]** con l&#39;operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare il campo **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Fate clic **[!UICONTROL Confirm]** due volte.

![](assets/wf-complement-query.png)

## Creazione di un&#39;attività di segmentazione{#creating-a-segmentation-activity}

1. Trascina e rilascia un&#39;attività di [segmentazione](../../automating/using/segmentation.md) e fai doppio clic su di essa.
1. Fate clic sul segmento e quindi aprite la transizione per eseguire il targeting delle persone nella prima città. Qui a Boston.
1. Trascinare **[!UICONTROL Location]** e selezionare **[!UICONTROL City]** con l&#39;operatore **[!UICONTROL equals to]** e il valore **[!UICONTROL Boston]**.
Nota: Per raggiungere tutte le persone che sono entrate a Boston, senza tenere conto del caso, deselezionare l&#39;opzione con distinzione tra maiuscole e minuscole.
1. Clic **[!UICONTROL Confirm]**.
1. In **[!UICONTROL List of outbound segments]**, fate clic **[!UICONTROL Add an element]** e fate clic su ![](assets/edit_darkgrey-24px.png) per creare un segmento con targeting delle persone nella seconda città. Qui Chicago.
1. Trascinare **[!UICONTROL Location]** e selezionare **[!UICONTROL City]** con l&#39;operatore **[!UICONTROL equals to]** e immettere **[!UICONTROL Chicago]** un valore.
1. Per raggiungere tutte le persone che hanno immesso chicago, senza tenere conto del caso, deselezionare l&#39;opzione sensibile al caso.
1. Clic **[!UICONTROL Confirm]**.

## Creazione di una consegna tramite e-mail{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascina e rilascia un&#39;attività di consegna [](../../automating/using/email-delivery.md) e-mail dopo ogni segmento.
1. Fate clic sull&#39;attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Simple email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate l&#39;e-mail con offerte specifiche per ogni posizione.

   Per ulteriori informazioni, consultate [progettare un&#39;e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Clic **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

