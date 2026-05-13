---
title: Configurare l’integrazione di Campaign e Analytics
description: Scopri come configurare l’integrazione di Adobe Analytics per iniziare a misurare il successo delle consegne e-mail.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
TQID: https://experienceleague.adobe.com/bt1FQbafwhEuRao-YFhynO-ecg5EaiUDskSFvxuFv-k
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 10%

---

# Configurare l’integrazione di Campaign e Analytics{#configure-campaign-analytics-integration}

Questa integrazione ti consente di condividere i dati degli indicatori di prestazioni chiave direttamente da Adobe Campaign ad Adobe Analytics Standard o Premium.

Per avviare l’integrazione tra Adobe Campaign Standard e Adobe Analytics, devi innanzitutto configurare l’account esterno collegato ad Adobe Analytics.

Gli account esterni e i flussi di lavoro tecnici possono essere gestiti solo dall’amministratore funzionale della piattaforma.

1. Dal menu avanzato, tramite il logo Adobe Campaign, selezionare **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selezionare l&#39;account esterno **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Specificare **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** nel campo **[!UICONTROL Connection]**.

   Questi parametri sono disponibili in Analytics selezionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Fai clic sul pulsante **[!UICONTROL Refresh report suites]**.
1. Seleziona nel menu a discesa **[!UICONTROL Analytics default report suite]** la suite di rapporti di Adobe Analytics che desideri arricchire con i dati di Adobe Campaign.

   Il tuo account esterno è ora pronto e collegato ad Adobe Analytics. È possibile disattivarla in qualsiasi momento selezionando la casella **[!UICONTROL Enabled]**.

   ![](assets/analytics.png)

Il flusso di lavoro tecnico **[!UICONTROL Share KPIs with Adobe Analytics]** verrà avviato automaticamente e potrà essere visualizzato dal menu avanzato selezionando **[!UICONTROL Administration > Application settings > Workflow]**. Questo flusso di lavoro tecnico può conservare i broadlog che risalgono a un massimo di 6 mesi fa. Tieni presente che questo flusso di lavoro è incrementale e invierà i dati del giorno precedente.

![](assets/analytics_3.png)

I dati sono ora disponibili in Adobe Analytics.

**Argomenti correlati:**

* [Account esterni](../../administration/using/external-accounts.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Video sulla condivisione dei KPI per il reporting integrato di Campaign](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html)
