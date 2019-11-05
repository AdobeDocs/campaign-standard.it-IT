---
title: Configurare l’integrazione Campaign-Analytics
description: Scopri come configurare l’integrazione di Adobe Analytics per iniziare a misurare il successo delle comunicazioni e-mail.
page-status-flag: mai attivato
uuid: bdaa00b0-7445-469c-8268-9d06c53ce2b0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: lavorare con campagne e analisi
discoiquuid: 92b9004c-cba0-41fd-a035-32bee1d6a42c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configurare l’integrazione Campaign-Analytics{#configure-campaign-analytics-integration}

Questa integrazione consente di condividere i dati Indicatore prestazioni chiave direttamente da Adobe Campaign ad Adobe Analytics Standard o Premium.

Per avviare l'integrazione tra Adobe Campaign Standard e Adobe Analytics, devi prima configurare l'account esterno collegato ad Adobe Analytics.

Gli account esterni e i flussi di lavoro tecnici possono essere gestiti solo dall'amministratore funzionale della piattaforma.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration > Application settings > External accounts]**.
1. Selezionate l’account **[!UICONTROL Share KPIs with Adobe Analytics]** esterno.

   ![](assets/analytics_2.png)

1. Specificate il vostro **[!UICONTROL Web services user name]** e **[!UICONTROL Web services share secret]** nel **[!UICONTROL Connection]** campo.

   Questi parametri si trovano in Analytics selezionando **[!UICONTROL Admin > Company settings > Web services]**.

   ![](assets/analytics_1.png)

1. Fate clic sul **[!UICONTROL Refresh report suites]** pulsante.
1. Seleziona nel **[!UICONTROL Analytics default report suite]** menu a discesa la suite di rapporti di Adobe Analytics da arricchire con i dati di Adobe Campaign.

   Il tuo account esterno è ora pronto e collegato ad Adobe Analytics. È possibile disattivarlo in qualsiasi momento selezionando la **[!UICONTROL Enabled]** casella.

   ![](assets/analytics.png)

Il flusso di lavoro **[!UICONTROL Share KPIs with Adobe Analytics]** tecnico viene ora avviato automaticamente e può essere visualizzato dal menu avanzato selezionando **[!UICONTROL Administration > Application settings > Workflow]**. Questo flusso di lavoro tecnico verrà eseguito automaticamente ogni 15 minuti e invierà dati fino a 6 mesi in Adobe Analytics.

![](assets/analytics_3.png)

I dati sono ora disponibili in Adobe Analytics.

**Argomenti correlati:**

* [Account esterni](../../administration/using/external-accounts.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Condivisione di KPI per video di reporting](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) delle campagne integrati

