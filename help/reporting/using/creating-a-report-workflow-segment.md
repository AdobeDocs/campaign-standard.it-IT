---
title: Creazione di un rapporto basato sui segmenti di flusso di lavoro
seo-title: Creazione di un rapporto basato sui segmenti di flusso di lavoro
description: Creazione di un rapporto basato sui segmenti di flusso di lavoro
seo-description: Scopri come controllare il successo della distribuzione in base ai segmenti dei tuoi flussi di lavoro nei rapporti.
page-status-flag: never-activated
uuid: f 75 e 005 b -5328-4 c 98-9 e 78-51 d 54 fd 0 e 246
contentOwner: beneat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: personalizzazione dei rapporti
discoiquuid: b 6 d 3 de 63-3 add -4881-8917-04 a 6 f 8 b 6 be 4 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c555c35004ffe3c3d7e2f845a3a2707b1985e190

---


# Creating a report based on workflow segments{#creating-a-report-workflow-segment}

Dopo aver creato un flusso di lavoro e aver filtrato la popolazione in diversi destinatari, potete misurare l'efficienza delle campagne di marketing in base ai segmenti definiti in questo flusso di lavoro di targeting.
Per eseguire il targeting di questi segmenti nei rapporti:

* [Passaggio 1: Aggiornare i profili personalizzati con i segmenti](#step-1--update-profiles-custom-resource-segments)
* [Passaggio 2: Creazione di un flusso di lavoro con segmenti](#step-2--create-a-workflow-segments)
* [Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Il contratto di utilizzo di reporting dinamico deve essere accettato per iniziare a raccogliere questi dati.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Step 1: Update Profiles custom resource with segments{#step-1--update-profiles-custom-resource-segments}

Before reporting on your segment code, you need to update your **[!UICONTROL Profiles]** custom resource for your segment codes to be stored.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. In the **[!UICONTROL Sending logs extension]** menu from the **[!UICONTROL Data structure]** tab, check **[!UICONTROL Add segment code]** to allow storage of your segment codes from targeting workflows and to send it to dynamic reporting.

   The **[!UICONTROL Segment code]** will then be available in the **[!UICONTROL Profile]** dimension section of your report.

   ![](assets/report_segment_4.png)

1. Salva la risorsa personalizzata.

1. Ora è necessario pubblicare la risorsa personalizzata.
From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

Ora puoi iniziare a creare il tuo flusso di lavoro con i codici dei segmenti.

Note that segment codes will be collected as soon as you enable the segment code in the **[!UICONTROL Sending logs extension]**.

## Step 2: Create a workflow with segments {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se la transizione di input dell'e-mail è vuota, il codice Segmento della transizione precedente verrà aggiunto per impostazione predefinita.

Occorre innanzitutto creare un flusso di lavoro con popolazione di destinazione diversa. Qui, vogliamo inviare un'e-mail che verrà personalizzata in base all'età del pubblico: una consegna per i profili precedenti da 20 a 30 anni e un'altra per i profili compresi tra 30 e 40 anni.

1. Crea il tuo flusso di lavoro. For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. Esegue il targeting dei profili da 20 a 40 anni per poi segmentarli in popolazioni più mirate.

   ![](assets/report_segment_1.png)

1. Add a **[!UICONTROL Segmentation]** activity to split your query results into two targeted populations. For more on segmentation, refer to this [page](../../automating/using/targeting-data.md#segmenting-data).

1. Double click the **[!UICONTROL Segmentation]** activity to configure it. Edit the first segment by clicking **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Query profiles between the age of 20 to 30 and click **[!UICONTROL Confirm]** when done.

   ![](assets/report_segment_8.png)

1. Click **[!UICONTROL Add an element]** to create your second segment and configure it as described in the steps above to target profiles between the age of 30 to 40.

1. Edit the **[!UICONTROL Segment code]** for each population to be passed on through dynamic reporting.

   >[!NOTE]
   >Questo passaggio è obbligatorio o non sarai in grado di comprendere i segmenti sui quali eseguire il rapporto.

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. Personalizzate le distribuzioni in base alle diverse popolazioni di destinazione. For more on email creation, refer to this [page](../../designing/using/about-email-content-design.md).

1. Salvate il flusso di lavoro.

1. Click **[!UICONTROL Start]** when your workflow is ready.

Ora puoi accedere ai tuoi rapporti per tenere traccia dei tuoi codici dei segmenti.

## Step 3: Create a dynamic report to filter segments {#step-3--create-a-dynamic-report-filter-segments}

Dopo aver inviato le consegne con il flusso di lavoro, puoi suddividere i rapporti utilizzando i codici dei segmenti dal flusso di lavoro.

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create new project]** button to start one from scratch.

   ![](assets/custom_profile_18.png)
1. Drag and drop the **[!UICONTROL Delivery]** dimension to your freeform table.

   ![](assets/report_segment_5.png)

1. Drag and drop different metrics to your table such as the **[!UICONTROL Open]** and **[!UICONTROL Click]** metrics to start filtering your data.
1. In the **[!UICONTROL Dimensions]** category, click the **[!UICONTROL Profile]** dimension then drag and drop the **[!UICONTROL Segment code]** dimension on your workflow's delivery to measure the success of your email delivery depending on the targeted populations.

   ![](assets/report_segment_6.png)

1. Se necessario, trascina e rilascia una visualizzazione nell'area di lavoro.

   ![](assets/report_segment_10.png)
