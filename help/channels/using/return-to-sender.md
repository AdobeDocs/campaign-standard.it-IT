---
title: Ritorna al mittente
description: Scopri come ricevere una notifica di un indirizzo errato ed escluderlo dalle comunicazioni future.
audience: channels
content-type: reference
topic-tags: direct-mail
feature: Direct Mail
role: User
level: Intermediate
exl-id: 6783aa68-7fd7-4f53-86bf-853c0fea5899
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---

# Ritorna al mittente{#return-to-sender}

Sono supportati gli scambi di file Flat con provider Direct Mail che incorporano le informazioni Return to Sender. Ciò consente di escludere gli indirizzi postali corrispondenti dalle comunicazioni future. Questo consente anche di ricevere una notifica di indirizzo errato e di interagire con il cliente attraverso altri canali o di incoraggiarlo ad aggiornare il proprio indirizzo postale.

Ad esempio, un contatto si è spostato in un nuovo luogo e non ti ha fornito il loro nuovo indirizzo postale. Il provider recupera l’elenco degli indirizzi errati e invia tali informazioni ad Adobe Campaign che elenco Bloccati automaticamente gli indirizzi errati.

Affinché questa funzionalità funzioni, il modello di consegna predefinito per direct mailing include, nel contenuto, l’ID del registro di consegna. Adobe Campaign sarà quindi in grado di sincronizzare il profilo e i dati di consegna con le informazioni restituite dal provider.

![](assets/direct_mail_return_sender_1.png)

Un modello di importazione è disponibile in **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplica questo modello per crearne uno personalizzato. Per ulteriori informazioni sull’utilizzo dei modelli di importazione, consulta [Utilizzo dei modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

![](assets/direct_mail_return_sender_2.png)

Al termine dell’importazione, Adobe Campaign esegue automaticamente le azioni seguenti:

* Vengono aggiunti indirizzi errati al elenco Bloccati a livello di profilo
* Gli indicatori principali di consegna (KPI) vengono aggiornati
* I registri di consegna vengono aggiornati
