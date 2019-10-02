---
title: Testing the subject line of an email
seo-title: Testing the subject line of an email
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
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---

# Verifica di un oggetto {#testing-a-subject}

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

* **Tasso** aperto previsto: Questo grafico fornisce un'idea del tasso di apertura previsto per l'e-mail con l'oggetto corrente.
* **Subject length: This indicator lets you see if the current length of the subject is correct or whether it would need to be longer or shorter.**
* **Parole** colorate: Durante il test dell'oggetto, le parole evidenziate in verde sono le parole che contribuiscono maggiormente ad aumentare la previsione di tasso aperto. Words highlighted in red are the words that contribute the least to increasing the open rate prediction. If you add or remove words in the subject, highlighted words will change.
* **Categorie e suggerimenti** per le parole: Verso la parte inferiore della finestra, vengono visualizzate una serie di categorie rilevanti per il modello selezionato. These categories are sorted by order of importance and they allow you to see whether your subject contains words that are associated with it via a check symbol. Each category contains a set of suggested words that could be used in your subject to make it more relevant and increase the open rate. These words are the words that are used the most often in a given category.

>[!NOTE]
>
>Personalization fields and punctuation marks are stripped from the subject analysis. In the case of dynamic/conditional text, all variants are considered as one subject line.

![](assets/predictive_subject_line_example.png)

## Importing models {#importing-models}

By default, there is no model running on your Adobe Campaign server. There are two ways to get a model and activate the feature:

* You can train a local model from the data of your previous email messages:

   * If you are already using Adobe Campaign, the local model will be automatically trained on the messages that you have already sent.
   * If you are new to Adobe Campaign, you can extract a CSV file from your previous system/ESP that contains 4 columns: date, subject, sent, opens. A tale scopo, passare a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** e seguire le istruzioni fornite sugli schermi successivi. Al termine del caricamento dell’oggetto, importate un modello locale come descritto di seguito. Il modello locale viene addestrato automaticamente con i dati caricati.
   * If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a pre-trained model or wait until you have enough delivery data in your system to train a local model. Il sistema determinerà automaticamente se il set di dati corrente contiene dati sufficienti per riconoscere i pattern e formare il modello.

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
* Modello per il treno: subjectlineTraining.x