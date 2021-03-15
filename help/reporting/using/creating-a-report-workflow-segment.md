---
solution: Campaign Standard
product: campaign
title: Creazione di un rapporto basato sui segmenti del flusso di lavoro
description: Scopri come verificare il successo della consegna in base ai segmenti dei flussi di lavoro nei rapporti.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Generazione rapporti
role: Leader
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 2%

---


# Creazione di un rapporto basato sui segmenti del flusso di lavoro{#creating-a-report-workflow-segment}

Dopo aver creato un flusso di lavoro e aver filtrato la popolazione in un pubblico di destinazione diverso, puoi misurare l’efficienza delle campagne di marketing in base ai segmenti definiti in questo flusso di lavoro di targeting.
Per eseguire il targeting di questi segmenti nei rapporti:

* [Passaggio 1: Aggiorna risorsa personalizzata Profili con segmenti](#step-1--update-profiles-custom-resource-segments)
* [Passaggio 2: Creare un flusso di lavoro con i segmenti](#step-2--create-a-workflow-segments)
* [Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Per iniziare a raccogliere questi dati, è necessario accettare l’accordo di utilizzo del reporting dinamico.
>Per ulteriori informazioni su questo contratto, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Passaggio 1: Aggiorna risorsa personalizzata Profili con segmenti{#step-1--update-profiles-custom-resource-segments}

Prima di generare rapporti sul codice del segmento, devi aggiornare la risorsa **[!UICONTROL Profiles]** personalizzata per memorizzare i codici del segmento.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, quindi seleziona la risorsa **[!UICONTROL Profile (profile)]**.
1. Nel menu **[!UICONTROL Sending logs extension]** della scheda **[!UICONTROL Data structure]** , seleziona **[!UICONTROL Add segment code]** per consentire la memorizzazione dei codici dei segmenti dai flussi di lavoro di targeting e per inviarli al reporting dinamico.

   La sezione **[!UICONTROL Segment code]** sarà quindi disponibile nella sezione **[!UICONTROL Profile]** della dimensione del rapporto.

   ![](assets/report_segment_4.png)

1. Salva la risorsa personalizzata.

1. Ora devi pubblicare la risorsa personalizzata.
Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Fai clic su **[!UICONTROL Prepare publication]**, quindi al termine della preparazione, fai clic sul pulsante **[!UICONTROL Publish]** . Per ulteriori informazioni sulla risorsa personalizzata, consulta questa [pagina](../../developing/using/updating-the-database-structure.md).

Ora puoi iniziare a creare il flusso di lavoro con i codici di segmento.

I codici dei segmenti verranno raccolti non appena si abilita il codice dei segmenti in **[!UICONTROL Sending logs extension]**.

## Passaggio 2: Creare un flusso di lavoro con segmenti {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se la transizione di input della consegna e-mail è vuota, il codice del segmento della transizione precedente verrà aggiunto per impostazione predefinita.

Innanzitutto devi creare un flusso di lavoro con una popolazione target diversa. In questo caso, vogliamo inviare un’e-mail che verrà personalizzata a seconda dell’età del pubblico: una consegna per profili da 20 a 30 anni e un&#39;altra per profili da 30 a 40 anni.

1. Crea il flusso di lavoro. Per ulteriori dettagli su come creare il flusso di lavoro, consulta questa [pagina](../../automating/using/building-a-workflow.md).

1. Aggiungi un’attività **[!UICONTROL Query]** trascinandola dalla palette e rilasciandola nell’area di lavoro.

1. Esegui il targeting dei profili da 20 a 40 anni per segmentarli successivamente in popolazioni più mirate.

   ![](assets/report_segment_1.png)

1. Aggiungi un’attività **[!UICONTROL Segmentation]** per suddividere i risultati della query in due popolazioni mirate. Per ulteriori informazioni sulla segmentazione, consulta questa [pagina](../../automating/using/segmentation.md).

1. Fai doppio clic sull’attività **[!UICONTROL Segmentation]** per configurarla. Modifica il primo segmento facendo clic su **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Esegui una query dei profili tra i 20 e i 30 anni e al termine fai clic su **[!UICONTROL Confirm]** .

   ![](assets/report_segment_8.png)

1. Fai clic su **[!UICONTROL Add an element]** per creare il secondo segmento e configurarlo come descritto nei passaggi precedenti per eseguire il targeting dei profili di età compresa tra i 30 e i 40 anni.

1. Modifica il **[!UICONTROL Segment code]** per ogni gruppo da trasmettere tramite reporting dinamico.

   >[!NOTE]
   >Questo passaggio è obbligatorio; in caso contrario, non sarai in grado di comprendere su quali segmenti creare rapporti.

   ![](assets/report_segment_9.png)

1. Trascina e rilascia un’attività **[!UICONTROL Email delivery]** dopo i segmenti.

   ![](assets/report_segment_3.png)

1. Personalizza le consegne in base alle diverse popolazioni mirate. Per ulteriori informazioni sulla creazione di e-mail, consulta questa [pagina](../../designing/using/designing-content-in-adobe-campaign.md).

1. Salva il flusso di lavoro.

1. Fai clic su **[!UICONTROL Start]** quando il flusso di lavoro è pronto.

Ora puoi accedere ai rapporti per tenere traccia dei codici dei segmenti.

## Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti {#step-3--create-a-dynamic-report-filter-segments}

Dopo aver inviato le consegne con il flusso di lavoro, puoi suddividere i rapporti utilizzando i codici di segmento dal flusso di lavoro.

1. Dalla scheda **[!UICONTROL Reports]** , seleziona un rapporto predefinito o fai clic sul pulsante **[!UICONTROL Create new project]** per iniziare da zero.

   ![](assets/custom_profile_18.png)
1. Trascina la dimensione **[!UICONTROL Delivery]** nella tabella a forma libera.

   ![](assets/report_segment_5.png)

1. Trascina metriche diverse nella tabella, ad esempio le metriche **[!UICONTROL Open]** e **[!UICONTROL Click]** per iniziare a filtrare i dati.
1. Nella categoria **[!UICONTROL Dimensions]** , fai clic sulla dimensione **[!UICONTROL Profile]** , quindi trascina e rilascia la dimensione **[!UICONTROL Segment code]** nella consegna del flusso di lavoro per misurare il successo della consegna e-mail a seconda delle popolazioni target.

   ![](assets/report_segment_6.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/report_segment_10.png)
