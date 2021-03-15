---
solution: Campaign Standard
product: campaign
title: Controllo del contenuto delle e-mail in Adobe Campaign Standard
description: Scopri come migliorare il recapito messaggi in Adobe Campaign Standard durante la modifica del contenuto delle e-mail.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 8%

---


# Controllo di contenuti e-mail{#control-email-content}

Per migliorare il tasso di recapito dei messaggi e-mail e assicurarsi che le e-mail raggiungano i destinatari, l’e-mail deve rispettare un certo numero di regole.

* **Nome e indirizzo** del mittente: L&#39;indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà e registrato al mittente. Il registro di dominio non deve essere privatizzato.
* **Oggetto**: Evitare la capitalizzazione e la punteggiatura eccessive, e le parole che sono spesso utilizzate dagli spammer (&quot;Win&quot;, &quot;Free&quot;, ecc.).
* **Personalizza l’e-mail**: La personalizzazione dell’e-mail aumenta le possibilità di apertura del messaggio.
* **Immagini e testo**: Rispetta un rapporto testo/immagine decente (ad esempio 60% di testo e 40% di immagini).
* **Collegamento di annullamento dell’abbonamento e pagina** di destinazione: Il collegamento di annullamento dell’abbonamento è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale.
* **Utilizza** gli strumenti offerti da Adobe Campaign per ottimizzare il contenuto dell’e-mail (analisi della consegna, analisi anti-spam).

Per ulteriori informazioni sulla modifica del contenuto delle e-mail, consulta la [panoramica di E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) e le [best practice per la progettazione dei messaggi](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nome e indirizzo del mittente {#sender-name}

Alcuni ISP controllano la validità dell’indirizzo del mittente (Da) prima di accettare i messaggi. Un indirizzo formato in modo non corretto può causare il rifiuto da parte del server ricevente. Devi accertarti che l’indirizzo corretto sia indicato a livello di istanza o negli scenari più utilizzati. Contattare l&#39;amministratore.

![](assets/delivery_content_edition16.png)

Per ulteriori informazioni, consulta [Personalizzazione del nome del mittente](../../designing/using/personalization.md#personalizing-the-sender).

## Ottimizzazione del tempo di invio {#send-time-optimization}

Per migliorare la frequenza di successo dei messaggi, puoi definire manualmente un orario di invio per destinatario. Laddove possibile, ogni profilo riceverà il messaggio alla data e all’orario specificati.

Per ulteriori informazioni, consulta [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md).

## Collegamento e modulo di rinuncia {#opt-out}

Per impostazione predefinita, quando il messaggio viene analizzato, una regola di tipologia controlla se è stato incluso un collegamento di rinuncia e genera un avviso in caso di assenza.

Devi verificare che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando invii la bozza, accertati che il collegamento sia valido, che il modulo sia online e che la convalida di queste modifiche selezioni il valore delle caselle Non più contatti. È necessario eseguire questo controllo sistematicamente perché l’errore umano è sempre possibile quando si inserisce il collegamento o si modifica il modulo.

Se viene rilevato un problema relativo all’annullamento dell’abbonamento dopo l’avvio della consegna, è comunque possibile eseguire manualmente un’annullamento dell’abbonamento (utilizzando, ad esempio, la funzione di aggiornamento di massa) per i destinatari che fanno clic sul collegamento di rinuncia anche se non sono stati in grado di confermare la scelta.

Come regola generale, non cercare di ostacolare i destinatari che desiderano rinunciare richiedendo loro di compilare campi come ad esempio il loro indirizzo e-mail o nome. La pagina di destinazione per l’annullamento dell’abbonamento deve avere un solo pulsante di convalida. La richiesta di conferma aggiuntiva non è affidabile: un utente può avere due indirizzi e-mail reindirizzati alla stessa casella (ad esempio: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se il profilo è in grado di ricordare solo il primo indirizzo e desidera annullare l’iscrizione tramite un messaggio inviato all’altro, questo verrà rifiutato dal modulo perché l’identificatore crittografato e l’indirizzo e-mail inserito non corrisponderanno.

## Analisi anti-spam {#anti-spam-analysis}

L’editor dei messaggi di Adobe Campaign integra un’ **Analisi anti-spam** che consente di valutare le e-mail per determinare se un messaggio corre il rischio di essere considerato come spam dagli strumenti anti-spam utilizzati al momento della ricezione. Per ulteriori informazioni, consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

Nell’editor del contenuto dei messaggi, fai clic su **[!UICONTROL Preview]**. Un messaggio ti avverte se il controllo anti-spam ha rilevato un rischio elevato per questo messaggio. Fai clic su **[!UICONTROL Anti-spam analysis]** per visualizzare i dettagli.

![](assets/sending_anti-spam_analysis.png)

## Controllo della reattività del messaggio {#message-responsiveness}

Prima di inviare il messaggio, puoi controllare l’aspetto del messaggio su diversi dispositivi. In questo modo sarà possibile visualizzarlo in modo ottimale su una varietà di client web, e-mail web e dispositivi.

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

Per ulteriori informazioni, consulta [Rendering e-mail](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
