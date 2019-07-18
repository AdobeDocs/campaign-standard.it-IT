---
title: Esclusione
seo-title: Esclusione
description: Esclusione
seo-description: L'attività di esclusione consente di escludere gli elementi di una popolazione in base a determinati criteri.
page-status-flag: never-activated
uuid: b 79 e 7 f 73-37 a 0-4 ec 3-ac 5 a -5449 dc 1 b 1 f 22
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: d 5312 fcd -43 ad -428 e-bde 9-90 f 062 e 9358 c
context-tags: esclusione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Exclusion{#exclusion}

## Description {#description}

![](assets/exclusion.png)

The **[!UICONTROL Exclusion]** activity allows you to exclude elements from one population according to certain criteria.

## Context of use {#context-of-use}

The **[!UICONTROL Exclusion]** activity is used essentially to carry out additional filtering on inbound transition populations.

Un set principale è definito nelle transizioni in entrata. I membri di altre transizioni in entrata sono esclusi dal set principale. La transizione in uscita dell'attività di esclusione contiene solo i membri del set principale che non si sono incontrati nelle altre transizioni in entrata.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Exclusion]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Primary set]** from the inbound transitions. Questo è il set da cui gli elementi sono esclusi. Gli altri set corrispondono agli elementi prima di essere esclusi dal set principale.

   >[!NOTE]
   >
   >Le transizioni in entrata devono contenere lo stesso tipo di popolazione. Ad esempio, se il set principale contiene profili di test, le altre transizioni devono contenere anche profili di prova.

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

L'esempio seguente mostra due attività di query configurate per filtrare i profili dal database Adobe Campaign che hanno compreso tra 18 e 27 anni e che hanno un indirizzo e-mail non valido. I profili con indirizzi e-mail non validi vengono quindi esclusi dal primo set. Questo consente di inviare un messaggio e-mail ad esempio.

![](assets/wkf_exclusion_example.png)

