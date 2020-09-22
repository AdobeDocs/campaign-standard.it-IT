---
title: Selezione di un pubblico in un messaggio
description: '"Procedura dettagliata per scegliere i tipi di pubblico di un messaggio e-mail: gruppo target principale e profili di test".'
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e725ef966bcd6df84ed0c82e17fad65f289fd013
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 83%

---


# Selezione di un pubblico in un messaggio{#selecting-an-audience-in-a-message}

Adobe Campaign ti consente di configurare diversi tipi di profilo all’interno del pubblico di un messaggio.

Se il messaggio è già stato creato, puoi definire i tipi di pubblico al momento della creazione del messaggio tramite la procedura guidata di creazione o dal dashboard dei messaggi.

>[!NOTE]
>
>Se il pubblico è stato creato all’interno di un flusso di lavoro e arricchito di dati aggiuntivi, non puoi utilizzare questi dati per personalizzare una consegna autonoma. È possibile utilizzarli solo da una consegna eseguita in un flusso di lavoro.

1. Dal dashboard, passa al blocco del pubblico per iniziare.

   ![](assets/delivery_audience_definition_1.png)

   Viene visualizzata la schermata che consente di definire i tipi di pubblico. Sono disponibili due schede che ti consentono di definire separatamente ogni tipo di pubblico a cui inviare il messaggio:

   * Target
   * Profili di test

   ![](assets/delivery_audience_definition_2.png)

1. Definisci il **[!UICONTROL Target]** principale del messaggio e-mail. Si tratta del pubblico target regolare del messaggio e-mail.

   Il target è definito nella scheda **[!UICONTROL Target]** ed è composto da profili identificati nel database.

   Puoi stabilire il target principale utilizzando le funzionalità dell’[editor delle query](../../automating/using/editing-queries.md#creating-queries).

   In questa scheda, la palette **[!UICONTROL Shortcuts]** contiene solo filtri preimpostati e i tipi di pubblico definiti nei profili identificati. La scheda **[!UICONTROL Explorer]** ti consente di accedere a configurazioni aggiuntive.

   Puoi quindi riutilizzare e combinare i tipi di pubblico esistenti, applicarvi ulteriori filtri, ecc.

1. Definisci i **[!UICONTROL Test profiles]** da utilizzare per le e-mail. I profili di test ricevono le bozze, che puoi inviare preliminarmente per verificare l’e-mail prima di inviarla al target principale.

   Per ulteriori informazioni sulla configurazione di profili di test, consulta la sezione [Profili di test](../../audiences/using/managing-test-profiles.md).

1. Se necessario, è possibile definire un gruppo di controlli utilizzando la scheda corrispondente. In questo modo potrete ritirare alcuni profili dalla destinazione in modo che non ricevano il messaggio. For more on this, see [Adding a control group](../../sending/using/control-group.md).

1. È inoltre possibile utilizzare gli indirizzi di sostituzione per ottenere una rappresentazione esatta del messaggio che il profilo riceverà.  Per ulteriori informazioni, consulta [Verifica dei messaggi e-mail tramite profili target](../../sending/using/testing-messages-using-target.md).

Il blocco dei tipi di pubblico viene quindi aggiornato e mostra che sono stati selezionati profili target e di test per l’e-mail in questione.

![](assets/delivery_audience_definition_3.png)

