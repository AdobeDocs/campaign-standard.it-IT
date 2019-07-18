---
title: Stati delle risorse
seo-title: Stati delle risorse
description: Stati delle risorse
seo-description: Scopri i diversi stati di risorse in base al loro stato di pubblicazione.
page-status-flag: never-activated
uuid: 215 c 0 a 2 e -27 ec -43 f 3-baac -1 eaac 7640784
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: sviluppo
content-type: riferimento
topic-tags: about-custom-resources
discoiquuid: 85516477-1 b 95-4273-a 0 a 7-d 2 cbb 9950 afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Resource statuses{#resource-statuses}

Le risorse possono avere stati diversi in base alla pubblicazione o allo stato di attivazione.

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**Stati pubblicazione**

* **Bozza**: la risorsa è stata appena creata o rielaborata. Per creare le tabelle di database e le API corrispondenti, la risorsa deve essere ripubblicata. Se una risorsa viene rielaborata, viene automaticamente riprodotta dopo il passaggio di pubblicazione.
* **Re-draft in sospeso**: la risorsa è stata rielaborata. Il processo di ribozza si verifica durante la pubblicazione successiva. La riprogettazione è irreversibile. Diversi messaggi di avviso avvisa l'utente di questo fatto sia durante la riscrittura che durante la preparazione alla pubblicazione.

   For more on re-drafting, see [Deleting a resource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >The **[!UICONTROL Cancel re-draft]** option is available when the resource that you want to re-draft still contains links through other resources with the "Published" status. Questa opzione consente di ripristinare il processo di ribozza. Le risorse personalizzate torneranno a rispondere ai loro stati originali.

* **Pubblicato**: la risorsa è stata pubblicata. Se la risorsa viene modificata dopo la data dell'ultima modifica, viene visualizzato un messaggio che chiede all'utente di ripubblicare per prendere in considerazione le modifiche più recenti.

**[!UICONTROL Do not publish latest modifications]** Il campo impedisce che le modifiche vengano prese in considerazione durante pubblicazioni future.

Questo campo può essere configurato nella definizione della risorsa personalizzata.
