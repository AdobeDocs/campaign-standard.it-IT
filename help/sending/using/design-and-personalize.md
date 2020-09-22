---
title: Creazione di contenuti personalizzati
seo-title: Creazione di contenuti personalizzati
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa77208174960a67c67af8a6de7edbbff47355a0
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 7%

---


# Creazione di contenuti personalizzati {#build-personalized-content}

Durante la progettazione del contenuto del messaggio, cercate di evitare problemi comuni che potrebbero impedire l&#39;esecuzione della distribuzione. Nella maggior parte dei casi, eventuali errori sono correlati alla [personalizzazione](../../designing/using/personalization.md), alla formattazione quando si [utilizza un contenuto](../../designing/using/using-existing-content.md) esistente e alla [conversione di un contenuto](../../designing/using/using-existing-content.md#converting-an-html-content) HTML e [delle immagini](../../designing/using/images.md).

## Ottimizzare la personalizzazione {#optimize-personalization}

Per evitare problemi comuni che potrebbero impedire l’esecuzione della consegna e migliorare l’esperienza dei destinatari,  Adobe Campaign consente di personalizzare i messaggi.

È possibile utilizzare i dati dei destinatari memorizzati nel database Adobe Campaign  oppure raccolti tramite tracciamento, pagine di destinazione, iscrizioni ecc.
Le nozioni di base sulla personalizzazione sono presentate in [questa sezione](../../designing/using/personalization.md).

Assicurati che il contenuto del messaggio sia progettato correttamente per evitare errori, generalmente correlati alla personalizzazione.

Il contenuto dinamico può essere aggiunto manualmente per visualizzare contenuti diversi ai destinatari in base alle condizioni definite nell&#39;editor di espressioni. Quando aggiungete contenuto dinamico, dovete sempre lasciare una variante predefinita per i destinatari che non soddisfano le condizioni selezionate.
Per ulteriori informazioni sul contenuto dinamico, consulta [questa sezione](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Suggerimenti** - Visualizzate l&#39;anteprima dell&#39;e-mail con diversi profili di test per assicurarvi che il contenuto dinamico sia stato configurato correttamente.

## Creare contenuto ottimizzato {#optimize-content}

Durante la creazione delle e-mail, tieni presente le best practice generali riportate di seguito.

* Design semplice

* Ricordate gli utenti dei dispositivi mobili

* Evita e-mail basate interamente su immagini

* Utilizzo di font sicuri per le e-mail

* Codifica di caratteri speciali

### Riga oggetto

Per migliorare i tassi di apertura, si [dovrà lavorare sulla linea](../../designing/using/subject-line.md) oggetto:

* Evitare soggetti troppo lunghi. Utilizza un massimo di 50 caratteri

* Evitare di usare parole ripetitive come &quot;free&quot; o &quot;offer&quot;, che potrebbero essere considerate spam

* Evitare lettere maiuscole e caratteri speciali come &quot;!&quot;, &quot;€&quot;, &quot;€&quot;, &quot;$&quot;

### Mirror, pagina

Includi sempre un collegamento della pagina mirror. La posizione preferita è la parte superiore dell’e-mail. [Ulteriori informazioni](../../designing/using/personalization.md#adding-a-content-block)

### Collegamento di annullamento dell’abbonamento

Il collegamento di annullamento della sottoscrizione è essenziale. Deve essere visibile e valido e il modulo deve essere funzionale. Scopri le linee guida per l’annullamento della sottoscrizione [in questa sezione](../../designing/using/personalization.md#about-targeting-dimension).

Per impostazione predefinita, quando il messaggio viene analizzato, una regola di [tipo](../../sending/using/control-rules.md) di controllo verifica se è stato incluso un collegamento di rinuncia e genera un avviso in caso di assenza.

**Suggerimento**: Poiché l’errore umano è sempre possibile, verificate che il collegamento di rinuncia funzioni correttamente prima di ogni invio. Ad esempio, al momento dell&#39;invio della prova, verificare che il collegamento sia valido, che il modulo sia online e che il campo Destinatario non contatta più sia cambiato in Sì.

Scoprite come inserire un collegamento di rifiuto [in questa sezione](../../designing/using/personalization.md#adding-a-content-block).

### Dimensione e-mail

Per evitare problemi di prestazioni o di recapito, la dimensione massima consigliata per un messaggio e-mail è di circa **35 KB**.

Per mantenere l’e-mail al di sotto del limite, tenete presente quanto segue:

* Rimuovere stili ridondanti o inutilizzati

* Spostare parte del contenuto dell’e-mail in una pagina di destinazione

* Riduzione del codice

Verificare eventuali modifiche prima dell&#39;invio finale

### Lunghezza SMS

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications). I messaggi SMS che utilizzano la codifica GSM sono limitati a 160 caratteri o 153 caratteri per SMS per messaggi inviati in più parti.

La traslitterazione consiste nel sostituire un carattere di un SMS con un altro quando quel carattere non è preso in considerazione dallo standard GSM. L&#39;inserimento di campi di personalizzazione nel contenuto del messaggio SMS potrebbe introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. È possibile autorizzare la traslazione dei caratteri selezionando la casella corrispondente nella scheda delle impostazioni del canale SMPP della corrispondente **[!UICONTROL External account]**.
Ulteriori informazioni [in questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Suggerimenti**:

* Per mantenere tutti i caratteri nei messaggi SMS così come sono, per non alterare i nomi propri, ad esempio, non abilitare la traslazione.

* Tuttavia, se i vostri messaggi SMS contengono molti caratteri che non sono presi in considerazione dallo standard GSM, abilitate la traslazione per limitare i costi di invio dei vostri messaggi.

Ulteriori informazioni [in questa sezione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Progettazione e-mail reattiva

La progettazione reattiva assicura il rendering ottimale dell’e-mail per il dispositivo su cui viene aperto.

* Utilizzate HTML e-mail reattive invece di HTML Web

* Utilizzate la modalità di anteprima e inviate le prove di stampa per testare il rendering su quanti più dispositivi possibile. Scopri come visualizzare l’ [anteprima del messaggio](../../sending/using/previewing-messages.md) prima dell’invio.

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

## Anteprima del messaggio {#preview-msg}

 Adobe consiglia di visualizzare in anteprima il messaggio per verificarne la personalizzazione e vedere in che modo i destinatari vedranno la consegna.

* Nella finestra di progettazione e-mail, il **[!UICONTROL Preview]** pulsante consente di visualizzare il rendering di ciascun contenuto per un destinatario. I campi di personalizzazione e gli elementi condizionali del contenuto vengono sostituiti con le informazioni corrispondenti per il profilo selezionato. [Ulteriori informazioni](../../sending/using/previewing-messages.md)
