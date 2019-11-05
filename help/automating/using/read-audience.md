---
title: Leggi audience
description: L'attività Leggi audience consente di recuperare un'audience esistente e di perfezionarla applicando ulteriori condizioni di filtro.
page-status-flag: mai attivato
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Leggi audience{#read-audience}

## Descrizione {#description}

![](assets/prefill.png)

L' **[!UICONTROL Read audience]** attività consente di recuperare un'audience esistente e di perfezionarla applicando ulteriori condizioni di filtro.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Read audience]** attività è una versione più semplice dell' **[!UICONTROL Query]** attività progettata per i casi in cui è solo necessario selezionare un'audience esistente.

## Configurazione {#configuration}

1. Rilascia un' **[!UICONTROL Read audience]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionate il pubblico da recuperare dalla **[!UICONTROL Properties]** scheda.

   Puoi recuperare tipi di pubblico dei seguenti tipi: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Per ulteriori informazioni sui tipi di pubblico, consulta la documentazione [Audiences](../../audiences/using/about-audiences.md) .

   L' **[!UICONTROL Use a dynamic audience]** opzione consente di definire il nome dell'audience di cui eseguire il targeting in base alle variabili degli eventi del flusso di lavoro. Per ulteriori informazioni, vedere la sezione [Personalizzazione delle attività con variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) di eventi.

   ![](assets/readaudience_activity1.png)

1. Se desiderate applicare un filtro aggiuntivo all'audience selezionata, aggiungete condizioni tramite la **[!UICONTROL Source filtering]** scheda dell'attività.

   Per ulteriori informazioni sulla creazione di condizioni di filtraggio, consultare la documentazione [Creazione di query](../../automating/using/editing-queries.md#creating-queries) .

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio: Riconciliare un pubblico di file con il database {#example--reconcile-a-file-audience-with-the-database}

Questo esempio mostra come utilizzare l' **[!UICONTROL Read audience]** attività per riconciliare un'audience creata direttamente da un'importazione di file.

Durante l'importazione di un file, potete salvarne direttamente il contenuto in un pubblico. Questo pubblico è un pubblico di file e i relativi dati non sono collegati ad alcuna risorsa di database.

Il flusso di lavoro di importazione è stato progettato come segue:

![](assets/readaudience_activity_example3.png)

* Un'attività [Carica file](../../automating/using/load-file.md) carica un file contenente i dati dei profili estratti da uno strumento esterno.

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

* Un'attività [Salva audience](../../automating/using/save-audience.md) salva i dati in arrivo come pubblico. Poiché i dati non sono ancora stati riconciliati, l'audience è un'audience di File e i suoi dati non sono ancora riconosciuti come dati di profilo.

Il flusso di lavoro di riconciliazione è progettato come segue:

![](assets/readaudience_activity_example2.png)

* Un' **[!UICONTROL Read audience]** attività carica l'audience File creata nel flusso di lavoro di importazione. I dati sul pubblico non sono ancora riconciliati con il database Adobe Campaign.
* Un'attività di [riconciliazione](../../automating/using/reconciliation.md) identifica i dati in arrivo come profili attraverso la relativa **[!UICONTROL Identification]** scheda. Ad esempio, utilizzando il campo **email** come criterio di riconciliazione.
* Un'attività [Aggiorna dati](../../automating/using/update-data.md) inserisce e aggiorna la risorsa dei profili del database con i dati in arrivo. Poiché i dati sono già identificati come profili, potete selezionare l' **[!UICONTROL Directly using the targeting dimension]** opzione e **[!UICONTROL Profiles]** nella **[!UICONTROL Identification]** scheda dell'attività. Quindi, è sufficiente aggiungere l'elenco dei campi che devono essere aggiornati nella scheda in base.

## Esempio: Unione su due tipi di pubblico raffinati {#example--union-on-two-refined-audiences}

Il flusso di lavoro definito in questo esempio mostra l'unione di due **[!UICONTROL Read audience]** attività. L'obiettivo di questo flusso di lavoro è quello di inviare un'e-mail ai membri Gold o Silver che hanno tra i 18 e i 30 anni.

Nel sistema sono già state create audience specifiche per tenere traccia dei membri Gold e Silver.

Il flusso di lavoro è progettato come segue:

![](assets/readaudience_activity_example1.png)

* Una prima **[!UICONTROL Read audience]** attività che recupera l'audience dei membri Gold e la perfeziona selezionando solo i profili con età compresa tra 18 e 30 anni.
* Una seconda **[!UICONTROL Read audience]** attività che recupera l'audience dei membri Silver e la perfeziona selezionando solo i profili con età compresa tra 18 e 30 anni.
* Un' **[!UICONTROL Union]** attività che unisce le popolazioni da entrambe **[!UICONTROL Read audiences]** le attività ad una popolazione finale.
* Un' **[!UICONTROL Email delivery]** attività che invia l'e-mail alla popolazione proveniente dall' **[!UICONTROL Union]** attività.

