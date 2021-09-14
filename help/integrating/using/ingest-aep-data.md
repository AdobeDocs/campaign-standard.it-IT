---
title: Inserire il pubblico di Adobe Experience Platform in Campaign
description: Scopri come inserire i tipi di pubblico di Adobe Experience Platform in Campaign Standard.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 7%

---

# Inserire il pubblico di Adobe Experience Platform in Campaign {#destinations}

Per acquisire i tipi di pubblico di Adobe Experience Platform in Campaign e utilizzarli nei flussi di lavoro, è innanzitutto necessario collegare Adobe Campaign as a Adobe Experience Platform **Destination** e configurarlo con il segmento da esportare.

Una volta configurata la destinazione, i dati verranno esportati nel percorso di archiviazione e dovrai creare un flusso di lavoro dedicato in Campaign Standard per acquisirli.

## Collegare Adobe Campaign come destinazione

In Adobe Experience Platform, configura una connessione con Adobe Campaign selezionando un percorso di archiviazione per i segmenti esportati. Questa procedura consente inoltre di selezionare i segmenti da esportare e specificare campi XDM aggiuntivi da includere.

Per ulteriori informazioni, consulta la [documentazione sulle destinazioni](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

Una volta configurata la destinazione, Adobe Experience Platform crea un file .txt o .csv delimitato da tabulazioni nel percorso di archiviazione fornito. Questa operazione è pianificata ed eseguita una volta ogni 24 ore.

Ora puoi configurare un flusso di lavoro Campaign Standard per l’acquisizione del segmento in Campaign.

## Creare un flusso di lavoro di importazione in Campaign Standard

Una volta configurato Campaign Standard come destinazione, è necessario creare un flusso di lavoro dedicato per importare il file esportato da Adobe Experience Platform.

A questo scopo, devi aggiungere e configurare un’attività **[!UICONTROL Transfer file]** . Per ulteriori informazioni su come configurare questa attività, consulta [questa sezione](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Puoi quindi creare il flusso di lavoro in base alle tue esigenze (aggiorna il database utilizzando i dati del segmento, invia consegne cross-channel al segmento, ecc.)

Ad esempio, il flusso di lavoro seguente scarica il file dalla posizione di archiviazione su base giornaliera, quindi aggiorna il database Campaign con i dati del segmento.

![](assets/rtcdp-workflow.png)

Esempi di flussi di lavoro di gestione dei dati sono disponibili nella sezione [casi di utilizzo dei flussi di lavoro](../../automating/using/about-workflow-use-cases.md#management) .

Argomenti correlati:

* [Attività di gestione dati](../../automating/using/about-data-management-activities.md)
* [Informazioni sull’importazione e l’esportazione di dati](../../automating/using/about-data-import-and-export.md)
