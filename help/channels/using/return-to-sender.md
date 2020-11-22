---
solution: Campaign Standard
product: campaign
title: Rendi al mittente
description: Scopri come ricevere notifiche su un indirizzo errato ed escluderlo dalle comunicazioni future.
audience: channels
content-type: reference
topic-tags: direct-mail
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Rendi al mittente{#return-to-sender}

Sono supportati gli scambi di file flat con i provider Direct Mail che includono informazioni sul ritorno al mittente. Ciò consente di escludere gli indirizzi postali corrispondenti dalle comunicazioni future. Questo consente anche di ricevere una notifica di indirizzo errato e di interagire con il cliente attraverso altri canali o di incoraggiarlo ad aggiornare il suo indirizzo postale.

Ad esempio, un contatto si è spostato in un nuovo luogo e non vi ha fornito il suo nuovo indirizzo postale. Il provider recupera l&#39;elenco degli indirizzi errati e invia queste informazioni a  Adobe Campaign, che elenco Bloccati automaticamente gli indirizzi errati.

Affinché questa funzionalità funzioni, il modello di consegna predefinita per la posta diretta include, nel contenuto, l&#39;ID del registro di consegna. Pertanto,  Adobe Campaign sarà in grado di sincronizzare il profilo e i dati di consegna con le informazioni restituite dal fornitore.

![](assets/direct_mail_return_sender_1.png)

Un modello di importazione è disponibile in **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplica questo modello per creare un modello personalizzato. Per ulteriori informazioni sull&#39;utilizzo dei modelli di importazione, vedere [Uso dei modelli](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)di importazione.

![](assets/direct_mail_return_sender_2.png)

Al termine dell’importazione,  Adobe Campaign esegue automaticamente le azioni seguenti:

* Gli indirizzi errati vengono aggiunti al elenco Bloccati a livello di profilo
* Gli indicatori principali di consegna (KPI) vengono aggiornati
* I registri di consegna vengono aggiornati
