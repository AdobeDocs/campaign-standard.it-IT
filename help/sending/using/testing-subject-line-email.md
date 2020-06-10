---
title: Verifica dell’oggetto di un messaggio e-mail
description: Scoprite come definire l'oggetto di un'e-mail in Designer e-mail.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 343ea01229779a32919bd68fd15e0c7ff6863353
workflow-type: tm+mt
source-wordcount: '1095'
ht-degree: 1%

---

# Verifica dell’oggetto di un messaggio e-mail {#testing-a-subject}


## Informazioni sull&#39;oggetto previsto {#about-predictive-subject-line}

Quando modificate un’e-mail, potete provare diverse righe di oggetto e ottenere una stima del tasso di apertura prima di inviarla.

Questa funzione è disattivata per impostazione predefinita. Viene attivata quando viene importato il primo modello. Un modello è il risultato di set di dati di formazione specifici per un determinato settore. I modelli consentono al sistema di prevedere la frequenza di apertura dell&#39;e-mail quando viene inviata una nuova riga oggetto.

>[!NOTE]
>
>Questa funzione è disponibile per i messaggi e-mail e per i database che contengono solo contenuti in lingua inglese. Il modello preparato non sarà coerente e porterà a risultati errati se l&#39;istanza contiene e-mail in altre lingue. L’opzione che consente di testare un oggetto è visibile solo se un modello è già disponibile nell’istanza.

Per ulteriori informazioni sull&#39;importazione di modelli, vedere questa [sezione](#importing-models).

## Verifica della riga oggetto {#testing-subject-line}

Per testare l’oggetto, effettuate le seguenti operazioni:

1. Create o aprite il messaggio e-mail.
1. Aprite il contenuto e inserite l’oggetto del messaggio e-mail nel campo di input corrispondente.
1. Fare clic sul **[!UICONTROL Test subject]** pulsante per accedere alla **[!UICONTROL Test your subject line]** finestra. È comunque possibile modificare l&#39;oggetto da questa finestra.
1. Selezionare il modello corretto da prendere in considerazione per la previsione del tasso aperto. Sono disponibili diversi modelli, ciascuno corrispondente a un settore specifico. Per ulteriori informazioni sull&#39;uso dei modelli, consultate questa [sezione](#importing-models).
1. Clic **[!UICONTROL Test]**.

Il soggetto viene quindi analizzato.

>[!NOTE]
>
>Se l&#39;oggetto è troppo breve, non può essere analizzato e viene visualizzato un messaggio di errore.

Sono stati calcolati diversi indicatori e viene visualizzato un set di strumenti per facilitare l’utente:

* **Tasso** aperto previsto: Questo grafico fornisce un&#39;idea del tasso di apertura previsto per l&#39;e-mail con l&#39;oggetto corrente.
* **Lunghezza** oggetto: Questo indicatore consente di verificare se la lunghezza corrente del soggetto è corretta o se deve essere più lunga o più breve.
* **Parole** colorate: Durante il test dell&#39;oggetto, le parole evidenziate in verde sono le parole che contribuiscono maggiormente ad aumentare la previsione di tasso aperto. Le parole evidenziate in rosso sono le parole che contribuiscono meno ad aumentare la previsione di tasso aperto. Se si aggiungono o si rimuovono parole nell&#39;oggetto, le parole evidenziate cambieranno.
* **Categorie e suggerimenti** per le parole: Verso la parte inferiore della finestra, vengono visualizzate una serie di categorie rilevanti per il modello selezionato. Queste categorie sono ordinate in base all&#39;ordine di importanza e consentono di verificare se l&#39;oggetto contiene parole associate tramite un simbolo di spunta. Ogni categoria contiene una serie di parole suggerite che potrebbero essere utilizzate nell&#39;oggetto per renderlo più rilevante e aumentare il tasso aperto. Queste parole sono le parole utilizzate più spesso in una determinata categoria.

>[!NOTE]
>
>I campi di personalizzazione e gli indicatori di punteggiatura vengono rimossi dall’analisi dell’oggetto. Nel caso del testo dinamico/condizionale, tutte le varianti sono considerate come un oggetto.

![](assets/predictive_subject_line_example.png)

## Importazione di modelli {#importing-models}

Per impostazione predefinita, sul server Adobe Campaign non è in esecuzione alcun modello. Esistono due modi per ottenere un modello e attivare la feature:

