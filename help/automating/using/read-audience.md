---
title: Leggi audience
seo-title: Leggi audience
description: Leggi audience
seo-description: L'attività Leggi audience consente di recuperare un pubblico esistente e di perfezionarlo applicando condizioni di filtro aggiuntive.
page-status-flag: never-activated
uuid: 58 c 54 e 71-f 4 a 7-4 ae 9-80 a 3-33 c 379 ab 1 db 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: 674684 e 5-8830-4 d 2 f-ba 97-59 ed 4 ba 7422 f
context-tags: Readaudience, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Read audience{#read-audience}

## Description {#description}

![](assets/prefill.png)

The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.

## Context of use {#context-of-use}

The **[!UICONTROL Read audience]** activity is a simpler version of the **[!UICONTROL Query]** activity designed for cases where you only need to select an existing audience.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Read audience]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the audience you want to retrieve from the **[!UICONTROL Properties]** tab.

   You can retrieve audiences of the following types: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** and **[!UICONTROL Experience Cloud]**. For more information on audience types, refer to the [Audiences](../../audiences/using/about-audiences.md) documentation.

   The **[!UICONTROL Use a dynamic audience]** option lets you define the name of the audience to target based on the workflow's events variables. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

   ![](assets/readaudience_activity1.png)

1. If you want to apply additional filtering to the selected audience, add conditions via the **[!UICONTROL Source filtering]** tab of the activity.

   For more information about creating filtering conditions, refer to the [Creating queries](../../automating/using/editing-queries.md#creating-queries) documentation.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example: Reconcile a File audience with the database {#example--reconcile-a-file-audience-with-the-database}

This example shows how to use the **[!UICONTROL Read audience]** activity to reconcile an audience directly created from a file import.

Durante l'importazione di un file, potete salvarne direttamente il contenuto in un'audience. Questo tipo di pubblico è un'audience di file e i relativi dati non sono collegati a risorse di database.

Il flusso di lavoro di importazione è indicato di seguito:

![](assets/readaudience_activity_example3.png)

* A [Load file](../../automating/using/load-file.md) activity uploads a file containing profiles data that were extracted from an external tool.

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

* A [Save audience](../../automating/using/save-audience.md) activity saves the incoming data as an audience. Poiché i dati non sono ancora stati riconciliati, l'audience è un'audience di file e i relativi dati non vengono ancora riconosciuti come dati di profilo.

Il flusso di lavoro per la riconciliazione è stato realizzato come segue:

![](assets/readaudience_activity_example2.png)

* A **[!UICONTROL Read audience]** activity uploads the File audience created in the import workflow. I dati del pubblico non sono ancora riconciliati con il database Adobe Campaign.
* A [Reconciliation](../../automating/using/reconciliation.md) activity identifies the incoming data as profiles through its **[!UICONTROL Identification]** tab. For example by using the **email** field as reconciliation criteria.
* An [Update data](../../automating/using/update-data.md) activity inserts and updates the profiles resource of the database with the incoming data. As the data is already identified as profiles, you can select the **[!UICONTROL Directly using the targeting dimension]** option and select **[!UICONTROL Profiles]** in the **[!UICONTROL Identification]** tab of the activity. Quindi, è sufficiente aggiungere l'elenco dei campi da aggiornare nella scheda di base.

## Example: Union on two refined audiences {#example--union-on-two-refined-audiences}

The workflow defined in this example shows the union of two **[!UICONTROL Read audience]** activities. L'obiettivo di questo flusso di lavoro consiste nell'inviare un'e-mail a membri Gold o Silver che hanno una durata compresa tra 18 e 30 anni.

Sono già state create audience specifiche nel sistema per tenere traccia dei membri Gold e Silver.

Il flusso di lavoro è progettato come segue:

![](assets/readaudience_activity_example1.png)

* A first **[!UICONTROL Read audience]** activity that retrieves the Gold members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* A second **[!UICONTROL Read audience]** activity that retrieves the Silver members audience and refines it by selecting only profiles that are between 18 and 30 years old.
* **[!UICONTROL Union]** Un'attività che unisce le popolazioni da entrambe **[!UICONTROL Read audiences]** le attività a una popolazione finale.
* An **[!UICONTROL Email delivery]** activity that sends the email to the population coming from the **[!UICONTROL Union]** activity.

