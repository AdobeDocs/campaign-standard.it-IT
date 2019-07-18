---
title: Utilizzo dei dati del flusso di lavoro
seo-title: Utilizzo dei dati del flusso di lavoro
description: Utilizzo dei dati del flusso di lavoro
seo-description: Scopri le diverse possibilità di utilizzo dei dati importati o mirati.
page-status-flag: never-activated
uuid: 3 dd 66 aeb -3 a 26-4214-b 6 a 0-242 c 2 b 7 fbc 49
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: workflow-general-operation
discoiquuid: 90 b 250 f 1-f 32 d -4256-83 ea -4 c 0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Using workflow data{#using-workflow-data}

Una volta identificati e preparati i dati, questi possono essere utilizzati nei seguenti contesti:

* The **[!UICONTROL Update data]** activity allows you to perform a mass update on fields in the database.
* The **[!UICONTROL Save audience]** activity allows you to update an existing audience or create a new audience from the population computed upstream in a workflow. The audiences created or updated from this activity are **List** or **File** audiences. Questa attività consente anche di esportare profili come pubblico/segmenti di Adobe Experience Cloud.
* The **[!UICONTROL Subscription Services]** activity allows you to take profiles in mass and subscribe them to a service or unsubscribe them from a service.
* The **[!UICONTROL Extract file]** activity allows you to export data from Adobe Campaign in the form of an external file.

Dopo aver definito una destinazione di profilo, puoi usare diverse attività per creare e inviare le consegne:

* The **[!UICONTROL Email delivery]** activity allows you to configure sending an email in a workflow. This can be a **single send** email and sent just once, or it can be a **recurring** email.
* The **[!UICONTROL SMS delivery]** activity allows you to configure sending an SMS in a workflow. This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.
* The **[!UICONTROL Mobile app delivery]** activity allows you to configure sending a push notification in a workflow. This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

