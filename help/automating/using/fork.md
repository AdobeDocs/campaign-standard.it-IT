---
title: Fork
description: L’attività Fork ti consente di creare transizioni in uscita per avviare più attività contemporaneamente.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: fork,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 1a5e1ecd-b3f1-4dbe-a816-12d27a3bc0f7
TQID: https://experienceleague.adobe.com/1-9VY3TjBBHAb-7bFikis3Ue5eWy5KXKSR4hXxXDLwc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 213
ht-degree: 98%

---

# Fork{#fork}

## Descrizione {#description}

![](assets/fork.png)

L’attività **[!UICONTROL Fork]** ti consente di creare transizioni in uscita per avviare più attività in contemporanea.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Fork]** ti consente di eseguire diverse attività in modo indipendente all’interno dello stesso flusso di lavoro.

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Fork]** nel flusso di lavoro.
1. Connettila alle altre attività che la precedono, come le query.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Specifica il numero di transizioni in uscita attraverso la creazione, l’eliminazione o la duplicazione delle transizioni. Puoi anche attribuire loro un nome e un’etichetta.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

L’esempio seguente mostra un’intersezione di due attività di query che eseguono il targeting dei profili provenienti dal database di Adobe Campaign. Nel caso specifico, si tratta delle donne che vivono a Parigi. L’attività Fork ti consente quindi di utilizzare più attività in contemporanea: una che salva il pubblico per ricordare la popolazione calcolata e un’altra che segmenta la popolazione inviando due e-mail diverse con un contenuto mirato per ciascun segmento. La prima e-mail viene inviata a donne di Parigi di età compresa tra i 18 e i 40 anni; un’altra ha invece come targeting donne di Parigi di età superiore ai 40 anni.

![](assets/wkf_fork_example.png)
