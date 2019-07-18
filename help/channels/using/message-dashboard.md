---
title: Pannello messaggio
seo-title: Pannello messaggio
description: Pannello messaggio
seo-description: Scoprite come è composto il dashboard di messaggio, compresa la barra delle azioni e i vari blocchi funzionali.
page-status-flag: never-activated
uuid: 9 bb 44 ee 8-2 cf 6-43 ce -94 a 4-367 f 4 e 469713
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: about-communication-channels
discoiquuid: 90 a 78742-697 f -46 da -8 c 54-108048 e 57 b 67
context-tags: distribuzione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Message dashboard{#message-dashboard}

Il pannello del messaggio è un'area di lavoro composta da icone diverse, raggruppate in una barra di azione e vari blocchi funzionali che consentono di stabilire i parametri del messaggio e di inviarli. Questi elementi vengono presentati di seguito.

![](assets/delivery_dashboard_2.png)

## Gray bar {#gray-bar}

La barra grigia raggruppa diverse icone collegate al messaggio.

* **[!UICONTROL Summary]**: mostra/nasconde le informazioni principali relative al messaggio.
* **[!UICONTROL Edit properties]**: consente di modificare i parametri avanzati del messaggio.
* **[!UICONTROL Reports]**: consente di accedere ai rapporti relativi al messaggio.

**Argomenti correlati:**

* [Configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Accesso ai rapporti](../../reporting/using/about-dynamic-reports.md)

## Action bar {#action-bar}

La barra delle azioni presenta icone diverse che consentono di interagire con il messaggio.

![](assets/delivery_dashboard_4.png)

A seconda dei parametri configurati e dell'avanzamento, alcune icone potrebbero non essere disponibili.

* **[!UICONTROL Show proofs]**: mostra/nasconde l'elenco di prove che sono state inviate, se esistono. Questo pulsante è abilitato solo dopo aver inviato le prove.

   For more on proofs, see [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**: consente di selezionare la modalità di approvazione da utilizzare: **[!UICONTROL Email rendering]** o **[!UICONTROL Proof]** entrambi. For more on test profiles, see [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   Questo pulsante è abilitato solo dopo aver configurato i profili di prova.

   >[!NOTE]
   >
   >For an SMS message, there is no other choice: it is automatically a **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**: inizia a preparare l'invio. The **[!UICONTROL Deployment]** block appears and displays the result of the preparation. Questo pulsante viene visualizzato solo dopo che la destinazione è stata inserita. Potete interrompere la preparazione in qualsiasi momento utilizzando il pulsante corrispondente.

   For more on message preparation, [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: conferma l'invio del messaggio. The sending statistics appear in the **[!UICONTROL Deployment]** block. Questo pulsante viene visualizzato solo dopo che l'invio è stato preparato. You can stop or pause the send at any time using the **Stop send** and **[!UICONTROL Pause]** buttons.

   For more on confirming sending, see [Sending messages](../../sending/using/confirming-the-send.md).

## Blocks {#blocks}

La schermata principale è composta da blocchi diversi. Fate clic all'interno di un blocco per accedere alla schermata del parametro corrispondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: consente di tenere traccia dell'avanzamento della preparazione o dell'invio dei messaggi. Fate clic sul pulsante nella sezione inferiore destra di questo blocco per accedere ai registri di invio e analisi. Questo blocco viene visualizzato solo dopo che l'invio è stato preparato. Per ulteriori informazioni. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: consente di stabilire la destinazione principale del messaggio nonché i profili di prova. See [Creating audiences](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: consente di specificare la data in cui verrà inviato il messaggio. See [Scheduling](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: consente di definire il contenuto del messaggio e visualizzarne l'anteprima. See [Defining content](../../designing/using/designing-content-in-adobe-campaign.md).

