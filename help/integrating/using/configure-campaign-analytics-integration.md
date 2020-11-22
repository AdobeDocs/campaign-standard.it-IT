---
solution: Campaign Standard
product: campaign
title: Configurare l’integrazione Campaign-Analytics
description: Scoprite come configurare l'integrazione  Adobe Analytics per iniziare a misurare il successo delle comunicazioni e-mail.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 9%

---


# Configurare l’integrazione Campaign-Analytics{#configure-campaign-analytics-integration}

Questa integrazione consente di condividere i dati Indicatore prestazioni chiave direttamente da  Adobe Campaign a  Adobe Analytics Standard o Premium.

Per avviare l&#39;integrazione tra  Adobe Campaign Standard e  Adobe Analytics, è innanzitutto necessario configurare l&#39;account esterno collegato a  Adobe Analytics.

Gli account esterni e i flussi di lavoro tecnici possono essere gestiti solo dall&#39;amministratore funzionale della piattaforma.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]**.
1. Select the **[!UICONTROL Share KPIs with Adobe Analytics]** external account.

   ![](assets/analytics_2.png)

1. Specificate il vostro **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** nel **[!UICONTROL Connection]** campo.

   Questi parametri si trovano in Analytics selezionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Fai clic sul pulsante **[!UICONTROL Refresh report suites]**.
1. Selezionate nel **[!UICONTROL Analytics default report suite]** menu a discesa la suite di rapporti Adobe Analytics  che desiderate arricchire con  dati Adobe Campaign.

   L&#39;account esterno è ora pronto e collegato a  Adobe Analytics. È possibile disattivarlo in qualsiasi momento selezionando la **[!UICONTROL Enabled]** casella.

   ![](assets/analytics.png)

Il flusso di lavoro **[!UICONTROL Share KPIs with Adobe Analytics]** tecnico viene ora avviato automaticamente e può essere visualizzato dal menu avanzato selezionando **[!UICONTROL Administration > Application settings > Workflow]**. Questo flusso di lavoro tecnico verrà eseguito automaticamente ogni 15 minuti e porterà fino a 6 mesi di dati in  Adobe Analytics.

![](assets/analytics_3.png)

I dati sono ora disponibili in  Adobe Analytics.

**Argomenti correlati:**

* [Account esterni](../../administration/using/external-accounts.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Condivisione di KPI per video di reporting](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html) delle campagne integrati

