---
title: Programmi e campagne
seo-title: Programmi e campagne
description: Programmi e campagne
seo-description: In Adobe Campaign, programmi e campagne consentono di raggruppare e delimitare le diverse attività di marketing a loro collegate. I report su programmi e campagne consentono di analizzarne l'impatto.
page-status-flag: never-activated
uuid: fe 2812 a 8-196 f -4 aba-a 739-fbbfffd 754 cb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: riferimento
topic-tags: piani di marketing
discoiquuid: 21 b 84028-d 1 a 7-4 ad 6-891 a -862 a 94565514
context-tags: campagna, panoramica; Purchgnexplorer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Programs and campaigns{#programs-and-campaigns}

## About plans, programs and campaigns {#about-plans--programs-and-campaigns}

Adobe Campaign ti consente di pianificare campagne di marketing in cui puoi creare e gestire diversi tipi di attività: e-mail, messaggi SMS, notifiche push, flussi di lavoro, pagine di destinazione. Queste campagne e il relativo contenuto possono essere raccolti nei programmi.

I programmi e le campagne consentono di ridisporre e visualizzare le diverse attività di marketing a loro collegate.

* A **program** may contain other programs as well as campaigns, workflows, and landing pages. Viene visualizzato nella timeline e ti aiuta a organizzare le attività di marketing: puoi separarle per paese, per marchio, per unità, ecc.
* A **campaign** enables you to gather all the marketing activities of your choice under a single entity. Una campagna può contenere messaggi e-mail, SMS, notifiche push, posta diretta, flussi di lavoro e pagine di destinazione.

Per organizzare meglio i piani di marketing, Adobe consiglia la seguente gerarchia: Programma &gt; Programmi secondari &gt; Campagne &gt; Flussi di lavoro &gt; Consegne.

I report su programmi e campagne consentono di analizzarne l'impatto. Ad esempio, è possibile creare rapporti a livello di campagna per aggregare dati su tutte le consegne contenute in quella campagna.

**Argomenti correlati:**

* [Timeline](../../start/using/timeline.md)
* [Informazioni sui rapporti dinamici](../../reporting/using/about-dynamic-reports.md)

## Creating a program {#creating-a-program}

Il programma è il primo livello di organizzazione. Può contenere programmi secondari, campagne, flussi di lavoro o pagine di destinazione.

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card.
1. Click on the **[!UICONTROL Create]** button.
1. In the **[!UICONTROL Creation mode]** screen, select a program type.

   ![](assets/programs_and_campaigns_2.png)

   The program types available are based on templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Program templates]** section. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the program.

   ![](assets/programs_and_campaigns_3.png)

1. Selezionate una data iniziale e finale nel programma. Queste date vengono applicate solo al programma stesso.

   Potete creare il programma all'interno di un programma principale. A tal fine, selezionate il programma principale dai programmi esistenti.

1. Click on **[!UICONTROL Create]** to confirm the creation of the program.

Il programma viene creato e visualizzato. Use the **[!UICONTROL Create]** button to add sub-programs, campaigns, workflows or landing pages.

>[!NOTE]
>
>Potete anche creare un programma dall'elenco delle attività di marketing.

## Creating a campaign {#creating-a-campaign}

Nei programmi e nei programmi secondari potete aggiungere campagne. Le campagne possono contenere attività di marketing come e-mail, SMS, notifiche push, flussi di lavoro e pagine di destinazione.

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card and access a program or sub-program.
1. Click on the **[!UICONTROL Create]** button and select **[!UICONTROL Campaign]**.
1. In the **[!UICONTROL Creation mode]** screen, select a campaign type.

   ![](assets/programs_and_campaigns_7.png)

   The campaign types available are based on templates defined in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Campaign templates]**. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the campaign.
1. Selezionate una data iniziale e finale nella campagna. Queste date vengono applicate solo alla campagna stessa.

   ![](assets/programs_and_campaigns_8.png)

1. Click on **[!UICONTROL Create]** to confirm the creation of the campaign.

La campagna viene creata e visualizzata. Use the **[!UICONTROL Create]** button to add marketing activities to your campaign.

>[!NOTE]
>
>A seconda del contratto di licenza, potete accedere solo ad alcune di queste attività.

Potete anche creare una campagna dall'elenco delle attività di marketing. Potete scegliere di collegare l'attività di marketing a un programma principale o a un programma secondario tramite la finestra proprietà della campagna.

## Programs and campaigns icons and statuses {#programs-and-campaigns-icons-and-statuses}

Ciascun programma e ciascuna campagna nell'elenco hanno un simbolo visivo e un'icona il cui colore indica lo stato di esecuzione. Questo stato dipende dal periodo di validità del programma o della campagna.

* Gray: the program/campaign has not yet started - **[!UICONTROL Editing]** status.
* Blue: the program/campaign is in progress - **[!UICONTROL In progress]** status.
* Green: the program/campaign has finished - **[!UICONTROL Finished]** status. By default, the current date is automatically shown as the validity start date and the end date is calculated according to the start date (**D+186 days**). Potete modificare queste date nelle proprietà del programma o della campagna.

![](assets/programs_and_campaigns.png)

