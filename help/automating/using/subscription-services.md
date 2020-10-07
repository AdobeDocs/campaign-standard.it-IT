---
title: Subscription Services
description: L’attività Subscription Services ti consente di prendere profili in massa e abbonarli a un servizio o annullarne l’abbonamento.
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1110'
ht-degree: 98%

---


# Subscription Services {#subscription-services}

## Descrizione {#description}

![](assets/wf_subscription.png)

L’attività **[!UICONTROL Subscription Services]** ti consente di prendere profili in massa e abbonarli a un servizio o annullarne l’abbonamento.

>[!CAUTION]
>
>Quando l’abbonamento viene gestito nel contesto di un flusso di lavoro, i profili che effettuano l’abbonamento o annullano l’abbonamento non ricevono i diversi messaggi e-mail di conferma definiti nelle proprietà del servizio.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Subscription Services]** è l’unica funzionalità di Adobe Campaign che consente a più profili di effettuare l’abbonamento o di annullare l’abbonamento a un servizio in un’unica azione.

Puoi utilizzare questa attività dopo aver eseguito il targeting o aver importato un file con dati identificati.

Se specificata in un file tramite colonne dedicate, questa attività ti consente inoltre di scegliere l’azione (abbonamento o annullamento dell’abbonamento) e il servizio su cui eseguire l’azione.

**Argomenti correlati:**

