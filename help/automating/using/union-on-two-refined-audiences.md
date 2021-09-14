---
title: Unione di due tipi di pubblico affinati
description: Questo caso d’uso mostra l’unione di due attività Read audience .
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 58%

---

# Unione di due tipi di pubblico affinati {#example--union-on-two-refined-audiences}

Il flusso di lavoro definito in questo esempio mostra l’unione di due attività **[!UICONTROL Read audience]**. L’obiettivo di questo flusso di lavoro è quello di inviare un messaggio e-mail agli iscritti Gold o Silver che hanno un’età compresa tra i 18 e i 30 anni. Nel sistema sono già stati creati tipi di pubblico specifici per tenere traccia degli iscritti Gold e Silver.

Il flusso di lavoro è progettato come segue:

![](assets/readaudience_activity_example1.png)

* Una prima attività [Read audience](../../automating/using/read-audience.md) che recupera il pubblico di iscritti Gold e lo perfeziona selezionando solo i profili di età compresa tra i 18 e i 30 anni.
* Una seconda attività **[!UICONTROL Read audience]** che recupera il pubblico di iscritti Silver e lo perfeziona selezionando solo i profili di età compresa tra i 18 e i 30 anni.
* Un&#39;attività [Union](../../automating/using/union.md) che unisce le popolazioni delle attività **[!UICONTROL Read audiences]** a una popolazione finale.
* Un&#39;attività [Email delivery](../../automating/using/email-delivery.md) che invia l&#39;e-mail alla popolazione proveniente dall&#39;attività **[!UICONTROL Union]**.
