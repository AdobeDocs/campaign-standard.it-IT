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
source-git-commit: 3fc0d9d7e90a31ffb34efc33d6f5c148ba5aac90

---

# Verifica dell’oggetto di un messaggio e-mail {#testing-a-subject}

Per testare l’oggetto, effettuate le seguenti operazioni:

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

* **Predicted open rate: This chart gives you an idea of the open rate you can expect for the email with its current subject.**
* **Lunghezza** oggetto: Questo indicatore consente di verificare se la lunghezza corrente del soggetto è corretta o se deve essere più lunga o più breve.
* **Colored words: When testing the subject, words highlighted in green are the words that contribute the most to increasing the open rate prediction.** Words highlighted in red are the words that contribute the least to increasing the open rate prediction. If you add or remove words in the subject, highlighted words will change.
* **Categories and word suggestions: Towards the lower part of the window, a number of relevant categories for the selected model are displayed.** Queste categorie sono ordinate in base all'ordine di importanza e consentono di verificare se l'oggetto contiene parole associate tramite un simbolo di spunta. Each category contains a set of suggested words that could be used in your subject to make it more relevant and increase the open rate. Queste parole sono le parole utilizzate più spesso in una determinata categoria.

>[!NOTE]
>
>I campi di personalizzazione e gli indicatori di punteggiatura vengono rimossi dall’analisi dell’oggetto. In the case of dynamic/conditional text, all variants are considered as one subject line.

![](assets/predictive_subject_line_example.png)

## Importazione di modelli {#importing-models}

Per impostazione predefinita, sul server Adobe Campaign non è in esecuzione alcun modello. There are two ways to get a model and activate the feature:

* È possibile formare un modello locale dai dati dei messaggi e-mail precedenti:

   * If you are already using Adobe Campaign, the local model will be automatically trained on the messages that you have already sent.
   * Se non avete mai usato Adobe Campaign, potete estrarre un file CSV dal sistema/ESP precedente che contiene 4 colonne: data, oggetto, inviato, aperto. A tale scopo, passare a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** e seguire le istruzioni fornite sugli schermi successivi. When the subject upload is complete, import a local model as described below. Il modello locale viene addestrato automaticamente con i dati caricati.
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
