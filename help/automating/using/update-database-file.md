---
title: Aggiornamento del database con dati esterni
description: Questo caso d’uso illustra come aggiungere o aggiornare profili al database di Adobe Campaign con i dati recuperati dal file.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: writer,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 2df7fbed-b979-4706-bd56-83f712cc3070
TQID: 'https://experienceleague.adobe.com/XLH6Hrqg2q-ZNlT-ZcNNlLlvP9xBSchfZs-mgWscROs'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 11%
---
# Aggiornamento del database con dati esterni {#update-database-file}

L&#39;esempio seguente mostra la configurazione di un&#39;attività **[!UICONTROL Update data]** dopo un&#39;attività **[!UICONTROL Load file]**. Lo scopo di questo flusso di lavoro è quello di aggiungere o aggiornare i profili al database di Adobe Campaign con i dati recuperati dal file.

In questo esempio, la chiave di riconciliazione utilizzata è **indirizzo e-mail**. Il file caricato nell&#39;attività [Load file](../../automating/using/load-file.md) è un file in formato **.txt** contenente i seguenti dati di esempio:

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

L&#39;attività [Aggiorna dati](../../automating/using/update-data.md) è configurata come segue:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)
