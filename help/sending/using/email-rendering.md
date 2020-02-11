---
title: Rendering di e-mail
description: Scoprite la funzione di rendering delle e-mail.
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Rendering di e-mail{#email-rendering}

Prima di premere il **[!UICONTROL Send]** pulsante, accertatevi che il messaggio venga visualizzato in modo ottimale su diversi client Web, e-mail e dispositivi.

Per consentire questo, Adobe Campaign acquisisce il rendering e lo rende disponibile in un rapporto dedicato. Questo consente di visualizzare in anteprima il messaggio inviato nei diversi contesti in cui potrebbe essere ricevuto.

I client per dispositivi mobili, messaggi e messaggi Web disponibili per il rendering **e-mail in Adobe Campaign sono elencati nel** sito [Web di Litmus (fate clic su](https://litmus.com/email-testing) Visualizza tutti i client **** e-mail).

## Verifica del rapporto di rendering per e-mail {#checking-the-email-rendering-report}

Dopo aver creato la consegna dell’e-mail e definito il contenuto e la popolazione di destinazione, effettuate le seguenti operazioni.

1. Fate clic su **Pubblico** per accedere alla **[!UICONTROL Test profiles]** scheda.

   ![](assets/email_rendering_05.png)

1. Utilizzate l&#39;editor di query per definire i profili di test da utilizzare, inclusi i profili di test utilizzati per il rendering **e-** mail. Consultate [I profili](../../audiences/using/managing-test-profiles.md)di test.

   ![](assets/email_rendering_06.png)

1. Controllare e confermare la query, quindi salvare le modifiche.
1. Fate clic sul **[!UICONTROL Test]** pulsante nella barra delle azioni.

   ![](assets/email_rendering_07.png)

1. Selezionate l’ **[!UICONTROL Email rendering]** opzione e fate clic su **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >L’ **[!UICONTROL Proof + Email rendering]** opzione consente di inviare una prova e utilizzare simultaneamente la funzione di rendering e-mail. Puoi far approvare il messaggio dai destinatari della prova e allo stesso tempo puoi verificare il modo in cui il messaggio verrà ricevuto a seconda delle inbox di destinazione. In questo caso, è necessario anche selezionare Prove profili. Consultate [I profili](../../audiences/using/managing-test-profiles.md)di test.

   La consegna del test viene inviata.

1. Le miniature di rendering sono disponibili pochi minuti dopo l’invio dei messaggi. Per accedervi, selezionate **[!UICONTROL Proofs]** nell’elenco a **[!UICONTROL Summary]** discesa.

   ![](assets/email_rendering_03.png)

1. Dall&#39; **[!UICONTROL Proofs]** elenco, fare clic sull&#39; **[!UICONTROL Access email rendering]** icona.

   ![](assets/email_rendering_04.png)

Viene visualizzato il rapporto dedicato sul rendering delle e-mail. Consultate Descrizione [del rapporto di rendering per e-](#email-rendering-report-description)mail.

**Argomenti** correlati:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Invio di prove](../../sending/using/sending-proofs.md)
* [Editor query](../../automating/using/editing-queries.md#about-query-editor)

## Descrizione rapporto rendering e-mail {#email-rendering-report-description}

Questo rapporto presenta i rendering delle e-mail così come appaiono al destinatario. I rendering e-mail possono variare a seconda del modo in cui il destinatario apre la consegna dell&#39;e-mail: in un browser, su un dispositivo mobile o tramite un&#39;applicazione e-mail.

>[!NOTE]
>
>Il numero di rendering disponibili è elencato nel contratto di licenza. Ogni consegna con il rendering **** E-mail abilitato diminuisce di un&#39;unità i rendering disponibili (denominati token). Se sei un client Litmus, puoi usare il tuo account Litmus per fornire e utilizzare il rendering E-mail in Adobe Campaign. Per ulteriori informazioni, contattate il vostro responsabile commerciale Adobe.

Il riepilogo del rapporto mostra il numero di messaggi ricevuti, indesiderati (spam), non ricevuti o in attesa di ricezione.

![](assets/inbox_rendering_report.png)

La relazione è divisa in tre parti: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, e **[!UICONTROL Webmails]**. Scorrete il rapporto verso il basso per visualizzare tutti i rendering raggruppati in queste tre categorie.

![](assets/inbox_rendering_report_3.png)

Per ottenere i dettagli per ciascun rapporto, fate clic sulla scheda corrispondente. Il rendering viene visualizzato per il metodo di ricezione selezionato.

![](assets/inbox_rendering_report_2.png)

La **[!UICONTROL Technical data]** scheda consente di ottenere ulteriori informazioni, ad esempio le date di ricezione e acquisizione e le intestazioni complete dei messaggi e-mail.
