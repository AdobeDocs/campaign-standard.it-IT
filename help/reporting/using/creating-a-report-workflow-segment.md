---
title: Creazione di un rapporto basato sui segmenti del flusso di lavoro
description: Scopri come verificare il successo della consegna in base ai segmenti dei flussi di lavoro nei rapporti.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Creazione di un rapporto basato sui segmenti del flusso di lavoro{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**può eseguire il targeting solo delle consegne e-mail e SMS.

Dopo aver creato un flusso di lavoro e aver filtrato la popolazione in un pubblico di destinazione diverso, puoi misurare l’efficienza delle campagne di marketing in base ai segmenti definiti in questo flusso di lavoro di targeting.
Per eseguire il targeting di questi segmenti nei rapporti:

* [Passaggio 1: Aggiorna risorsa personalizzata Profili con segmenti](#step-1--update-profiles-custom-resource-segments)
* [Passaggio 2: Creare un flusso di lavoro con i segmenti](#step-2--create-a-workflow-segments)
* [Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Per iniziare a raccogliere questi dati, è necessario accettare l’accordo di utilizzo del reporting dinamico.
>
>Per ulteriori informazioni su questo accordo, consulta questo [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Passaggio 1: Aggiorna risorsa personalizzata Profili con segmenti{#step-1--update-profiles-custom-resource-segments}

Prima di generare rapporti sul codice del segmento, devi aggiornare il **[!UICONTROL Profiles]** risorsa personalizzata per i codici di segmento da memorizzare.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, quindi seleziona la **[!UICONTROL Profile (profile)]** risorsa.
1. In **[!UICONTROL Sending logs extension]** dal menu **[!UICONTROL Data structure]** scheda, controllo **[!UICONTROL Add segment code]** per consentire la memorizzazione dei codici dei segmenti dai flussi di lavoro di targeting e per inviarli al reporting dinamico.

   La **[!UICONTROL Segment code]** sarà quindi disponibile nella **[!UICONTROL Profile]** sezione della dimensione del rapporto.

   ![](assets/report_segment_4.png)

1. Salva la risorsa personalizzata.

1. Ora devi pubblicare la risorsa personalizzata.
Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Fai clic su **[!UICONTROL Prepare publication]** al termine della preparazione, fai clic sul pulsante **[!UICONTROL Publish]** pulsante . Per ulteriori informazioni sulla risorsa personalizzata, consulta [page](../../developing/using/updating-the-database-structure.md).

Ora puoi iniziare a creare il flusso di lavoro con i codici di segmento.

I codici di segmento verranno raccolti non appena abiliti il codice di segmento nel **[!UICONTROL Sending logs extension]**.

## Passaggio 2: Creare un flusso di lavoro con i segmenti {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se la transizione di input della consegna e-mail è vuota, il codice del segmento della transizione precedente verrà aggiunto per impostazione predefinita.

Innanzitutto devi creare un flusso di lavoro con una popolazione target diversa. In questo caso, vogliamo inviare un’e-mail che verrà personalizzata a seconda dell’età del pubblico: una consegna per profili da 20 a 30 anni e un&#39;altra per profili da 30 a 40 anni.

1. Crea il flusso di lavoro. Per ulteriori dettagli su come creare il flusso di lavoro, consulta questo [page](../../automating/using/building-a-workflow.md).

1. Aggiungi un **[!UICONTROL Query]** trascinandola dalla palette e rilasciandola nell’area di lavoro.

1. Esegui il targeting dei profili da 20 a 40 anni per segmentarli successivamente in popolazioni più mirate.

   ![](assets/report_segment_1.png)

1. Aggiungi un **[!UICONTROL Segmentation]** attività per suddividere i risultati della query in due popolazioni mirate. Per ulteriori informazioni sulla segmentazione, consulta questo [page](../../automating/using/segmentation.md).

1. Fai doppio clic sul pulsante **[!UICONTROL Segmentation]** per configurarlo. Modifica il primo segmento facendo clic su **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Esegui una query dei profili tra i 20 e i 30 anni e fai clic su **[!UICONTROL Confirm]** al termine.

   ![](assets/report_segment_8.png)

1. Fai clic su **[!UICONTROL Add an element]** per creare il secondo segmento e configurarlo come descritto nei passaggi precedenti per eseguire il targeting dei profili di età compresa tra i 30 e i 40 anni.

1. Modifica le **[!UICONTROL Segment code]** per ogni popolazione da trasmettere tramite reporting dinamico.

   >[!NOTE]
   >Questo passaggio è obbligatorio; in caso contrario, non sarai in grado di comprendere su quali segmenti creare rapporti.

   ![](assets/report_segment_9.png)

1. Trascina e rilascia una **[!UICONTROL Email delivery]** attività dopo i segmenti.

   ![](assets/report_segment_3.png)

1. Personalizza le consegne in base alle diverse popolazioni mirate. Per ulteriori informazioni sulla creazione di e-mail, consulta questo [page](../../designing/using/designing-content-in-adobe-campaign.md).

1. Salva il flusso di lavoro.

1. Fai clic su **[!UICONTROL Start]** quando il flusso di lavoro è pronto.

Ora puoi accedere ai rapporti per tenere traccia dei codici dei segmenti.

## Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti {#step-3--create-a-dynamic-report-filter-segments}

Dopo aver inviato le consegne con il flusso di lavoro, puoi suddividere i rapporti utilizzando i codici di segmento dal flusso di lavoro.

1. Da **[!UICONTROL Reports]** seleziona un rapporto predefinito o fai clic sul pulsante **[!UICONTROL Create new project]** per iniziare da zero.

   ![](assets/custom_profile_18.png)
1. Trascina e rilascia la **[!UICONTROL Delivery]** alla tabella a forma libera.

   ![](assets/report_segment_5.png)

1. Trascina metriche diverse nella tabella, ad esempio **[!UICONTROL Open]** e **[!UICONTROL Click]** per iniziare a filtrare i dati.
1. In **[!UICONTROL Dimensions]** , fai clic su **[!UICONTROL Profile]** quindi trascina e rilascia la **[!UICONTROL Segment code]** dimensione della consegna del flusso di lavoro per misurare il successo della consegna e-mail in base alle popolazioni target.

   ![](assets/report_segment_6.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/report_segment_10.png)
