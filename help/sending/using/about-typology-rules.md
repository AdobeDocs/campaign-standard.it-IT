---
title: Informazioni sulle tipologie e le regole di tipologia
description: Scopri come funzionano le tipologie e le regole di tipologia in Adobe Campaign.
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
translation-type: tm+mt
source-git-commit: 396084934a41d103eecd6fe141c700c118000f75

---


# Informazioni sulle tipologie e le regole di tipologia{#about-typology-rules}

Campaign Standard consente di collegare un messaggio a una **tipologia**, per verificare se il messaggio è valido e soddisfa i criteri di qualità.

Le tipologie sono insiemi di regole **di** tipologia, che vengono eseguite durante la fase di analisi dei messaggi. Consentono di assicurarsi che le e-mail contengano sempre alcuni elementi (come un collegamento per l’annullamento della sottoscrizione o un oggetto) o regole di filtro per escludere i gruppi dalla destinazione prevista (come utenti non iscritti, concorrenti o clienti non fedeli).

![](assets/typology_messagelink.png)

Tipologie pronte all&#39;uso e regole di tipologia sono disponibili in Campaign Standard. A seconda delle esigenze, puoi anche creare nuove regole e aggiungerle a tipi nuovi o esistenti per il collegamento ai messaggi.

I passaggi per creare e applicare una tipologia ai messaggi sono:

1. Creare regole di tipologia (vedere [questa sezione](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Create una tipologia e fate riferimento alle regole create al suo interno (consultate [questa sezione](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configurate la distribuzione in modo da utilizzare la tipologia creata (consultate [questa sezione](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante la preparazione dei messaggi, i profili sono esclusi quando il criterio è soddisfatto. Potete controllare i registri per monitorare le esclusioni.