* È possibile formare un modello locale dai dati dei messaggi e-mail precedenti.
* È possibile importare modelli preformati che sono specifici di determinati settori (medici, ecc.) mediante la funzione di importazione [del](../../automating/using/managing-packages.md) pacchetto.

### Formazione di un modello locale {#training-local-model}

* Se utilizzi già Adobe Campaign, il modello locale verrà addestrato automaticamente sui messaggi che hai già inviato.
* Se non avete mai usato Adobe Campaign, potete estrarre un file CSV dal sistema/ESP precedente che contiene 4 colonne: data, oggetto, apertura, invio. A tal fine, passare a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** e seguire le istruzioni fornite sugli schermi successivi. Al termine del caricamento dell’oggetto, importate un modello locale come descritto di seguito. Il modello locale viene addestrato automaticamente con i dati caricati.
* Se non avete mai avuto accesso ad Adobe Campaign e non potete ottenere un file CSV come descritto in precedenza, potete utilizzare un modello [](#pre-trained-models) preformato o aspettare che nel sistema siano presenti dati di consegna sufficienti per formare un modello locale. Il sistema determinerà automaticamente se il set di dati corrente contiene dati sufficienti per riconoscere i pattern e formare il modello.

>[!NOTE]
>
>Non esiste un numero definito di linee oggetto necessarie per formare il proprio modello. For more on this, see [Troubleshooting](#troubleshooting).
>
>È possibile avere un solo modello addestrato sull&#39;istanza.

Per formare un modello locale:
1. Scarica subjectLineTraining.xml da [qui](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html) e utilizza la funzione di importazione [del](../../automating/using/managing-packages.md) pacchetto per caricarlo nell’istanza di Adobe Campaign. Un flusso di lavoro tecnico eseguirà automaticamente la formazione per voi.
1. La prima volta che si desidera formare un modello, un amministratore può imporre l&#39; **[!UICONTROL SubjectLine Training workflow]** avvio dal menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** .
1. Una volta che un modello è stato caricato e preparato, la funzione viene attivata automaticamente e accanto al campo dell&#39;oggetto dei messaggi viene visualizzata una nuova opzione.
1. Quindi, il flusso di lavoro tecnico continuerà automaticamente a formare il modello ogni settimana.

### Importazione di modelli preformati {#pre-trained-models}

Per accedere a questi modelli, fare clic [qui](https://experience.adobe.com/#/downloads/content/software-distribution/en/campaign.html). Utilizzate la funzione di importazione [del](../../automating/using/managing-packages.md) pacchetto per caricare un modello nell&#39;istanza di Adobe Campaign.

I modelli disponibili per l&#39;uso sono:

* Industria cosmetica: subjectInsightCosmetic.xml
* Industria dei supermercati: subjectInsightSupermarket.xml
* Settore medicale: subjectInsightMedical.xml
* Modello per il treno: subjectlineTraining.xml.

Questi modelli non possono essere formati.

Una volta caricato un modello, la funzione viene attivata automaticamente e accanto al campo dell&#39;oggetto dei messaggi viene visualizzata una nuova opzione.

>[!NOTE]
>
>L&#39;importazione e la generazione di modelli qualificati possono essere eseguite solo da un amministratore.

## Risoluzione dei problemi {#troubleshooting}

L&#39;oggetto predittivo è un processo di machine-learning che tiene conto di tutte le righe oggetto caricate con i relativi tassi aperti. Questo consente al sistema di prevedere la frequenza di apertura di un&#39;e-mail quando viene inviata una nuova riga oggetto.

Per poter formare il proprio modello, le linee oggetto devono essere diverse e non devono presentare duplicati, indipendentemente dal numero di linee oggetto utilizzate per formare il modello.

La qualità delle linee oggetto è essenziale. Se non sono disponibili dati di qualità sufficienti per l&#39;elaborazione, o se tutte le righe oggetto precedenti sono troppo simili, il sistema non sarà in grado di formare il modello e potrebbe essere visualizzato un messaggio di errore. Ciò significa che il set di record esistente non consente di fornire un suggerimento predittivo affidabile.

In questo caso, è necessario esaminare i dati che si stanno caricando e assicurarsi che le linee oggetto siano sufficientemente variabili per formare in modo efficiente il modello.

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
