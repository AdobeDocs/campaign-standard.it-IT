---
title: Modelli per messaggi multilingue
description: Scopri come definire ed eseguire le consegne di e-mail/SMS in più lingue attraverso un'unica distribuzione basata sulla lingua preferita dei clienti segmentati automaticamente. Report sulle prestazioni di ogni distribuzione fino al livello della lingua e dei singoli livelli.
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Modelli per messaggi multilingue {#multilingual-messages-template}

Un modello multilingue è un modello specifico per la gestione dei messaggi multilingue. Questo tipo di modello è disponibile per ****Email** e messaggi **** SMS e può essere utilizzato in modalità standalone, all&#39;interno di un flusso di lavoro o in una consegna periodica.

Nei modelli delle funzioni multilingue, la gestione della lingua è basata sulle varianti. **Ogni variante rappresenta una lingua**. Adobe Campaign Standard è in grado di impostare un massimo di 40 varianti.

Adobe Campaign viene fornito con una lingua predefinita impostata su **EN**. La lingua predefinita può essere modificata in un&#39;altra variante, ma non deve mai essere eliminata.

Durante la creazione del modello, potete aggiungere il numero di varianti corrispondente al numero di lingue necessarie nel messaggio.

Per creare un modello SMS o e-mail, effettuate le seguenti operazioni:

1. Duplica un modello multilingue esistente (SMS o E-mail).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Potete anche modificare un modello standard esistente in un modello multilingue facendo clic sul **[!UICONTROL Initialize content variant]**pulsante nelle proprietà del modello.

1. Modificate le proprietà per personalizzare l’etichetta, il tracciamento, ecc.
1. Modificate il numero di varianti desiderate facendo clic sulla sezione delle varianti. Viene visualizzata la finestra delle varianti

   ![](assets/multi_template_variants.png)

   È possibile aggiungere o rimuovere varianti. Per aggiungere una variante, completare la **[!UICONTROL New content variant]**finestra.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Non eliminare la variante &quot;predefinita&quot;, in quanto è la variante inviata ai profili senza un parametro di lingua preferito completato.

1. Se necessario, personalizzare la variante dell&#39;etichetta e fare clic su **[!UICONTROL Confirm]**.
1. Potete anche aggiungere direttamente il contenuto per ogni variante.

È ora possibile creare un messaggio e-mail o un messaggio SMS basato su questo modello multilingue.

**Argomenti correlati:**

* [Creazione di un messaggio e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)
* [Creazione di profili](../../audiences/using/creating-profiles.md)
