---
title: Stati delle risorse
description: Scoprite i diversi stati delle risorse in base al relativo stato di pubblicazione.
page-status-flag: mai attivato
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: development
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Stati delle risorse{#resource-statuses}

Le risorse possono avere stati diversi in base al loro stato di pubblicazione o attivazione.

Sono disponibili due colonne dedicate alla visualizzazione di questi stati sullo **[!UICONTROL Custom resources]** schermo.

![](assets/schema_colonne_1.png)

**Stati pubblicazione**

* **Bozza**: la risorsa è stata appena creata o rielaborata. Per creare le tabelle del database e le API corrispondenti, la risorsa deve essere ripubblicata. Se una risorsa viene rielaborata, viene automaticamente resa inattiva dopo il passaggio di pubblicazione.
* **Ricarica** in sospeso: la risorsa è stata rielaborata. Il processo di rielaborazione verrà eseguito durante la pubblicazione successiva. La riformulazione è irreversibile. Diversi messaggi di avviso avvisano l’utente di questo problema sia durante la rielaborazione che durante la preparazione della pubblicazione.

   Per ulteriori informazioni sulla rielaborazione, consultate [Eliminazione di una risorsa](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >L' **[!UICONTROL Cancel re-draft]** opzione è disponibile quando la risorsa che si desidera rigenerare contiene ancora collegamenti tramite altre risorse con lo stato "Pubblicato". Questa opzione consente di ripristinare il processo di "ri-bozza". Le risorse personalizzate torneranno quindi agli stati originali.

* **Pubblicato**: la risorsa è stata pubblicata. Se la risorsa viene modificata dopo l’ultima data di modifica, viene visualizzato un messaggio in cui si chiede all’utente di ripubblicare il contenuto per tenere conto delle ultime modifiche.

Il **[!UICONTROL Do not publish latest modifications]** campo impedisce che le modifiche vengano prese in considerazione durante pubblicazioni future.

Questo campo può essere configurato nella definizione delle risorse personalizzate.
