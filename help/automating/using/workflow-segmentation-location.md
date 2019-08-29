---
title: '" Esempio di utilizzo del flusso di lavoro: Segmentazione nella posizione "'
seo-title: '" Esempio di utilizzo del flusso di lavoro: Segmentazione nella posizione "'
description: '" Esempio di utilizzo del flusso di lavoro: Segmentazione nella posizione "'
seo-description: '" Esempio di utilizzo del flusso di lavoro: Segmentazione nella posizione "'
page-status-flag: never-activated
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: 'flusso di lavoro, casi di utilizzo, query, segmentazione, consegna '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e77c8a65834009f2f7157d9535ae8e12e59244ff

---


# Esempio di utilizzo del flusso di lavoro: Segmentazione sulla posizione {#segmentation-on-location}

Potete inviare un messaggio e-mail di targeting ai clienti con offerte nei negozi locali.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** il tipo di flusso di lavoro e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà del flusso di lavoro e fate clic **[!UICONTROL Create]** su.

## Selezione dei destinatari mediante e-mail{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascina e rilascia un **[!UICONTROL Query activity]**![](assets/query.png).
1. Fate doppio clic sull'attività.
1. In **[!UICONTROL Shortcuts]**, trascinate **[!UICONTROL Profiles]** e selezionate il campo **[!UICONTROL email]** con l'operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinate **[!UICONTROL Profiles]** e selezionate il campo **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Fate clic **[!UICONTROL Confirm]** due volte.

## Creazione di un'attività di segmentazione{#creating-a-segmentation-activity}

1. Trascina e rilascia un **[!UICONTROL Segmentation]** 'attività e fai doppio clic su di essa.
1. Fate clic sul segmento e quindi aprite la transizione per eseguire il targeting delle persone nella prima città. Qui Boston.
1. Trascinate **[!UICONTROL Location]** e rilasciate **[!UICONTROL City]** con l'operatore **[!UICONTROL equals to]** e il valore **[!UICONTROL Boston]**.
Nota: Per raggiungere tutte le persone entrate a Boston, disattivate l'opzione Maiuscole/minuscole.
1. Click **[!UICONTROL Confirm]**.
1. In **[!UICONTROL List of outbound segments]**, fai clic **[!UICONTROL Add an element]** su di esso ![](assets/edit_darkgrey-24px.png) per creare un segmento di destinazione delle persone nella seconda città. Qui Chicago.
1. Trascinate **[!UICONTROL Location]** e rilasciate **[!UICONTROL City]** con l'operatore **[!UICONTROL equals to]** e inserite **[!UICONTROL Chicago]** il valore.
1. Per raggiungere tutte le persone entrate in Chicago, non considerare il caso in cui deselezionare l'opzione Distinzione tra maiuscole e minuscole.
1. Click **[!UICONTROL Confirm]**.

## Creazione di un'e-mail di consegna{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, trascina e rilascia un **[!UICONTROL Email Delivery]** segmento dopo ogni segmento.
1. Fate clic sull'attività e ![](assets/edit_darkgrey-24px.png) selezionatela.
1. Selezionate **[!UICONTROL Simple email]** e fate clic **[!UICONTROL Next]** su.
1. Selezionate un modello e-mail e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà e-mail e fate clic **[!UICONTROL Next]** su.
1. Per creare il layout dell'e-mail, fai clic **[!UICONTROL Email Designer]** su.
1. Inserire elementi o selezionare un modello esistente.
1. Personalizzate l'e-mail con offerte specifiche per ogni posizione.

Per ulteriori informazioni, fare riferimento [alla progettazione di un messaggio e-mail](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

1. Fate clic su **[!UICONTROL Preview]** per controllare il layout.
1. Click **[!UICONTROL Save]**.

**Argomenti correlati:**

* [Attività query](../../automating/using/query.md)
* [Attività di segmentazione](../../automating/using/segmentation.md)
* [Consegna e-mail](../../automating/using/email-delivery.md)
