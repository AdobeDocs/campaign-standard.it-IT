---
title: Rendi al mittente
description: Scopri come ricevere notifiche su un indirizzo errato ed escluderlo dalle comunicazioni future.
page-status-flag: mai attivato
uuid: 11981c2f-0b7f-4166-9daa-ec6a6b4d5367
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: direct-mail
discoiquuid: 5f20ff3f-8242-4735-8c60-c57610edff52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Rendi al mittente{#return-to-sender}

Sono supportati gli scambi di file flat con i provider Direct Mail che includono informazioni sul ritorno al mittente. Ciò consente di escludere gli indirizzi postali corrispondenti dalle comunicazioni future. Questo consente anche di ricevere una notifica di indirizzo errato e di contattare il cliente attraverso altri canali o di incoraggiarlo ad aggiornare il suo indirizzo postale.

Ad esempio, un contatto si è spostato in un nuovo luogo e non vi ha fornito il suo nuovo indirizzo postale. Il provider recupera l'elenco degli indirizzi errati e invia queste informazioni ad Adobe Campaign, che elenca automaticamente in blacklist gli indirizzi errati.

Affinché questa funzionalità funzioni, il modello di consegna predefinita per la posta diretta include, nel contenuto, l'ID del registro di consegna. Adobe Campaign sarà quindi in grado di sincronizzare il profilo e i dati di consegna con le informazioni restituite dal fornitore.

![](assets/direct_mail_return_sender_1.png)

Un modello di importazione è disponibile in **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplica questo modello per creare un modello personalizzato. Per ulteriori informazioni sull'uso dei modelli di importazione, vedere [Uso dei modelli](../../automating/using/defining-import-templates.md)di importazione.

![](assets/direct_mail_return_sender_2.png)

Al termine dell'importazione, Adobe Campaign esegue automaticamente le azioni seguenti:

* Gli indirizzi errati vengono inseriti in blacklist a livello di profilo
* Gli indicatori principali di consegna (KPI) vengono aggiornati
* I registri di consegna vengono aggiornati

