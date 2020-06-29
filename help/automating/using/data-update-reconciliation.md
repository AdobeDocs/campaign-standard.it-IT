---
title: Aggiornamento dei dati tramite riconciliazione
description: L'esempio seguente illustra un flusso di lavoro che crea un'audience di profili direttamente da un file importato contenente nuovi client.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 175709a41607bb9d64da7fac77dd749fa84f7360
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 0%

---


# Aggiornamento dei dati tramite riconciliazione {#data-update-reconciliation}

L&#39;esempio seguente illustra un flusso di lavoro che crea un&#39;audience di profili direttamente da un file importato contenente nuovi client. È costituito dalle seguenti attività:

![](assets/identification_example2.png)

* Un&#39;attività [Carica file](../../automating/using/load-file.md) , che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

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

* Un&#39;attività di [riconciliazione](../../automating/using/reconciliation.md) , che collega ogni colonna del file caricato a una colonna della dimensione del profilo. Record di file che non è possibile identificare (dati mancanti, tipo di dati incompatibile, ecc.) vengono ignorate per preservare l&#39;integrità dei dati di audience finali.

   ![](assets/identification_example1.png)

* Un&#39;attività di [salvataggio dell&#39;audience](../../automating/using/save-audience.md) , che consente di salvare l&#39;audience dei profili.

   ![](assets/identification_example3.png)
