---
title: Esportare dati da Campaign ad Adobe Experience Platform
description: Scopri come esportare i dati da Campaign Standard a Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 5%

---

# Esportare dati da Campaign ad Adobe Experience Platform {#sources}

Per esportare i dati di Campaign Standard in Adobe Real-time Customer Data Platform (RTCDP), devi innanzitutto creare un flusso di lavoro in Campaign Standard per esportare nel percorso di archiviazione di Amazon Storage Service (S3) o Azure Blob i dati che desideri condividere.

Dopo aver configurato il flusso di lavoro e aver inviato i dati al percorso di archiviazione, è necessario connettere il percorso di archiviazione BLOB S3 o Azure come **Source** in Adobe Experience Platform.

>[!NOTE]
>
>Si consiglia di esportare solo i dati generati da Campaign (ad esempio invii, aperture, clic ecc.) a Adobe Experience Platform. I dati acquisiti da un’origine di terze parti (come il CRM) devono essere importati direttamente in Adobe Experience Platform.

## Creare un flusso di lavoro di esportazione in Campaign Standard

Per esportare i dati da Campaign Standard nel percorso di archiviazione S3 o BLOB di Azure, devi creare un flusso di lavoro per eseguire il targeting dei dati da esportare e inviarli al percorso di archiviazione.

A questo scopo, aggiungi e configura:

* Attività **[!UICONTROL Extract file]** per estrarre i dati di destinazione in un file CSV. Per ulteriori informazioni su come configurare questa attività, consulta [questa sezione](../../automating/using/extract-file.md).

  ![](assets/rtcdp-extract-file.png)

* Un&#39;attività **[!UICONTROL Transfer file]** per trasferire il file CSV nel percorso di archiviazione. Per ulteriori informazioni su come configurare questa attività, consulta [questa sezione](../../automating/using/transfer-file.md).

  ![](assets/rtcdp-transfer-file.png)

Ad esempio, il flusso di lavoro seguente estrae i registri regolarmente in un file CSV, quindi trasferisce il file in un percorso di archiviazione.

![](assets/aep-export.png)

Esempi di flussi di lavoro per la gestione dei dati sono disponibili nella sezione [casi di utilizzo dei flussi di lavoro](../../automating/using/about-workflow-use-cases.md#management).

Argomenti correlati:

* [Attività di gestione dati](../../automating/using/about-data-management-activities.md)
* [Informazioni sull’importazione e l’esportazione di dati](../../automating/using/about-data-import-and-export.md)


## Collegare la posizione di archiviazione come Source

Di seguito sono elencati i passaggi principali per connettere il servizio di archiviazione Amazon (S3) o il percorso di archiviazione BLOB di Azure come **Source** in Adobe Experience Platform. Informazioni dettagliate su ciascuno di questi passaggi sono disponibili nella [documentazione dei connettori Source](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it).

1. Nel menu di Adobe di Experience Platform **[!UICONTROL Sources]**, crea una connessione al percorso di archiviazione:

   * [Creare una connessione di origine Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=it)
   * [Connettore BLOB di Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=it)

   >[!NOTE]
   >
   >Il percorso di archiviazione può essere Amazon S3, SFTP con password, SFTP con chiave SSH o connessioni BLOB di Azure. Il metodo preferito per inviare dati ad Adobe Campaign è tramite Amazon S3 o Azure Blob:

   ![](assets/rtcdp-connector.png)

1. Configurare un flusso di dati per una connessione batch di archiviazione cloud. Un flusso di dati è un’attività pianificata che recupera e acquisisce i dati dal percorso di archiviazione a un set di dati Adobe Experience Platform. Questi passaggi ti consentono di configurare l’acquisizione dei dati dalla posizione di archiviazione, inclusa la selezione dei dati e la mappatura dei campi CSV su uno schema XDM.

   Informazioni dettagliate sono disponibili in [questa pagina](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=it).

   ![](assets/rtcdp-map-xdm.png)

1. Dopo aver configurato Source, Adobe Experience Platform importa il file dal percorso di archiviazione fornito.

   Questa operazione può essere pianificata in base alle tue esigenze. È consigliabile eseguire l’esportazione fino a 6 volte al giorno, a seconda del carico già presente nell’istanza.
