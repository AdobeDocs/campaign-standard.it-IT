---
title: AND-join
description: L'attività AND-join consente di sincronizzare più rami di esecuzione di un flusso di lavoro.
page-status-flag: mai attivato
uuid: 9b54fd4c-9915-400f-a494-74e52c329b8a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 4b55efa2-652e-4493-bfa7-eaee59b383ca
context-tags: andjoin,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# AND-join{#and-join}

## Descrizione {#description}

![](assets/and_join.png)

L' **[!UICONTROL AND-join]** attività consente di sincronizzare più rami di esecuzione di un flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL AND-join]** attività attiva la propria transizione in uscita solo una volta che tutte le transizioni in entrata vengono attivate, in altre parole, una volta completate tutte le attività precedenti.

## Configurazione {#configuration}

1. Rilasciate più attività, ad esempio query, nel flusso di lavoro per creare almeno due rami di esecuzione diversi.
1. Trascinate e rilasciate un' **[!UICONTROL AND-join]** attività nel flusso di lavoro.
1. Connettetelo dopo i due rami diversi che desiderate sincronizzare.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionare il set principale da mantenere nella transizione in uscita. Se non selezionate alcun set, verrà inviata una popolazione casuale dall'attività.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'esempio seguente mostra due rami del flusso di lavoro prima che siano uniti all' **[!UICONTROL AND-join]** attività. L'estrazione dei file può avvenire solo quando sono abilitate le tre transizioni in entrata dell' **[!UICONTROL AND-join]** attività.

![](assets/wkf_and-join_example.png)

