---
title: Esclusione
description: L’attività Exclusion ti consente di escludere elementi da una popolazione in base a determinati criteri.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: exclusion,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dccb9545-0d7e-4d40-9a8f-2915b4da99a7
TQID: https://experienceleague.adobe.com/46Q9UK-l1t1bBo9PZiasUxF2nqbLs7luEzqOJt7PU1k
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 98%

---

# Esclusione{#exclusion}

## Descrizione {#description}

![](assets/exclusion.png)

L’attività **[!UICONTROL Exclusion]** consente di escludere elementi da una popolazione in base a determinati criteri.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Exclusion]** è utilizzata essenzialmente per eseguire un filtraggio aggiuntivo sulle popolazioni di transizione in entrata.

Un set primario è definito tra le transizioni in entrata. I membri di altre transizioni in entrata sono esclusi dal set primario. La transizione in uscita dell’attività di esclusione contiene solo i membri del set primario che non sono stati incontrati nelle altre transizioni in entrata.

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Exclusion]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona il **[!UICONTROL Primary set]** dalle transizioni in entrata. Questo è il set da cui gli elementi sono esclusi. Gli altri set confrontano gli elementi prima che vengano esclusi dal set primario.

   >[!NOTE]
   >
   >Le transizioni in entrata devono contenere lo stesso tipo di popolazione. Ad esempio, se il set primario contiene profili di test, anche le altre transizioni devono contenere profili di test.

1. Se necessario, gestisci le [Transizioni](../../automating/using/activity-properties.md) dell’attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

L’esempio seguente mostra due attività di query configurate per filtrare dal database di Adobe Campaign i profili che hanno tra i 18 e i 27 anni e dispongono di un indirizzo e-mail non valido. I profili con indirizzi e-mail non validi sono quindi esclusi dal primo set. Ciò consente ad esempio di inviare un messaggio e-mail.

![](assets/wkf_exclusion_example.png)
