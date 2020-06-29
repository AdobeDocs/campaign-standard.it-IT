---
title: Retargeting di non-openers
description: Questo esempio di utilizzo mostra come riassegnare i non aperture.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 2%

---


# Flusso di lavoro di retargeting che invia una nuova consegna a non-openers{#retargeting-delivery-to-non-openers}

Potete inviare un messaggio e-mail ai clienti e quindi un messaggio SMS a coloro che non hanno aperto il messaggio.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Creazione di un&#39;attività di query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascinate e rilasciate un&#39;attività [Query](../../automating/using/query.md) .
1. Fate doppio clic sull&#39;attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL email]** con l&#39;operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no ]**.
1. Clic **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di una consegna tramite e-mail{#creating-an-email-delivery}

1. Trascinate e rilasciate una consegna [e-](../../automating/using/email-delivery.md) mail dopo ogni segmento.
1. Fate clic sull&#39;attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Simple email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate **[!UICONTROL Add an outbound transition without the population]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Using the Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate l&#39;e-mail con offerte specifiche per ogni posizione.Per ulteriori informazioni, consultate [progettare un&#39;e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Clic **[!UICONTROL Save]**.

## Targeting di non-openers in un&#39;attività di query{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, trascinate e rilasciate un&#39;attività [Wait](../../automating/using/wait.md) .
1. In **[!UICONTROL Duration]**, clicca su ![](assets/duration-icon.png) e seleziona un giorno.
1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascina e rilascia un **[!UICONTROL Query activity]**.
1. Fate doppio clic sull&#39;attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Tracking Logs]** e con l&#39;operatore **[!UICONTROL exists]**.
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, trascinare **[!UICONTROL delivery]** con l&#39;operatore **[!UICONTROL is equal to]** e selezionare la consegna come valore.
1. In **[!UICONTROL Shortcuts]**> **[!UICONTROL Delivery]**, trascinare **[!UICONTROL type]** e selezionare **[!UICONTROL Open]** come valore.
1. Selezionare l&#39;operatore tra le regole come **[!UICONTROL except]**.
1. Clic **[!UICONTROL Confirm]**.

## Creazione di una consegna sms{#creating-a-sms-delivery}

1. Trascinate e rilasciate una consegna sms dopo ogni segmento.
1. Fate clic sull&#39;attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Simple sms]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello sms e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà sms e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del vostro sms, fate clic su **[!UICONTROL Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate i vostri sms con offerte specifiche per ogni posizione.
Per ulteriori informazioni, consultare la sezione [Progettazione di un sms](../../channels/using/creating-an-sms-message.md) .
1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Clic **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Argomenti correlati:**

* [Canale e-mail](../../channels/using/creating-an-email.md)
