---
solution: Campaign Standard
product: campaign
title: Stati delle risorse
description: Scopri i diversi stati delle risorse in base al loro stato di pubblicazione.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Stati delle risorse{#resource-statuses}

A seconda del loro stato di pubblicazione o attivazione, le risorse possono avere stati diversi.

Nella schermata **[!UICONTROL Custom resources]** sono presenti due colonne dedicate alla visualizzazione di questi stati.

![](assets/schema_colonne_1.png)

**Stati di pubblicazione**

* **Bozza**: la risorsa è stata appena creata o rielaborata. Per creare le tabelle del database e le API corrispondenti, è necessario ripubblicare la risorsa. Se una risorsa viene rielaborata, diventa automaticamente inattiva dopo il passaggio di pubblicazione.
* **Riprogettazione** in sospeso: la risorsa è stata rielaborata. Il processo di riprogettazione verrà eseguito durante la pubblicazione successiva. La riformulazione è irreversibile. Vengono visualizzati diversi messaggi di avviso per informare l’utente, sia durante la riprogettazione che durante la preparazione della pubblicazione.

   Per ulteriori informazioni sulla riprogettazione, consulta [Eliminazione di una risorsa](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >L’opzione **[!UICONTROL Cancel re-draft]** è disponibile quando la risorsa che desideri rielaborare contiene ancora collegamenti tramite altre risorse con lo stato &quot;Pubblicato&quot;. Questa opzione consente di ripristinare il processo di &quot;riprogettazione&quot;. Le risorse personalizzate torneranno quindi ai loro stati originali.

* **Pubblicato**: la risorsa è stata pubblicata. Se la risorsa viene modificata dopo l’ultima data di modifica, viene visualizzato un messaggio per invitarti a ripubblicare la risorsa per tenere conto delle ultime modifiche.

Il campo **[!UICONTROL Do not publish latest modifications]** impedisce che le modifiche vengano prese in considerazione durante le pubblicazioni future.

Questo campo può essere configurato nella definizione della risorsa personalizzata.
