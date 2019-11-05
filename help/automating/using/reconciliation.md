---
title: Riconciliazione
description: L’attività Riconciliazione consente di collegare dati non identificati a risorse esistenti.
page-status-flag: mai attivato
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: gestione dei dati
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: riconciliazione,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Riconciliazione{#reconciliation}

## Descrizione {#description}

![](assets/reconciliation.png)

L' **[!UICONTROL Reconciliation]** attività consente di collegare dati non identificati a risorse esistenti.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Reconciliation]** attività è essenzialmente utilizzata a scopo di gestione dei dati e implica due diversi casi d'uso:

* Aggiunta di relazioni: una **[!UICONTROL Links]** scheda consente di aggiungere collegamenti tra i dati in entrata e diverse altre dimensioni del database di Adobe Campaign.

   Ad esempio, un file contenente i dati di acquisto può contenere anche informazioni per identificare i prodotti acquistati e l'acquirente. Due dimensioni aggiuntive (oltre a quelle degli **acquisti**) sono pertanto interessate dai dati del file: le dimensioni **Prodotti** e **Profili** . Le relazioni devono quindi essere create tra queste e la dimensione **Acquisti** (fare riferimento all'esempio seguente).

   Quando si definisce una relazione, ai dati in entrata viene aggiunta una colonna per fare riferimento alla chiave esterna della dimensione collegata.

   >[!NOTE]
   >
   >Questa operazione implica che i dati delle dimensioni collegate sono già presenti nel database. Ad esempio, se importate un file di acquisti che mostra quale prodotto è stato acquistato, in quale momento, da quale client, ecc., il prodotto e il client devono già esistere nel database.

* Identificazione dei dati: una **[!UICONTROL Identification]** scheda consente di collegare semplicemente i dati in entrata alle colonne di una dimensione esistente nel database Adobe Campaign. Dopo l'attività, i dati sono identificati come appartenenti alla dimensione definita.

   Ad esempio, potete eseguire un salvataggio di audience, un aggiornamento del database, ecc.

Ad esempio, l' **[!UICONTROL Reconciliation]** attività può essere posizionata dopo un'attività di dati di caricamento allo scopo di importare dati non standard nel database.

## Configurazione {#configuration}

1. Trascina un' **[!UICONTROL Reconciliation]** attività nel flusso di lavoro, in seguito a una transizione contenente una popolazione la cui dimensione di targeting non proviene direttamente da Adobe Campaign. Per ulteriori informazioni, consulta [Impostazione del targeting di dimensioni e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Per definire i collegamenti tra i dati in entrata e altre dimensioni del database, passare alla **[!UICONTROL Links]** scheda.

   Aggiungi tutte le relazioni necessarie. Per ogni relazione, selezionate prima la dimensione collegata, quindi nei dettagli del collegamento, specificate i campi corrispondenti.

1. Per identificare semplicemente i dati in entrata, passare alla **[!UICONTROL Identification]** scheda e selezionare la **[!UICONTROL Identify the document from the working data]** casella.

   Selezionare la dimensione di targeting a cui si desidera riconciliare i dati in entrata.

   Aggiungi criteri di riconciliazione per collegare un record di transizione in entrata a un record dimensione di targeting selezionato. Se vengono specificati più criteri, questi devono essere verificati per consentire il funzionamento del collegamento tra tutti i dati.

   Scegliete la **[!UICONTROL Processing unidentified source lines]** modalità:

   * **[!UICONTROL Ignore them]**: solo i dati identificabili vengono conservati nella transizione in uscita dell'attività.
   * **[!UICONTROL Keep in the outbound population]**: tutti i dati della transizione in entrata vengono conservati nella transizione in uscita dell'attività.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio 1: Definizione relazione {#example-1--relation-definition}

L'esempio seguente illustra un flusso di lavoro che aggiorna il database utilizzando i dati di acquisto in un file. I dati di acquisto contengono dati che fanno riferimento a elementi di altre dimensioni, come le e-mail del cliente e i codici prodotto.

>[!NOTE]
>
>Le risorse **Transazioni** e **Prodotti** utilizzate in questo esempio non esistono nel database Adobe Campaign per impostazione predefinita. Sono stati quindi creati in precedenza utilizzando la funzione Risorse [](../../developing/using/data-model-concepts.md) personalizzate. I profili corrispondenti agli indirizzi e-mail nel file importato, così come i prodotti, sono stati caricati in precedenza nel database.

Il flusso di lavoro è costituito dalle seguenti attività:

![](assets/reconciliation_example1.png)

* Un' **[!UICONTROL Load file]** attività che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

   * Data transazione
   * Indirizzo e-mail client
   * Codice del prodotto acquistato
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

* Un' **[!UICONTROL Reconciliation]** attività per eseguire il binding dei dati di acquisto con i profili di database e i prodotti. È pertanto necessario definire una relazione tra i dati del file e la tabella del profilo, nonché la tabella del prodotto. Questa configurazione viene eseguita nella **[!UICONTROL Relations]** scheda dell'attività:

   * Relazione con i **profili**: la colonna **client** del file è collegata al campo **email** della dimensione **Profili** .
   * Relazione con i **prodotti**: la colonna **prodotto** del file è collegata al campo **productCode** della dimensione **Profili** .
   Le colonne vengono aggiunte ai dati in entrata per fare riferimento alle chiavi esterne delle dimensioni collegate.

   ![](assets/reconciliation_example3.png)

* Un' **[!UICONTROL Update data]** attività consente di definire i campi del database da aggiornare utilizzando i dati importati. Poiché i dati erano già stati identificati come appartenenti alla dimensione **Transazioni** nell'attività precedente, qui è possibile utilizzare l'opzione di **[!UICONTROL Directly using the targeting dimension]** identificazione.

   Utilizzando l'opzione che rileva automaticamente i campi da aggiornare, i collegamenti configurati nell'attività precedente (a profili e prodotti) vengono aggiunti all'elenco di **[!UICONTROL Fields to update]**. È inoltre necessario assicurarsi che il campo corrispondente alla data della transazione sia correttamente aggiunto a questo elenco.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)

## Esempio 2: Identificazione {#example-2--identification}

L'esempio seguente illustra un flusso di lavoro che crea un'audience di profili direttamente da un file importato contenente nuovi client. È costituito dalle seguenti attività:

![](assets/identification_example2.png)

* Un' **[!UICONTROL Load file]** attività che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

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

* Un' **[!UICONTROL Reconciliation]** attività che collega ciascuna colonna del file caricato a una colonna dimensione profilo. Record di file che non è possibile identificare (dati mancanti, tipo di dati incompatibile, ecc.) vengono ignorate per preservare l'integrità dei dati di audience finali.

   ![](assets/identification_example1.png)

* Un' **[!UICONTROL Save audience]** attività che consente di salvare l'audience dei profili.

   ![](assets/identification_example3.png)

