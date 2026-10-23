---
title: Ritorna al mittente
description: Scopri come ricevere notifiche su un indirizzo errato ed escluderlo da comunicazioni future.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
TQID: 'https://experienceleague.adobe.com/g-0yLI3-qYRfbF-gXuO8AtyCI3Qr5F7an5hqVzaQCE8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: ede6e1ec-9279-415e-b828-a09735018d48
    internal-label: Direct mail
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%
---
# Ritorna al mittente{#return-to-sender}

Sono supportati gli scambi di file sequenziali con i provider di Direct Mail che incorporano le informazioni di ritorno al mittente. Ciò consente di escludere gli indirizzi postali corrispondenti da comunicazioni future. Ciò ti consente anche di ricevere notifiche su un indirizzo errato e di interagire con il cliente attraverso altri canali o di incoraggiarlo ad aggiornare il proprio indirizzo postale.

Ad esempio, un contatto è stato spostato in un nuovo luogo e non ti ha fornito il nuovo indirizzo postale. Il provider recupera l’elenco degli indirizzi errati e invia queste informazioni ad Adobe Campaign, che li inserisce nell&#39;elenco Bloccati automaticamente in base all’.

Affinché questa funzionalità funzioni, il modello di consegna predefinito per la direct mailing include nel contenuto l’ID del registro di consegna. Adobe Campaign sarà quindi in grado di sincronizzare i dati di profilo e di consegna con le informazioni restituite dal provider.

![](assets/direct_mail_return_sender_1.png)

Un modello di importazione è disponibile in **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplica questo modello per crearne uno personalizzato. Per ulteriori informazioni sull&#39;utilizzo dei modelli di importazione, vedere [Utilizzo dei modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Al termine dell’importazione, Adobe Campaign esegue automaticamente le azioni seguenti:

* Gli indirizzi non corretti vengono aggiunti al inserisco nell&#39;elenco Bloccati di a livello di profilo
* Gli indicatori principali di consegna (KPI, Delivery Main Indicators) vengono aggiornati
* I registri di consegna vengono aggiornati
