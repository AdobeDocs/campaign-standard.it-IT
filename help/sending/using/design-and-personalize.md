---
solution: Campaign Standard
product: campaign
title: Creare contenuti personalizzati
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Scopri come progettare il contenuto dei messaggi e cerca di evitare problemi comuni che potrebbero impedire l’esecuzione della consegna. 
feature: Recapito messaggi
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 7%

---

# Creare contenuti personalizzati {#build-personalized-content}

Durante la progettazione del contenuto del messaggio, cerca di evitare problemi comuni che potrebbero impedire l’esecuzione della consegna. Nella maggior parte dei casi, i possibili errori sono correlati alla [personalizzazione](../../designing/using/personalization.md), alla formattazione quando [si utilizza un contenuto esistente](../../designing/using/using-existing-content.md) e alla [conversione di un contenuto HTML](../../designing/using/using-existing-content.md#converting-an-html-content) e [immagini](../../designing/using/images.md).

## Ottimizzare la personalizzazione {#optimize-personalization}

Per evitare problemi comuni che potrebbero impedire l’esecuzione della consegna e migliorare l’esperienza dei destinatari, Adobe Campaign ti consente di personalizzare i messaggi.

Puoi utilizzare i dati dei destinatari memorizzati nel database di Adobe Campaign o raccolti tramite tracciamento, pagine di destinazione, abbonamenti, ecc.
Le nozioni di base sulla personalizzazione sono presentate in [questa sezione](../../designing/using/personalization.md).

Assicurati che il contenuto del messaggio sia progettato correttamente per evitare errori, generalmente correlati alla personalizzazione.

Puoi aggiungere manualmente il contenuto dinamico per visualizzare contenuti diversi ai destinatari in base alle condizioni definite nell’editor espressioni. Quando aggiungi contenuto dinamico, devi sempre lasciare una variante predefinita per i destinatari che non soddisfano le condizioni selezionate.
Per ulteriori informazioni sul contenuto dinamico, consulta [questa sezione](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Suggerimenti** : visualizza l’anteprima del messaggio e-mail con diversi profili di test per assicurarti che il contenuto dinamico sia stato configurato correttamente.

## Creare contenuti ottimizzati {#optimize-content}

Quando crei le e-mail, ricorda le best practice generali riportate di seguito.

* Mantieni il design semplice

* Tenere a mente gli utenti dei dispositivi mobili

* Evita e-mail interamente basate su immagini

* Utilizza font sicuri per e-mail

* Codifica caratteri speciali

### Linea oggetto

Lavora sulla [riga oggetto](../../designing/using/subject-line.md) per migliorare i tassi di apertura:

* Evita soggetti troppo lunghi. Utilizza un massimo di 50 caratteri

* Evita di usare parole ripetitive come &quot;libero&quot; o &quot;offerta&quot;, che potrebbero essere considerate come spam

* Evitare lettere maiuscole e caratteri speciali come &quot;!&quot;, &quot; £&quot;, &quot;€&quot;, &quot;$&quot;

### Pagina speculare

Includi sempre un collegamento alla pagina speculare. La posizione preferita è la parte superiore dell’e-mail. [Ulteriori informazioni](../../designing/using/personalization.md#adding-a-content-block)

### Collegamento di annullamento dell’abbonamento

Il collegamento di annullamento dell’abbonamento è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale. Scopri le linee guida per l’annullamento dell’abbonamento [in questa sezione](../../designing/using/personalization.md#about-targeting-dimension).

Per impostazione predefinita, quando il messaggio viene analizzato, un controllo [regola di tipologia](../../sending/using/control-rules.md) controlla se è stato incluso un collegamento di rinuncia e genera un avviso se manca.

**Suggerimento**: Poiché l’errore umano è sempre possibile, controlla che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando invii la bozza, accertati che il collegamento sia valido, che il modulo sia online e che il campo Destinatario non venga più contattato sia stato modificato in Sì.

Scopri come inserire un collegamento di rinuncia [in questa sezione](../../designing/using/personalization.md#adding-a-content-block).

### Dimensione e-mail {#email-size}

Per evitare problemi di prestazioni o recapito messaggi, la dimensione massima consigliata di un messaggio e-mail è di circa **35 KB**.

Per mantenere l’e-mail sotto il limite, considera quanto segue:

* Rimuovere gli stili ridondanti o inutilizzati

* Sposta parte del contenuto delle e-mail in una [pagina di destinazione](../../channels/using/getting-started-with-landing-pages.md)

* Minimizzare il codice

Verifica eventuali modifiche prima dell’invio finale.

In Adobe Campaign, la dimensione massima predefinita di un messaggio e-mail è impostata su **100MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Se il limite viene raggiunto, il messaggio che supera il limite avrà esito negativo e nei registri di consegna verrà visualizzato un messaggio di errore. Gli altri messaggi della stessa consegna non saranno interessati. In tal caso, devi adattare la parte dinamica del modello e-mail o i frammenti di contenuto utilizzati dalla consegna. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Ad Adobe, si consiglia di mantenere il valore predefinito della dimensione massima del messaggio. Tuttavia, questo valore può essere modificato nell&#39;opzione **[!UICONTROL Maximum message size]**, tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**, solo da [amministratori funzionali](../../administration/using/users-management.md#functional-administrators).

>[!IMPORTANT]
>
>Se imposti questo valore su zero, non verrà applicato alcun limite.

### Lunghezza SMS

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications). I messaggi SMS che utilizzano la codifica GSM sono limitati a 160 caratteri o 153 caratteri per SMS per messaggi inviati in più parti.

La traslitterazione consiste nel sostituire un carattere di un SMS con un altro quando quel carattere non è preso in considerazione dallo standard GSM. Tieni presente che l’inserimento di campi di personalizzazione nel contenuto del messaggio SMS può introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Puoi autorizzare la traslitterazione dei caratteri selezionando la casella corrispondente nella scheda delle impostazioni del canale SMPP della **[!UICONTROL External account]** corrispondente.
Ulteriori informazioni [in questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Suggerimenti**:

* Per mantenere tutti i caratteri nei messaggi SMS così come sono, per non modificare i nomi propri, ad esempio, non abilitare la traslitterazione.

* Tuttavia, se i messaggi SMS contengono molti caratteri che non vengono presi in considerazione dallo standard GSM, abilita la traslitterazione per limitare i costi di invio dei messaggi.

Ulteriori informazioni [in questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Progettazione e-mail reattiva

La progettazione reattiva assicura il rendering ottimale di un’e-mail per il dispositivo su cui viene aperta.

* Utilizza l’HTML dell’e-mail reattiva anziché l’HTML del web

* Utilizza la modalità anteprima e invia bozze per testare il rendering su quanti più dispositivi possibile. Scopri come [visualizzare in anteprima il messaggio](../../sending/using/previewing-messages.md) prima dell’invio.

* E-mail Designer di Campaign viene fornito con modelli in formato dinamico per la progettazione per dispositivi mobili. Per ulteriori informazioni, consulta [questa pagina](../../designing/using/using-reusable-content.md#content-templates).

## Gestire le immagini {#manage-images}

Segui le linee guida riportate di seguito quando si tratta di utilizzare le immagini.

### Impedisci il blocco delle immagini

Alcuni client di posta elettronica bloccano le immagini per impostazione predefinita e alcuni utenti modificano le impostazioni per bloccare le immagini per il salvataggio sull’utilizzo dei dati. Pertanto, se le immagini non vengono scaricate, l&#39;intero messaggio può essere perso. Per evitare questo:

* Bilancia il contenuto con immagine e testo. Evita e-mail interamente basate su immagini.

* Se il testo deve essere contenuto in un’immagine, utilizza il testo alt e title per assicurarti che il messaggio venga trasmesso. Personalizzare lo stile del testo alt/title per migliorarne l’aspetto.

* Evita l’uso di immagini in background in quanto non sono supportate da alcuni client e-mail.

### Rendere le immagini reattive

Prova a rendere le immagini reattive e ridimensionabili. Tieni presente che questo può avere un impatto sui costi in quanto la creazione richiede più tempo.

### Usa riferimenti di immagine assoluti

Per essere accessibile dall’esterno, le immagini utilizzate nelle e-mail e nelle risorse pubbliche collegate alle campagne devono essere presenti su un server accessibile dall’esterno.

## Anteprima del messaggio {#preview-msg}

Adobe consiglia di visualizzare l’anteprima del messaggio per verificarne la personalizzazione e il modo in cui i destinatari visualizzeranno la consegna.

Nella finestra di progettazione e-mail, il pulsante **[!UICONTROL Preview]** consente di visualizzare il rendering di ciascun contenuto per un destinatario. I campi di personalizzazione e gli elementi condizionali del contenuto vengono sostituiti con le informazioni corrispondenti per il profilo selezionato. [Ulteriori informazioni](../../sending/using/previewing-messages.md)
