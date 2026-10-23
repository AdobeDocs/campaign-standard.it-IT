---
title: Selezione di un pubblico in un messaggio
description: 'Procedura dettagliata per scegliere i tipi di pubblico di un’e-mail: popolazione target principale e profili di test.'
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
feature: Audiences
role: User
level: Intermediate
exl-id: 239959ad-6386-42bf-a86a-5694cdaecd83
TQID: 'https://experienceleague.adobe.com/Ev0HCh32pGzPlVPe8SrCwBOFdEh-iXSGI6XYt9WMmLc'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 66%
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

   La destinazione è definita nella scheda **[!UICONTROL Target]** ed è composta da profili identificati nel database. Puoi stabilire il target principale utilizzando le funzionalità dell’[editor di query](../../automating/using/editing-queries.md#creating-queries).

   In questa scheda, la palette **[!UICONTROL Shortcuts]** contiene solo filtri preimpostati e i tipi di pubblico definiti nei profili identificati. La scheda **[!UICONTROL Explorer]** ti consente di accedere a configurazioni aggiuntive.

   Puoi quindi riutilizzare e combinare i tipi di pubblico esistenti, applicarvi ulteriori filtri, ecc.

   >[!NOTE]
   >
   >Quando esegui il targeting di un pubblico, tieni presente che alla definizione del pubblico non viene fatto riferimento, ma **copiata** nella query. Se apporti modifiche al pubblico dopo che è stato impostato il targeting in una query, assicurati di configurare nuovamente la query per tenere conto della nuova definizione.

1. Definisci i **[!UICONTROL Test profiles]** da utilizzare per le e-mail. I profili di test ricevono le bozze, che puoi inviare preliminarmente per verificare l’e-mail prima di inviarla al target principale.

   Per ulteriori informazioni sulla configurazione di profili di test, consulta la sezione [Profili di test](../../audiences/using/managing-test-profiles.md).

1. Se necessario, è possibile definire un gruppo di controllo utilizzando la scheda corrispondente. Questo ti consentirà di ritirare alcuni profili dal target in modo che non ricevano il messaggio. Per ulteriori informazioni, vedere [Aggiunta di un gruppo di controllo](../../sending/using/control-group.md).

1. Puoi inoltre utilizzare indirizzi di sostituzione per ottenere una rappresentazione esatta del messaggio che verrà ricevuto dal profilo.  Per ulteriori informazioni, consulta [Verifica dei messaggi e-mail tramite profili target](../../sending/using/testing-messages-using-target.md).

Il blocco dei tipi di pubblico viene quindi aggiornato e mostra che sono stati selezionati profili target e di test per l’e-mail in questione.

![](assets/delivery_audience_definition_3.png)
