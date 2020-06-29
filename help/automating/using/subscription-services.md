---
title: Servizi sottoscrizione
description: L’attività Servizi iscrizione consente di prendere profili in massa e iscriverli a un servizio o annullarne l’iscrizione a un servizio.
page-status-flag: never-activated
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Servizi sottoscrizione {#subscription-services}

## Descrizione {#description}

![](assets/wf_subscription.png)

L&#39; **[!UICONTROL Subscription Services]** attività consente di prendere profili in massa e iscriverli a un servizio o annullarne l&#39;iscrizione a un servizio.

>[!CAUTION]
>
>Quando l’iscrizione viene gestita nel contesto di un flusso di lavoro, i profili sottoscritti o non sottoscritti non ricevono i diversi messaggi e-mail di conferma definiti nelle proprietà del servizio.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Subscription Services]** attività è l&#39;unica funzionalità di Adobe Campaign  che consente la sottoscrizione o l&#39;annullamento della sottoscrizione di più profili da un servizio in un&#39;unica azione.

Potete utilizzare questa attività dopo aver eseguito il targeting o aver importato un file con dati identificati.

Se specificata in un file tramite colonne dedicate, questa attività consente anche di scegliere l&#39;azione (sottoscrizione o annullamento della sottoscrizione) e il servizio su cui eseguire l&#39;azione.

**Argomenti correlati:**

