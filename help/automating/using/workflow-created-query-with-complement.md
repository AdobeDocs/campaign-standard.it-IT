---
title: Creazione di consegne con un complemento
description: Questo caso d’uso mostra come creare consegne con un complemento.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,segmentation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5cd71e07-f955-4c15-bdfb-14b0daccec1a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 39%

---

# Creazione di consegne con un complemento {#deliveries-with-complement}

Puoi inviare un’e-mail ai clienti: una per i clienti creati meno di un anno fa, una per i clienti creati più di un anno fa.

1. In **[!UICONTROL Marketing Activities]**, fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL Workflow]**.
1. Seleziona **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà del flusso di lavoro e fai clic su **[!UICONTROL Create]**.

## Creare un’attività Query {#create-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia un’attività [Query](../../automating/using/query.md) .
1. Fai doppio clic sull’attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL email]** con l&#39;operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Fai clic su **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creare un’attività di segmentazione {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia un&#39;attività [Segmentation](../../automating/using/segmentation.md) e fai doppio clic su di essa.
1. Passa il puntatore del mouse sul segmento, quindi fai clic su ![](assets/edit_darkgrey-24px.png) per eseguire il targeting dei clienti aggiunti quest&#39;anno nel database.
1. Trascinare e rilasciare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL Created]** con il tipo di filtro **[!UICONTROL Relative]**.
1. Cambia **[!UICONTROL Level of precision]** in **[!UICONTROL Year]** e seleziona **[!UICONTROL This year]**.
1. Fai due volte clic su **[!UICONTROL Confirm]**.
1. In **[!UICONTROL Advanced Options]**, selezionare **[!UICONTROL Generate complement]** per creare un segmento destinato ai destinatari rimanenti.
1. Fai clic su **[!UICONTROL Confirm]**.
1. Fai clic su **[!UICONTROL Save]**.

![](assets/wf-complement-segmentation.png)

>[!NOTE]
>
>Per osservare la struttura della regola, fare clic su **[!UICONTROL Advanced Mode]**.

## Creazione di una consegna e-mail {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascina e rilascia un&#39;attività [Email delivery](../../automating/using/email-delivery.md) dopo ogni segmento.
1. Fai clic sull’attività e seleziona ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Seleziona **[!UICONTROL Single send email]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di e-mail e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’e-mail e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’e-mail, fai clic su **[!UICONTROL Email Designer]**.
1. Inserisci elementi o seleziona un modello esistente.
1. Personalizza il tuo indirizzo e-mail con offerte specifiche per ogni consegna.
1. Seleziona **[!UICONTROL Preview]** per controllare il layout.
1. Fai clic su **[!UICONTROL Save]**.

Per ulteriori informazioni, consulta [Progettazione di un’e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

![](assets/wf-deliveries-with-a-complement.png)
