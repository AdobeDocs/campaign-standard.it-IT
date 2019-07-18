---
title: Definizione del contenuto dinamico in un'e-mail
seo-title: Definizione del contenuto dinamico in un'e-mail
description: Definizione del contenuto dinamico in un'e-mail
seo-description: Seguite questi passaggi per visualizzare contenuti diversi in un'e-mail in base alle condizioni definite dall'editor di espressioni di Adobe Campaign.
page-status-flag: never-activated
uuid: b 1 c 5013 f -3201-4239-8202-511 a 6902 d 604
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: definizione-condizionale del contenuto
discoiquuid: d 0 d 009 a 5-6022-433 e-acdf -2 b 51 a 243 a 5 c 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining dynamic content in an email{#defining-dynamic-content-in-an-email}

In un'e-mail, potete definire contenuti diversi che verranno visualizzati in modo dinamico ai destinatari in base alle condizioni definite dall'editor di espressioni. Ad esempio, utilizzando la stessa e-mail, puoi fare in modo che ogni profilo riceva un messaggio diverso in base al relativo intervallo di età.

Defining dynamic content is different from [defining visibility conditions](../../designing/using/defining-a-visibility-condition.md).

1. Selezionare un frammento, un componente o un elemento. In questo esempio, selezionate un'immagine.
1. Click the **[!UICONTROL Dynamic content]** icon from the contextual toolbar.

   ![](assets/dynamic_content_2.png)

   The **[!UICONTROL Dynamic content]** section appears in the palette on the left.

   ![](assets/dynamic_content_3.png)

   Per impostazione predefinita, questa sezione contiene due elementi: la variante predefinita e una nuova variante.

   >[!NOTE]
   >
   >Il contenuto deve avere sempre una variante predefinita. Non è possibile eliminarlo.

1. Click the **[!UICONTROL Edit]** button to define the display conditions for the first alternative variant.

   ![](assets/dynamic_content_4.png)

1. Specificare un'etichetta e selezionare i campi da impostare come condizioni. For example, from the **[!UICONTROL General]** node, select the **[!UICONTROL Age]** field

   ![](assets/dynamic_content_5.png)

1. Impostate le condizioni di filtro. Ad esempio, si desidera che venga visualizzato un contenuto diverso per le persone che hanno età compresa tra 18 e 25 anni.

   ![](assets/dynamic_content_6.png)

1. Una volta impostate tutte le condizioni, definite l'ordine di priorità in cui applicare la condizione e salvate le modifiche.

   ![](assets/dynamic_content_7.png)

   I contenuti verranno visualizzati nella palette in ordine di priorità, dall'alto verso il basso. For more on priorities, refer to [this section](../../designing/using/defining-dynamic-content-in-an-email.md#order-of-priority).

1. Caricate una nuova immagine per la variante appena definita.

   ![](assets/dynamic_content_8.png)

   I destinatari di età compresa tra 18 e 25 anni vedranno la nuova immagine.

   ![](assets/dynamic_content_10.png)

1. Click **[!UICONTROL Add a condition]** to add a new content and its linked rule.

   ![](assets/dynamic_content_9.png)

   Ad esempio, potete aggiungere un'immagine diversa da visualizzare a persone di età compresa tra 26 e 35 anni.

1. Procedete in modo simile per qualsiasi altro elemento dell'e-mail che desiderate visualizzare in modo dinamico. Può essere testo, pulsante, frammento, ecc. Salvate le modifiche.

>[!CAUTION]
>
>Dopo aver preparato il messaggio e prima di inviarlo, esegui il test utilizzando una prova. In caso contrario, alcuni errori potrebbero non essere rilevati e l'e-mail potrebbe non essere inviata.

**Argomenti correlati:**

* [Invio di prove](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)
* [Modifica avanzata delle espressioni](../../automating/using/editing-queries.md#about-query-editor)

## Order of priority {#order-of-priority}

Nell'editor di espressioni, quando si definisce un contenuto dinamico, l'ordine di priorità è quello indicato di seguito.

1. You define two different dynamic contents with **two different conditions**, for example:

   **Condizione 1:** il genere del profilo è masculine,

   **Condizione 2:** il profilo è compreso tra 20 e 30 anni.

   ![](assets/delivery_content_61.png)

   Alcuni profili nel database corrispondono alle due condizioni, ma è possibile inviare un solo e-mail con un contenuto dinamico.

1. Occorre quindi definire la priorità per il contenuto dinamico. A condition with an order of priority of **1** (and therefore the corresponding dynamic content) will be sent to a profile even if another condition whose priority order is **2** or **3** is also met by this profile.

   ![](assets/delivery_content_62.png)

Potete definire solo un ordine di priorità per contenuto dinamico.
