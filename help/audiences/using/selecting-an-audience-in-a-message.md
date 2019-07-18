---
title: Selezione di un'audience in un messaggio
seo-title: Selezione di un'audience in un messaggio
description: Selezione di un'audience in un messaggio
seo-description: '" Procedura passo-passo per scegliere le audience di un messaggio e-mail: popolazione di destinazione principale e profili di test. "'
page-status-flag: never-activated
uuid: 7 d 8 f 8446-f 2 e 0-49 c 1-83 f 6-9667 b 29 bc 228
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audience
content-type: riferimento
topic-tags: gestione dei tipi di pubblico
discoiquuid: 158 da 6 ff -8899-4 e 7 b-b 925-8 a 42 c 3 de 46 a 1
context-tags: Deliverycreation, wizard; distribuzione, pubblico,
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c9e33f51ab497b8bd111dfc307670f2fde5d804f

---


# Selecting an audience in a message{#selecting-an-audience-in-a-message}

Adobe Campaign consente di configurare diversi tipi di profilo all'interno dell'audience di un messaggio.

Le audience possono essere definite quando si crea il messaggio tramite la procedura guidata di creazione o nel caso in cui il messaggio sia già stato creato.

>[!NOTE]
>
>Se l'audience è stata integrata in un flusso di lavoro e arricchita con dati aggiuntivi, non sarà possibile utilizzare tali dati per personalizzare una consegna standalone. Possono essere utilizzati solo da una distribuzione eseguita in un flusso di lavoro.

1. Dal dashboard, passate al blocco di pubblico per iniziare.

   ![](assets/delivery_audience_definition_1.png)

   Viene visualizzata la schermata per definire l'audience. Dispone di due schede che consentono di definire separatamente ogni tipo di pubblico che riceverà il messaggio:

   * Target
   * Profili di test
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. Questo è il pubblico di destinazione del messaggio e-mail.

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   You can establish your main target using the [query editor](../../automating/using/editing-queries.md#creating-queries) functionalities.

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. The **[!UICONTROL Explorer]** tab allows you to access additional configurations.

   Puoi quindi riutilizzare e combinare i tipi di pubblico esistenti, applicarvi altri filtri, ecc.

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. I profili di prova riceveranno le prove che potete inviare prima di testare l'e-mail prima di inviarla alla destinazione principale.

   For more information on configuring test profiles, refer to the [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md) section.

Il blocco di audience viene quindi aggiornato e mostra che è stato selezionato un profilo target e test per l'e-mail in questione.

![](assets/delivery_audience_definition_3.png)

