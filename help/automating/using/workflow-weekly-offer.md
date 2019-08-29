---
title: '" Esempio di utilizzo del flusso di lavoro: Creazione di una consegna settimanale "'
seo-title: '" Esempio di utilizzo del flusso di lavoro: Creazione di una consegna settimanale "'
description: '" Esempio di utilizzo del flusso di lavoro: Creazione di una consegna settimanale "'
seo-description: '" Esempio di utilizzo del flusso di lavoro: Creazione di una consegna settimanale "'
page-status-flag: never-activated
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: 'esecuzione-attività '
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: flusso di lavoro, casi d'uso, query, consegna, pianificazione
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Esempio d'uso Worflow: Creazione di un'e-mail di consegna ogni martedì{#creating-email-every-tuesday}

Potete inviare un messaggio e-mail ogni martedì a tutti i clienti per Offerte speciali.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** il tipo di flusso di lavoro e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà del flusso di lavoro e fate clic **[!UICONTROL Create]** su.

## Creazione di un'attività Pianificatore{#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, trascina e rilascia un **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. Fate doppio clic sull'attività.
1. Configurare l'esecuzione della distribuzione.
1. In **[!UICONTROL Execution frequency]**, seleziona **[!UICONTROL Weekly]**.
1. Selezionate un **[!UICONTROL Time]** 'e-mail **[!UICONTROL Repetition frequency]** per le consegne.
1. In **[!UICONTROL Days of the week]**, seleziona **[!UICONTROL Tuesday]**.
1. Specificate un **[!UICONTROL Start]** parametro e **[!UICONTROL Expiration]** un parametro per il flusso di lavoro.

![](assets/scheduler_properties.png)

>[!NOTE]
>
>Per avviare il flusso di lavoro in una **[!UICONTROL Time Zone]****[!UICONTROL Execution options]** scheda specifica, impostate il fuso orario per il pianificatore nel campo Fuso orario.

1. Confermate l'attività e salvate il flusso di lavoro.

## Creazione di un'attività query{#creating-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, per selezionare i destinatari, trascina un **[!UICONTROL query]** 'attività e fai doppio clic su di essa.
1. In **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL Profile]**, trascina e rilascia **[!UICONTROL Email]**.
1. Selezionare **[!UICONTROL is not empty]** come operatore.
1. In **[!UICONTROL Shortcuts]** &gt; **[!UICONTROL General]**, aggiungete profili e selezionate **[!UICONTROL no longer contact by email]** insieme al valore **[!UICONTROL No]**.
1. Click **[!UICONTROL Confirm]**.

## Creazione di una consegna e-mail{#creating-an-email-delivery}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, trascina e rilascia un **[!UICONTROL Email delivery]**.
1. Fate clic sull'attività e ![](assets/edit_darkgrey-24px.png) selezionatela.
1. Selezionate **[!UICONTROL Recurring email]** e fate clic **[!UICONTROL Next]** su.
1. Selezionate un modello e-mail e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà e-mail e fate clic **[!UICONTROL Next]** su.
1. Per creare il layout dell'e-mail, fai clic **[!UICONTROL Use Email Designer]** su.
1. Inserire elementi o selezionare un modello esistente.
1. Personalizzate l'e-mail utilizzando i campi e i collegamenti.
1. Click **[!UICONTROL Save]**.

Per ulteriori informazioni, fare riferimento [alla progettazione di un messaggio e-mail](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).

**Argomenti correlati:**

* [Attività query](../..//automating/using/query.md)
* [Attività del pianificatore](../..//automating/using/scheduler.md)
* [Consegna e-mail](../..//automating/using/email-delivery.md)
* [Canale e-mail](../..//channels/using/creating-an-email.md)
