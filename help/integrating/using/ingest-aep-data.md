---
title: Inserire il pubblico di Adobe Experience Platform in Campaign
description: Scopri come acquisire il pubblico di Adobe Experience Platform in Campaign Standard.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
TQID: https://experienceleague.adobe.com/LdVWEXa90p4yOKgPGG5LUOGRk3xWE8kJ8SkKM7ODBXk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2: id: b70f632b-2cfd-43d0-9266-284281100d70id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 7%

---

# Inserire il pubblico di Adobe Experience Platform in Campaign {#destinations}

Per acquisire i tipi di pubblico di Adobe Experience Platform in Campaign e utilizzarli nei flussi di lavoro, devi innanzitutto collegare Adobe Campaign as a una **destinazione** di Adobe Experience Platform e configurarla con il segmento da esportare.

Una volta configurata la destinazione, i dati verranno esportati nella posizione di archiviazione e sarà necessario creare un flusso di lavoro dedicato in Campaign Standard per acquisirli.

## Connettere Adobe Campaign come destinazione

In Adobe Experience Platform, configura una connessione con Adobe Campaign selezionando una posizione di archiviazione per i segmenti esportati. Questi passaggi ti consentono anche di selezionare i segmenti da esportare e specificare campi XDM aggiuntivi da includere.

Per ulteriori informazioni, consulta la [documentazione sulle destinazioni](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

Dopo aver configurato la destinazione, Adobe Experience Platform crea un file .txt o .csv delimitato da tabulazioni nel percorso di archiviazione fornito. Questa operazione è pianificata ed eseguita una volta ogni 24 ore.

Ora puoi configurare un flusso di lavoro Campaign Standard per acquisire il segmento in Campaign.

## Creare un flusso di lavoro di importazione in Campaign Standard

Una volta che Campaign Standard è stato configurato come destinazione, devi creare un flusso di lavoro dedicato per importare il file esportato da Adobe Experience Platform.

A tale scopo, è necessario aggiungere e configurare un&#39;attività **[!UICONTROL Transfer file]**. Per ulteriori informazioni su come configurare questa attività, consulta [questa sezione](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

Puoi quindi creare il flusso di lavoro in base alle tue esigenze (aggiorna il database utilizzando i dati del segmento, invia consegne cross-channel al segmento, ecc.)

Ad esempio, il flusso di lavoro seguente scarica il file dalla posizione di archiviazione su base giornaliera, quindi aggiorna il database di Campaign con i dati del segmento.

![](assets/rtcdp-workflow.png)

Esempi di flussi di lavoro per la gestione dei dati sono disponibili nella sezione [casi di utilizzo dei flussi di lavoro](../../automating/using/about-workflow-use-cases.md#management).

Argomenti correlati:

* [Attività di gestione dati](../../automating/using/about-data-management-activities.md)
* [Informazioni sull’importazione e l’esportazione di dati](../../automating/using/about-data-import-and-export.md)
