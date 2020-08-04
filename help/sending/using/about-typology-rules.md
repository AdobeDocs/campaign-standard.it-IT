---
title: Informazioni su tipologie e regole di tipologia
description: Scopri come funzionano le tipologie e le relative regole all’interno di Adobe Campaign.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: ht
source-git-commit: 396084934a41d103eecd6fe141c700c118000f75
workflow-type: ht
source-wordcount: '190'
ht-degree: 100%

---


# Informazioni su tipologie e regole di tipologia{#about-typology-rules}

Campaign Standard consente di collegare un messaggio a una **tipologia** per verificarne la validità e per controllare se il messaggio soddisfa i criteri di qualità.

Le tipologie sono insiemi di **regole di tipologia** che vengono eseguite durante la fase di analisi dei messaggi. Consentono di assicurarsi che le e-mail contengano sempre alcuni elementi, come un collegamento per l’annullamento dell’abbonamento o una riga dell’oggetto oppure regole di filtro per escludere i gruppi dal target previsto, ad esempio utenti non abbonati, concorrenti o clienti non fidelizzati.

![](assets/typology_messagelink.png)

Le tipologie pronte all’uso e le regole di tipologia sono disponibili all’interno di Campaign Standard. A seconda delle esigenze, puoi anche creare nuove regole e aggiungerle a tipologie nuove o esistenti per eseguire il collegamento ai messaggi.

I passaggi per la creazione e l’applicazione di una tipologia ai messaggi sono i seguenti:

1. Creare le regole di tipologia (consulta [questa sezione](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Creare una tipologia e fare riferimento alle regole create al suo interno (consulta [questa sezione](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configurare la distribuzione in modo da utilizzare la tipologia creata (consulta [questa sezione](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante la preparazione dei messaggi, i profili vengono esclusi quando il criterio è soddisfatto. Per monitorare le esclusioni, puoi controllare i registri.
