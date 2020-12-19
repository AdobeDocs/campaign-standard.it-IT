---
solution: Campaign Standard
product: campaign
title: Creare contenuti personalizzati
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Creare contenuti personalizzati {#build-personalized-content}

Durante la progettazione del contenuto del messaggio, cercate di evitare problemi comuni che potrebbero impedire l&#39;esecuzione della distribuzione. Nella maggior parte dei casi, eventuali errori sono correlati a [personalizzazione](../../designing/using/personalization.md), formattazione quando si utilizza [un contenuto esistente](../../designing/using/using-existing-content.md) e [conversione di un contenuto HTML](../../designing/using/using-existing-content.md#converting-an-html-content) e [immagini](../../designing/using/images.md).

## Ottimizzazione della personalizzazione {#optimize-personalization}

Per evitare problemi comuni che potrebbero impedire l’esecuzione della consegna e migliorare l’esperienza dei destinatari,  Adobe Campaign consente di personalizzare i messaggi.

È possibile utilizzare i dati dei destinatari memorizzati nel database Adobe Campaign  oppure raccolti tramite tracciamento, pagine di destinazione, iscrizioni ecc.
Le nozioni di base sulla personalizzazione sono presentate in [questa sezione](../../designing/using/personalization.md).

Assicurati che il contenuto del messaggio sia progettato correttamente per evitare errori, generalmente correlati alla personalizzazione.

Il contenuto dinamico può essere aggiunto manualmente per visualizzare contenuti diversi ai destinatari in base alle condizioni definite nell&#39;editor di espressioni. Quando aggiungete contenuto dinamico, dovete sempre lasciare una variante predefinita per i destinatari che non soddisfano le condizioni selezionate.
Per ulteriori informazioni sul contenuto dinamico, consultare la sezione [this](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Suggerimenti**  - Visualizzate l&#39;anteprima dell&#39;e-mail con diversi profili di test per assicurarvi che il contenuto dinamico sia stato configurato correttamente.

## Creazione di contenuto ottimizzato {#optimize-content}

Durante la creazione delle e-mail, tieni presente le best practice generali riportate di seguito.

* Design semplice

* Ricordate gli utenti dei dispositivi mobili

* Evita e-mail basate interamente su immagini

* Utilizzo di font sicuri per le e-mail

* Codifica di caratteri speciali

### Riga oggetto

Lavorare sulla [linea oggetto](../../designing/using/subject-line.md) per migliorare le tariffe aperte:

* Evitare soggetti troppo lunghi. Utilizza un massimo di 50 caratteri

* Evitare di usare parole ripetitive come &quot;free&quot; o &quot;offer&quot;, che potrebbero essere considerate spam

* Evitare lettere maiuscole e caratteri speciali come &quot;!&quot;, &quot;€&quot;, &quot;€&quot;, &quot;$&quot;

### Mirror, pagina

Includi sempre un collegamento della pagina mirror. La posizione preferita è la parte superiore dell’e-mail. [Ulteriori informazioni](../../designing/using/personalization.md#adding-a-content-block)

### Collegamento di annullamento dell’abbonamento

Il collegamento di annullamento della sottoscrizione è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale. Scopri le linee guida relative ai collegamenti di annullamento dell&#39;iscrizione [in questa sezione](../../designing/using/personalization.md#about-targeting-dimension).

Per impostazione predefinita, quando il messaggio viene analizzato, un controllo [regola di tipologia](../../sending/using/control-rules.md) controlla se è stato incluso un collegamento di rinuncia e genera un avviso se risulta mancante.

**Suggerimento**: Poiché l’errore umano è sempre possibile, verificate che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, al momento dell&#39;invio della prova, verificare che il collegamento sia valido, che il modulo sia online e che il campo Destinatario non contatta più sia cambiato in Sì.

Scoprite come inserire un collegamento di rinuncia [in questa sezione](../../designing/using/personalization.md#adding-a-content-block).

### Dimensione e-mail

Per evitare problemi di prestazioni o di recapito, la dimensione massima consigliata per un messaggio e-mail è di circa **35 KB**.

Per mantenere l’e-mail al di sotto del limite, tenete presente quanto segue:

* Rimuovere stili ridondanti o inutilizzati

* Spostare parte del contenuto dell’e-mail in una pagina di destinazione

* Riduzione del codice

Verificare eventuali modifiche prima dell&#39;invio finale

### Lunghezza SMS

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications). I messaggi SMS che utilizzano la codifica GSM sono limitati a 160 caratteri o 153 caratteri per SMS per messaggi inviati in più parti.

La traslitterazione consiste nel sostituire un carattere di un SMS con un altro quando quel carattere non è preso in considerazione dallo standard GSM. L&#39;inserimento di campi di personalizzazione nel contenuto del messaggio SMS potrebbe introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. È possibile autorizzare la traslazione dei caratteri selezionando la casella corrispondente nella scheda delle impostazioni del canale SMPP della **[!UICONTROL External account]** corrispondente.
Ulteriori informazioni [in questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Suggerimenti**:

* Per mantenere tutti i caratteri nei messaggi SMS così come sono, per non alterare i nomi propri, ad esempio, non abilitare la traslazione.

* Tuttavia, se i vostri messaggi SMS contengono molti caratteri che non sono presi in considerazione dallo standard GSM, abilitate la traslazione per limitare i costi di invio dei vostri messaggi.

Ulteriori informazioni [in questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Progettazione e-mail reattiva

La progettazione reattiva assicura il rendering ottimale dell’e-mail per il dispositivo su cui viene aperto.

* Utilizzate HTML e-mail reattive invece di HTML Web

* Utilizzate la modalità di anteprima e inviate le prove di stampa per testare il rendering su quanti più dispositivi possibile. Scopri come visualizzare l&#39;anteprima del messaggio [prima dell&#39;invio.](../../sending/using/previewing-messages.md)

* Campaign Email Designer viene fornito con modelli reattivi per la progettazione di contenuti per dispositivi mobili. Ulteriori informazioni [in questa pagina](../../designing/using/using-reusable-content.md#content-templates).

## Gestire le immagini {#manage-images}

Seguite le linee guida riportate di seguito quando si tratta di usare le immagini.

### Impedire il blocco delle immagini

Per impostazione predefinita, alcuni client e-mail bloccano le immagini e alcuni utenti modificano le proprie impostazioni per bloccare le immagini da salvare in base all’utilizzo dei dati. Pertanto, se le immagini non vengono scaricate, l&#39;intero messaggio può andare perso. Per evitare ciò:

* Bilancia i contenuti con immagini e testo. Evitate e-mail basate interamente su immagini.

* Se il testo deve essere contenuto in un’immagine, usate il testo alternativo e del titolo per essere certi che il messaggio possa essere trasmesso. Applicate uno stile al testo alt/title per migliorarne l’aspetto.

* Evitate l’utilizzo di immagini di sfondo poiché non sono supportate da alcuni client e-mail.

### Rendere le immagini reattive

Cercate di rendere le immagini reattive e ridimensionabili. Questo può avere un impatto sui costi in quanto la creazione richiede più tempo.

### Utilizzare riferimenti di immagine assoluti

Per essere accessibili dall&#39;esterno, le immagini utilizzate nelle e-mail e nelle risorse pubbliche collegate alle campagne devono essere presenti su un server esterno accessibile.

## Visualizza in anteprima il messaggio {#preview-msg}

 Adobe consiglia di visualizzare in anteprima il messaggio per verificarne la personalizzazione e vedere in che modo i destinatari vedranno la consegna.

Nella finestra di progettazione e-mail, il pulsante **[!UICONTROL Preview]** consente di visualizzare il rendering di ciascun contenuto per un destinatario. I campi di personalizzazione e gli elementi condizionali del contenuto vengono sostituiti con le informazioni corrispondenti per il profilo selezionato. [Ulteriori informazioni](../../sending/using/previewing-messages.md)
