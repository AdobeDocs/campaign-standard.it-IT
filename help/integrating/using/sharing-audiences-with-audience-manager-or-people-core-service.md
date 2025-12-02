---
title: Condivisione dei tipi di pubblico con Audience Manager o il servizio core People
description: Scopri come importare o esportare il pubblico nelle diverse soluzioni Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 3%

---

# Condivisione dei tipi di pubblico con Audience Manager o il servizio core People{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importare un pubblico {#importing-an-audience}

L’integrazione del servizio core People consente di importare direttamente un pubblico in Adobe Campaign tramite un flusso di lavoro tecnico per arricchire il database. Per ulteriori informazioni sulla condivisione del pubblico nel servizio core People, consulta questa [documentazione](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=it).

L&#39;importazione di tipi di pubblico/segmenti dal servizio core People in Adobe Campaign può essere eseguita dal menu **[!UICONTROL Audiences]** solo dagli utenti connessi tramite IMS (autenticazione tramite Adobe ID).

1. Passa al menu **[!UICONTROL Audiences]**.
1. Nella barra delle azioni, seleziona **[!UICONTROL Create]** per passare alla schermata e creare un pubblico.
1. Specifica l’etichetta del nuovo pubblico.
1. Impostare il pubblico **[!UICONTROL Type]** su **[!UICONTROL Experience Cloud]** per indicare che il pubblico in fase di creazione è un pubblico importato dal servizio core People.
1. Dal campo **[!UICONTROL Name of the shared audience]**, seleziona il pubblico da importare. È possibile importare solo i segmenti. I dati granulari, comprese coppie chiave-valore, caratteristiche e regole, non sono supportati.

   ![](assets/aam_import_audience.png)

1. Selezionare il **[!UICONTROL Shared Data Source]** corrispondente.

   Se l&#39;origine dati selezionata è configurata per l&#39;utilizzo di un algoritmo di crittografia, un&#39;opzione aggiuntiva consente di **[!UICONTROL Force reconciliation with a profile]**. Selezionare questa opzione se il campo **[!UICONTROL Channel]** dell&#39;origine dati è impostato su E-mail o dispositivo mobile (SMS) e se si desidera sfruttare i dati del profilo.

   Se non selezioni **[!UICONTROL Force reconciliation with a profile]** e **[!UICONTROL Channel]** nell&#39;origine dati AMC è impostato su E-mail o Mobile (SMS), tutti gli ID dichiarati crittografati vengono decrittografati. Viene creato/aggiornato un pubblico di tipo **File** con un elenco di tutti gli indirizzi e-mail/numeri di telefono cellulare. In questo modo, nessun indirizzo e-mail/numero di telefono cellulare viene perso durante l’importazione di un pubblico condiviso tramite questa integrazione, anche se tale profilo non esiste in Campaign. Tieni presente che questo tipo di pubblico non può essere utilizzato direttamente in quanto deve essere riconciliato manualmente utilizzando i flussi di lavoro.

1. Conferma la creazione del pubblico.

   Il pubblico viene quindi importato tramite un flusso di lavoro tecnico. È composto da record di cui è stato possibile riconciliare l’ID (&quot;ID visitatore&quot; o &quot;ID dichiarato&quot;) con la dimensione del profilo. Gli ID dei segmenti del servizio core People che non sono riconosciuti da Adobe Campaign non vengono importati.

Il pubblico viene ora importato nel database di Adobe Campaign. La sincronizzazione del processo di importazione richiede 24-36 ore, quando i segmenti vengono importati direttamente dal servizio core People o da Audience Manager. Dopo questo periodo, potrai trovare e utilizzare il nuovo pubblico in Adobe Campaign.

>[!NOTE]
>
>Se importi tipi di pubblico da Adobe Analytics ad Adobe Campaign, questi devono prima essere condivisi nel servizio core People o in Audience Manager. Questo processo richiede 12-24 ore, che devono essere aggiunte alla sincronizzazione di 24-36 ore con Campaign. In questo caso specifico, l’arco temporale di condivisione del pubblico può essere fino a 60 ore. Per ulteriori informazioni sulla condivisione del pubblico Adobe Analytics nel servizio core People e in Audience Manager, consulta questa [documentazione](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=it).

## Esportazione di un pubblico {#exporting-an-audience}

Un pubblico può essere esportato da Adobe Campaign ad Audience Manager o al servizio core People tramite un flusso di lavoro e l&#39;attività **[!UICONTROL Save audience]**.

Può essere eseguito in un nuovo flusso di lavoro e solo dagli utenti connessi tramite IMS (autenticazione tramite Adobe ID).

1. Crea un nuovo flusso di lavoro da un programma, una campagna o l’elenco delle attività di marketing.
1. Utilizzando le diverse attività disponibili, esegui il targeting di un set di profili.
1. Dopo il targeting, trascina e rilascia un&#39;attività **[!UICONTROL Save audience]** nel flusso di lavoro, quindi aprila.
1. Seleziona **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specifica il pubblico utilizzando il campo **[!UICONTROL Shared audience]**. Nella finestra visualizzata puoi scegliere se selezionare un pubblico esistente o crearne uno nuovo:

   * Se selezioni un pubblico esistente, al pubblico verranno aggiunti solo i nuovi record.
   * Per esportare l&#39;elenco dei profili in un nuovo pubblico, completare il campo **[!UICONTROL Segment name]**, quindi fare clic su **[!UICONTROL Create]** prima di selezionare il nuovo pubblico creato.

   ![](assets/aam_save_audience_segment_picker.png)

   Per essere riconciliati e scambiati, i record devono avere un Adobe Experience Cloud ID (&#39;ID visitatore&#39; o &#39;ID dichiarato&#39;). I record non riconciliati vengono ignorati durante l’importazione e l’esportazione di tipi di pubblico.

1. Per terminare, fai clic sul segno di spunta in alto a destra dello schermo.
1. Selezionare il **[!UICONTROL Shared Data Source]** corrispondente.
1. Se lo desideri, seleziona la casella **[!UICONTROL Generate an outbound transition]** per utilizzare i profili esportati. Vengono esportati solo i profili che è possibile riconciliare.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
1. Avvia il flusso di lavoro per esportare il pubblico. La sincronizzazione tra Adobe Campaign e il servizio core People può richiedere diverse ore

La sincronizzazione tra Adobe Campaign e il servizio core People richiede 24-36 ore. Dopo questo periodo, potrai trovare il nuovo pubblico nel servizio core People e riutilizzarlo in altre soluzioni Adobe Experience Cloud. Per ulteriori informazioni sull&#39;utilizzo di un pubblico condiviso di Adobe Campaign nel servizio core People di Adobe, consulta questa [documentazione](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html?lang=it).

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Tipi di pubblico](../../audiences/using/about-audiences.md)
