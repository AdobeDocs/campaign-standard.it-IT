---
title: Tornate al mittente
seo-title: Tornate al mittente
description: Tornate al mittente
seo-description: Scoprite come ricevere notifiche di un indirizzo errato e escluderle da comunicazioni future.
page-status-flag: never-activated
uuid: 11981 c 2 f -0 b 7 f -4166-9 daa-ec 6 a 6 b 4 d 5367
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: direct-mail
discoiquuid: 5 f 20 ff 3 f -8242-4735-8 c 60-c 57610 edff 52
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Return to sender{#return-to-sender}

Sono supportati gli scambi di file flat con provider di servizi di Direct Mail che includono le informazioni sul mittente. Ciò consente di escludere da comunicazioni future gli indirizzi postali corrispondenti. Questo consente anche di ricevere notifiche di indirizzo errato e di contattare il cliente attraverso altri canali o di incoraggiarlo ad aggiornare l'indirizzo postale.

Ad esempio, un contatto è stato spostato in una nuova posizione e non indica il nuovo indirizzo postale. Il fornitore recupera l'elenco di indirizzi errati e invia queste informazioni ad Adobe Campaign, che elenca automaticamente gli indirizzi errati.

Per utilizzare questa funzionalità, il modello di consegna predefinito per posta diretta include nel contenuto l'ID del registro di consegna. Pertanto, Adobe Campaign sarà in grado di sincronizzare il profilo e i dati di consegna con le informazioni restituite dal fornitore.

![](assets/direct_mail_return_sender_1.png)

An import template is available under **[!UICONTROL Adobe Campaign > Resources > Templates > Import templates > Update Direct Mail quarantines and delivery logs]**. Duplicate questo modello per creare personalizzati. For more on using import templates, refer to [Using import templates](../../automating/using/defining-import-templates.md).

![](assets/direct_mail_return_sender_2.png)

Al termine dell'importazione, Adobe Campaign esegue automaticamente le azioni seguenti:

* Gli indirizzi errati vengono inseriti in blacklist a livello di profilo
* Gli indicatori principali di consegna vengono aggiornati
* I registri di consegna vengono aggiornati

