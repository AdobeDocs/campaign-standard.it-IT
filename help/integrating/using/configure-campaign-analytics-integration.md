---
title: Configurare l’integrazione di Campaign e Analytics
description: Scopri come configurare l’integrazione Adobe Analytics per iniziare a misurare il successo delle consegne e-mail.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---

# Configurare l’integrazione di Campaign e Analytics{#configure-campaign-analytics-integration}

Questa integrazione ti consente di condividere i dati Key Performance Indicator direttamente da Adobe Campaign ad Adobe Analytics Standard o Premium.

Per avviare l’integrazione tra Adobe Campaign Standard e Adobe Analytics, devi prima configurare l’account esterno collegato ad Adobe Analytics.

Gli account esterni e i flussi di lavoro tecnici possono essere gestiti solo dall’amministratore funzionale della piattaforma.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration > Application settings > External accounts]**.
1. Seleziona l’account esterno **[!UICONTROL Share KPIs with Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Specifica i valori **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** nel campo **[!UICONTROL Connection]** .

   Questi parametri si trovano in Analytics selezionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Fai clic sul pulsante **[!UICONTROL Refresh report suites]**.
1. Seleziona nel menu a discesa **[!UICONTROL Analytics default report suite]** la suite di rapporti Adobe Analytics da arricchire con i dati di Adobe Campaign.

   L’account esterno è ora pronto e collegato ad Adobe Analytics. Puoi disattivarlo in qualsiasi momento selezionando la casella **[!UICONTROL Enabled]** .

   ![](assets/analytics.png)

Il flusso di lavoro tecnico **[!UICONTROL Share KPIs with Adobe Analytics]** viene ora avviato automaticamente e può essere visualizzato dal menu avanzato selezionando **[!UICONTROL Administration > Application settings > Workflow]**. Questo flusso di lavoro tecnico verrà eseguito automaticamente ogni 15 minuti e invierà fino a 6 mesi di dati in Adobe Analytics.

![](assets/analytics_3.png)

I dati sono ora disponibili in Adobe Analytics.

**Argomenti correlati:**

* [Account esterni](../../administration/using/external-accounts.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Video sulla condivisione di KPI per il reporting ](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html) integrato di Campaign
