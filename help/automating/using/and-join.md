---
solution: Campaign Standard
product: campaign
title: AND-join
description: L’attività AND-join ti consente di sincronizzare più rami di esecuzione di un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 98%

---


# AND-join{#and-join}

## Descrizione {#description}

![](assets/and_join.png)

L’attività **[!UICONTROL AND-join]** ti consente di sincronizzare più rami di esecuzione di un flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL AND-join]** attiva solo la relativa transizione in uscita dopo che tutte le transizioni in entrata vengono attivate, in altre parole, dopo che tutte le attività precedenti sono state completate.

## Configurazione {#configuration}

1. Rilascia più attività, ad esempio query, nel flusso di lavoro per creare almeno due rami di esecuzione diversi.
1. Trascina e rilascia un’attività **[!UICONTROL AND-join]** nel flusso di lavoro.
1. Connettila dopo i due rami diversi che desideri sincronizzare.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona il set principale da mantenere nella transizione in uscita. Se non selezioni alcun set, viene inviata una popolazione casuale dall’attività.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

L’esempio seguente mostra due rami del flusso di lavoro prima che vengano uniti all’attività **[!UICONTROL AND-join]**. L’estrazione del file può avvenire solo quando sono abilitate le tre transizioni in entrata dell’attività **[!UICONTROL AND-join]**.

![](assets/wkf_and-join_example.png)

