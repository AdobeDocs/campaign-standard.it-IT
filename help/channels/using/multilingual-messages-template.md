---
title: Modelli per messaggi multilingue
description: Scopri come definire ed eseguire le consegne e-mail/SMS multilingue attraverso un’unica consegna basata sulla lingua preferita dei clienti segmentati automaticamente. Rapporto sulle prestazioni di ogni consegna fino al livello della lingua e dei singoli livelli.
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
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 100%

---


# Modelli per messaggi multilingue {#multilingual-messages-template}

Un modello multilingue è un modello specifico per gestire messaggi multilingue. Questo tipo di modello è disponibile per messaggi **E-mail** e **SMS** ed è utilizzabile in modalità autonoma, all’interno di un flusso di lavoro o in una consegna ricorrente.

Nei modelli delle funzioni multilingue, la gestione della lingua si basa su varianti. **Ogni variante rappresenta una lingua**. Adobe Campaign Standard è in grado di impostare un massimo di 40 varianti.

Adobe Campaign viene fornito con una lingua predefinita impostata su **EN**. Puoi modificare la lingua predefinita con un’altra variante ma non dovresti mai eliminarla.

Durante la creazione del modello, nel messaggio puoi aggiungere il numero di varianti corrispondente al numero di lingue necessarie.

Per creare un modello SMS o e-mail, segui questi passaggi:

1. Duplica un modello multilingue esistente (SMS o e-mail).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Puoi anche modificare un modello standard esistente in uno multilingue facendo clic sul pulsante **[!UICONTROL Initialize content variant]** nelle proprietà del modello.

1. Modifica le proprietà per personalizzare l’etichetta, il tracciamento, ecc.

1. Modifica il numero di varianti desiderate facendo clic sulla sezione delle varianti. Viene visualizzata la finestra delle varianti.

   ![](assets/multi_template_variants.png)

   Puoi aggiungere o rimuovere varianti. Per aggiungere una variante, compila la finestra **[!UICONTROL New content variant]**.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Non eliminare la variante &quot;predefinita&quot;, in quanto si tratta della variante inviata ai profili senza un parametro di lingua preferito completato.

1. Se necessario, personalizza la variante dell’etichetta e fai clic su **[!UICONTROL Confirm]**.

1. Puoi anche aggiungere direttamente il contenuto per ogni variante.

Ora puoi creare un messaggio e-mail o SMS basato su questo modello multilingue.

**Argomenti correlati:**

* [Creazione di un messaggio e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)
* [Creazione di profili](../../audiences/using/creating-profiles.md)
