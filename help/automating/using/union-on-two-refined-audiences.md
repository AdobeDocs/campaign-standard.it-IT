---
title: Unione di due tipi di pubblico affinati
description: Questo caso d’uso mostra l’unione di due attività Read audience.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 43%

---

# Unione di due tipi di pubblico affinati {#example--union-on-two-refined-audiences}

Il flusso di lavoro definito in questo esempio mostra l’unione di due attività **[!UICONTROL Read audience]**. L’obiettivo di questo flusso di lavoro è quello di inviare un’e-mail agli iscritti Gold o Silver che hanno un’età compresa tra i 18 e i 30 anni. Nel sistema sono già stati creati tipi di pubblico specifici per tenere traccia degli iscritti Gold e Silver.

Il flusso di lavoro è progettato come segue:

![](assets/readaudience_activity_example1.png)

* Una prima attività [Read audience](../../automating/using/read-audience.md) che recupera il pubblico di iscritti Gold e lo perfeziona selezionando solo i profili di età compresa tra 18 e 30 anni.
* Una seconda attività **[!UICONTROL Read audience]** che recupera il pubblico di iscritti Silver e lo perfeziona selezionando solo i profili di età compresa tra i 18 e i 30 anni.
* Un&#39;attività [Union](../../automating/using/union.md) che unisce le popolazioni di entrambe le attività **[!UICONTROL Read audiences]** in un gruppo finale.
* Un&#39;attività [Email delivery](../../automating/using/email-delivery.md) che invia l&#39;e-mail ai gruppi provenienti dall&#39;attività **[!UICONTROL Union]**.
