---
title: Controllo del contenuto delle e-mail in Adobe Campaign Standard
description: Scopri come migliorare il recapito messaggi in Adobe Campaign Standard durante la modifica del contenuto delle e-mail.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 8%

---

# Controllo dei contenuti dell’e-mail{#control-email-content}

<!--TO KEEP because specific to Campaign-->

Per essere sicuri che le e-mail raggiungano i destinatari e migliorino il tasso di recapito delle e-mail, devono rispettare una serie di regole. In caso contrario, il contenuto di alcuni messaggi può essere rilevato come spam. Adobe Campaign offre diversi strumenti per rendere i contenuti conformi a queste regole.

Segui i principi elencati di seguito durante la progettazione del contenuto del messaggio:

* [Nome e indirizzo del mittente](#sender-name): l&#39;indirizzo deve identificare esplicitamente il mittente. Il dominio deve essere di proprietà e registrato al mittente. Il registro di dominio non deve essere privatizzato.

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalizzazione e ottimizzazione del tempo di invio](#perso-send-time-optimization): la personalizzazione del contenuto e la definizione del tempo di invio per destinatario aumentano le possibilità di apertura del messaggio.
* Immagini e testo: rispettare un rapporto testo/immagine decente (ad esempio 60% di testo e 40% di immagini).
* [Collegamento di annullamento dell’abbonamento](#opt-out) e pagina di destinazione: il collegamento di annullamento dell’abbonamento è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale.
* Anteprima: utilizza gli strumenti offerti da Adobe Campaign per controllare e ottimizzare il contenuto della tua e-mail ([Analisi anti-spam](#anti-spam-analysis), [Rendering di e-mail](#message-responsiveness)).

Per ulteriori suggerimenti su come ottimizzare il recapito messaggi durante la progettazione dei contenuti, consulta la sezione [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html).

>[!NOTE]
>
>Per ulteriori informazioni sulla modifica del contenuto delle e-mail, consulta la [Panoramica di E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) e [Best practice per la progettazione dei messaggi](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nome e indirizzo del mittente {#sender-name}

Alcuni ISP controllano la validità dell’indirizzo del mittente (**[!UICONTROL From]**) prima di accettare i messaggi. Un indirizzo formato in modo non corretto può causare il rifiuto da parte del server ricevente.

![](assets/delivery_content_edition16.png)

Devi accertarti che l’indirizzo corretto sia indicato a livello di istanza o negli scenari più utilizzati. A questo scopo, contatta l’amministratore.

Per ulteriori informazioni, consulta [Definizione del mittente dell’e-mail di un messaggio e-mail](../../designing/using/subject-line.md#email-sender).

## Personalizzazione e ottimizzazione del tempo di invio {#perso-send-time-optimization}

Per migliorare l’esperienza dei destinatari e farli aprire l’e-mail, Adobe Campaign ti consente di personalizzare i messaggi. Per ulteriori informazioni, consulta [questa sezione](../../designing/using/personalization.md).

Per aumentare il tasso di apertura dei messaggi, puoi anche definire manualmente un tempo di invio per destinatario. Laddove possibile, ogni profilo riceverà il messaggio alla data e all’orario specificati. Per ulteriori informazioni, consulta [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md).

## Collegamento e modulo di rinuncia {#opt-out}

Per impostazione predefinita, quando il messaggio viene analizzato, una regola di tipologia controlla se è stato incluso un collegamento di rinuncia e genera un avviso in caso di assenza. Per ulteriori informazioni sulla gestione dei collegamenti, consulta [questa sezione](../../designing/using/links.md).

Devi verificare che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando [invio della prova](../../sending/using/sending-proofs.md), assicurati che il collegamento sia valido, che il modulo sia online e che la convalida di questo controlli il **[!UICONTROL No longer contact]** scatole. È necessario eseguire questo controllo sistematicamente perché l’errore umano è sempre possibile quando si inserisce il collegamento o si modifica il modulo. Per ulteriori informazioni sulla gestione del consenso e del diniego, consulta [questa sezione](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

Se viene rilevato un problema relativo all’annullamento dell’abbonamento dopo l’avvio della consegna, è comunque possibile eseguire manualmente un’annullamento dell’abbonamento (utilizzando, ad esempio, la funzione di aggiornamento di massa) per i destinatari che fanno clic sul collegamento di rinuncia anche se non sono stati in grado di confermare la scelta.

Come regola generale, non devi cercare di ostacolare i destinatari che desiderano rinunciare richiedendo loro di compilare campi come ad esempio il loro indirizzo e-mail o nome. La pagina di destinazione per l’annullamento dell’abbonamento deve avere un solo pulsante di convalida.

La richiesta di conferma aggiuntiva non è affidabile: un utente può avere due indirizzi e-mail reindirizzati alla stessa casella (ad esempio: firstname.lastname@club.com e firstname.lastname@internet-club.com). Se il profilo è in grado di ricordare solo il primo indirizzo e desidera annullare l’iscrizione tramite un messaggio inviato all’altro, questo verrà rifiutato dal modulo perché l’identificatore crittografato e l’indirizzo e-mail inserito non corrisponderanno.

## Analisi anti-spam {#anti-spam-analysis}

L’editor dei messaggi di Adobe Campaign integra un **Analisi anti-spam** che consente di valutare le e-mail per determinare se un messaggio corre il rischio di essere considerato come spam dagli strumenti anti-spam utilizzati al momento della ricezione. Per ulteriori informazioni, consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

Nell’editor del contenuto dei messaggi, fai clic su **[!UICONTROL Preview]**. Un messaggio ti avverte se il controllo anti-spam ha rilevato un rischio elevato per questo messaggio. Fai clic su **[!UICONTROL Anti-spam analysis]** per visualizzare i dettagli.

![](assets/sending_anti-spam_analysis.png)

## Rendering di e-mail {#message-responsiveness}

Prima di inviare il messaggio, puoi verificarne la reattività controllando l’aspetto del messaggio su diversi dispositivi. In questo modo sarà possibile visualizzarlo in modo ottimale su una varietà di client web, e-mail web e dispositivi.

![](assets/inbox_rendering_report_3.png)

Per ottenere questo risultato, Adobe Campaign acquisisce il rendering e lo rende disponibile in un report dedicato. Ciò ti permette di visualizzare in anteprima il messaggio inviato nei vari contesti in cui potrebbe essere ricevuto.

Per ulteriori informazioni, consulta [Rendering e-mail](../../sending/using/email-rendering.md).
