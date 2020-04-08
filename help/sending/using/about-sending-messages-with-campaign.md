---
title: Informazioni sull’invio di messaggi con Campaign
description: Scopri i diversi passaggi per testare e inviare un messaggio.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c49fcd793cbb13d26ccf3a47af145de7acd697e7

---


# Informazioni sull’invio di messaggi con Campaign{#about-sending-messages-with-campaign}

Dopo aver definito la destinazione e creato il contenuto di un messaggio, è necessario verificare e approvare il contenuto, la personalizzazione, il rendering e la configurazione, e assicurarsi che tutto sia corretto prima di inviare il messaggio alla destinazione principale.

A tal fine, le best practice sono le seguenti:

* Prepara l’invio: questo passaggio consente di analizzare e preparare i messaggi da inviare. La preparazione dei messaggi analizza il target, la personalizzazione e la validità del messaggio. Gli errori rilevati durante questo passaggio devono essere corretti prima di poter procedere ulteriormente. Puoi avviare la preparazione dei messaggi il numero di volte necessario. For more on message preparation, refer to [this section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >Potete impostare regole di affaticamento tra canali globali che escluderanno automaticamente i profili sollecitati dalle campagne. Consultate [Regole](../../sending/using/fatigue-rules.md)di fatica.

* Visualizzare l&#39;anteprima dei messaggi utilizzando un profilo di prova. For more on previewing messages, refer to [this section](../../sending/using/previewing-messages.md).
* Inviare prove di stampa ai messaggi di prova. For more on proofs, refer to [this  section](../../sending/using/sending-proofs.md).
* Controllare il rendering dei messaggi: accertatevi che il messaggio venga visualizzato in modo ottimale su diversi client Web, e-mail e dispositivi. Ulteriori informazioni sul rendering delle e-mail in [questa sezione](../../sending/using/email-rendering.md).

Potete quindi:

* Pianificare l&#39;invio: puoi definire quando i messaggi verranno inviati. Ad esempio, puoi adattare l&#39;invio al fuso orario del destinatario, ottimizzare l&#39;ora di invio o calcolare la data di invio. Ulteriori informazioni in [questa sezione](../../sending/using/about-scheduling-messages.md).
* Invia il messaggio: una volta pronto il messaggio, è possibile avviare l&#39;invio. I registri e i rapporti di accesso sono quindi disponibili per monitorare la distribuzione dei messaggi e misurare il successo della campagna. Adobe Campaign fornisce inoltre un sistema di avvisi e-mail per tenere traccia dei successi o degli errori di consegna. Ulteriori informazioni in [questa pagina](../../sending/using/confirming-the-send.md).

## Argomenti correlati

| Pagine utili | Risorse aggiuntive |
|---|---|
| [Ottimizzazione della recapito](../../sending/using/about-deliverability.md) | [Gestione della fatica](../../sending/using/fatigue-rules.md) |
| [Velocità di consegna controllata](../../reporting/using/delivery-throughput.md) | [Progettazione di e-mail di test A/B](../../channels/using/designing-an-a-b-test-email.md) |
| [Ricezione di una notifica in caso di errore](../../sending/using/receiving-alerts-when-failures-happen.md) | [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md) |
| [Creazione di un gruppo di controllo](../../automating/using/workflow-control-group.md) | [Invio di messaggi di follow-up](../../channels/using/follow-up-messages.md) |