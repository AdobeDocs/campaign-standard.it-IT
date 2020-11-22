---
solution: Campaign Standard
product: campaign
title: Panoramica
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---


# Panoramica {#calling-a-workflow-with-external-parameters}

Campaign Standard consente di richiamare un flusso di lavoro con parametri (un nome di audience per il targeting, un nome di file da importare, una parte del contenuto del messaggio, ecc.). In questo modo, puoi integrare facilmente le automatizzazioni Campaign con il sistema esterno.

Prendiamo l&#39;esempio seguente, in cui desideriamo inviare e-mail direttamente da un CMS. In tal caso, potete configurare il sistema per selezionare l&#39;audience e il contenuto dell&#39;e-mail nel CMS. Facendo clic su Invia, si chiamerà un flusso di lavoro Campaign con questi parametri, che consente di utilizzarli nel flusso di lavoro per definire il pubblico e il contenuto dell&#39;URL da utilizzare nella distribuzione.

La procedura da seguire per chiamare un flusso di lavoro con parametri è la seguente:

1. Dichiarare i parametri nell&#39; **[!UICONTROL External signal]** attività. See [Declaring the parameters in the External signal activity](../../automating/using/declaring-parameters-external-signal.md).
1. Configurate l&#39; **[!UICONTROL End]** attività o la chiamata API per definire i parametri e attivare l&#39; **[!UICONTROL External signal]** attività del flusso di lavoro. Consulta [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)
1. Una volta attivato il flusso di lavoro, i parametri vengono assimilati nelle variabili degli eventi del flusso di lavoro e possono essere utilizzati all&#39;interno del flusso di lavoro. Consulta [questa pagina](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
