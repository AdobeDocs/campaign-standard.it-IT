---
title: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne con un complemento "'
seo-title: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne con un complemento "'
description: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne con un complemento "'
seo-description: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne con un complemento "'
page-status-flag: never-activated
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: flusso di lavoro, casi di utilizzo, segmentazione
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# Esempio di utilizzo del flusso di lavoro: Creazione di consegne con un complemento {#deliveries-with-complement}

Potete inviare un messaggio e-mail ai clienti: uno per i client creati meno di un anno fa, uno per i client creati più di un anno fa.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** il tipo di flusso di lavoro e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà del flusso di lavoro e fate clic **[!UICONTROL Create]** su.

## Creazione di un'attività query {#create-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascina e rilascia un **[!UICONTROL Query activity]**![](assets/query.png).
1. Fate doppio clic sull'attività.
1. In **[!UICONTROL Shortcuts]**, trascinate **[!UICONTROL Profiles]** e selezionate **[!UICONTROL email]** con l'operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinate **[!UICONTROL Profiles]** e selezionate **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Click **[!UICONTROL Confirm]**.

## Creare un'attività di segmentazione {#create-a-segmentation-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascina un **[!UICONTROL Segmentation]** 'attività e fai doppio clic su di essa.
1. Passa il cursore del mouse sul segmento e fai clic ![](assets/edit_darkgrey-24px.png) sui clienti aggiunti quest'anno nel database.
1. Trascinate **[!UICONTROL Profiles]** e selezionate **[!UICONTROL Created]** il tipo **[!UICONTROL Relative]** di filtro.
1. Modificate **[!UICONTROL Level of precision]** e **[!UICONTROL Year]** selezionate **[!UICONTROL This year]**.
1. Fate clic **[!UICONTROL Confirm]** due volte.
1. In **[!UICONTROL Advanced Options]**, verifica **[!UICONTROL Generate complement]** di creare un segmento con i destinatari rimanenti.
1. Click **[!UICONTROL Confirm]**.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>Per osservare la struttura della regola, fate clic **[!UICONTROL Advanced Mode]** su.

## Creazione di una consegna e-mail {#create-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, trascina e rilascia un'e-mail di consegna dopo ogni segmento.
1. Fate clic sull'attività e ![](assets/edit_darkgrey-24px.png) selezionatela.
1. Selezionate **[!UICONTROL Single send email]** e fate clic **[!UICONTROL Next]** su.
1. Selezionate un modello e-mail e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà e-mail e fate clic **[!UICONTROL Next]** su.
1. Per creare il layout dell'e-mail, fai clic **[!UICONTROL Email Designer]** su.
1. Inserire elementi o selezionare un modello esistente.
1. Personalizzate l'e-mail con offerte specifiche per ogni consegna.
1. Fate clic su **[!UICONTROL Preview]** per controllare il layout.
1. Click **[!UICONTROL Save]**.

Per ulteriori informazioni, fare riferimento [alla progettazione di un messaggio e-mail](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

**Argomenti correlati:**

* [Query](../../automating/using/query.md)
* [Attività di segmentazione](../../automating/using/segmentation.md)
* [Consegna e-mail](../../automating/using/email-delivery.md)
