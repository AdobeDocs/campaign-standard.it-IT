---
title: Fork
description: L'attività Fork consente di creare transizioni in uscita per avviare più attività contemporaneamente.
page-status-flag: mai attivato
uuid: e4eaf69b-84ee-4f79-8b80-99284697cd2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: f8ffe7af-e18c-4599-8fd0-fcd192565323
context-tags: fork,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Fork{#fork}

## Descrizione {#description}

![](assets/fork.png)

L' **[!UICONTROL Fork]** attività consente di creare transizioni in uscita per avviare più attività contemporaneamente.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Fork]** attività consente di eseguire diverse attività indipendentemente all'interno dello stesso flusso di lavoro.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Fork]** attività nel flusso di lavoro.
1. Connettetelo alle altre attività che vengono prima di esso, come le query.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Specificate il numero di transizioni in uscita creandole, eliminandole o duplicandole. Potete anche attribuire loro un nome e un'etichetta.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'esempio seguente mostra un'intersezione di due attività di query destinate ai profili provenienti dal database Adobe Campaign, in questo caso, alle donne che vivono a Parigi. L'attività di forchetta consente quindi di utilizzare più attività contemporaneamente: uno che salva l'audience per ricordare la popolazione calcolata e l'altro che segmenta la popolazione inviando due e-mail diverse con un contenuto mirato per ciascun segmento. La prima e-mail viene inviata alle donne parigine di età compresa tra i 18 e i 40 anni e alle altre donne parigine di età superiore ai 40 anni.

![](assets/wkf_fork_example.png)

