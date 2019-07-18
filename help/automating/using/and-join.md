---
title: AND-join
seo-title: AND-join
description: AND-join
seo-description: L'attività di partecipazione AND consente di sincronizzare più rami di esecuzione di un flusso di lavoro.
page-status-flag: never-activated
uuid: 9 b 54 fd 4 c -9915-400 f-a 494-74 e 52 c 329 b 8 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 4 b 55 efa 2-652 e -4493-bfa 7-eaee 59 b 383 ca
context-tags: andjoin, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# AND-join{#and-join}

## Description {#description}

![](assets/and_join.png)

The **[!UICONTROL AND-join]** activity allows you to synchronize multiple execution branches of a workflow.

## Context of use {#context-of-use}

The **[!UICONTROL AND-join]** activity only triggers its outbound transition once all the inbound transitions are activated, in other words, once all of the preceding activities have finished.

## Configuration {#configuration}

1. Rilascia più attività, come query nel flusso di lavoro, per formare almeno due rami di esecuzione diversi.
1. Drag and drop an **[!UICONTROL AND-join]** activity into your workflow.
1. Collegatela dopo i due diversi rami che desiderate sincronizzare.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Selezionate il set principale da mantenere nella transizione in uscita. Se non selezionate alcun set, viene inviata una popolazione casuale dall'attività.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

The following example shows two workflow branches before they are joined with the **[!UICONTROL AND-join]** activity. File extraction can only take place when the three inbound transitions of the **[!UICONTROL AND-join]** activity are enabled.

![](assets/wkf_and-join_example.png)

