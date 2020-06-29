---
title: Creazione di una consegna settimanale
description: Questo caso di utilizzo mostra come creare una consegna settimanale.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,delivery,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 3%

---


# Creazione di una consegna tramite e-mail ogni martedì{#creating-email-every-tuesday}

Potete inviare un&#39;e-mail ogni martedì a tutti i clienti per le Offerte Speciali.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Creazione di un&#39;attività di Scheduler{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, trascinate e rilasciate un&#39;attività [Scheduler](../../automating/using/scheduler.md) .
1. Fate doppio clic sull&#39;attività.
1. Configura l&#39;esecuzione della consegna.
1. In **[!UICONTROL Execution frequency]**, selezionate **[!UICONTROL Weekly]**.
1. Selezionate un **[!UICONTROL Time]** e un **[!UICONTROL Repetition frequency]** nome per le consegne.
1. In **[!UICONTROL Days of the week]**, selezionate **[!UICONTROL Tuesday]**.
1. Specificate un **[!UICONTROL Start]** e un **[!UICONTROL Expiration]** parametro per il flusso di lavoro.
1. Confermate l&#39;attività e salvate il flusso di lavoro.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Per avviare il flusso di lavoro in una determinata posizione, **[!UICONTROL Time Zone]** nella **[!UICONTROL Execution options]** scheda impostare il fuso orario per il pianificatore nel campo Fuso orario. Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedere [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

## Creazione di un&#39;attività Query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, per selezionare i destinatari, trascinate e rilasciate un&#39;attività [Query](../../automating/using/query.md) e fate doppio clic su di essa.
1. In **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**, trascinare **[!UICONTROL Email]**.
1. Selezionare **[!UICONTROL is not empty]** come operatore.
1. In **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**, aggiungi i profili e selezionali **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL No]**.
1. Clic **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di una consegna tramite e-mail{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascina e rilascia un&#39;attività di consegna [tramite](../../automating/using/email-delivery.md) e-mail.
1. Fate clic sull&#39;attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Recurring email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Use Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate l&#39;e-mail utilizzando campi e collegamenti.
1. Clic **[!UICONTROL Save]**.

Per ulteriori informazioni, consultate [progettare un&#39;e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Argomenti correlati:**

* [Canale e-mail](../../channels/using/creating-an-email.md)
