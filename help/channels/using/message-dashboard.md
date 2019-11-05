---
title: Dashboard messaggi
description: Scopri di cosa è composto il dashboard dei messaggi, inclusa la barra delle azioni e i vari blocchi funzionali.
page-status-flag: mai attivato
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: about-communication-channel
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: consegna,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Dashboard messaggi{#message-dashboard}

Il dashboard dei messaggi è un'area di lavoro composta da diverse icone, raggruppate in una barra delle azioni, e da vari blocchi funzionali che consentono di stabilire i parametri del messaggio e inviarli. Questi elementi sono presentati di seguito.

![](assets/delivery_dashboard_2.png)

## Barra grigia {#gray-bar}

La barra grigia raggruppa diverse icone collegate al messaggio.

* **[!UICONTROL Summary]**: mostra/nasconde le informazioni principali relative al messaggio.
* **[!UICONTROL Edit properties]**: consente di modificare i parametri [](../../administration/using/configuring-email-channel.md#list-of-email-properties)avanzati del messaggio.
* **[!UICONTROL Reports]**: consente di accedere ai rapporti relativi al messaggio.

**Argomenti correlati:**

* [Configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Accesso ai rapporti](../../reporting/using/about-dynamic-reports.md)

## Barra delle azioni {#action-bar}

La barra delle azioni ha diverse icone che consentono di interagire con il messaggio.

![](assets/delivery_dashboard_4.png)

A seconda dei parametri impostati e dell’avanzamento, alcune icone potrebbero non essere disponibili.

* **[!UICONTROL Show proofs]**: mostra/nasconde l’elenco delle prove che sono state inviate, se esistenti. Questo pulsante è attivato solo dopo l’invio delle prove.

   Per ulteriori informazioni sulle prove di stampa, consultate [Gestione dei profili di test e invio delle prove](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**: consente di selezionare la modalità di approvazione da utilizzare: **[!UICONTROL Email rendering]**, **[!UICONTROL Proof]** o entrambi per un'e-mail. Per ulteriori informazioni sui profili di test, consultate [Invio di prove](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   Questo pulsante è attivato solo dopo che sono stati definiti i profili di test.

   >[!NOTE]
   >
   >Per un messaggio SMS, non esiste altra scelta: è automaticamente un **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**: inizia a preparare l'invio. Il **[!UICONTROL Deployment]** blocco viene visualizzato e visualizza il risultato della preparazione. Questo pulsante viene visualizzato solo dopo che è stata immessa la destinazione. È possibile interrompere la preparazione in qualsiasi momento utilizzando il pulsante corrispondente.

   Per ulteriori informazioni sulla preparazione dei messaggi, [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: conferma l’invio del messaggio. Le statistiche di invio vengono visualizzate nel **[!UICONTROL Deployment]** blocco. Questo pulsante viene visualizzato solo dopo che l’invio è stato preparato. Puoi interrompere o mettere in pausa l’invio in qualsiasi momento utilizzando i **pulsanti Interrompi invio** e **[!UICONTROL Pause]** Interrompi.

   Per ulteriori informazioni sulla conferma dell’invio, consulta [Invio di messaggi](../../sending/using/confirming-the-send.md).

## Blocchi {#blocks}

Lo schermo principale è costituito da diversi blocchi. Fate clic all’interno di un blocco per accedere alla schermata dei parametri corrispondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: consente di monitorare l’avanzamento della preparazione o dell’invio dei messaggi. Fare clic sul pulsante che si trova nella sezione inferiore destra di questo blocco per accedere ai registri di invio e analisi. Questo blocco viene visualizzato solo dopo che l'invio è stato preparato. Per ulteriori informazioni su questo argomento. Consultate [Conferma dell’invio](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: consente di stabilire la destinazione principale del messaggio e i profili di test. Consultate [Creazione di audience](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: consente di specificare la data in cui verrà inviato il messaggio. Vedere [Pianificazione](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: consente di definire il contenuto del messaggio e visualizzarne l'anteprima. See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

