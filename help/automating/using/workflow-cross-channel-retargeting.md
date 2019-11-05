---
title: '"Workflow use-case: Retargeting non-openers"'
description: '"Workflow use-case: Retargeting non-openers"'
page-status-flag: mai attivato
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'workflow,use-case,query,attesa,consegna '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caso di utilizzo del flusso di lavoro: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers{#retargeting-delivery-to-non-openers}

Potete inviare un messaggio e-mail ai clienti e quindi un messaggio SMS a coloro che non hanno aperto il messaggio.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Creazione di un'attività di query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascinate e rilasciate una **[!UICONTROL Query activity]**![](assets/query.png).
1. Fate doppio clic sull'attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL email]** con l'operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no ]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di una consegna tramite e-mail{#creating-an-email-delivery}

1. Trascinate e rilasciate un segmento **[!UICONTROL Email delivery]** dopo ogni segmento.
1. Fate clic sull'attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Simple email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate **[!UICONTROL Add an outbound transition without the population]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Using the Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate l'e-mail con offerte specifiche per ogni posizione.Per ulteriori informazioni, consultate [progettare un'e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Click **[!UICONTROL Save]**.

## Targeting di non-openers in un'attività di query{#targeting-non-openers-in-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, trascinate e rilasciate una **[!UICONTROL Wait activity]**![](assets/wait.png).
1. In **[!UICONTROL Duration]**, clicca su ![](assets/duration-icon.png) e seleziona un giorno.
1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascinate e rilasciate una **[!UICONTROL Query activity]**![](assets/query.png).
1. Fate doppio clic sull'attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Tracking Logs]** e con l'operatore **[!UICONTROL exists]**.
1. In **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, trascinare **[!UICONTROL delivery]** con l'operatore **[!UICONTROL is equal to]** e selezionare la consegna come valore.
1. In **[!UICONTROL Shortcuts]**&gt; **[!UICONTROL Delivery]**, trascinare **[!UICONTROL type]** e selezionare **[!UICONTROL Open]** come valore.
1. Selezionare l'operatore tra le regole come **[!UICONTROL except]**.
1. Click **[!UICONTROL Confirm]**.

## Creazione di una consegna sms{#creating-a-sms-delivery}

1. Trascinate e rilasciate una consegna sms dopo ogni segmento.
1. Fate clic sull'attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Simple sms]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello sms e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà sms e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del vostro sms, fate clic su **[!UICONTROL Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate i vostri sms con offerte specifiche per ogni posizione.
Per ulteriori informazioni, vedere [Progettazione di un sms](../../channels/using/creating-an-sms-message.md).
1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Click **[!UICONTROL Save]**.

![](assets/wf-retargeting-non-openers.png)

**Argomenti correlati:**

* [Query](../../automating/using/query.md)
* [Consegna SMS](../../automating/using/sms-delivery.md)
* [Recapito e-mail](../../automating/using/email-delivery.md)
* [Canale e-mail](../../channels/using/creating-an-email.md)
