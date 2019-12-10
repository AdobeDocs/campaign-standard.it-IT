---
title: Controllo del contenuto delle e-mail in Adobe Campaign Standard
description: Scopri come migliorare la recapito in Adobe Campaign Standard quando modifichi il contenuto delle e-mail.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f0580e1ab75d4250bfb1cb801ff08b31b91cdc5a

---


# Controllo del contenuto delle e-mail{#control-email-content}

Per migliorare il tasso di recapito delle e-mail e assicurarsi che le e-mail arrivino ai destinatari, queste devono rispettare un certo numero di regole.

* **Nome e indirizzo** del mittente: L'indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà e registrato del mittente. Il registro di dominio non deve essere privatizzato.
* **Oggetto**: Evitare l'eccessiva capitalizzazione e punteggiatura, e le parole che sono frequentemente utilizzate dagli spammer ("Win", "Free", ecc.).
* **Personalizza il tuo messaggio e-mail**: La personalizzazione dell’e-mail aumenta le possibilità di apertura del messaggio.
* **Immagini e testo**: Rispetta un rapporto testo/immagine decente (ad esempio, testo al 60% e immagini al 40%).
* **Rimuovi iscrizione e pagina** di destinazione: Il collegamento di annullamento della sottoscrizione è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale.
* **Utilizza gli strumenti** offerti da Adobe Campaign per ottimizzare il contenuto delle e-mail (analisi della distribuzione, analisi anti-spam).

Per ulteriori informazioni sulla modifica del contenuto delle e-mail, consultare la panoramica [di Designer e-](../../designing/using/designing-content-in-adobe-campaign.md) mail e le procedure [consigliate per la progettazione dei](../../designing/using/overview.md#content-design-best-practices)messaggi.

## Nome e indirizzo del mittente {#sender-name}

Alcuni ISP controllano la validità dell'indirizzo del mittente (Da) prima di accettare i messaggi. Un indirizzo con formato non corretto potrebbe essere rifiutato dal server ricevente. È necessario assicurarsi che l'indirizzo corretto sia specificato a livello di istanza o negli scenari più frequentemente utilizzati. Contattate l’amministratore.

![](assets/delivery_content_edition16.png)

Per ulteriori informazioni, consulta [Personalizzazione del nome](../../designing/using/personalization.md#personalizing-the-sender)del mittente.

## Riga oggetto {#subject-line}

Quando modificate un’e-mail, potete provare diverse righe di oggetto e ottenere una stima del tasso di apertura prima di inviarla. Per ulteriori informazioni, consultate [Verifica dell’oggetto di un messaggio e-mail](../../sending/using/testing-subject-line-email.md).

![](assets/predictive_subject_line_example.png)

Per ulteriori informazioni sulla definizione dell’oggetto di un messaggio e-mail, consultate [questa sezione](../../designing/using/subject-line.md).

## Ottimizzazione dell'ora di invio {#send-time-optimization}

Per migliorare il tasso di successo dei messaggi, puoi definire manualmente un orario di invio per destinatario. Ogni profilo riceve il messaggio alla data e all'ora specificate, quando possibile.

Per ulteriori informazioni, vedere [Ottimizzazione del tempo](../../sending/using/optimizing-the-sending-time.md)di invio.

## Collegamento e modulo di rifiuto {#opt-out}

Per impostazione predefinita, quando il messaggio viene analizzato, una regola di tipologia verifica se è stato incluso un collegamento di rinuncia e genera un avviso se risulta mancante.

È necessario verificare che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando si invia la prova, verificare che il collegamento sia valido, che il modulo sia in linea e che la convalida di tali modifiche venga convalidato il valore delle caselle di contatto No più. È consigliabile eseguire questo controllo in modo sistematico perché l'errore umano è sempre possibile quando si inserisce il collegamento o si modifica il modulo.

Se viene rilevato un problema relativo all'annullamento dell'iscrizione dopo l'avvio della consegna, è comunque possibile eseguire un'annullamento dell'iscrizione manualmente (utilizzando, ad esempio, la funzione di aggiornamento di massa) per i destinatari che fanno clic sul collegamento di rinuncia anche se non sono stati in grado di confermare la scelta.

Come regola generale, non cercate di ostacolare i destinatari che desiderano rifiutare richiedendo loro di compilare campi quali ad esempio il loro indirizzo e-mail o nome. La pagina di destinazione per l’annullamento della sottoscrizione deve contenere un solo pulsante di convalida. La richiesta di conferma aggiuntiva non è affidabile: un utente può avere due indirizzi e-mail reindirizzati alla stessa casella (ad esempio: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se il profilo è in grado di ricordare solo il primo indirizzo e desidera annullare l'iscrizione tramite un messaggio inviato all'altro, il modulo rifiuterà l'operazione perché l'identificatore crittografato e l'indirizzo e-mail immesso non corrisponderanno.

## Analisi anti-spam {#anti-spam-analysis}

L'editor dei messaggi di Adobe Campaign integra un'analisi **** anti-spam che consente di segnare le e-mail per determinare se un messaggio corre il rischio di essere considerato come spam dagli strumenti anti-spam utilizzati al momento della ricezione. Per ulteriori informazioni, vedere [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

Nell'editor del contenuto del messaggio, fai clic su **[!UICONTROL Preview]**. Un messaggio avverte se il controllo anti-spam ha rilevato un rischio elevato per questo messaggio. Fate clic **[!UICONTROL Anti-spam analysis]** per visualizzare i dettagli.

![](assets/sending_anti-spam_analysis.png)

## Verifica della reattività del messaggio {#message-responsiveness}

Prima di inviare il messaggio, puoi verificare l’aspetto del messaggio su diversi dispositivi. In questo modo, sarà possibile visualizzarlo in modo ottimale su diversi client Web, e-mail e dispositivi.

Per consentire questo, Adobe Campaign acquisisce il rendering e lo rende disponibile in un rapporto dedicato. Questo consente di visualizzare in anteprima il messaggio inviato nei diversi contesti in cui potrebbe essere ricevuto.

Per ulteriori informazioni, consultate Rendering [e-](../../sending/using/email-rendering.md)mail.

![](assets/inbox_rendering_report_3.png)
