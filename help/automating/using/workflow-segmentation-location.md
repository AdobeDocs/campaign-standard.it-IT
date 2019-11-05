---
title: '"Workflow use-case: Segmentazione sulla posizione"'
description: '"Workflow use-case: Segmentazione sulla posizione"'
page-status-flag: mai attivato
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: 'workflow,use-case,query,segmentazione,consegna '
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caso di utilizzo del flusso di lavoro: Segmentazione sulla posizione {#segmentation-on-location}

Potete inviare un'e-mail di targeting ai clienti con offerte sui loro negozi locali.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Selezione dei destinatari contattabili tramite e-mail{#selecting-recipients-contactable-via-email}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascinate e rilasciate una **[!UICONTROL Query activity]**![](assets/query.png).
1. Fate doppio clic sull'attività.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare il campo **[!UICONTROL email]** con l'operatore **[!UICONTROL is not empty]**.
1. In **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profiles]** e selezionare il campo **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.
1. Fate clic **[!UICONTROL Confirm]** due volte.

![](assets/wf-complement-query.png)

## Creazione di un'attività di segmentazione{#creating-a-segmentation-activity}

1. Trascinate e rilasciate un' **[!UICONTROL Segmentation]** attività e fate doppio clic su di essa.
1. Fate clic sul segmento e quindi aprite la transizione per eseguire il targeting delle persone nella prima città. Qui Boston.
1. Trascinare **[!UICONTROL Location]** e selezionare **[!UICONTROL City]** con l'operatore **[!UICONTROL equals to]** e il valore **[!UICONTROL Boston]**.
Nota: Per raggiungere tutte le persone che sono entrate a Boston, senza tenere conto del caso, deselezionare l'opzione sensibile al caso.
1. Click **[!UICONTROL Confirm]**.
1. In **[!UICONTROL List of outbound segments]**, fate clic **[!UICONTROL Add an element]** e fate clic su ![](assets/edit_darkgrey-24px.png) per creare un segmento con targeting delle persone nella seconda città. Qui Chicago.
1. Trascinare **[!UICONTROL Location]** e selezionare **[!UICONTROL City]** con l'operatore **[!UICONTROL equals to]** e immettere **[!UICONTROL Chicago]** un valore.
1. Per raggiungere tutte le persone che hanno immesso chicago, senza tenere conto del caso, deselezionare l'opzione sensibile al caso.
1. Click **[!UICONTROL Confirm]**.

## Creazione di una consegna tramite e-mail{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, trascina e rilascia un **[!UICONTROL Email Delivery]** segmento dopo ogni segmento.
1. Fate clic sull'attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Simple email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate l'e-mail con offerte specifiche per ogni posizione.

Per ulteriori informazioni, consultate [progettare un'e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

1. Fate clic **[!UICONTROL Preview]** per controllare il layout.
1. Click **[!UICONTROL Save]**.

![](assets/wf-segmentation-location.png)

**Argomenti correlati:**

* [Attività query](../../automating/using/query.md)
* [Attività di segmentazione](../../automating/using/segmentation.md)
* [Recapito e-mail](../../automating/using/email-delivery.md)
