---
title: Selezione di un’audience in un messaggio
description: '"Procedura dettagliata per scegliere il pubblico di un messaggio e-mail: popolazione target principale e profili di test."'
page-status-flag: mai attivato
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: management-audience
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,procedura guidata;consegna,pubblico,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Selezione di un’audience in un messaggio{#selecting-an-audience-in-a-message}

Adobe Campaign consente di configurare diversi tipi di profilo all'interno del pubblico di un messaggio.

È possibile definire il pubblico al momento della creazione del messaggio tramite la procedura guidata di creazione o dal dashboard dei messaggi, se il messaggio è già stato creato.

>[!NOTE]
>
>Se l'audience è stata creata all'interno di un flusso di lavoro e arricchita di dati aggiuntivi, non sarà possibile utilizzare questi dati per personalizzare una distribuzione autonoma. Possono essere utilizzati solo da una consegna eseguita in un flusso di lavoro.

1. Dal dashboard, andate al blocco del pubblico per iniziare.

   ![](assets/delivery_audience_definition_1.png)

   Viene visualizzata la schermata che consente di definire le audience. Sono disponibili due schede che consentono di definire separatamente ogni tipo di pubblico a cui verrà inviato il messaggio:

   * Target
   * Profili di prova
   ![](assets/delivery_audience_definition_2.png)

1. Definite il principale **[!UICONTROL Target]** del messaggio e-mail. Si tratta del pubblico di destinazione regolare del messaggio e-mail.

   La destinazione è definita nella **[!UICONTROL Target]** scheda ed è composta da profili identificati provenienti dal database.

   È possibile stabilire la destinazione principale utilizzando le funzionalità dell'editor [](../../automating/using/editing-queries.md#creating-queries) query.

   In questa scheda, la **[!UICONTROL Shortcuts]** palette contiene solo i filtri predefiniti e le audience definite nei profili identificati. La **[!UICONTROL Explorer]** scheda consente di accedere a configurazioni aggiuntive.

   Potete quindi riutilizzare e combinare le audience esistenti, applicare ulteriori filtri, ecc.

1. Definite il tipo di **[!UICONTROL Test profiles]** e-mail da utilizzare. I profili di test riceveranno le prove che potete inviare prima di testare l'e-mail prima di inviarla alla destinazione principale.

   Per ulteriori informazioni sulla configurazione dei profili di test, consultare la sezione Profili [di](../../sending/using/managing-test-profiles-and-sending-proofs.md) test.

Il blocco audience viene quindi aggiornato e mostra che sono stati selezionati un profilo target e di test per l'e-mail in questione.

![](assets/delivery_audience_definition_3.png)

