---
title: '"Workflow use-case: Creazione di una consegna settimanale"'
description: '"Workflow use-case: Creazione di una consegna settimanale"'
page-status-flag: mai attivato
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: 'attività di esecuzione '
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,consegna,scheduler
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Caso di utilizzo del flusso di lavoro: Creare una consegna tramite e-mail ogni martedì{#creating-email-every-tuesday}

Potete inviare un'e-mail ogni martedì a tutti i clienti per le Offerte Speciali.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

## Creazione di un'attività di Scheduler{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, trascina e rilascia un **[!UICONTROL Scheduler activity]**.
1. Fate doppio clic sull'attività.
1. Configura l'esecuzione della consegna.
1. In **[!UICONTROL Execution frequency]**, selezionate **[!UICONTROL Weekly]**.
1. Selezionare un **[!UICONTROL Time]** e un **[!UICONTROL Repetition frequency]** per le consegne.
1. In **[!UICONTROL Days of the week]**, selezionate **[!UICONTROL Tuesday]**.
1. Specificate un **[!UICONTROL Start]** e un **[!UICONTROL Expiration]** parametro per il flusso di lavoro.
1. Confermate l'attività e salvate il flusso di lavoro.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Per avviare il flusso di lavoro in una determinata posizione, **[!UICONTROL Time Zone]** nella **[!UICONTROL Execution options]** scheda impostare il fuso orario per il pianificatore nel campo Fuso orario.

## Creazione di un'attività Query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, per selezionare i destinatari, trascinate e rilasciate un' **[!UICONTROL query]** attività e fate doppio clic su di essa.
1. In **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL Profile]**, trascinare **[!UICONTROL Email]**.
1. Selezionare **[!UICONTROL is not empty]** come operatore.
1. In **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL General]**, aggiungi i profili e selezionali **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL No]**.
1. Click **[!UICONTROL Confirm]**.

![](assets/wf-complement-query.png)

## Creazione di una consegna tramite e-mail{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, trascina e rilascia un **[!UICONTROL Email delivery]**.
1. Fate clic sull'attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Recurring email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Use Email Designer]**.
1. Inserite elementi o selezionate un modello esistente.
1. Personalizzate l'e-mail utilizzando campi e collegamenti.
1. Click **[!UICONTROL Save]**.

Per ulteriori informazioni, consultate [progettare un'e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).

**Argomenti correlati:**

* [Attività query](../..//automating/using/query.md)
* [Attività di pianificazione](../..//automating/using/scheduler.md)
* [Recapito e-mail](../..//automating/using/email-delivery.md)
* [Canale e-mail](../..//channels/using/creating-an-email.md)
