---
title: Creazione di un report basato sui segmenti del flusso di lavoro
description: Scopri come controllare il successo della distribuzione in base ai segmenti dei flussi di lavoro nei tuoi rapporti.
page-status-flag: never-activated
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: customizing-reports
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# Creazione di un report basato sui segmenti del flusso di lavoro{#creating-a-report-workflow-segment}

Dopo aver creato un flusso di lavoro e aver filtrato la popolazione in un pubblico di destinazione diverso, potete misurare l&#39;efficienza delle campagne di marketing in base ai segmenti definiti in questo flusso di lavoro di targeting.
Per eseguire il targeting di questi segmenti nei report:

* [Passaggio 1: Aggiorna risorsa personalizzata profili con segmenti](#step-1--update-profiles-custom-resource-segments)
* [Passaggio 2: Creazione di un flusso di lavoro con i segmenti](#step-2--create-a-workflow-segments)
* [Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Per iniziare a raccogliere questi dati, è necessario accettare il contratto di utilizzo per i rapporti dinamici.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Passaggio 1: Aggiorna risorsa personalizzata profili con segmenti{#step-1--update-profiles-custom-resource-segments}

Prima di generare rapporti sul codice del segmento, è necessario aggiornare la risorsa **[!UICONTROL Profiles]** personalizzata per memorizzare i codici del segmento.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, then select the **[!UICONTROL Profile (profile)]** resource.
1. Nel **[!UICONTROL Sending logs extension]** menu dalla **[!UICONTROL Data structure]** scheda, selezionate **[!UICONTROL Add segment code]** per consentire la memorizzazione dei codici dei segmenti dai flussi di lavoro di targeting e inviarli ai report dinamici.

   Il rapporto **[!UICONTROL Segment code]** sarà quindi disponibile nella sezione **[!UICONTROL Profile]** Dimensioni del rapporto.

   ![](assets/report_segment_4.png)

1. Salvate la risorsa personalizzata.

1. È ora necessario pubblicare la risorsa personalizzata.
Dal menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Al **[!UICONTROL Prepare publication]** termine della preparazione, fare clic sul **[!UICONTROL Publish]** pulsante. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

Ora puoi iniziare a creare il flusso di lavoro con i codici dei segmenti.

I codici dei segmenti verranno raccolti non appena avrai abilitato il codice dei segmenti nel **[!UICONTROL Sending logs extension]**.

## Passaggio 2: Creazione di un flusso di lavoro con i segmenti {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se la transizione di input per la consegna dell’e-mail è vuota, per impostazione predefinita verrà aggiunto il codice Segmento dalla transizione precedente.

È innanzitutto necessario creare un flusso di lavoro con popolazione di destinazione diversa. Qui, desideriamo inviare un&#39;e-mail che sarà personalizzata a seconda dell&#39;età del nostro pubblico: una consegna per profili da 20 a 30 anni e un&#39;altra per profili da 30 a 40 anni.

1. Crea il flusso di lavoro. For more details on how to create your workflow, refer to this [page](../../automating/using/building-a-workflow.md).

1. Add a **[!UICONTROL Query]** activity by dragging it from the palette and dropping it in the workspace.

1. Esegue il targeting dei profili da 20 a 40 anni per suddividerli successivamente in popolazioni più mirate.

   ![](assets/report_segment_1.png)

1. Aggiungete un&#39; **[!UICONTROL Segmentation]** attività per suddividere i risultati della query in due popolazioni mirate. For more on segmentation, refer to this [page](../../automating/using/segmentation.md).

1. Fate doppio clic sull&#39; **[!UICONTROL Segmentation]** attività per configurarla. Modificate il primo segmento facendo clic su **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Effettuate le query sui profili tra i 20 e i 30 anni e fate clic **[!UICONTROL Confirm]** al termine.

   ![](assets/report_segment_8.png)

1. Fai clic **[!UICONTROL Add an element]** per creare il secondo segmento e configurarlo come descritto nei passaggi descritti sopra per eseguire il targeting dei profili tra i 30 e i 40 anni.

1. Modificare la **[!UICONTROL Segment code]** voce per ogni popolazione da trasmettere attraverso il reporting dinamico.

   >[!NOTE]
   >Questo passaggio è obbligatorio, altrimenti non sarai in grado di capire su quali segmenti generare i rapporti.

   ![](assets/report_segment_9.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity after your segments.

   ![](assets/report_segment_3.png)

1. Personalizza le tue consegne in base alle diverse popolazioni mirate. For more on email creation, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. Salva il flusso di lavoro.

1. Fate clic **[!UICONTROL Start]** quando il flusso di lavoro è pronto.

Ora puoi accedere ai rapporti per tenere traccia dei codici dei segmenti.

## Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti {#step-3--create-a-dynamic-report-filter-segments}

Dopo aver inviato le consegne con il flusso di lavoro, puoi suddividere i rapporti utilizzando i codici dei segmenti dal flusso di lavoro.

1. Dalla **[!UICONTROL Reports]** scheda, selezionate un rapporto out-of-the-box oppure fate clic sul **[!UICONTROL Create new project]** pulsante per iniziare da zero.

   ![](assets/custom_profile_18.png)
1. Trascinare la **[!UICONTROL Delivery]** dimensione nella tabella a forma libera.

   ![](assets/report_segment_5.png)

1. Trascina diverse metriche nella tabella, ad esempio **[!UICONTROL Open]** e **[!UICONTROL Click]** metriche, per iniziare a filtrare i dati.
1. Nella **[!UICONTROL Dimensions]** categoria, fai clic sulla **[!UICONTROL Profile]** dimensione, quindi trascina e rilascia la **[!UICONTROL Segment code]** dimensione per la distribuzione del flusso di lavoro, per misurare il successo della distribuzione delle e-mail in base alle popolazioni mirate.

   ![](assets/report_segment_6.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/report_segment_10.png)
