---
title: Dashboard messaggi
description: Scopri di cosa è composto il dashboard dei messaggi, inclusa la barra delle azioni e i vari blocchi funzionali.
page-status-flag: never-activated
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Dashboard messaggi{#message-dashboard}

Il dashboard dei messaggi è un&#39;area di lavoro composta da diverse icone, raggruppate in una barra delle azioni, e da vari blocchi funzionali che consentono di stabilire i parametri del messaggio e inviarli. Questi elementi sono presentati di seguito.

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

   Per ulteriori informazioni sulle prove, consultate [Invio delle prove](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: consente di selezionare la modalità di approvazione da utilizzare: **[!UICONTROL Email rendering]** (solo e-mail) **[!UICONTROL Proof]** o entrambi. Per ulteriori informazioni sui profili di test, consultate [Invio di prove](../../sending/using/sending-proofs.md). Questo pulsante è attivato solo dopo la creazione dei profili di test.

* **[!UICONTROL Prepare send]**: inizia a preparare l&#39;invio. Il **[!UICONTROL Deployment]** blocco viene visualizzato e visualizza il risultato della preparazione. Questo pulsante viene visualizzato solo dopo che è stata immessa la destinazione. È possibile interrompere la preparazione in qualsiasi momento utilizzando il pulsante corrispondente. For more on message preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: conferma l’invio del messaggio. Le statistiche di invio vengono visualizzate nel **[!UICONTROL Deployment]** blocco. Questo pulsante viene visualizzato solo dopo che l’invio è stato preparato. Puoi interrompere o mettere in pausa l’invio in qualsiasi momento utilizzando i **pulsanti Interrompi invio** e **[!UICONTROL Pause]** Interrompi. Per ulteriori informazioni sulla conferma dell&#39;invio, vedere [Invio di messaggi](../../sending/using/confirming-the-send.md).

## Blocchi {#blocks}

Lo schermo principale è costituito da diversi blocchi. Fate clic all’interno di un blocco per accedere alla schermata dei parametri corrispondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: consente di monitorare l’avanzamento della preparazione o dell’invio dei messaggi. Fare clic sul pulsante nella sezione inferiore destra di questo blocco per accedere ai registri di invio e analisi. Questo blocco viene visualizzato solo dopo che l&#39;invio è stato preparato. Per ulteriori informazioni su questo argomento. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: consente di stabilire la destinazione principale del messaggio e i profili di test. Consulta [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: consente di specificare la data in cui verrà inviato il messaggio. Vedere [Pianificazione](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: consente di definire il contenuto del messaggio e visualizzarne l&#39;anteprima. See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## Avvisi {#warnings}

In alcuni casi, un avviso potrebbe apparire in un banner giallo sopra il dashboard dei messaggi.

![](assets/delivery_dashboard_warnings.png)

Segue un elenco dei messaggi che è possibile visualizzare:

* *&quot;L&#39;opzione della modalità di prova SMTP è abilitata per questo messaggio e-mail: nessun messaggio verrà inviato.&quot;*

   Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;Il routing dell&#39;account esterno è stato disabilitato.&quot;*

   Per ulteriori informazioni, consulta [Conti](../../administration/using/external-accounts.md)esterni.

* *&quot;Impossibile inviare i messaggi perché l&#39;affinità IP corrente non è gestita da alcun processo di invio.&quot;*

   Se viene visualizzato questo messaggio, si verifica un problema a livello di definizione dell&#39;affinità IP o a livello di processo di invio. Contattate l’amministratore  Adobe.

* *&quot;Si tratta di un modello di messaggio transazionale integrato. Se desiderate modificarlo, dovete duplicarlo e lavorare sulla copia.&quot;*

   Alcuni di questi modelli di messaggi transazionali forniti con il prodotto sono modelli integrati per pagine di destinazione. Per ulteriori informazioni, consulta [questa sezione](../../channels/using/landing-page-templates.md).

* *&quot;Questo messaggio è un modello tecnico per messaggi transazionali. Non potete modificarlo o pubblicarlo.&quot;*

   Questo avviso viene visualizzato in modelli vuoti di messaggi transazionali non modificabili. For more on transactional messages, see [this section](../../channels/using/getting-started-with-transactional-msg.md).
