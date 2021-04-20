---
solution: Campaign Standard
product: campaign
title: Configurare l’integrazione Campaign-Analytics
description: Scopri come configurare l’integrazione Adobe Analytics per iniziare a misurare il successo delle consegne e-mail.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---


# Configurare l’integrazione Campaign-Analytics{#configure-campaign-analytics-integration}

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

