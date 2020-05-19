---
title: Esclusione
description: L'attività Esclusione consente di escludere elementi da una popolazione in base a determinati criteri.
page-status-flag: never-activated
uuid: b79e7f73-37a0-4ec3-ac5a-5449dc1b1f22
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: d5312fcd-43ad-428e-bde9-90f062e9358c
context-tags: exclusion,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Esclusione{#exclusion}

## Descrizione {#description}

![](assets/exclusion.png)

L&#39; **[!UICONTROL Exclusion]** attività consente di escludere elementi da una popolazione in base a determinati criteri.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Exclusion]** attività è utilizzata essenzialmente per realizzare ulteriori filtraggi sulle popolazioni di transizione in entrata.

Un set primario è definito tra le transizioni in entrata. I membri di altre transizioni in entrata sono esclusi dal set primario. La transizione in uscita dell&#39;attività di esclusione contiene solo i membri del set primario che non si sono incontrati nelle altre transizioni in entrata.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Exclusion]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionare le transizioni **[!UICONTROL Primary set]** in entrata. Questo è il set da cui gli elementi sono esclusi. Gli altri set corrispondono agli elementi prima di essere esclusi dal set principale.

   >[!NOTE]
   >
   >Le transizioni in entrata devono contenere lo stesso tipo di popolazione. Ad esempio, se il set principale contiene profili di test, le altre transizioni devono contenere anche profili di test.

1. Se necessario, gestite le [Transizioni](../../automating/using/activity-properties.md) dell&#39;attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

## Esempio {#example}

L&#39;esempio seguente mostra due attività di query configurate per filtrare i profili dal database di Adobe Campaign che hanno tra i 18 e i 27 anni e hanno un indirizzo e-mail non valido. I profili con indirizzi e-mail non validi vengono quindi esclusi dal primo set. Questo consente di inviare un messaggio e-mail, ad esempio.

![](assets/wkf_exclusion_example.png)

