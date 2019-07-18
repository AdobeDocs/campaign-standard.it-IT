---
title: Configurazione dell'integrazione con Campaign-Analytics
seo-title: Configurazione dell'integrazione con Campaign-Analytics
description: Configurazione dell'integrazione con Campaign-Analytics
seo-description: Scopri come configurare l'integrazione di Adobe Analytics per iniziare a misurare il successo delle comunicazioni e-mail.
page-status-flag: never-activated
uuid: bdaa 00 b 0-7445-469 c -8268-9 d 06 c 53 ce 2 b 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-analytics
discoiquuid: 92 b 9004 c-cba 0-41 fd-a 035-32 bee 1 d 6 a 42 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configure Campaign-Analytics integration{#configure-campaign-analytics-integration}

Questa integrazione consente di condividere i dati dell'indicatore prestazioni chiave direttamente da Adobe Campaign ad Adobe Analytics Standard o Premium.

Per avviare l'integrazione tra Adobe Campaign Standard e Adobe Analytics, devi prima configurare l'account esterno collegato ad Adobe Analytics.

Gli account esterni e i flussi di lavoro tecnici possono essere gestiti solo dall'amministratore funzionale della piattaforma.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Specify your **[!UICONTROL Web services user name]** and **[!UICONTROL Web services share secret]** in the **[!UICONTROL Connection]** field.

   These parameters can be found in Analytics by selecting **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Click the **[!UICONTROL Refresh report suites]** button.
1. Select in the **[!UICONTROL Analytics default report suite]** drop-down the Adobe Analytics report suite you want to enrich with Adobe Campaign data.

   L'account esterno è ora pronto e collegato ad Adobe Analytics. You can disable it at any time by checking the **[!UICONTROL Enabled]** box.

   ![](assets/analytics.png)

The **[!UICONTROL Share KPIs with Adobe Analytics]** technical workflow will now automatically launch and can be viewed from the advanced menu by selecting **[!UICONTROL Administration > Application settings > Workflow]**. Questo flusso di lavoro tecnico viene eseguito automaticamente ogni 15 minuti e invierà fino a 6 mesi di vecchi dati in Adobe Analytics.

![](assets/analytics_3.png)

I tuoi dati sono ora disponibili in Adobe Analytics.

**Argomenti correlati:**

* [Account esterni](../../administration/using/external-accounts.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Condivisione di KPI per video di reporting](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) campagna integrata

