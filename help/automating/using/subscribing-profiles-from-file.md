---
title: Iscrizione di profili da un file a un servizio specifico
description: Questo caso d’uso mostra come importare un file contenente dei profili e iscriverli a un servizio esistente.
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
source-wordcount: '238'
ht-degree: 0%

---


# Iscrizione di profili a un servizio specifico dopo l’importazione di un file {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Questo esempio illustra come importare un file contenente profili e iscriverlo a un servizio esistente. Dopo l&#39;importazione del file, è necessario eseguire una riconciliazione in modo che i dati importati possano essere identificati come profili. Per garantire che il file non contenga duplicati, sui dati verrà eseguita un&#39;attività di deduplicazione.

Il flusso di lavoro viene presentato come segue:

![](assets/subscription_activity_example1.png)

* Un&#39;attività [Carica file](../../automating/using/load-file.md) carica il file di profilo e definisce la struttura delle colonne importate.

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

* Un&#39;attività di [riconciliazione](../../automating/using/reconciliation.md) identifica i dati del file come appartenenti alla dimensione del profilo del database del Adobe Campaign . È configurata solo la **[!UICONTROL Identification]** scheda. Identifica i dati del file in base agli indirizzi e-mail dei profili.

   ![](assets/subscription_activity_example3.png)

* Una [deduplicazione](../../automating/using/deduplication.md) basata sul campo **e-mail** della risorsa temporanea (derivante dalla riconciliazione) identifica eventuali duplicati. Se i dati importati dal file contengono duplicati, la sottoscrizione a un servizio non riuscirà per tutti i dati.

   ![](assets/subscription_activity_example5.png)

* Un&#39;attività Servizi [](../../automating/using/subscription-services.md) iscrizione consente di selezionare il servizio al quale devono essere sottoscritti i profili, il campo corrispondente alla data di iscrizione e l&#39;origine dell&#39;iscrizione.

   ![](assets/subscription_activity_example4.png)
