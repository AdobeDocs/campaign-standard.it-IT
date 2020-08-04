---
title: AND-join
description: L’attività AND-join ti consente di sincronizzare più rami di esecuzione di un flusso di lavoro.
page-status-flag: never-activated
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '178'
ht-degree: 100%

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

