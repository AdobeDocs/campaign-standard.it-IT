---
solution: Campaign Standard
product: campaign
title: Controllo del contenuto delle e-mail in  Adobe Campaign Standard
description: Scoprite come migliorare la recapito in  Adobe Campaign Standard durante la modifica del contenuto delle e-mail.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 1e7359db2de1a9c420af33ac85c0597c098ae3f8
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 8%

---


# Controllo di contenuti e-mail{#control-email-content}

Per migliorare il tasso di recapito delle e-mail e assicurarsi che le e-mail arrivino ai destinatari, l&#39;e-mail deve rispettare un certo numero di regole.

* **Nome e indirizzo** del mittente: L&#39;indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà e registrato del mittente. Il registro di dominio non deve essere privatizzato.
* **Oggetto**: Evitare l&#39;eccessiva capitalizzazione e punteggiatura, e le parole che sono frequentemente utilizzate dagli spammer (&quot;Win&quot;, &quot;Free&quot;, ecc.).
* **Personalizza il tuo messaggio e-mail**: La personalizzazione dell’e-mail aumenta le possibilità di apertura del messaggio.
* **Immagini e testo**: Rispetta un rapporto testo/immagine decente (ad esempio, testo al 60% e immagini al 40%).
* **Rimuovi iscrizione e pagina** di destinazione: Il collegamento di annullamento della sottoscrizione è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale.
* **Utilizzate** gli strumenti offerti da  Adobe Campaign per ottimizzare il contenuto dell&#39;e-mail (analisi della distribuzione, analisi anti-spam).

Per ulteriori informazioni sulla modifica del contenuto delle e-mail, consultare la [panoramica di Designer e-mail](../../designing/using/designing-content-in-adobe-campaign.md) e le [procedure ottimali per la progettazione dei messaggi](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nome e indirizzo del mittente {#sender-name}

Alcuni ISP controllano la validità dell&#39;indirizzo del mittente (Da) prima di accettare i messaggi. Un indirizzo con formato non corretto potrebbe essere rifiutato dal server ricevente. È necessario assicurarsi che l&#39;indirizzo corretto sia specificato a livello di istanza o negli scenari più frequentemente utilizzati. Contattate l’amministratore.

![](assets/delivery_content_edition16.png)

Per ulteriori informazioni, vedere [Personalizzazione del nome del mittente](../../designing/using/personalization.md#personalizing-the-sender).

## Ottimizzazione dell&#39;ora di invio {#send-time-optimization}

Per migliorare il tasso di successo dei messaggi, puoi definire manualmente un orario di invio per destinatario. Laddove possibile, ogni profilo riceverà il messaggio alla data e all’orario specificati.

Per ulteriori informazioni, vedere [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md).

## Collegamento e modulo di rifiuto {#opt-out}

Per impostazione predefinita, quando il messaggio viene analizzato, una regola di tipologia verifica se è stato incluso un collegamento di rinuncia e genera un avviso se risulta mancante.

È necessario verificare che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando si invia la prova, verificare che il collegamento sia valido, che il modulo sia in linea e che la convalida di tali modifiche venga convalidato il valore delle caselle di contatto No più. È consigliabile eseguire questo controllo in modo sistematico perché l&#39;errore umano è sempre possibile quando si inserisce il collegamento o si modifica il modulo.

Se viene rilevato un problema relativo all&#39;annullamento dell&#39;iscrizione dopo l&#39;avvio della consegna, è comunque possibile eseguire un&#39;annullamento dell&#39;iscrizione manualmente (utilizzando, ad esempio, la funzione di aggiornamento di massa) per i destinatari che fanno clic sul collegamento di annullamento dell&#39;iscrizione anche se non sono stati in grado di confermare la scelta.

Come regola generale, non cercate di ostacolare i destinatari che desiderano rifiutare richiedendo loro di compilare campi quali ad esempio il loro indirizzo e-mail o nome. La pagina di destinazione per l’annullamento della sottoscrizione deve contenere un solo pulsante di convalida. La richiesta di conferma aggiuntiva non è affidabile: un utente può avere due indirizzi e-mail reindirizzati alla stessa casella (ad esempio: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se il profilo è in grado di ricordare solo il primo indirizzo e desidera annullare l&#39;iscrizione tramite un messaggio inviato all&#39;altro, il modulo rifiuterà l&#39;operazione perché l&#39;identificatore crittografato e l&#39;indirizzo e-mail immesso non corrisponderanno.

## Analisi anti-spam {#anti-spam-analysis}

 editor messaggi Adobe Campaign integra un **analisi anti-spam** che consente di segnare le e-mail per determinare se un messaggio corre il rischio di essere considerato come spam dagli strumenti anti-spam utilizzati al momento della ricezione. Per ulteriori informazioni, vedere [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

Nell&#39;editor del contenuto del messaggio, fai clic su **[!UICONTROL Preview]**. Un messaggio avverte se il controllo anti-spam ha rilevato un rischio elevato per questo messaggio. Fare clic su **[!UICONTROL Anti-spam analysis]** per visualizzare i dettagli.

![](assets/sending_anti-spam_analysis.png)

## Verifica della risposta del messaggio {#message-responsiveness}

Prima di inviare il messaggio, puoi verificare l’aspetto del messaggio su diversi dispositivi. In questo modo, sarà possibile visualizzarlo in modo ottimale su una varietà di client Web, e-mail e dispositivi Web.

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

Per ulteriori informazioni, consulta [Rendering e-mail](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
