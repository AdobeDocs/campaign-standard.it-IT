---
title: Panoramica
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 538056e6-b5c0-4258-a34b-524fe6e3cbbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 2%

---

# Panoramica {#calling-a-workflow-with-external-parameters}

Campaign Standard ti consente di chiamare un flusso di lavoro con parametri (un nome di pubblico per il target, un nome di file da importare, una parte del contenuto del messaggio, ecc.). In questo modo, puoi integrare facilmente le automazioni di Campaign con il sistema esterno.

Prendiamo l’esempio seguente, in cui vogliamo inviare le e-mail direttamente da un CMS. In tal caso, puoi configurare il sistema per selezionare il pubblico e il contenuto dell’e-mail nel CMS. Facendo clic su Invia verrà quindi richiamato un flusso di lavoro di Campaign con questi parametri, che potrai utilizzare nel flusso di lavoro per definire il pubblico e il contenuto dell’URL da utilizzare nella consegna.

Il processo per chiamare un flusso di lavoro con parametri è il seguente:

1. Dichiara i parametri in **[!UICONTROL External signal]** attività. Consulta [Dichiarazione dei parametri nell’attività External signal](../../automating/using/declaring-parameters-external-signal.md).
1. Configurare **[!UICONTROL End]** per definire i parametri e attivare il flusso di lavoro. **[!UICONTROL External signal]** attività. Consulta [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)
1. Una volta attivato il flusso di lavoro, i parametri vengono acquisiti nelle variabili degli eventi del flusso di lavoro e possono essere utilizzati all’interno del flusso di lavoro. Consulta [questa pagina](../../automating/using/customizing-workflow-external-parameters.md).

![](assets/extsignal_process.png)
