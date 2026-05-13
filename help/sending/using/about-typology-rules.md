---
title: Informazioni su tipologie e regole di tipologia
description: Scopri come funzionano le tipologie e le relative regole all’interno di Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
TQID: https://experienceleague.adobe.com/fFTJTgKfIhII-D6pefx9hqnX3a022odFZS5AAmNK1Ao
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 193
ht-degree: 100%

---

# Informazioni su tipologie e regole di tipologia{#about-typology-rules}

Campaign Standard consente di collegare un messaggio a una **tipologia** per verificarne la validità e per controllare se il messaggio soddisfa i criteri di qualità.

Le tipologie sono insiemi di **regole di tipologia** che vengono eseguite durante la fase di analisi dei messaggi. Consentono di assicurarti che le e-mail contengano sempre alcuni elementi, come  l’oggetto o un collegamento per l’annullamento dell’iscrizione, oppure regole di filtro per escludere alcuni gruppi dal target previsto (ad esempio utenti non iscritti, aziende concorrenti o clientela non fidelizzata).

![](assets/typology_messagelink.png)

Le tipologie pronte all’uso e le regole di tipologia sono disponibili all’interno di Campaign Standard. A seconda delle esigenze, puoi anche creare nuove regole e aggiungerle a tipologie nuove o esistenti per eseguire il collegamento ai messaggi.

I passaggi per la creazione e l’applicazione di una tipologia ai messaggi sono i seguenti:

1. Creare le regole di tipologia (consulta [questa sezione](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Creare una tipologia e fare riferimento alle regole create al suo interno (consulta [questa sezione](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configurare la distribuzione in modo da utilizzare la tipologia creata (consulta [questa sezione](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante la preparazione dei messaggi, i profili vengono esclusi quando il criterio è soddisfatto. Per monitorare le esclusioni, puoi controllare i registri.
