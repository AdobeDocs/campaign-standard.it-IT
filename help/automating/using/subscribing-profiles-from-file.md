---
solution: Campaign Standard
product: campaign
title: Iscrizione di profili da un file a un servizio specifico
description: Questo caso d’uso mostra come importare un file contenente dei profili e iscriverli a un servizio esistente.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---


# Subscribing profiles to a specific service after importing a file {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Questo esempio illustra come importare un file contenente profili ed effettuarne l’abbonamento a un servizio esistente. Dopo l’importazione del file, è necessario eseguire una riconciliazione in modo tale che i dati importati possano essere identificati come profili. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un’attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* A [Load file](../../automating/using/load-file.md) activity loads the profile file and defines the structure of the imported columns.

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

* A [Reconciliation](../../automating/using/reconciliation.md) activity identifies the data from the file as belonging to the profile dimension of the Adobe Campaign database. Solo la scheda **[!UICONTROL Identification]** è configurata. Essa identifica i dati del file in base agli indirizzi e-mail dei profili.

   ![](assets/subscription_activity_example3.png)

* A [Deduplication](../../automating/using/deduplication.md) based on the **email** field of the temporary resource (resulting from the reconciliation) identifies any duplicates. Se i dati importati dal file contengono duplicati, l’abbonamento a un servizio non riuscirà per tutti i dati.

   ![](assets/subscription_activity_example5.png)

* A [Subscription Services](../../automating/using/subscription-services.md) activity lets you select the service to which the profiles must be subscribed, the field corresponding to the subscription date, and the origin of the subscription.

   ![](assets/subscription_activity_example4.png)