* [Caso di utilizzo: Aggiornamento di più stati di iscrizione da un file](../../automating/using/updating-subscriptions-from-file.md)
* [Caso di utilizzo: Iscrizione di profili da un file a un servizio specifico](../../automating/using/subscribing-profiles-from-file.md)

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Subscription Services]** attività nel flusso di lavoro.
1. Connettilo dopo altre attività di targeting, ad esempio una query o una riconciliazione dopo un&#39;importazione.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionate le **[!UICONTROL Service]** sottoscrizioni per le quali desiderate gestire una delle seguenti opzioni:

   * **[!UICONTROL Select a specific service]**: selezionate manualmente un servizio.
   * **[!UICONTROL Select services from the inbound transition]**: il servizio è specificato nella transizione in entrata. Ad esempio, è possibile importare un file che specifica il servizio da gestire per ogni riga. Se scegli questa opzione, accertati che sia stato creato un collegamento tra i dati e la risorsa **Servizio** , come mostrato in [questo esempio](#example--updating-multiple-subscription-statuses-from-a-file).

      Il servizio su cui eseguire l&#39;operazione viene quindi selezionato dinamicamente per ciascun record.

1. Selezionate la modalità **[!UICONTROL Operation type]** da eseguire utilizzando una delle seguenti opzioni:

   * **[!UICONTROL Select a specific operation type]**: selezionate manualmente se desiderate **[!UICONTROL Subscribe]** o **[!UICONTROL Unsubscribe]** profili.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: selezionare la colonna dei dati in entrata che specifica l&#39;operazione da eseguire per ciascun record.

      In questa colonna, l&#39;operazione deve essere specificata come booleana o come numero intero. Utilizzate **0** per annullare l’iscrizione di un record e **1** per iscrivervi.

      Se i valori contenuti in un file importato non corrispondono ai requisiti di cui sopra, potete comunque utilizzare l&#39;opzione [Remapping dei valori](../../automating/using/load-file.md#column-format) disponibile nell&#39; **[!UICONTROL Load file]** attività.

1. Se i dati in entrata contengono una colonna corrispondente alla data di iscrizione del profilo al servizio, selezionatela. Potete lasciare vuoto il campo, ma non impostare alcuna data di iscrizione durante l’esecuzione del flusso di lavoro.
1. Definire l&#39;origine della sottoscrizione. È possibile impostarlo su uno dei campi dei dati in entrata o su un valore costante selezionato dall&#39;utente, selezionando l&#39; **[!UICONTROL Set a constant as origin]** opzione. Potete lasciarlo vuoto ma non viene impostata alcuna origine durante l&#39;esecuzione del flusso di lavoro.
1. Se necessario, potete generare una transizione in uscita. Questa transizione contiene esattamente gli stessi dati dell&#39;attività in entrata.
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

   È ora pronto per essere eseguito. Una volta eseguiti, potete visualizzare i profili per i quali è stata sottoscritta o che è stata annullata la sottoscrizione al servizio nei dettagli del servizio.

## Esempio: Iscrizione di profili a un servizio specifico dopo l’importazione di un file {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Questo esempio illustra come importare un file contenente profili e iscriverlo a un servizio esistente. Dopo l&#39;importazione del file, è necessario eseguire una riconciliazione in modo che i dati importati possano essere identificati come profili. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un&#39;attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* Un&#39; **[!UICONTROL Load file]** attività carica il file di profilo e definisce la struttura delle colonne importate.

   Per questo esempio, il file caricato è in formato .csv e contiene i dati seguenti:

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

* Un&#39; **[!UICONTROL Reconciliation]** attività identifica i dati del file come appartenenti alla dimensione del profilo del database del Adobe Campaign . È configurata solo la **[!UICONTROL Identification]** scheda. Identifica i dati del file in base agli indirizzi e-mail dei profili.

   ![](assets/subscription_activity_example3.png)

* Un **[!UICONTROL Deduplication]** basato sul campo **e-mail** della risorsa temporanea (derivante dalla riconciliazione) identifica eventuali duplicati. Se i dati importati dal file contengono duplicati, la sottoscrizione a un servizio non riuscirà per tutti i dati.

   ![](assets/subscription_activity_example5.png)

* Un&#39; **[!UICONTROL Subscription Services]** attività consente di selezionare il servizio al quale devono essere sottoscritti i profili, il campo corrispondente alla data di iscrizione e l&#39;origine dell&#39;iscrizione.

   ![](assets/subscription_activity_example4.png)

## Esempio: Aggiornamento di più stati di iscrizione da un file {#example--updating-multiple-subscription-statuses-from-a-file}

Questo esempio illustra come importare un file contenente dei profili e aggiornare la propria sottoscrizione a diversi servizi specificati nel file. Dopo l&#39;importazione del file, è necessario eseguire una riconciliazione in modo che i dati importati possano essere identificati come profili con un collegamento ai servizi. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un&#39;attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* Un&#39; **[!UICONTROL Load file]** attività carica il file di profilo e definisce la struttura delle colonne importate.

   Per questo esempio, il file caricato è in formato .csv e contiene i dati seguenti:

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

   Come avrete notato, l&#39;operazione è specificata nel file come &quot;sub&quot; o &quot;non sub&quot;. Il sistema prevede che un valore **booleano** o **Intero** riconosca l&#39;operazione da eseguire: &quot;0&quot; per annullare l’iscrizione e &quot;1&quot; per iscriversi. Per soddisfare questo requisito, viene eseguito un nuovo mapping dei valori nel dettaglio della colonna &quot;operation&quot;.

   ![](assets/subscription_example_remapping.png)

   Se il file utilizza già &quot;0&quot; e &quot;1&quot; per identificare l&#39;operazione, non è necessario rimappare tali valori. Assicurarsi solo che la colonna sia elaborata come **booleano** o **Intero** nella **[!UICONTROL Column definition]** scheda.

* Un&#39; **[!UICONTROL Reconciliation]** attività identifica i dati del file come appartenenti alla dimensione del profilo del database del Adobe Campaign . Tramite la **[!UICONTROL Identification]** scheda, il campo **e-mail** del file corrisponde al campo **e-mail** della risorsa del profilo.

   ![](assets/subscription_activity_example3.png)

   Nella **[!UICONTROL Relations]** scheda, viene creato un collegamento con la risorsa del servizio per consentire il riconoscimento del campo del **servizio** del file. In questo esempio, i valori corrispondono al campo del **nome** della risorsa del servizio.

   ![](assets/subscription_example_service_relation.png)

* Un **[!UICONTROL Deduplication]** basato sul campo **e-mail** della risorsa temporanea (derivante dalla riconciliazione) identifica i duplicati. È importante eliminare i duplicati, in quanto la sottoscrizione a un servizio non riesce per tutti i dati in caso di duplicati.

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** identifica i servizi da aggiornare come provenienti dalla transizione, attraverso il collegamento creato nell&#39; **[!UICONTROL Reconciliation]** attività.

   Il file **[!UICONTROL Operation type]** viene identificato come proveniente dal campo **operativo** del file. Qui è possibile selezionare solo i campi booleani o Interi. Se la colonna del file che contiene l&#39;operazione da eseguire non viene visualizzata nell&#39;elenco, accertatevi di aver impostato correttamente il formato della colonna nell&#39; **[!UICONTROL Load file]** attività, come spiegato in precedenza in questo esempio.

   ![](assets/subscription_activity_example_from_file.png)

