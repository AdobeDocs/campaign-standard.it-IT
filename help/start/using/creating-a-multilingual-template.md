---
title: Creazione di un modello multilingue
seo-title: Creazione di un modello multilingue
description: Creazione di un modello multilingue
seo-description: Scopri come definire ed eseguire le consegne e-mail/SMS in più lingue tramite una singola distribuzione basata sulla lingua preferita dei clienti specifici. Segnala le prestazioni di ogni distribuzione fino alla lingua e ai singoli livelli.
page-status-flag: never-activated
uuid: 7 a 2 cd 5 f 7-c 0 fc -4825-a 770-a 62816 c 66 b 3 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: riferimento
topic-tags: gestione dei modelli
discoiquuid: 064 c 5 c 4 a-f 579-4 bab-adf 3-51 c 92 eb 4518 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a multilingual template{#creating-a-multilingual-template}

Un modello multilingue è un modello specifico per gestire messaggi in più lingue.

This kind of template is available for **Email and SMS messages** and useable in standalone mode, within a workflow or in a recurring delivery.

Nei modelli delle funzioni multilingue, la gestione delle lingue si basa su varianti. **Ogni variante rappresenta una lingua.**

Adobe Campaign Standard è in grado di impostare un massimo di 40 varianti.

Adobe Campaign viene fornito con una lingua predefinita impostata su IT. La lingua predefinita può essere modificata in un'altra variante, ma non deve mai essere eliminata.

Durante la creazione dei modelli, è possibile aggiungere il numero di varianti corrispondenti al numero di lingue necessarie nel messaggio.

Per eseguire la creazione di un modello SMS o e-mail, attenetevi alla procedura seguente:

1. Duplica un modello multilingue esistente (SMS o E-mail).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >You can also modify an existing standard template in a multilingual template by clicking on the **[!UICONTROL Initialize content variant]** button in the template properties.

1. Modifica le proprietà per personalizzare etichetta, tracciamento ecc.
1. Modificare il numero di varianti desiderato facendo clic sulla sezione varianti. La finestra variants viene visualizzata

   ![](assets/multi_template_variants.png)

   È possibile aggiungere o rimuovere varianti. To add a variant, complete the **[!UICONTROL New content variant]** window.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Non eliminare la variante «predefinita» poiché è la variante inviata ai profili senza un parametro lingua preferito completato.

1. Se necessario, personalizzate la variante dell'etichetta e fate clic su Conferma.
1. È inoltre possibile aggiungere direttamente il contenuto per ogni variante.

Ora sei pronto per creare un messaggio e-mail o un messaggio SMS basato su questo modello multilingue.

**Argomenti correlati:**

* [Creazione di un'e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)
* [Creazione di profili](../../audiences/using/creating-profiles.md)

