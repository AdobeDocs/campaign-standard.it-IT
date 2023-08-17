---
title: Aggiornamento dei dati tramite riconciliazione
description: L’esempio seguente illustra un flusso di lavoro che crea un pubblico di profili direttamente da un file importato contenente nuovi clienti.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 67%

---

# Aggiornamento dei dati tramite riconciliazione {#data-update-reconciliation}

L’esempio seguente illustra un flusso di lavoro che crea un pubblico di profili direttamente da un file importato contenente nuovi clienti. È costituito dalle seguenti attività:

![](assets/identification_example2.png)

* A [Carica file](../../automating/using/load-file.md) che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

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

* A [Reconciliation](../../automating/using/reconciliation.md) che collega ciascuna colonna del file caricato a una colonna della dimensione del profilo. I record di file che non è possibile identificare (dati mancanti, tipo di dati incompatibile, ecc.) vengono ignorati per preservare l’integrità dei dati di pubblico finali.

  ![](assets/identification_example1.png)

* A [Salva pubblico](../../automating/using/save-audience.md) che consente di salvare il pubblico di profili.

  ![](assets/identification_example3.png)
