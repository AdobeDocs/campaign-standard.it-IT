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
ht-degree: 81%

---


# Creazione di una consegna tramite e-mail ogni martedì{#creating-email-every-tuesday}

Puoi inviare un’e-mail ogni martedì a tutti i clienti per informare sulle offerte speciali.

1. In **[!UICONTROL Marketing Activities]**, fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL Workflow]**.
1. Seleziona **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà del flusso di lavoro e fai clic su **[!UICONTROL Create]**.

## Creazione di un’attività Scheduler{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, trascinate e rilasciate un&#39;attività [Scheduler](../../automating/using/scheduler.md) .
1. Fai doppio clic sull’attività.
1. Configura l’esecuzione della consegna.
1. In **[!UICONTROL Execution frequency]**, seleziona **[!UICONTROL Weekly]**.
1. Seleziona un **[!UICONTROL Time]** e una **[!UICONTROL Repetition frequency]** per le consegne.
1. In **[!UICONTROL Days of the week]**, seleziona **[!UICONTROL Tuesday]**.
1. Specifica uno **[!UICONTROL Start]** e un parametro di **[!UICONTROL Expiration]** per il flusso di lavoro.
1. Conferma l’attività e salva il flusso di lavoro.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Per avviare il flusso di lavoro in un determinato **[!UICONTROL Time Zone]**, nella scheda **[!UICONTROL Execution options]**, imposta il fuso orario per la pianificazione nel campo corrispondente. Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

## Creazione di un’attività Query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, to select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. In **[!UICONTROL Shortcuts]** > **[!UICONTROL Profile]**, trascina e rilascia **[!UICONTROL Email]**.
1. Seleziona **[!UICONTROL is not empty]** come operatore.
1. In **[!UICONTROL Shortcuts]** > **[!UICONTROL General]**, aggiungi profili e seleziona **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL No]**.
1. Fai clic su **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di una consegna e-mail{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascina e rilascia un&#39;attività di consegna [tramite](../../automating/using/email-delivery.md) e-mail.
1. Fai clic sull’attività e seleziona ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Seleziona **[!UICONTROL Recurring email]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di e-mail e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’e-mail e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’e-mail, fai clic su **[!UICONTROL Use Email Designer]**.
1. Inserisci elementi o seleziona un modello esistente.
1. Personalizza il messaggio e-mail utilizzando campi e collegamenti.
1. Fai clic su **[!UICONTROL Save]**.

Per ulteriori informazioni, consulta [Progettazione di un’e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Argomenti correlati:**

* [Canale e-mail](../../channels/using/creating-an-email.md)
