---
solution: Campaign Standard
product: campaign
title: Panoramica
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Flussi di lavoro
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 4%

---


# Panoramica {#calling-a-workflow-with-external-parameters}

Campaign Standard consente di chiamare un flusso di lavoro con parametri (un nome di pubblico per il targeting, un nome di file per l’importazione, una parte del contenuto del messaggio, ecc.). In questo modo, puoi integrare facilmente le automatizzazioni Campaign con il tuo sistema esterno.

Prendiamo l’esempio seguente, dove desideri inviare e-mail direttamente da un CMS. In tal caso, puoi configurare il sistema per selezionare il pubblico e il contenuto dell’e-mail nel CMS. Fai clic su Invia per chiamare un flusso di lavoro Campaign con questi parametri, per utilizzarli nel flusso di lavoro per definire il pubblico e il contenuto URL da utilizzare nella consegna.

Il processo per chiamare un flusso di lavoro con parametri è il seguente:

1. Dichiara i parametri nell’attività **[!UICONTROL External signal]** . Consulta [Dichiarazione dei parametri nell&#39;attività del segnale esterno](../../automating/using/declaring-parameters-external-signal.md).
1. Configura l’attività **[!UICONTROL End]** o la chiamata API per definire i parametri e attivare l’attività del flusso di lavoro **[!UICONTROL External signal]**. Consulta [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)
1. Una volta attivato il flusso di lavoro, i parametri vengono acquisiti nelle variabili degli eventi del flusso di lavoro e possono essere utilizzati all’interno del flusso di lavoro. Consulta [questa pagina](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
