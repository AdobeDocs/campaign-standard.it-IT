---
title: Configurare l’integrazione di Campaign e Analytics
description: Scopri come configurare l’integrazione di Adobe Analytics per iniziare a misurare il successo delle consegne e-mail.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: 26260b9e633d8be1652eeb46c982864a7477da27
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# Configurare l’integrazione di Campaign e Analytics{#configure-campaign-analytics-integration}

Questa integrazione ti consente di condividere i dati degli indicatori di prestazioni chiave direttamente da Adobe Campaign ad Adobe Analytics Standard o Premium.

Per avviare l’integrazione tra Adobe Campaign Standard e Adobe Analytics, devi innanzitutto configurare l’account esterno collegato ad Adobe Analytics.

Gli account esterni e i flussi di lavoro tecnici possono essere gestiti solo dall’amministratore funzionale della piattaforma.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleziona la **[!UICONTROL Share KPIs with Adobe Analytics]** account esterno.

   ![](assets/analytics_2.png)

1. Specifica il **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** nel **[!UICONTROL Connection]** campo.

   Questi parametri si trovano in Analytics selezionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Fai clic sul pulsante **[!UICONTROL Refresh report suites]**.
1. Seleziona in **[!UICONTROL Analytics default report suite]** menu a discesa la suite di rapporti di Adobe Analytics che desideri arricchire con i dati di Adobe Campaign.

   Il tuo account esterno è ora pronto e collegato ad Adobe Analytics. Puoi disattivarla in qualsiasi momento selezionando la **[!UICONTROL Enabled]** casella.

   ![](assets/analytics.png)

Il **[!UICONTROL Share KPIs with Adobe Analytics]** viene avviato automaticamente il flusso di lavoro tecnico, che può essere visualizzato dal menu avanzato selezionando **[!UICONTROL Administration > Application settings > Workflow]**. Questo flusso di lavoro tecnico può conservare i broadlog che risalgono a un massimo di 6 mesi fa. Tieni presente che questo flusso di lavoro è incrementale e invierà i dati del giorno precedente.

![](assets/analytics_3.png)

I dati sono ora disponibili in Adobe Analytics.

**Argomenti correlati:**

* [Account esterni](../../administration/using/external-accounts.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Condividere i KPI per il reporting integrato di Campaign](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html) video
