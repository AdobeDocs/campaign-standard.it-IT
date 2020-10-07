---
title: Aggiornamento di più stati di abbonamento da un file
description: Questo caso d’uso mostra come importare un file contenente dei profili e aggiornare la sottoscrizione a diversi servizi specificati nel file.
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
source-wordcount: '417'
ht-degree: 76%

---


# Aggiornamento di più stati di abbonamento da un file {#updating-multiple-subscription-statuses-from-a-file}

Questo esempio illustra come importare un file contenente profili e aggiornarne l’abbonamento a diversi servizi specificati nel file. Dopo l’importazione del file, è necessario eseguire una riconciliazione in modo tale che i dati importati possano essere identificati come profili con un collegamento ai servizi. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un’attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* A [Load file](../../automating/using/load-file.md) activity loads the profile file and defines the structure of the imported columns.

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

* A [Reconciliation](../../automating/using/reconciliation.md) activity identifies the data from the file as belonging to the profile dimension of the Adobe Campaign database. Tramite la scheda **[!UICONTROL Identification]**, il campo **e-mail** del file viene fatto corrisponde al campo **e-mail** della risorsa del profilo.

   ![](assets/subscription_activity_example3.png)

   Nella scheda **[!UICONTROL Relations]**, viene creato un collegamento con la risorsa del servizio per consentire il riconoscimento del campo **service** del file. In questo esempio, i valori corrispondono al campo **name** della risorsa del servizio.

   ![](assets/subscription_example_service_relation.png)

* A [Deduplication](../../automating/using/deduplication.md) based on the **email** field of the temporary resource (resulting from the reconciliation) identifies duplicates. È importante eliminare i duplicati poiché l’abbonamento a un servizio non riuscirà per tutti i dati in caso di duplicati.

   ![](assets/subscription_activity_example5.png)

* A [Subscription Services](../../automating/using/subscription-services.md) activity identifies the services to update as coming from the transition, through the link created in the **[!UICONTROL Reconciliation]** activity.

   Il **[!UICONTROL Operation type]** viene identificato come proveniente dal campo **operation** del file. Qui è possibile selezionare solo campi con un valore booleano o un numero intero. Se la colonna del file che contiene l’operazione da eseguire non viene visualizzata nell’elenco, accertati di aver impostato correttamente il formato della colonna nell’attività **[!UICONTROL Load file]**, come spiegato in precedenza in questo esempio.

   ![](assets/subscription_activity_example_from_file.png)
