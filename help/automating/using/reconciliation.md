---
title: Riconciliazione
seo-title: Riconciliazione
description: Riconciliazione
seo-description: L'attività di riconciliazione consente di collegare dati non identificati alle risorse esistenti.
page-status-flag: never-activated
uuid: 7884 db 8 c -1717-4724-be 15-3 b 0 b 32 ccc 071
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: gestione dati-attività
discoiquuid: cb 8 c 43 f 4-9 cdd -4 e 85-99 a 4-004 b 36 b 336 aa
context-tags: riconciliazione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Reconciliation{#reconciliation}

## Description {#description}

![](assets/reconciliation.png)

The **[!UICONTROL Reconciliation]** activity allows you to link unidentified data to existing resources.

## Context of use {#context-of-use}

The **[!UICONTROL Reconciliation]** activity is essentially used for Data Management purposes and implies two different use cases:

* Adding relations: a **[!UICONTROL Links]** tab allows you to add links between the inbound data and several other Adobe Campaign database dimensions.

   Ad esempio, un file contenente dati di acquisto potrebbe contenere anche informazioni per identificare i prodotti acquistati e l'acquirente. Two additional dimensions (besides that of **Purchases**) are therefore concerned by the file data: the **Products** and **Profiles** dimensions. Relations then need to be created between these and the **Purchases** dimension (refer to the following example).

   Quando si definisce una relazione, viene aggiunta una colonna ai dati in entrata per fare riferimento alla chiave esterna della dimensione collegata.

   >[!NOTE]
   >
   >Questa operazione implica che i dati delle dimensioni collegate siano già presenti nel database. Ad esempio, se importate un file di acquisti che mostra quale prodotto è stato acquistato, in che ora, in quale client, ecc., il prodotto e il client devono già esistere nel database.

* Data identification: an **[!UICONTROL Identification]** tab allows you to simply link inbound data to columns of an existing dimension in the Adobe Campaign database. Dopo l'attività, i dati sono identificati come appartenenti alla dimensione definita.

   Ad esempio, puoi eseguire un pubblico salvato, aggiornare il database e così via.

For example, the **[!UICONTROL Reconciliation]** activity can be placed after a load data activity with the aim of importing non-standard data into the database.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Reconciliation]** activity into your workflow, following a transition containing a population whose targeting dimension does not directly come from Adobe Campaign. For more on this, referr to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to define links between the inbound data and other database dimensions, go to the **[!UICONTROL Links]** tab.

   Aggiungete tutte le relazioni necessarie. Per ogni relazione, seleziona innanzitutto la dimensione collegata, quindi nel dettaglio del collegamento specificate i campi corrispondenti.

1. If you would like to simply identify the inbound data, go to the **[!UICONTROL Identification]** tab and check the **[!UICONTROL Identify the document from the working data]** box.

   Seleziona la dimensione di targeting a cui vuoi riconciliare i dati in ingresso.

   Aggiungete criteri di riconciliazione per collegare un record di transizione in ingresso a un record di dimensione di targeting selezionato. Se vengono specificati più criteri, questi devono essere verificati per consentire il funzionamento del collegamento tra tutti i dati.

   Choose the **[!UICONTROL Processing unidentified source lines]** mode:

   * **[!UICONTROL Ignore them]**: solo i dati identificabili vengono mantenuti nella transizione in uscita dell'attività.
   * **[!UICONTROL Keep in the outbound population]**: tutti i dati della transizione in ingresso vengono mantenuti nella transizione in uscita dell'attività.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example 1: Relation definition {#example-1--relation-definition}

L'esempio seguente illustra un flusso di lavoro che aggiorna il database utilizzando i dati di acquisto in un file. I dati di acquisto contengono dati che fanno riferimento a elementi di altre dimensioni, come le e-mail e i codici di prodotto del cliente.

>[!NOTE]
>
>The **Transactions** and **Products** resources used in this example do not exist in the Adobe Campaign database by default. They were therefore created beforehand using the [Custom resources](../../developing/using/data-model-concepts.md) function. I profili corrispondenti agli indirizzi e-mail nel file importato e i prodotti sono stati caricati in anticipo nel database.

Il flusso di lavoro è costituito dalle attività seguenti:

![](assets/reconciliation_example1.png)

* **[!UICONTROL Load file]** Un'attività, che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

   * Data transazione
   * Indirizzo e-mail del cliente
   * Codice di prodotto acquistato
   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* **[!UICONTROL Reconciliation]** Un'attività per associare i dati di acquisto ai profili di database e ai prodotti. È pertanto necessario definire una relazione tra i dati del file e la tabella del profilo e la tabella di prodotto. This configuration is carried out in the activity's **[!UICONTROL Relations]** tab:

   * Relation with the **Profiles**: the file's **client** column is linked to the **email** field of the **Profiles** dimension.
   * Relation with the **Products**: the file's **product** column is linked to the **productCode** field of the **Profiles** dimension.
   Le colonne vengono aggiunte ai dati in entrata per fare riferimento alle chiavi esterne delle dimensioni collegate.

   ![](assets/reconciliation_example3.png)

* An **[!UICONTROL Update data]** activity allows you to define the database fields to update using the imported data. As the data was already identified as belonging to the **Transactions** dimension in the previous activity, here you can use the **[!UICONTROL Directly using the targeting dimension]** identification option.

   By using the option that automatically detects fields to update, the links configured in the previous activity (to profiles and products) are added to the list of **[!UICONTROL Fields to update]**. È inoltre necessario essere certi che il campo che corrisponde alla data di transazione sia aggiunto correttamente a questo elenco.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Example 2: Identification {#example-2--identification}

L'esempio seguente illustra un flusso di lavoro che crea un'audience di profili direttamente da un file importato contenente nuovi client. È composto dalle attività seguenti:

![](assets/identification_example2.png)

* **[!UICONTROL Load file]** Un'attività, che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

   ```
   lastname;firstname;email;dateofbirth
   jackman;megan;megan.jackman@testmail.com;07/08/1975
   phillips;edward;phillips@testmail.com;09/03/1986
   weaver;justin;justin_w@testmail.com;11/15/1990
   martin;babeth;babeth_martin@testmail.net;11/25/1964
   reese;richard;rreese@testmail.com;02/08/1987
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
   grimes;daryl;daryl_890@testmail.com;12/06/1979
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
   ```

* **[!UICONTROL Reconciliation]** Un'attività, che collega ciascuna colonna del file caricato a una colonna di dimensione del profilo. I record di file che non possono essere identificati (dati mancanti, tipo di dati incompatibile, ecc.) vengono ignorate per mantenere l'integrità dei dati finali dell'audience.

   ![](assets/identification_example1.png)

* **[!UICONTROL Save audience]** Un'attività, che salva l'audience dei profili.

   ![](assets/identification_example3.png)

