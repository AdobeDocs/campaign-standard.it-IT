---
title: Stati delle risorse
description: Scopri i diversi stati delle risorse in base al loro stato di pubblicazione.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
TQID: https://experienceleague.adobe.com/f0ihge9X4opmgRRdswkBt7yMWSmJc36viZKWXPoQCe4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 233
ht-degree: 1%

---

# Stati delle risorse{#resource-statuses}

A seconda del loro stato di pubblicazione o attivazione, le risorse possono avere stati diversi.

Sono disponibili due colonne dedicate alla visualizzazione di questi stati nella schermata **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Stati pubblicazione**

* **Bozza**: la risorsa è stata appena creata o riscritta. Per creare le tabelle del database e le API corrispondenti, è necessario ripubblicare la risorsa. Se una risorsa viene riscritta, diventa automaticamente inattiva dopo il passaggio di pubblicazione.
* **Nuova bozza in sospeso**: la risorsa è stata riscritta. Il processo di riprogettazione si verificherà durante la pubblicazione successiva. La riprogettazione è irreversibile. Vengono visualizzati diversi messaggi di avviso per informare l’utente, sia durante la riprogettazione che durante la preparazione alla pubblicazione.

  Per ulteriori informazioni sulla riprogettazione, vedere [Eliminazione di una risorsa](../../developing/using/deleting-a-resource.md).

  >[!NOTE]
  >
  >L&#39;opzione **[!UICONTROL Cancel re-draft]** è disponibile quando la risorsa di cui si desidera rielaborare la bozza contiene ancora collegamenti attraverso altre risorse con stato &quot;Pubblicato&quot;. Questa opzione consente di ripristinare il processo di &quot;riprogettazione&quot;. Le risorse personalizzate torneranno quindi allo stato originale.

* **Pubblicato**: la risorsa è stata pubblicata. Se la risorsa viene modificata dopo l’ultima data di modifica, viene visualizzato un messaggio per invitarti a ripubblicare la risorsa per tenere conto delle ultime modifiche.

Il campo **[!UICONTROL Do not publish latest modifications]** impedisce che le modifiche vengano prese in considerazione durante le pubblicazioni future.

Questo campo può essere configurato nella definizione di risorsa personalizzata.
