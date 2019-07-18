---
title: Personalizzazione dell'oggetto di un'e-mail
seo-title: Personalizzazione dell'oggetto di un'e-mail
description: Personalizzazione dell'oggetto di un'e-mail
seo-description: È possibile personalizzare l'oggetto di un'e-mail, ma anche provare diversi oggetti e ottenere una stima della relativa frequenza di apertura.
page-status-flag: never-activated
uuid: 345 b 5 f 4 b -8 e 2 c -4 f 8 e-postal 7-0 e 9 b 40 a 44932
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: personalizzazione del contenuto
discoiquuid: f 7 a 5 e 935-54 cf -422 e -8459-27221409 a 200
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Personalizing the subject line of an email{#personalizing-the-subject-line-of-an-email}

## Personalizing an email subject {#personalizing-an-email-subject}

L'oggetto del messaggio è obbligatorio per preparare e inviare il messaggio.

>[!NOTE]
>
>Se l'oggetto è vuoto, viene visualizzato un avviso nel dashboard Messaggio e in Email Designer.

To configure the email subject, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon) and fill in the **[!UICONTROL Subject]** section.

![](assets/email_designer_subject.png)

Puoi anche aggiungere campi personalizzati, blocchi di contenuto e contenuti dinamici all'oggetto facendo clic sulle icone corrispondenti.

**Argomenti correlati:**

* [Inserimento di un campo personalizzato](../../designing/using/inserting-a-personalization-field.md)
* [Aggiunta di un blocco di contenuto](../../designing/using/adding-a-content-block.md)
* [Definizione del contenuto dinamico in un'e-mail](../../designing/using/defining-dynamic-content-in-an-email.md)

## Predictive subject line {#predictive-subject-line}

Quando si modifica un'e-mail, è possibile provare diversi oggetti e ottenere una stima della relativa frequenza prima di inviarla.

Per impostazione predefinita questa funzione è disattivata. Viene attivato quando viene importato il primo modello. Un modello è il risultato di set di dati della formazione specifici di un determinato settore. I modelli consentono al sistema di prevedere la velocità di apertura dell'e-mail quando viene inviata una nuova riga.

>[!NOTE]
>
>Questa funzione è disponibile per i messaggi e-mail e per i database contenenti contenuto inglese. Il modello preparato non sarà coerente e darà luogo a risultati erronei se l'istanza contiene e-mail in altre lingue. L'opzione che consente di testare un oggetto è visibile solo se nell'istanza è già disponibile un modello.

### Testing a subject {#testing-a-subject}

Per provare l'oggetto:

1. Crea o apri l'e-mail.
1. Aprite il contenuto e inserite l'oggetto dell'e-mail nel campo di immissione corrispondente.
1. Click the **[!UICONTROL Test subject]** button to access the **[!UICONTROL Test your subject line]** window. Potete comunque modificare l'oggetto da questa finestra.
1. Seleziona il modello corretto da considerare per la stima della frequenza aperta. Sono disponibili diversi modelli, ciascuno dei quali corrisponde a un settore specifico.
1. Click **[!UICONTROL Test]**.

L'oggetto viene quindi analizzato.

>[!NOTE]
>
>Se l'oggetto è troppo breve, non può essere analizzato e viene visualizzato un messaggio di errore.

Vengono calcolati diversi indicatori e viene visualizzato un set di strumenti:

* **Tasso di apertura previsto**: Questo grafico fornisce un'idea del tasso di apertura previsto per l'e-mail con l'oggetto corrente.
* **Lunghezza oggetto**: Questo indicatore consente di verificare se la lunghezza corrente dell'oggetto è corretta o se deve essere più lunga o più breve.
* **Parole colorate**: Quando si verifica l'oggetto, le parole evidenziate in verde sono le parole che contribuiscono maggiormente ad aumentare la stima delle percentuali di apertura. Le parole evidenziate in rosso sono parole che contribuiscono al minimo per aumentare la stima di apertura. Se si aggiungono o si rimuovono parole in oggetto, le parole evidenziate cambiano.
* **Categorie e suggerimenti per le parole**: Verso la parte inferiore della finestra, vengono visualizzate diverse categorie rilevanti per il modello selezionato. Queste categorie sono ordinate per ordine di importanza e consentono di vedere se l'oggetto contiene parole associate tramite un simbolo di spunta. Ciascuna categoria contiene una serie di parole suggerite che possono essere utilizzate nel tuo oggetto per renderlo più rilevante e aumentare il tasso di apertura. Queste parole sono parole utilizzate più spesso in una determinata categoria.

>[!NOTE]
>
>I campi di personalizzazione e i segni di punteggiatura vengono rimossi dall'analisi oggetto. Nel caso del testo dinamico/condizionale, tutte le varianti vengono considerate come un unico oggetto.

![](assets/predictive_subject_line_example.png)

### Importing models {#importing-models}

Per impostazione predefinita, non esiste alcun modello in esecuzione sul server Adobe Campaign. Esistono due modi per ottenere un modello e attivare la funzione:

* Puoi formare un modello locale dai dati dei messaggi e-mail precedenti:

   * Se utilizzi già Adobe Campaign, il modello locale verrà automaticamente preparato sui messaggi che hai già inviato.
   * Se non conosci Adobe Campaign, puoi estrarre un file CSV dal sistema precedente/ESP che contiene 4 colonne: data, oggetto, inviato, si apre. To do that, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** and follow the instructions provided on the successive screens. Al termine del caricamento dell'oggetto, importate un modello locale come descritto di seguito. Il modello locale viene automaticamente preparato con i dati caricati.
   * Se non conosci Adobe Campaign e non riesci a ottenere un file CSV come descritto qui sopra, puoi utilizzare un modello predefinito o attendere fino a quando non hai sufficiente dati di consegna nel sistema per formare un modello locale. Il sistema determina automaticamente se il set di dati corrente contiene dati sufficienti per riconoscere i pattern e per formare il modello.

      >[!NOTE]
      >
      >Non esiste alcun numero definito di oggetti necessari per formare il proprio modello. Per essere in grado di formare gli oggetti, è necessario che le righe siano diverse e senza duplicati. Se i dati da elaborare non sono sufficienti, il sistema non sarà in grado di formare il modello. Nell'istanza è presente solo un modello preparato.
   To train a local model, download the subjectLineTraining.xml from [here](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) and use the [package import](../../automating/using/managing-packages.md) feature to upload it to your Adobe Campaign instance. Un flusso di lavoro tecnico effettua automaticamente la formazione.

   The first time you want to train a model, an administrator can force the **[!UICONTROL SubjectLine Training workflow]** to start from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** menu.

   Una volta caricato e preparato un modello, la funzione viene attivata automaticamente e accanto al campo dell'oggetto dei messaggi viene visualizzata una nuova opzione.

   Quindi, il flusso di lavoro tecnico continua a formare il modello ogni settimana.

* Potete importare modelli preconfigurati specifici per determinate industrie (medici, ecc.) using the [package import](../../automating/using/managing-packages.md) feature. These models are available [here](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) and cannot be trained.

   Una volta caricato un modello, la funzione viene attivata automaticamente e accanto al campo dell'oggetto dei messaggi viene visualizzata una nuova opzione.

>[!NOTE]
>
>L'importazione e la generazione di modelli di progettazione possono essere eseguite solo da un amministratore.

I modelli disponibili sono:

* Settore cosmetico: subjectInsightCosmetic.xml
* Settore supermarket: subjectInsightSupermarket.xml
* Settore medico: subjectInsightMedical.xml
* Modello da formare: Subjectlinetraeup. xml.

