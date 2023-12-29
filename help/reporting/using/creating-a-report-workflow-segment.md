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
source-wordcount: '640'
ht-degree: 2%

---

# Creazione di un rapporto basato sui segmenti del flusso di lavoro{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]** può eseguire il targeting solo delle consegne e-mail e SMS.

Dopo aver creato un flusso di lavoro e aver filtrato la popolazione in base a un pubblico di destinazione diverso, puoi misurare l’efficienza delle campagne di marketing in base ai segmenti definiti in questo flusso di lavoro di destinazione.
Per eseguire il targeting di questi segmenti nei rapporti:

* [Passaggio 1: aggiornare la risorsa personalizzata Profili con i segmenti](#step-1--update-profiles-custom-resource-segments)
* [Passaggio 2: creare un flusso di lavoro con i segmenti](#step-2--create-a-workflow-segments)
* [Passaggio 3: creare un rapporto dinamico per filtrare i segmenti](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Per iniziare a raccogliere questi dati, è necessario accettare l’accordo di utilizzo del Reporting dinamico.
>
>Per ulteriori informazioni su questo contratto, consulta [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Passaggio 1: aggiornare la risorsa personalizzata Profili con i segmenti{#step-1--update-profiles-custom-resource-segments}

Prima di creare rapporti sul codice del segmento, devi aggiornare i **[!UICONTROL Profiles]** risorsa personalizzata per la memorizzazione dei codici di segmento.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, quindi seleziona la **[!UICONTROL Profile (profile)]** risorsa.
1. In **[!UICONTROL Sending logs extension]** menu dal menu **[!UICONTROL Data structure]** scheda, spunta **[!UICONTROL Add segment code]** per consentire l’archiviazione dei codici di segmento dai flussi di lavoro di targeting e per inviarli al reporting dinamico.

   Il **[!UICONTROL Segment code]** sarà quindi disponibile nel **[!UICONTROL Profile]** sezione dimensionale del rapporto.

   ![](assets/report_segment_4.png)

1. Salva la risorsa personalizzata.

1. Ora devi pubblicare la risorsa personalizzata.
Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Clic **[!UICONTROL Prepare publication]** al termine della preparazione, fai clic su **[!UICONTROL Publish]** pulsante. Per ulteriori informazioni sulla risorsa personalizzata, consulta questa [pagina](../../developing/using/updating-the-database-structure.md).

Ora puoi iniziare a creare il flusso di lavoro con i codici di segmento.

I codici di segmento verranno raccolti non appena abiliti il codice di segmento in **[!UICONTROL Sending logs extension]**.

## Passaggio 2: creare un flusso di lavoro con i segmenti {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se la transizione di input della consegna e-mail è vuota, per impostazione predefinita verrà aggiunto il codice del segmento della transizione precedente.

Devi innanzitutto creare un flusso di lavoro con una popolazione di destinazione diversa. In questo caso, vogliamo inviare un’e-mail che sarà personalizzata in base all’età del pubblico: una consegna per profili di età compresa tra i 20 e i 30 anni e un’altra per profili di età compresa tra i 30 e i 40 anni.

1. Crea il flusso di lavoro. Per ulteriori dettagli su come creare il flusso di lavoro, consulta questa [pagina](../../automating/using/building-a-workflow.md).

1. Aggiungi un **[!UICONTROL Query]** trascinandolo dalla palette e rilasciandolo nell’area di lavoro.

1. I profili target di età compresa tra i 20 e i 40 anni consentono di segmentarli in popolazioni più mirate.

   ![](assets/report_segment_1.png)

1. Aggiungi un **[!UICONTROL Segmentation]** attività per suddividere i risultati della query in due popolazioni target. Per ulteriori informazioni sulla segmentazione, consulta questa [pagina](../../automating/using/segmentation.md).

1. Fai doppio clic su **[!UICONTROL Segmentation]** per configurarlo. Modifica il primo segmento facendo clic su **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Eseguire query sui profili di età compresa tra 20 e 30 anni e fare clic su **[!UICONTROL Confirm]** al termine.

   ![](assets/report_segment_8.png)

1. Clic **[!UICONTROL Add an element]** per creare il secondo segmento e configurarlo come descritto nei passaggi precedenti per eseguire il targeting dei profili tra i 30 e i 40 anni.

1. Modifica il **[!UICONTROL Segment code]** per ogni popolazione da trasmettere mediante reporting dinamico.

   >[!NOTE]
   >Questo passaggio è obbligatorio, altrimenti non sarai in grado di capire su quali segmenti eseguire il rapporto.

   ![](assets/report_segment_9.png)

1. Trascina e rilascia una **[!UICONTROL Email delivery]** attività dopo i segmenti.

   ![](assets/report_segment_3.png)

1. Personalizza le consegne in base alle diverse popolazioni target. Per ulteriori informazioni sulla creazione di e-mail, consulta questa [pagina](../../designing/using/designing-content-in-adobe-campaign.md).

1. Salva il flusso di lavoro.

1. Clic **[!UICONTROL Start]** quando il workflow è pronto.

Ora puoi accedere ai tuoi rapporti per tenere traccia dei codici di segmento.

## Passaggio 3: creare un rapporto dinamico per filtrare i segmenti {#step-3--create-a-dynamic-report-filter-segments}

Dopo aver inviato le consegne con il flusso di lavoro, puoi suddividere i rapporti utilizzando i codici di segmento del flusso di lavoro.

1. Dalla sezione **[!UICONTROL Reports]** , seleziona un rapporto predefinito o fai clic sulla scheda **[!UICONTROL Create new project]** per iniziare da zero.

   ![](assets/custom_profile_18.png)
1. Trascina la **[!UICONTROL Delivery]** nella tabella a forma libera.

   ![](assets/report_segment_5.png)

1. Trascina e rilascia nella tabella diverse metriche, ad esempio **[!UICONTROL Open]** e **[!UICONTROL Click]** metriche per iniziare a filtrare i dati.
1. In **[!UICONTROL Dimensions]** categoria, fai clic su **[!UICONTROL Profile]** dimensione, quindi trascina e rilascia la **[!UICONTROL Segment code]** dimensione sulla consegna del flusso di lavoro per misurare il successo della consegna e-mail in base alle popolazioni target.

   ![](assets/report_segment_6.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/report_segment_10.png)
