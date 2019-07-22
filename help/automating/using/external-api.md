---
title: API esterna
seo-title: API esterna
description: API esterna
seo-description: null
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
context-tags: Externalapi, workflow, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1444a636f401ed9c34295aaca1a2b3271d6700a4

---


# External API {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

The **[!UICONTROL External API]** activity brings data into the workflow from an **external system** via a **REST API** call.

The REST endpoints can be a Customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

Le caratteristiche principali di questa attività sono:

* Limite dimensione dati risposta http 5 MB
* Gestione non riuscita con transizione in uscita in uscita
* Timeout richiesta 60 secondi
* I reindirizzamenti HTTP non sono consentiti
* Gli URL non HTTPS vengono rifiutati
* " Accetta: application/json "headheader e" Content-Type: application/json» è consentita l'intestazione della risposta

## Configuration {#configuration}

Drag and drop an **[!UICONTROL External API]** activity into your workflow and open the activity to start the configuration.

### Mappatura in entrata

La mappatura in entrata è una tabella temporanea generata da una precedente attività in entrata che verrà visualizzata e inviata come JSON nell'interfaccia utente.
In base a questa tabella temporanea, l'utente può apportare modifiche ai dati in ingresso.

![](assets/externalAPI-inbound.png)

The **Inbound resource** dropdown lets you select the query activity that will create the temporary table.

The **Add count parameter** checkbox will a count value for each row coming from the temporary table. Questa casella di controllo è disponibile solo se l'attività in entrata genera una tabella temporanea.

The **Inbound Columns** section allow the user to add any fields from the inbound transition table. Le colonne selezionate saranno le chiavi nell'oggetto dati. L'oggetto dati nel JSON sarà un elenco array contenente dati per le colonne selezionate da ogni riga della tabella di transizione in entrata.

The **customize parameter** text box lets you add a valid JSON with additional data needed by the external API. Questi dati aggiuntivi saranno aggiunti all'oggetto params nel JSON generato.

### Mappatura in uscita

This tab lets you define the sample **JSON structure** returned by the API Call.

![](assets/externalAPI-outbound.png)

The JSON structure pattern is: **{“data”:[{“key”:“value”}, {“key”:“value”},...]}**

The sample JSON definition must have the **following characteristics**:

* **data** è un nome di proprietà obbligatorio in JSON, il contenuto di "dati" è un array JSON.
* **Gli elementi** Array devono contenere proprietà di primo livello (i livelli più dettagliati non sono supportati).
   **I nomi delle proprietà** terminerebbero a diventare nomi di colonna per lo schema di output della tabella temporanea di output.
* **La definizione del nome** della colonna si basa sul primo elemento dell'array "dati".
Columns definition (add/remove) and the type value of the property can be edited in the **Column definition** tab.

If the **parsing is validated** a message appears and invite you to customize the data mapping in the "Column definition" tab. In altri casi, viene visualizzato un messaggio di errore.

### Esecuzione

This tab lets you define the **HTTPS Endpoint** that will send data to ACS. If needed, you can enter authentication information in the fields below.
![](assets/externalAPI-execution.png)

### Proprietà

This tab lets you control **general properties** on the external API activity like the displayed label in the UI. L'ID interno non è personalizzabile.

![](assets/externalAPI-properties.png)

### Definizione colonna

    &gt; [! NOTA]
    &gt;
    &gt; Questa scheda viene visualizzata quando** il formato dati risposta** viene completato e convalidato nella scheda Mappatura in uscita.

The **Column definition** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors and make it match the types that are already present in the Adobe Campaign database for future operations.

![](assets/externalAPI-column.png)

Ad esempio, è possibile modificare l'etichetta di una colonna, selezionandone il tipo (stringa, numero intero, data, ecc.)oppure specifica anche l'elaborazione degli errori.

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### Transizione

This tab lets you activate the **outbound transition** and its label. This specific transition is useful in case of **timeout** or if the payload exceed the **data size limit**.

![](assets/externalAPI-transition.png)

### Opzioni di esecuzione

Questa scheda è disponibile nella maggior parte delle attività del flusso di lavoro. For more information, consult the [Activity properties](../../automating/using/executing-a-workflow.md#activity-properties) section.

![](assets/externalAPI-options.png)

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
