---
title: Creazione di un rapporto basato sui segmenti del flusso di lavoro
seo-title: Creazione di un rapporto basato sui segmenti del flusso di lavoro
description: Creazione di un rapporto basato sui segmenti del flusso di lavoro
seo-description: Scopri come controllare il successo della distribuzione in base ai segmenti dei flussi di lavoro nei tuoi rapporti.
page-status-flag: mai attivato
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: personalizzazione dei report
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Creazione di un rapporto basato sui segmenti del flusso di lavoro{#creating-a-report-workflow-segment}

Dopo aver creato un flusso di lavoro e aver filtrato la popolazione in un pubblico di destinazione diverso, potete misurare l'efficienza delle campagne di marketing in base ai segmenti definiti in questo flusso di lavoro di targeting.
Per eseguire il targeting di questi segmenti nei report:

* [Passaggio 1: Aggiorna risorsa personalizzata profili con segmenti](#step-1--update-profiles-custom-resource-segments)
* [Passaggio 2: Creazione di un flusso di lavoro con i segmenti](#step-2--create-a-workflow-segments)
* [Passaggio 3: Creare un rapporto dinamico per filtrare i segmenti](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Per iniziare a raccogliere questi dati, è necessario accettare il contratto di utilizzo per i rapporti dinamici.
>Per ulteriori informazioni su questo accordo, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Passaggio 1: Aggiorna risorsa personalizzata profili con segmenti{#step-1--update-profiles-custom-resource-segments}

Prima di generare rapporti sul codice del segmento, è necessario aggiornare la risorsa **[!UICONTROL Profiles]** personalizzata per memorizzare i codici del segmento.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]**, quindi seleziona la **[!UICONTROL Profile (profile)]** risorsa.
1. Nel **[!UICONTROL Sending logs extension]** menu dalla **[!UICONTROL Data structure]** scheda, selezionate **[!UICONTROL Add segment code]** per consentire la memorizzazione dei codici dei segmenti dai flussi di lavoro di targeting e inviarli ai report dinamici.

   Il rapporto **[!UICONTROL Segment code]** sarà quindi disponibile nella sezione **[!UICONTROL Profile]** Dimensioni del rapporto.

   ![](assets/report_segment_4.png)

1. Salvate la risorsa personalizzata.

1. È ora necessario pubblicare la risorsa personalizzata.
Dal menu avanzato, selezionate **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Al **[!UICONTROL Prepare publication]** termine della preparazione, fare clic sul **[!UICONTROL Publish]** pulsante. Per ulteriori informazioni sulla risorsa personalizzata, consultate questa [pagina](../../developing/using/updating-the-database-structure.md).

Ora puoi iniziare a creare il flusso di lavoro con i codici dei segmenti.

I codici dei segmenti verranno raccolti non appena avrai abilitato il codice dei segmenti nel **[!UICONTROL Sending logs extension]**.

## Passaggio 2: Creazione di un flusso di lavoro con i segmenti {#step-2--create-a-workflow-segments}

>[!NOTE]
>Se la transizione di input per la consegna dell’e-mail è vuota, per impostazione predefinita viene aggiunto il codice Segmento dalla transizione precedente.

È innanzitutto necessario creare un flusso di lavoro con popolazione di destinazione diversa. Qui, vogliamo inviare un'e-mail che sarà personalizzata a seconda dell'età del nostro pubblico: una consegna per i profili da 20 a 30 anni e un'altra per quelli da 30 a 40 anni.

1. Crea il flusso di lavoro. Per ulteriori dettagli su come creare il flusso di lavoro, consultate questa [pagina](../../automating/using/building-a-workflow.md).

1. Aggiungete un' **[!UICONTROL Query]** attività trascinandola dalla palette e rilasciandola nell'area di lavoro.

1. Esegue il targeting dei profili da 20 a 40 anni per suddividerli successivamente in popolazioni più mirate.

   ![](assets/report_segment_1.png)

1. Aggiungete un' **[!UICONTROL Segmentation]** attività per suddividere i risultati della query in due popolazioni mirate. Per ulteriori informazioni sulla segmentazione, consulta questa [pagina](../../automating/using/targeting-data.md#segmenting-data).

1. Fate doppio clic sull' **[!UICONTROL Segmentation]** attività per configurarla. Modificate il primo segmento facendo clic su **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Effettuate le query sui profili tra i 20 e i 30 anni e fate clic **[!UICONTROL Confirm]** al termine.

   ![](assets/report_segment_8.png)

1. Fai clic **[!UICONTROL Add an element]** per creare il secondo segmento e configurarlo come descritto nei passaggi descritti sopra per eseguire il targeting dei profili tra i 30 e i 40 anni.

1. Modificare la **[!UICONTROL Segment code]** voce per ogni popolazione da trasmettere tramite reporting dinamico.

   >[!NOTE]
   >Questo passaggio è obbligatorio, altrimenti non sarai in grado di capire su quali segmenti generare i rapporti.

   ![](assets/report_segment_9.png)

1. Trascinare un' **[!UICONTROL Email delivery]** attività dopo i segmenti.

   ![](assets/report_segment_3.png)

1. Personalizza le tue consegne in base alle diverse popolazioni mirate. Per ulteriori informazioni sulla creazione di e-mail, consultate questa [pagina](../../designing/using/overview.md).

1. Salvare il flusso di lavoro.

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
