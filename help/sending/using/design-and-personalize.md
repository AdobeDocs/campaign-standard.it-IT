---
title: Creare contenuti personalizzati
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Scopri come progettare il contenuto del messaggio e come evitare problemi comuni che potrebbero impedire l’esecuzione della consegna. 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 9%

---

# Creare contenuti personalizzati {#build-personalized-content}

Durante la progettazione del contenuto del messaggio, cerca di evitare problemi comuni che potrebbero impedirti di eseguire la consegna. Nella maggior parte dei casi, i possibili errori sono correlati a [personalizzazione](../../designing/using/personalization.md), formattazione quando [utilizzo di un contenuto esistente](../../designing/using/using-existing-content.md) - e [conversione di un contenuto HTML](../../designing/using/using-existing-content.md#converting-an-html-content) - e [immagini](../../designing/using/images.md).

## Ottimizzare la personalizzazione {#optimize-personalization}

Per evitare problemi comuni che potrebbero impedire l’esecuzione della consegna e migliorare l’esperienza dei destinatari, Adobe Campaign consente di personalizzare i messaggi.

Puoi utilizzare i dati dei destinatari memorizzati nel database di Adobe Campaign o raccolti tramite tracciamento, pagine di destinazione, abbonamenti, ecc.
Le nozioni di base sulla personalizzazione sono presentate in [questa sezione](../../designing/using/personalization.md).

Assicurati che il contenuto del messaggio sia progettato correttamente per evitare errori, che sono generalmente correlati alla personalizzazione.

Il contenuto dinamico può essere aggiunto manualmente per visualizzare contenuti diversi ai destinatari in base alle condizioni definite nell’editor di espressioni. Quando aggiungi contenuto dinamico, devi sempre lasciare una variante predefinita per i destinatari che non soddisfano le condizioni selezionate.
Per ulteriori informazioni sul contenuto dinamico, consulta [questa sezione](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Suggerimenti** - Visualizzare l’anteprima del messaggio e-mail con diversi profili di test per verificare che il contenuto dinamico sia stato configurato correttamente.

## Creare contenuti ottimizzati {#optimize-content}

Durante la creazione delle e-mail, tieni presenti le best practice generali riportate di seguito.

* Design semplice

* Tieni presente gli utenti mobili

* Evita e-mail interamente basate su immagini

* Utilizza font sicuri per le e-mail

* Codifica caratteri speciali

### Oggetto

Lavorare su [oggetto](../../designing/using/subject-line.md) per migliorare i tassi di apertura:

* Evitare soggetti troppo lunghi. Utilizza un massimo di 50 caratteri

* Evita di usare parole ripetitive come &quot;gratuito&quot; o &quot;offerta&quot;, che potrebbero essere considerate spam

* Evita lettere maiuscole e caratteri speciali come &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

### Pagina mirror

Includi sempre un collegamento a una pagina speculare. La posizione preferita è nella parte superiore dell’e-mail. [Ulteriori informazioni](../../designing/using/personalization.md#adding-a-content-block)

### Collegamento di annullamento dell’abbonamento

Il collegamento di annullamento dell’abbonamento è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale. Scopri le linee guida per i collegamenti di annullamento dell’abbonamento [in questa sezione](../../designing/using/personalization.md#about-targeting-dimension).

Per impostazione predefinita, quando il messaggio viene analizzato, un controllo [regola di tipologia](../../sending/using/control-rules.md) controlla se è stato incluso un collegamento di rinuncia e, in caso contrario, genera un avviso.

**Suggerimento**: poiché gli errori umani sono sempre possibili, controlla che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, quando invii la bozza, accertati che il collegamento sia valido, che il modulo sia in linea e che il campo Non contattare più questo destinatario sia impostato su Sì.

Scopri come inserire un collegamento di rinuncia [in questa sezione](../../designing/using/personalization.md#adding-a-content-block).

### Dimensione e-mail {#email-size}

Per evitare problemi di prestazioni o recapito messaggi, la dimensione massima consigliata per un’e-mail è circa **35 KB**.

Per mantenere l’e-mail entro il limite, considera quanto segue:

* Rimuovi stili ridondanti o inutilizzati

* Spostare parte del contenuto dell’e-mail in una [pagina di destinazione](../../channels/using/getting-started-with-landing-pages.md)

* Minimizzare il codice

Assicurati di verificare eventuali modifiche prima dell’invio finale.

In Adobe Campaign, la dimensione massima predefinita di un’e-mail è impostata su **100 MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Se viene raggiunto il limite, il messaggio che supera il limite non riuscirà e nei registri di consegna verrà visualizzato un messaggio di errore. Gli altri messaggi della stessa consegna non saranno interessati. In tal caso, devi adattare la parte dinamica del modello e-mail o i frammenti di contenuto utilizzati dalla consegna. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

L’Adobe consiglia di mantenere il valore predefinito per la dimensione massima dei messaggi. Tuttavia, questo valore può essere modificato nel **[!UICONTROL Maximum message size]** , tramite **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu, per [amministratori funzionali](../../administration/using/users-management.md#functional-administrators) solo.

>[!IMPORTANT]
>
>Se imposti questo valore su zero, non verrà applicato alcun limite.

### Lunghezza SMS

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications). I messaggi SMS che utilizzano la codifica GSM sono limitati a 160 caratteri o 153 caratteri per SMS per messaggi inviati in più parti.

La traslitterazione consiste nel sostituire un carattere di un SMS con un altro quando quel carattere non è preso in considerazione dallo standard GSM. L’inserimento di campi di personalizzazione nel contenuto del messaggio SMS potrebbe introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Puoi autorizzare la traslitterazione di caratteri selezionando la casella corrispondente nella scheda delle impostazioni del canale SMPP della **[!UICONTROL External account]**.
Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Suggerimenti**:

* Per mantenere invariati tutti i caratteri nei messaggi SMS, ad esempio per non modificare i nomi propri, non abilitare la traslitterazione.

* Tuttavia, se i messaggi SMS contengono molti caratteri che non sono presi in considerazione dallo standard GSM, abilita la traslitterazione per limitare i costi di invio dei messaggi.

Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Progettazione reattiva delle e-mail

Il design reattivo assicura che un’e-mail venga riprodotta in modo ottimale per il dispositivo su cui viene aperta.

* Utilizza e-mail HTML responsive anziché web HTML

* Utilizza la modalità anteprima e invia bozze per testare il rendering su quanti più dispositivi possibile. Scopri come [messaggio di anteprima](../../sending/using/previewing-messages.md) prima dell’invio.

* Campaign E-mail Designer viene fornito con modelli formattati per la progettazione reattiva per dispositivi mobili. Per ulteriori informazioni, consulta [questa pagina](../../designing/using/using-reusable-content.md#content-templates).

## Gestione immagini {#manage-images}

Per l&#39;utilizzo delle immagini, attenersi alle istruzioni riportate di seguito.

### Impedisci il blocco delle immagini

Per impostazione predefinita, alcuni client di posta elettronica bloccano le immagini e alcuni utenti modificano le proprie impostazioni in modo da bloccare le immagini per il salvataggio nell’utilizzo dei dati. Pertanto, se le immagini non vengono scaricate, l’intero messaggio può andare perso. Per evitare questo problema:

* Bilancia il contenuto con immagine e testo. Evita di inviare e-mail interamente basate su immagini.

* Se il testo deve essere contenuto in un’immagine, utilizza il testo alt e il testo del titolo per assicurarti che il messaggio venga trasmesso. Personalizzate lo stile del testo alt/titolo per migliorarne l&#39;aspetto.

* Evita l’uso di immagini di sfondo, in quanto non sono supportate da alcuni client e-mail.

### Rendi le immagini dinamiche

Prova a rendere le immagini dinamiche e ridimensionabili. Tieni presente che questo può avere un impatto sui costi, poiché la generazione richiede più tempo.

### Usa riferimenti immagine assoluti

Per essere accessibili dall’esterno, le immagini utilizzate nelle e-mail e nelle risorse pubbliche collegate alle campagne devono essere presenti su un server accessibile dall’esterno.

## Anteprima del messaggio {#preview-msg}

L’Adobe consiglia di visualizzare l’anteprima del messaggio per controllarne la personalizzazione e per vedere come i destinatari visualizzeranno la consegna.

In E-mail designer, il **[!UICONTROL Preview]** consente di visualizzare il rendering di ciascun contenuto per un destinatario. I campi di personalizzazione e gli elementi condizionali del contenuto vengono sostituiti con le informazioni corrispondenti per il profilo selezionato. [Ulteriori informazioni](../../sending/using/previewing-messages.md)
