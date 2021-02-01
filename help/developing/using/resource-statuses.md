---
solution: Campaign Standard
product: campaign
title: Stati delle risorse
description: Scoprite i diversi stati delle risorse in base al relativo stato di pubblicazione.
audience: developing
content-type: reference
topic-tags: about-custom-resources
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# Stati delle risorse{#resource-statuses}

A seconda della pubblicazione o dello stato di attivazione, le risorse possono avere stati diversi.

Sono disponibili due colonne dedicate alla visualizzazione di questi stati nella schermata **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Stati pubblicazione**

* **Bozza**: la risorsa è stata appena creata o rielaborata. Per creare le tabelle del database e le API corrispondenti, la risorsa deve essere ripubblicata. Se una risorsa viene rielaborata, diventa automaticamente inattiva dopo il passaggio della pubblicazione.
* **Ricarica** in sospeso: la risorsa è stata rielaborata. Il processo di rielaborazione si verificherà durante la pubblicazione successiva. La riformulazione è irreversibile. Vari messaggi di avviso vengono visualizzati per informare l’utente, sia durante la rielaborazione che durante la preparazione della pubblicazione.

   Per ulteriori informazioni sulla rielaborazione, vedere [Eliminazione di una risorsa](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >L&#39;opzione **[!UICONTROL Cancel re-draft]** è disponibile quando la risorsa che si desidera rigenerare contiene ancora collegamenti tramite altre risorse con lo stato &quot;Pubblicato&quot;. Questa opzione consente di ripristinare il processo di &quot;ri-bozza&quot;. Le risorse personalizzate torneranno quindi agli stati originali.

* **Pubblicato**: la risorsa è stata pubblicata. Se la risorsa viene modificata dopo l’ultima data di modifica, viene visualizzato un messaggio per invitarvi a ripubblicare la risorsa per tenere conto delle modifiche più recenti.

Il campo **[!UICONTROL Do not publish latest modifications]** impedisce che le modifiche vengano prese in considerazione durante pubblicazioni future.

Questo campo può essere configurato nella definizione delle risorse personalizzate.
