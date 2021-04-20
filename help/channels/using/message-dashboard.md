---
solution: Campaign Standard
product: campaign
title: Dashboard messaggi
description: Scopri di cosa è composto il dashboard dei messaggi, inclusa la barra delle azioni e i vari blocchi funzionali.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '591'
ht-degree: 4%

---


# Dashboard messaggi{#message-dashboard}

Il dashboard dei messaggi è un’area di lavoro composta da diverse icone, raggruppate in una barra delle azioni, e da vari blocchi funzionali che ti consentono di stabilire i parametri del messaggio e inviarli. Questi elementi sono presentati in seguito.

![](assets/delivery_dashboard_2.png)

## Barra grigia {#gray-bar}

La barra grigia raggruppa varie icone collegate al messaggio.

* **[!UICONTROL Summary]**: mostra/nasconde le informazioni principali relative al messaggio.
* **[!UICONTROL Edit properties]**: ti consente di modificare i parametri  [avanzati del messaggio](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**: consente di accedere ai rapporti relativi al messaggio.

**Argomenti correlati:**

* [Configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Accesso ai rapporti](../../reporting/using/about-dynamic-reports.md)

## Barra delle azioni {#action-bar}

La barra delle azioni dispone di icone diverse che consentono di interagire con il messaggio.

![](assets/delivery_dashboard_4.png)

A seconda dei parametri impostati e dell’avanzamento, alcune icone potrebbero non essere disponibili.

* **[!UICONTROL Show proofs]**: mostra/nasconde l’elenco delle bozze inviate, se presenti. Questo pulsante viene attivato solo dopo l’invio delle bozze.

   Per ulteriori informazioni sulle bozze, consulta [Invio di bozze](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: consente di selezionare la modalità di approvazione da utilizzare:  **[!UICONTROL Email rendering]** (solo e-mail),  **[!UICONTROL Proof]** o entrambi. Per ulteriori informazioni sui profili di test, consulta [Invio di bozze](../../sending/using/sending-proofs.md). Questo pulsante viene attivato solo dopo la creazione dei profili di test.

* **[!UICONTROL Prepare send]**: inizia a preparare l’invio. Viene visualizzato il blocco **[!UICONTROL Deployment]** che visualizza il risultato della preparazione. Questo pulsante viene visualizzato solo dopo l’immissione della destinazione. Puoi interrompere la preparazione in qualsiasi momento utilizzando il pulsante corrispondente. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: conferma l’invio del messaggio. Le statistiche di invio vengono visualizzate nel blocco **[!UICONTROL Deployment]** . Questo pulsante viene visualizzato solo dopo la preparazione dell’invio. Puoi interrompere o mettere in pausa l’invio in qualsiasi momento utilizzando i pulsanti **Interrompi invio** e **[!UICONTROL Pause]** . Per ulteriori informazioni sulla conferma dell’invio, consulta [Invio di messaggi](../../sending/using/confirming-the-send.md).

## Blocchi {#blocks}

La schermata principale è composta da diversi blocchi. Fai clic all’interno di un blocco per accedere alla schermata dei parametri corrispondente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: consente di tenere traccia dell’avanzamento della preparazione o dell’invio dei messaggi. Fai clic sul pulsante che si trova nella sezione in basso a destra di questo blocco per accedere ai registri di invio e analisi. Questo blocco viene visualizzato solo dopo che l’invio è stato preparato. Per saperne di più. Consulta [Conferma invio](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: ti consente di stabilire il target principale del messaggio e i profili di test. Consulta [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: consente di specificare la data in cui il messaggio verrà inviato. Vedere [Pianificazione](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: ti consente di definire il contenuto del messaggio e visualizzarlo in anteprima. Consulta [Passaggi chiave per inviare un messaggio](../../channels/using/key-steps-to-send-a-message.md).

## Avvisi {#warnings}

In alcuni casi, un avviso può comparire in un banner giallo sopra il dashboard dei messaggi.

![](assets/delivery_dashboard_warnings.png)

Di seguito è riportato un elenco dei messaggi che possono essere visualizzati:

* *&quot;L’opzione della modalità di prova SMTP è abilitata per questo messaggio e-mail: non verrà inviato alcun messaggio.&quot;*

   Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;L&#39;account esterno di routing è stato disabilitato.&quot;*

   Per ulteriori informazioni, consulta [Account esterni](../../administration/using/external-accounts.md).

* *&quot;Impossibile inviare i messaggi perché l&#39;affinità IP corrente non viene gestita da alcun processo di invio.&quot;*

   Se ricevi questo messaggio, si verifica un problema a livello di definizione dell’affinità IP o a livello del processo di invio. Contattare l&#39;amministratore di Adobe.

* *&quot;Si tratta di un modello di messaggio transazionale preconfigurato. Se desideri modificarlo, devi duplicarlo e lavorare sulla copia.&quot;*

   Alcuni di questi modelli predefiniti per messaggi transazionali sono modelli di pagina di destinazione incorporati. Per ulteriori informazioni, consulta [questa sezione](../../channels/using/landing-page-templates.md).

* *&quot;Questo messaggio è un modello di messaggio transazionale tecnico. Non puoi modificarlo o pubblicarlo.&quot;*

   Questo avviso viene visualizzato in modelli di messaggi transazionali vuoti non modificabili. Per ulteriori informazioni sui messaggi transazionali, consulta [questa sezione](../../channels/using/getting-started-with-transactional-msg.md).
