---
title: Foratura
seo-title: Foratura
description: Foratura
seo-description: L'attività Fork consente di creare transizioni in uscita per avviare diverse attività contemporaneamente.
page-status-flag: never-activated
uuid: e 4 eaf 69 b -84 ee -4 f 79-8 b 80-99284697 cd 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: f 8 ffe 7 af-e 18 c -4599-8 fd 0-fcd 192565323
context-tags: fork, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Fork{#fork}

## Description {#description}

![](assets/fork.png)

The **[!UICONTROL Fork]** activity allows you to create outbound transitions to start several activities at the same time.

## Context of use {#context-of-use}

The **[!UICONTROL Fork]** activity allows you to carry out several different activities independently within the same workflow.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Fork]** activity into your workflow.
1. Connettetevi alle altre attività che vengono prima di essa, come query.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specificare il numero di transizioni in uscita mediante la creazione, l'eliminazione o la duplicazione. Potete anche attribuire un nome e un'etichetta.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

L'esempio seguente mostra un'intersezione di due attività di query che interessano profili dal database Adobe Campaign, in questo caso donne che risiedono a Parigi. L'attività della foratura consente di utilizzare più attività contemporaneamente: uno che salva il pubblico in modo da ricordare la popolazione calcolata e un altro che segmenta la popolazione per inviare due e-mail con contenuto mirato per ogni segmento. Il primo e-mail viene inviato alle donne bianche età tra 18 e 40 e un altro targeting delle donne parsimonie età superiore al 40.

![](assets/wkf_fork_example.png)

