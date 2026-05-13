---
title: AND-join
description: L’attività AND-join ti consente di sincronizzare più rami di esecuzione di un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: andjoin,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b03c6df3-0104-4900-9468-46824d62e0a6
TQID: https://experienceleague.adobe.com/ydaYzPE9SwLuC-d4nVSaFgLLp-R0Kuceq7hUI89aN1Y
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 181
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
