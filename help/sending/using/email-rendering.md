---
title: Rendering di e-mail
description: Scopri la funzione di rendering di e-mail.
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
source-git-commit: 3af649cfaae195ae5e75406ca3a0743b9b1f65d2
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 85%

---


# Rendering di e-mail{#email-rendering}

Prima di premere il pulsante **[!UICONTROL Send]**, accertati che il messaggio venga visualizzato in modo ottimale in vari client web, servizi di posta sul web e dispositivi.

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

I client per dispositivi mobili, di messaggistica e di posta sul web disponibili per il **rendering di e-mail** all’interno di Adobe Campaign sono elencati nel [sito web](https://litmus.com/email-testing) di Litmus (fai clic su **View all email clients**).

## Verifica del report di rendering di e-mail {#checking-the-email-rendering-report}

Dopo aver creato la consegna e-mail e averne definito il contenuto e la popolazione target, effettua le seguenti operazioni.

1. Fai clic su **Audience** per accedere alla scheda **[!UICONTROL Test profiles]**.

   ![](assets/email_rendering_05.png)

1. Utilizza l’editor delle query per definire i profili di test che desideri utilizzare, inclusi quelli per il **rendering di e-mail**. Consulta [Informazioni sui profili di test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Controlla e conferma la query, quindi salva le modifiche.
1. Fai clic sul pulsante **[!UICONTROL Test]** nella barra delle azioni.

   ![](assets/email_rendering_07.png)

1. Seleziona l’opzione **[!UICONTROL Email rendering]** e fai clic su **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >L’opzione **[!UICONTROL Proof + Email rendering]** ti consente di inviare una bozza e utilizzare contemporaneamente la funzione di rendering di e-mail. Puoi far approvare il messaggio dai destinatari della bozza e al contempo verificare la modalità in cui verrà ricevuto a seconda delle caselle in entrata a cui è destinato. In questo caso, è necessario selezionare anche i profili di test di bozza. Consulta [Informazioni sui profili di test](../../audiences/using/managing-test-profiles.md).

   Viene inviata la consegna del test.

1. Le miniature di rendering sono disponibili dopo pochi minuti dall’invio dei messaggi. Per accedervi, seleziona **[!UICONTROL Proofs]** nell’elenco a discesa **[!UICONTROL Summary]**.

   ![](assets/email_rendering_03.png)

1. Dall’elenco **[!UICONTROL Proofs]**, fai clic sull’icona **[!UICONTROL Access email rendering]**.

   ![](assets/email_rendering_04.png)

Viene visualizzato il report dedicato di rendering di e-mail. Consulta [Descrizione del report di rendering di e-mail](#email-rendering-report-description).

**Argomenti correlati**:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Invio di bozze](../../sending/using/sending-proofs.md)
* [Editor delle query](../../automating/using/editing-queries.md#about-query-editor)

## Descrizione del report di rendering di e-mail {#email-rendering-report-description}

Questo report presenta i rendering delle e-mail così come sono visualizzati al destinatario. I rendering di e-mail possono variare a seconda della modalità con cui il destinatario apre la consegna e-mail: in un browser, su un dispositivo mobile o tramite un’applicazione e-mail.

>[!NOTE]
>
>Il numero di rendering disponibili è elencato nel contratto di licenza. Ogni consegna con il **Rendering di e-mail** abilitato diminuisce di un’unità i rendering disponibili, denominati token.
>
>Account Token per ogni singolo rendering e non per l&#39;intero rapporto di rendering E-mail, il che significa che:
>
>**Ogni volta** che viene generato il rapporto di rendering Inbox, viene dedotto un token per client di messaggistica: un token per il rendering di Outlook 2000, uno per il rendering di Outlook, uno per il rendering di Apple Mail e così via.
>
>**Per la stessa consegna**, se generate di nuovo il rendering E-mail, il numero di token disponibili viene nuovamente diminuito dal numero di rendering generati.


Il riepilogo del report mostra il numero di messaggi ricevuti, indesiderati (spam), non ricevuti o in attesa di ricezione.

![](assets/inbox_rendering_report.png)

Il report è diviso in tre parti: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]** e **[!UICONTROL Webmails]**. Per visualizzare tutti i rendering raggruppati in queste tre categorie, scorri il report verso il basso.

![](assets/inbox_rendering_report_3.png)

Per ottenere i dettagli di ciascun report, fai clic sulla scheda corrispondente. Viene visualizzato il rendering per il metodo di ricezione selezionato.

![](assets/inbox_rendering_report_2.png)

La scheda **[!UICONTROL Technical data]** ti consente di ottenere ulteriori informazioni, ad esempio le date di ricezione e acquisizione e le intestazioni complete dei messaggi e-mail.
