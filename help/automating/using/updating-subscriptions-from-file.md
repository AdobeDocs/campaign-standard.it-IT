---
title: Aggiornamento di più stati di iscrizione da un file
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---


# Aggiornamento di più stati di iscrizione da un file {#updating-multiple-subscription-statuses-from-a-file}

Questo esempio illustra come importare un file contenente dei profili e aggiornare la propria sottoscrizione a diversi servizi specificati nel file. Dopo l&#39;importazione del file, è necessario eseguire una riconciliazione in modo che i dati importati possano essere identificati come profili con un collegamento ai servizi. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un&#39;attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* Un&#39;attività [Carica file](../../automating/using/load-file.md) carica il file di profilo e definisce la struttura delle colonne importate.

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

* Un&#39;attività di [riconciliazione](../../automating/using/reconciliation.md) identifica i dati del file come appartenenti alla dimensione del profilo del database del Adobe Campaign . Tramite la **[!UICONTROL Identification]** scheda, il campo **e-mail** del file corrisponde al campo **e-mail** della risorsa del profilo.

   ![](assets/subscription_activity_example3.png)

   Nella **[!UICONTROL Relations]** scheda, viene creato un collegamento con la risorsa del servizio per consentire il riconoscimento del campo del **servizio** del file. In questo esempio, i valori corrispondono al campo del **nome** della risorsa del servizio.

   ![](assets/subscription_example_service_relation.png)

* Una [deduplicazione](../../automating/using/deduplication.md) basata sul campo **e-mail** della risorsa temporanea (derivante dalla riconciliazione) identifica i duplicati. È importante eliminare i duplicati, in quanto la sottoscrizione a un servizio non riesce per tutti i dati in caso di duplicati.

   ![](assets/subscription_activity_example5.png)

* Un&#39;attività Servizi [](../../automating/using/subscription-services.md) iscrizione identifica i servizi da aggiornare come derivanti dalla transizione, attraverso il collegamento creato nell&#39; **[!UICONTROL Reconciliation]** attività.

   Il file **[!UICONTROL Operation type]** viene identificato come proveniente dal campo **operativo** del file. Qui è possibile selezionare solo i campi booleani o Interi. Se la colonna del file che contiene l&#39;operazione da eseguire non viene visualizzata nell&#39;elenco, accertatevi di aver impostato correttamente il formato della colonna nell&#39; **[!UICONTROL Load file]** attività, come spiegato in precedenza in questo esempio.

   ![](assets/subscription_activity_example_from_file.png)
