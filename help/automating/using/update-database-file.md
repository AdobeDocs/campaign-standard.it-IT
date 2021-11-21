---
title: Aggiornamento del database con dati esterni
description: Questo caso d’uso illustra come aggiungere o aggiornare profili al database Adobe Campaign con i dati recuperati dal file.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 33%

---

# Aggiornamento del database con dati esterni {#update-database-file}

L’esempio seguente mostra la configurazione di un **[!UICONTROL Update data]** attività successiva a **[!UICONTROL Load file]** attività. Lo scopo del presente flusso di lavoro è quello di aggiungere o aggiornare i profili del database Adobe Campaign sulla base dei dati recuperati dal file.

In questo esempio, la chiave di riconciliazione utilizzata è la **indirizzo e-mail**. Il file caricato nel [Load file](../../automating/using/load-file.md) è un’attività **.txt** file di formato contenente i seguenti dati di esempio:

```
lastname;firstname;email;birthdate
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

La [Update data](../../automating/using/update-data.md) l’attività viene configurata come segue:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
