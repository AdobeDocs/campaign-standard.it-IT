---
title: Unione su due tipi di pubblico raffinati
description: Questo caso di utilizzo mostra l'unione di due attività di lettura dell'audience.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '150'
ht-degree: 0%

---


# Unione su due tipi di pubblico raffinati {#example--union-on-two-refined-audiences}

Il flusso di lavoro definito in questo esempio mostra l&#39;unione di due **[!UICONTROL Read audience]** attività. L&#39;obiettivo di questo flusso di lavoro è quello di inviare un&#39;e-mail ai membri Gold o Silver che hanno tra i 18 e i 30 anni. Nel sistema sono già state create audience specifiche per tenere traccia dei membri Gold e Silver.

Il flusso di lavoro è progettato come segue:

![](assets/readaudience_activity_example1.png)

* Una prima attività di [lettura dell&#39;audience](../../automating/using/read-audience.md) che recupera l&#39;audience dei membri Gold e la perfeziona selezionando solo i profili con età compresa tra 18 e 30 anni.
* Una seconda **[!UICONTROL Read audience]** attività che recupera l&#39;audience dei membri Silver e la perfeziona selezionando solo i profili con età compresa tra 18 e 30 anni.
* Un&#39;attività [dell&#39;Unione](../../automating/using/union.md) che unisce le popolazioni di entrambe **[!UICONTROL Read audiences]** le attività a una popolazione finale.
* Un&#39;attività di consegna [e-mail che invia l&#39;e-mail alla popolazione proveniente dall&#39;](../../automating/using/email-delivery.md) **[!UICONTROL Union]** attività.