* [Caso di utilizzo: Aggiornamento di più stati di iscrizione da un file](../../automating/using/updating-subscriptions-from-file.md)
* [Caso di utilizzo: Iscrizione di profili da un file a un servizio specifico](../../automating/using/subscribing-profiles-from-file.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Subscription Services]** nel flusso di lavoro.
1. Collegala dopo altre attività di targeting quali una query o una riconciliazione a seguito di un’importazione.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona il **[!UICONTROL Service]** per il quale desideri gestire gli abbonamenti utilizzando una delle seguenti opzioni:

   * **[!UICONTROL Select a specific service]**: seleziona manualmente un servizio.
   * **[!UICONTROL Select services from the inbound transition]**: il servizio è specificato nella transizione in entrata. Ad esempio, puoi importare un file che specifica il servizio da gestire per ogni riga. Se scegli questa opzione, accertati che in precedenza sia stato creato un collegamento tra i dati e la risorsa **Servizio**, come mostrato in [questo esempio](#example--updating-multiple-subscription-statuses-from-a-file).

      Il servizio su cui eseguire l’operazione viene quindi selezionato in modo dinamico per ogni record.

1. Seleziona il **[!UICONTROL Operation type]** da eseguire utilizzando una delle seguenti opzioni:

   * **[!UICONTROL Select a specific operation type]**: seleziona manualmente se desideri **[!UICONTROL Subscribe]** o **[!UICONTROL Unsubscribe]** di profili.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: seleziona la colonna dei dati in entrata che specifica l’operazione da eseguire per ogni record.

      In questa colonna, l’operazione deve essere specificata come un valore booleano o un numero intero. Utilizza **0** per annullare l’abbonamento di un record e **1** per effettuare l’abbonamento.

      Se i valori contenuti in un file importato non corrispondono ai requisiti di cui sopra, puoi comunque utilizzare l’opzione [Nuova mappatura dei valori](../../automating/using/load-file.md#column-format) disponibile nell’attività **[!UICONTROL Load file]**.

1. Se i dati in entrata contengono una colonna corrispondente alla data di abbonamento del profilo al servizio, selezionala. Puoi lasciarla vuota ma non viene impostata alcuna data di abbonamento durante l’esecuzione del flusso di lavoro.
1. Definisci l’origine dell’abbonamento. Puoi impostarla su uno dei campi dei dati in entrata o su un valore costante desiderato selezionando l’opzione **[!UICONTROL Set a constant as origin]**. Puoi lasciarla vuota ma non viene impostata alcuna origine durante l’esecuzione del flusso di lavoro.
1. Se necessario, puoi generare una transizione in uscita. Questa transizione contiene esattamente gli stessi dati dell’attività in entrata.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

   È ora pronto per essere eseguito. Dopo l’esecuzione, puoi visualizzare i profili che si sono abbonati o hanno annullato l’abbonamento al servizio nei dettagli del servizio.

## Esempio: abbonamento di profili a un servizio specifico dopo l’importazione di un file {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Questo esempio illustra come importare un file contenente profili ed effettuarne l’abbonamento a un servizio esistente. Dopo l’importazione del file, è necessario eseguire una riconciliazione in modo tale che i dati importati possano essere identificati come profili. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un’attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* Un’attività **[!UICONTROL Load file]** carica il file dei profili e definisce la struttura delle colonne importate.

   Per questo esempio, il file caricato è in formato .csv e contiene i seguenti dati:

   ```
   lastname;firstname;email;birthdate;subdate
   jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
   phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
   weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
   martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
   reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
   grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
   ```

   ![](assets/subscription_activity_example2.png)

* Un’attività **[!UICONTROL Reconciliation]** identifica i dati del file come appartenenti alla dimensione di profilo del database di Adobe Campaign. Solo la scheda **[!UICONTROL Identification]** è configurata. Essa identifica i dati del file in base agli indirizzi e-mail dei profili.

   ![](assets/subscription_activity_example3.png)

* Una **[!UICONTROL Deduplication]** basata sul campo **e-mail** della risorsa temporanea (derivante dalla riconciliazione) identifica eventuali duplicati. Se i dati importati dal file contengono duplicati, l’abbonamento a un servizio non riuscirà per tutti i dati.

   ![](assets/subscription_activity_example5.png)

* Un’attività **[!UICONTROL Subscription Services]** ti consente di selezionare il servizio al quale i profili devono effettuare l’abbonamento, il campo corrispondente alla data di abbonamento e l’origine dell’abbonamento.

   ![](assets/subscription_activity_example4.png)

## Esempio: aggiornamento di più stati di abbonamento da un file {#example--updating-multiple-subscription-statuses-from-a-file}

Questo esempio illustra come importare un file contenente profili e aggiornarne l’abbonamento a diversi servizi specificati nel file. Dopo l’importazione del file, è necessario eseguire una riconciliazione in modo tale che i dati importati possano essere identificati come profili con un collegamento ai servizi. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un’attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* Un’attività **[!UICONTROL Load file]** carica il file dei profili e definisce la struttura delle colonne importate.

   Per questo esempio, il file caricato è in formato .csv e contiene i seguenti dati:

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   Come avrai notato, l’operazione è specificata nel file come &quot;sub&quot; o &quot;non sub&quot;. Il sistema richiede un **valore booleano** o un **numero intero** per riconoscere l’operazione da eseguire: &quot;0&quot; per annullare l’abbonamento e &quot;1&quot; per effettuare l’abbonamento. Per soddisfare questo requisito, viene eseguito una nuova mappatura dei valori nel dettaglio della colonna &quot;operazione&quot;.

   ![](assets/subscription_example_remapping.png)

   Se il file utilizza già &quot;0&quot; e &quot;1&quot; per identificare l’operazione, non devi ripetere la mappatura di tali valori. Assicurati solo che la colonna sia elaborata come un **valore booleano** o un **numero intero** nella scheda **[!UICONTROL Column definition]**.

* Un’attività **[!UICONTROL Reconciliation]** identifica i dati del file come appartenenti alla dimensione di profilo del database di Adobe Campaign. Tramite la scheda **[!UICONTROL Identification]**, il campo **e-mail** del file viene fatto corrisponde al campo **e-mail** della risorsa del profilo.

   ![](assets/subscription_activity_example3.png)

   Nella scheda **[!UICONTROL Relations]**, viene creato un collegamento con la risorsa del servizio per consentire il riconoscimento del campo **service** del file. In questo esempio, i valori corrispondono al campo **name** della risorsa del servizio.

   ![](assets/subscription_example_service_relation.png)

* Una **[!UICONTROL Deduplication]** basata sul campo **email** della risorsa temporanea (derivante dalla riconciliazione) identifica i duplicati. È importante eliminare i duplicati poiché l’abbonamento a un servizio non riuscirà per tutti i dati in caso di duplicati.

   ![](assets/subscription_activity_example5.png)

* Un’attività **[!UICONTROL Subscription Services]** identifica i servizi da aggiornare come provenienti dalla transizione, attraverso il collegamento creato nell’attività **[!UICONTROL Reconciliation]**.

   Il **[!UICONTROL Operation type]** viene identificato come proveniente dal campo **operation** del file. Qui è possibile selezionare solo campi con un valore booleano o un numero intero. Se la colonna del file che contiene l’operazione da eseguire non viene visualizzata nell’elenco, accertati di aver impostato correttamente il formato della colonna nell’attività **[!UICONTROL Load file]**, come spiegato in precedenza in questo esempio.

   ![](assets/subscription_activity_example_from_file.png)

