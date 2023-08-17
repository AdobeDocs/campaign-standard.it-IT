---
title: Dashboard messaggi
description: Scopri di cosa è composto il dashboard dei messaggi, inclusa la barra delle azioni e i vari blocchi funzionali.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---

# Dashboard messaggi{#message-dashboard}

Il dashboard dei messaggi è un’area di lavoro composta da icone diverse, raggruppate in una barra delle azioni, e vari blocchi funzionali che ti consentono di stabilire i parametri del messaggio e di inviarlo. Tali elementi sono presentati di seguito.

![](assets/delivery_dashboard_2.png)

## Barra grigia {#gray-bar}

La barra grigia raggruppa varie icone collegate al messaggio.

* **[!UICONTROL Summary]**: mostra/nasconde le informazioni principali relative al messaggio.
* **[!UICONTROL Edit properties]**: consente di modificare i [parametri avanzati](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**: ti consente di accedere ai rapporti relativi al messaggio.

**Argomenti correlati:**

* [Configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Accesso ai rapporti](../../reporting/using/about-dynamic-reports.md)

## Barra delle azioni {#action-bar}

La barra delle azioni è dotata di icone diverse che consentono di interagire con il messaggio.

![](assets/delivery_dashboard_4.png)

A seconda dei parametri configurati e dell’avanzamento, alcune icone potrebbero non essere disponibili.

* **[!UICONTROL Show proofs]**: mostra/nasconde l’elenco delle bozze inviate, se presenti. Questo pulsante è abilitato solo dopo l’invio delle bozze.

  Per ulteriori informazioni sulle bozze, consulta [Invio di bozze](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: consente di selezionare la modalità di approvazione da utilizzare: **[!UICONTROL Email rendering]** (solo e-mail), **[!UICONTROL Proof]** o entrambi. Per ulteriori informazioni sui profili di test, consulta [Invio di bozze](../../sending/using/sending-proofs.md). Questo pulsante è abilitato solo dopo aver creato i profili di test.

* **[!UICONTROL Prepare send]**: inizia a preparare l’invio. Il **[!UICONTROL Deployment]** Il blocco viene visualizzato e visualizza il risultato della preparazione. Questo pulsante viene visualizzato solo dopo l&#39;immissione della destinazione. Puoi interrompere la preparazione in qualsiasi momento utilizzando il pulsante corrispondente. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: conferma l’invio del messaggio. Le statistiche di invio vengono visualizzate nel **[!UICONTROL Deployment]** blocco. Questo pulsante viene visualizzato solo dopo la preparazione dell’invio. Puoi interrompere o mettere in pausa l’invio in qualsiasi momento utilizzando **Interrompi invio** e **[!UICONTROL Pause]** pulsanti. Per ulteriori informazioni sulla conferma dell’invio, consulta [Invio di messaggi](../../sending/using/confirming-the-send.md).

## Blocchi {#blocks}

La schermata principale è composta da diversi blocchi. Fai clic all’interno di un blocco per accedere alla schermata dei parametri corrispondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: consente di tenere traccia dell’avanzamento della preparazione o dell’invio del messaggio. Fai clic sul pulsante che si trova nella sezione in basso a destra di questo blocco per accedere ai registri di invio e analisi. Questo blocco viene visualizzato solo una volta che l’invio è stato preparato. Per ulteriori informazioni. Consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: ti consente di stabilire il target principale del messaggio e i profili di test. Consulta [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: ti consente di specificare la data in cui il messaggio verrà inviato. Consulta [Pianificazione](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: ti consente di definire il contenuto del messaggio e di visualizzarne l’anteprima. Consulta [Passaggi fondamentali per l’invio di un messaggio](../../channels/using/key-steps-to-send-a-message.md).

## Avvertenze {#warnings}

In alcuni casi, un’avvertenza potrebbe apparire in un banner giallo sopra il dashboard dei messaggi.

![](assets/delivery_dashboard_warnings.png)

Di seguito è riportato un elenco dei messaggi che è possibile visualizzare:

* *&quot;L’opzione della modalità di test SMTP è abilitata per questa e-mail: non verrà inviato alcun messaggio.&quot;*

  Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;L&#39;account esterno di routing è stato disabilitato.&quot;*

  Per ulteriori informazioni, consulta [Account esterni](../../administration/using/external-accounts.md).

* *&quot;Impossibile inviare i messaggi perché l&#39;affinità IP corrente non è gestita da alcun processo di invio.&quot;*

  Se visualizzi questo messaggio, si verifica un problema a livello di definizione di affinità IP o a livello di processo di invio. Contatta l’amministratore Adobe.

* *&quot;Questo è un modello di messaggio transazionale pronto all’uso. Se desideri modificarlo, devi duplicarlo e lavorarci sopra.&quot;*

  Alcuni di questi modelli di messaggi transazionali predefiniti sono modelli di pagina di destinazione incorporati. Per ulteriori informazioni, consulta [questa sezione](../../channels/using/landing-page-templates.md).

* *&quot;Questo messaggio è un modello tecnico per messaggi transazionali. Non è possibile modificarlo o pubblicarlo.&quot;*

  Questo avviso viene visualizzato in modelli di messaggi transazionali vuoti che non sono modificabili. Per ulteriori informazioni sui messaggi transazionali, consulta [questa sezione](../../channels/using/getting-started-with-transactional-msg.md).
