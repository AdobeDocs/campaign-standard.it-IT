---
title: Retargeting di non-aperti
description: Questo caso d’uso mostra come effettuare il retargeting dei non-opener.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query,wait,delivery
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cba4e5c6-8acd-47a1-824e-14415e90d451
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 37%

---

# Flusso di lavoro di retargeting per l’invio di una nuova consegna a non-opener{#retargeting-delivery-to-non-openers}

Puoi inviare un’e-mail ai clienti e quindi un sms a coloro che non hanno aperto l’e-mail.

1. In **[!UICONTROL Marketing Activities]**, fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL Workflow]**.
1. Seleziona **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fai clic su **[!UICONTROL Next]**.
1. Inserisci le proprietà del flusso di lavoro e fai clic su **[!UICONTROL Create]**.

## Creazione di un’attività di query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia un’attività [Query](../../automating/using/query.md) .
1. Fai doppio clic sull’attività.
1. In entrata **[!UICONTROL Shortcuts]**, trascinare e rilasciare **[!UICONTROL Profiles]** e seleziona **[!UICONTROL email]** con l’operatore **[!UICONTROL is not empty]**.
1. In entrata **[!UICONTROL Shortcuts]**, trascinare e rilasciare **[!UICONTROL Profiles]** e seleziona **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Fai clic su **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di una consegna e-mail{#creating-an-email-delivery}

1. Trascina e rilascia una [Consegna e-mail](../../automating/using/email-delivery.md) dopo ogni segmento.
1. Fai clic sull’attività e seleziona ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Seleziona **[!UICONTROL Simple email]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona **[!UICONTROL Add an outbound transition without the population]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di e-mail e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’e-mail e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’e-mail, fai clic su **[!UICONTROL Using the Email Designer]**.
1. Inserisci elementi o seleziona un modello esistente.
1. Personalizza l’e-mail con le offerte specifiche per ogni posizione.Per ulteriori informazioni, consulta [progettazione di un’e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Seleziona **[!UICONTROL Preview]** per controllare il layout.
1. Fai clic su **[!UICONTROL Save]**.

## Targeting di non-opener in un’attività di query{#targeting-non-openers-in-a-query-activity}

1. In entrata **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, trascina e rilascia una [Wait](../../automating/using/wait.md) attività.
1. In entrata **[!UICONTROL Duration]**, fai clic su ![](assets/duration-icon.png) e selezionare un giorno.
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia una **[!UICONTROL Query activity]**.
1. Fai doppio clic sull’attività.
1. In entrata **[!UICONTROL Shortcuts]**, trascinare e rilasciare **[!UICONTROL Tracking Logs]** e con l’operatore **[!UICONTROL exists]**.
1. In entrata **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, trascinare e rilasciare **[!UICONTROL delivery]** con l’operatore **[!UICONTROL is equal to]** e seleziona la consegna come valore.
1. In entrata **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, trascinare e rilasciare **[!UICONTROL type]** e verifica **[!UICONTROL Open]** come valore.
1. Seleziona l’operatore tra le regole come **[!UICONTROL except]**.
1. Fai clic su **[!UICONTROL Confirm]**.

## Creazione di una consegna sms{#creating-a-sms-delivery}

1. Trascina e rilascia una consegna sms dopo ogni segmento.
1. Fai clic sull’attività e seleziona ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Seleziona **[!UICONTROL Simple sms]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di SMS e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’sms e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’sms, fai clic su **[!UICONTROL Email Designer]**.
1. Inserisci elementi o seleziona un modello esistente.
1. Personalizza l’sms con offerte specifiche per ogni posizione.
Per ulteriori informazioni, consulta [Progettazione di un sms](../../channels/using/creating-an-sms-message.md) sezione.
1. Seleziona **[!UICONTROL Preview]** per controllare il layout.
1. Fai clic su **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Argomenti correlati:**

* [Canale e-mail](../../channels/using/creating-an-email.md)
