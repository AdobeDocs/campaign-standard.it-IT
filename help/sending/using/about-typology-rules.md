---
solution: Campaign Standard
product: campaign
title: Informazioni su tipologie e regole di tipologia
description: Scopri come funzionano le tipologie e le relative regole all’interno di Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Regole di tipologia
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '192'
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
