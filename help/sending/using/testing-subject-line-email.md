---
title: Verifica dell’oggetto di un messaggio e-mail
seo-title: Verifica dell’oggetto di un messaggio e-mail
description: Verifica dell’oggetto di un messaggio e-mail
seo-description: Scoprite come definire l'oggetto di un'e-mail in Designer e-mail.
page-status-flag: mai attivato
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 62992dbedea7209ca26ae9e1a475a0c87405a4d9

---

# Verifica di un oggetto {#testing-a-subject}

Per verificare la riga dell'oggetto:

1. Create o aprite il messaggio e-mail.
1. Aprite il contenuto e inserite l’oggetto del messaggio e-mail nel campo di input corrispondente.
1. Fare clic sul **[!UICONTROL Test subject]** pulsante per accedere alla **[!UICONTROL Test your subject line]** finestra. È comunque possibile modificare l'oggetto da questa finestra.
1. Selezionare il modello corretto da prendere in considerazione per la previsione del tasso aperto. Sono disponibili diversi modelli, ciascuno corrispondente a un settore specifico.
1. Click **[!UICONTROL Test]**.

Il soggetto viene quindi analizzato.

>[!NOTE]
>
>Se l'oggetto è troppo breve, non può essere analizzato e viene visualizzato un messaggio di errore.

Vengono calcolati diversi indicatori e viene visualizzato un set di strumenti per facilitare l’utente:

* **Tasso** aperto previsto: Questo grafico fornisce un'idea del tasso di apertura previsto per l'e-mail con l'oggetto corrente.
* **Lunghezza** oggetto: Questo indicatore consente di verificare se la lunghezza corrente del soggetto è corretta o se deve essere più lunga o più breve.
* **Parole** colorate: Durante il test dell'oggetto, le parole evidenziate in verde sono le parole che contribuiscono maggiormente ad aumentare la previsione di tasso aperto. Le parole evidenziate in rosso sono quelle che contribuiscono meno ad aumentare la previsione di tasso aperto. Se si aggiungono o si rimuovono parole nell'oggetto, le parole evidenziate cambieranno.
* **Categorie e suggerimenti** per le parole: Verso la parte inferiore della finestra, vengono visualizzate una serie di categorie rilevanti per il modello selezionato. Queste categorie sono ordinate in base all'ordine di importanza e consentono di verificare se l'oggetto contiene parole associate tramite un simbolo di spunta. Ogni categoria contiene una serie di parole suggerite che potrebbero essere utilizzate nell'oggetto per renderlo più rilevante e aumentare il tasso aperto. Queste parole sono le parole utilizzate più spesso in una determinata categoria.

>[!NOTE]
>
>I campi di personalizzazione e gli indicatori di punteggiatura vengono rimossi dall’analisi dell’oggetto. Nel caso del testo dinamico/condizionale, tutte le varianti sono considerate come un oggetto.

![](assets/predictive_subject_line_example.png)

## Importazione di modelli {#importing-models}

Per impostazione predefinita, sul server Adobe Campaign non è in esecuzione alcun modello. Esistono due modi per ottenere un modello e attivare la feature:

* È possibile formare un modello locale dai dati dei messaggi e-mail precedenti:

   * Se utilizzi già Adobe Campaign, il modello locale verrà addestrato automaticamente sui messaggi che hai già inviato.
   * Se non avete mai usato Adobe Campaign, potete estrarre un file CSV dal sistema/ESP precedente che contiene 4 colonne: data, oggetto, inviato, aperto. A tale scopo, passare a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** e seguire le istruzioni fornite sugli schermi successivi. Al termine del caricamento dell’oggetto, importate un modello locale come descritto di seguito. Il modello locale viene addestrato automaticamente con i dati caricati.
   * Se non avete mai avuto accesso ad Adobe Campaign e non potete ottenere un file CSV come descritto in precedenza, potete utilizzare un modello preformato o aspettare che nel sistema siano presenti dati di consegna sufficienti per formare un modello locale. Il sistema determinerà automaticamente se il set di dati corrente contiene dati sufficienti per riconoscere i pattern e formare il modello.

      >[!NOTE]
      >
      >Non esiste un numero definito di linee oggetto necessarie per formare il proprio modello. Per essere in grado di formarlo, le linee del soggetto devono essere diverse e non devono avere duplicati. Se i dati non sono sufficienti per l'elaborazione, il sistema non sarà in grado di formare il modello. È possibile avere un solo modello addestrato sull'istanza.
   Per formare un modello locale, scaricate subjectLineTraining.xml da [qui](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) e utilizzate la funzione di importazione [del](../../automating/using/managing-packages.md) pacchetto per caricarlo nell'istanza di Adobe Campaign. Un flusso di lavoro tecnico eseguirà automaticamente la formazione per voi.

   La prima volta che si desidera formare un modello, un amministratore può imporre l' **[!UICONTROL SubjectLine Training workflow]** avvio dal menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** .

   Una volta che un modello è stato caricato e preparato, la funzione viene attivata automaticamente e accanto al campo dell'oggetto dei messaggi viene visualizzata una nuova opzione.

   Quindi, il flusso di lavoro tecnico continuerà automaticamente a formare il modello ogni settimana.

* È possibile importare modelli preformati che sono specifici di determinati settori (medici, ecc.) mediante la funzione di importazione [del](../../automating/using/managing-packages.md) pacchetto. Questi modelli sono disponibili [qui](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) e non possono essere formati.

   Una volta caricato un modello, la funzione viene attivata automaticamente e accanto al campo dell'oggetto dei messaggi viene visualizzata una nuova opzione.

>[!NOTE]
>
>L'importazione e la generazione di modelli qualificati possono essere eseguite solo da un amministratore.

I modelli disponibili per l'uso sono:

* Industria cosmetica: subjectInsightCosmetic.xml
* Industria dei supermercati: subjectInsightSupermarket.xml
* Settore medicale: subjectInsightMedical.xml
* Modello per il treno: subjectlineTraining.xml.