---
title: Selezione di un pubblico in un messaggio
description: '"Procedura dettagliata per scegliere i tipi di pubblico di un messaggio e-mail: gruppo target principale e profili di test".'
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
feature: Audiences
role: User
level: Intermediate
exl-id: 239959ad-6386-42bf-a86a-5694cdaecd83
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 74%

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

   Il target è definito nella scheda **[!UICONTROL Target]** ed è composto da profili identificati nel database. Puoi stabilire il target principale utilizzando le funzionalità dell’[editor delle query](../../automating/using/editing-queries.md#creating-queries).

   In questa scheda, la palette **[!UICONTROL Shortcuts]** contiene solo filtri preimpostati e i tipi di pubblico definiti nei profili identificati. La scheda **[!UICONTROL Explorer]** ti consente di accedere a configurazioni aggiuntive.

   Puoi quindi riutilizzare e combinare i tipi di pubblico esistenti, applicarvi ulteriori filtri, ecc.

   >[!NOTE]
   >
   >Quando esegui il targeting di un pubblico, tieni presente che non viene fatto riferimento alla definizione del pubblico, ma **copiato** nella query. Se apporti modifiche al pubblico dopo che è stato eseguito il targeting in una query, assicurati di configurare nuovamente la query per tenere conto della nuova definizione.

1. Definisci i **[!UICONTROL Test profiles]** da utilizzare per le e-mail. I profili di test ricevono le bozze, che puoi inviare preliminarmente per verificare l’e-mail prima di inviarla al target principale.

   Per ulteriori informazioni sulla configurazione di profili di test, consulta la sezione [Profili di test](../../audiences/using/managing-test-profiles.md).

1. Se necessario, è possibile definire un gruppo di controllo utilizzando la scheda corrispondente. In questo modo puoi ritirare alcuni profili dal target in modo che non ricevano il messaggio. Per ulteriori informazioni, consulta [Aggiunta di un gruppo di controllo](../../sending/using/control-group.md).

1. Puoi inoltre utilizzare gli indirizzi di sostituzione per ottenere una rappresentazione esatta del messaggio che verrà ricevuto dal profilo.  Per ulteriori informazioni, consulta [Verifica dei messaggi e-mail tramite profili target](../../sending/using/testing-messages-using-target.md).

Il blocco dei tipi di pubblico viene quindi aggiornato e mostra che sono stati selezionati profili target e di test per l’e-mail in questione.

![](assets/delivery_audience_definition_3.png)
