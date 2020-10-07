---
title: Riconciliare un pubblico di tipo File con il database
description: Questo esempio mostra come utilizzare l'attività Leggi audience per riconciliare un'audience creata direttamente da un'importazione di file.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 87%

---


# Riconciliare un pubblico di tipo File con il database {#example--reconcile-a-file-audience-with-the-database}

Questo esempio mostra come utilizzare l’attività **[!UICONTROL Read audience]** per riconciliare un pubblico creato direttamente da un’importazione di file.

Durante l’importazione di un file, puoi salvarne direttamente il contenuto in un pubblico. Questo è un pubblico di tipo File e i relativi dati non sono collegati ad alcuna risorsa di database.

Il flusso di lavoro di importazione è progettato come segue:

![](assets/readaudience_activity_example3.png)

* L’attività [Load file](../../automating/using/load-file.md) carica un file contenente i dati di profili estratti da uno strumento esterno.

   Ad esempio:

   ```
   lastname;firstname;birthdate;email;crmID
   Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
   Mars;Daniel;17/11/1987;dannymars@example.com;123545
   Smith;Clara;08/02/1989;hayden.smith@example.com;124567
   Durance;Allison;15/12/1978;allison.durance@example.com;120987
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
   Binder;Tom;19/01/1982;tombinder@example.com;128653
   Binder;Tommy;19/01/1915;tombinder@example.com;134576
   Connor;Jade;10/10/1979;connor.jade@example.com;132452
   Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
   Ross;Timothy;04/07/1986;timross@example.com;157643
   ```

* L’attività [Save audience](../../automating/using/save-audience.md) salva i dati in arrivo come pubblico. Poiché i dati non sono ancora stati riconciliati, il pubblico è di tipo File e i relativi dati non sono ancora stati riconosciuti come dati di profilo.

Il flusso di lavoro di riconciliazione è progettato come segue:

![](assets/readaudience_activity_example2.png)

* A [Read audience](../../automating/using/read-audience.md) activity uploads the File audience created in the import workflow. I dati sul pubblico non sono ancora stati riconciliati con il database di Adobe Campaign.
* L’attività [Reconciliation](../../automating/using/reconciliation.md) identifica i dati in arrivo come profili attraverso la relativa scheda **[!UICONTROL Identification]**. Ad esempio utilizzando il campo **e-mail** come criterio di riconciliazione.
* L’attività [Update data](../../automating/using/update-data.md) inserisce e aggiorna la risorsa dei profili del database con i dati in arrivo. Poiché i dati sono già stati identificati come profili, puoi selezionare l’opzione **[!UICONTROL Directly using the targeting dimension]** e successivamente **[!UICONTROL Profiles]** nella scheda **[!UICONTROL Identification]** dell’attività. Quindi, ti basta semplicemente aggiungere l’elenco dei campi che devono essere aggiornati nella scheda corrispondente.
