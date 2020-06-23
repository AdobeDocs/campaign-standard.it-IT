---
title: Condivisione dei tipi di pubblico con Audience Manager o il servizio core People
description: Scopri come importare o esportare il pubblico nelle diverse soluzioni Adobe Experience Cloud.
page-status-flag: never-activated
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 2%

---


# Condivisione dei tipi di pubblico con Audience Manager o il servizio core People{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importazione di un&#39;audience {#importing-an-audience}

L&#39;integrazione del servizio di base Persone consente di importare direttamente un&#39;audience  Adobe Campaign tramite un flusso di lavoro tecnico per arricchire il database. Per ulteriori informazioni sulla condivisione di audience nel servizio di base Persone, consulta questa [documentazione](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

L&#39;importazione di audience/segmenti dal servizio di base Persone nel Adobe Campaign  può essere effettuata dal **[!UICONTROL Audiences]** menu solo dagli utenti connessi tramite IMS (autenticazione tramite  Adobe ID).

1. Vai al **[!UICONTROL Audiences]** menu.
1. Nella barra delle azioni, selezionate **[!UICONTROL Create]** da portare sullo schermo per creare un pubblico.
1. Specifica l&#39;etichetta della nuova audience.
1. Impostate l&#39;audience **[!UICONTROL Type]** per **[!UICONTROL Experience Cloud]** indicare che l&#39;audience creata è un&#39;audience importata dal servizio di base Persone.
1. Dal **[!UICONTROL Name of the shared audience]** campo, selezionate il pubblico da importare. È possibile importare solo i segmenti. I dati granulari, incluse coppie chiave-valore, caratteristiche e regole, non sono supportati.

   ![](assets/aam_import_audience.png)

1. Selezionare la **[!UICONTROL Shared Data Source]** voce corrispondente.

   Se l&#39;origine dati selezionata è configurata per l&#39;utilizzo di un algoritmo di cifratura, un&#39;ulteriore opzione vi offre la possibilità di **[!UICONTROL Force reconciliation with a profile]**. Selezionare questa opzione se il **[!UICONTROL Channel]** campo dell&#39;origine dati è impostato su E-mail o Mobile (SMS) e se si desidera sfruttare i dati del profilo.

   Se non si seleziona l&#39; **[!UICONTROL Force reconciliation with a profile]** e se **[!UICONTROL Channel]** è impostato in Origine dati AMC su E-mail o Mobile (SMS), tutti gli ID dichiarati crittografati vengono decrittografati. Viene creato/aggiornato un pubblico di tipo **File** con un elenco di tutti gli indirizzi e-mail/numeri di telefono cellulare. In questo modo, durante l&#39;importazione di un&#39;audience condivisa tramite questa integrazione non viene perso alcun indirizzo e-mail/numero di telefono cellulare, anche se tale profilo non esiste in Campaign. Questo tipo di pubblico non può essere utilizzato direttamente perché deve essere riconciliato manualmente tramite i flussi di lavoro.

1. Confermate la creazione dell&#39;audience.

   L&#39;audience viene quindi importata tramite un flusso di lavoro tecnico. È composta da record di cui l&#39;ID (&#39;ID visitatore&#39; o &#39;ID dichiarato&#39;) è stato in grado di riconciliarsi con la dimensione del profilo. Gli ID dai segmenti del servizio di base Persone che non sono riconosciuti dal Adobe Campaign  non vengono importati.

Il pubblico viene ora importato nel database del Adobe Campaign . La sincronizzazione del processo di importazione richiede 24-36 ore, quando i segmenti vengono importati direttamente dal servizio di base Persone o  Audience Manager. Dopo questo periodo, potrete trovare e utilizzare la nuova audience in  Adobe Campaign.

>[!NOTE]
>
>Se importate audience da Adobe  Analytics a  Adobe Campaign, queste devono prima essere condivise in Servizio core Persone o  Audience Manager. Questo processo richiede 12-24 ore, che devono essere aggiunte alla sincronizzazione di 24-36 ore con Campaign. In questo caso specifico, il periodo di condivisione dell&#39;audience può essere fino a 60 ore. Per ulteriori informazioni sulla condivisione di audience di Adobe  Analytics nel servizio Persone di base e in Audience Manager, consulta questa [documentazione](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-publish.html).

## Esportazione di un&#39;audience {#exporting-an-audience}

Un&#39;audience può essere esportata da  Adobe Campaign a  servizio di base Audience Manager o Persone utilizzando un flusso di lavoro e l&#39; **[!UICONTROL Save audience]** attività.

Può essere eseguito in un nuovo flusso di lavoro e solo dagli utenti connessi tramite IMS (autenticazione tramite  Adobe ID).

1. Crea un nuovo flusso di lavoro da un programma, una campagna o un elenco di attività di marketing.
1. Utilizzando le diverse attività disponibili, eseguite il targeting di un set di profili.
1. Dopo il targeting, trascinate e rilasciate un&#39; **[!UICONTROL Save audience]** attività nel flusso di lavoro, quindi apritela.
1. Selezionare **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specificate l&#39;audience utilizzando il **[!UICONTROL Shared audience]** campo. Nella finestra che si apre, potete scegliere se selezionare un&#39;audience esistente o crearne una nuova:

   * Se selezionate un&#39;audience esistente, solo i nuovi record verranno aggiunti all&#39;audience.
   * Per esportare l&#39;elenco dei profili in una nuova audience, completa il **[!UICONTROL Segment name]** campo e fai clic **[!UICONTROL Create]** prima di selezionare l&#39;audience appena creata.
   ![](assets/aam_save_audience_segment_picker.png)

   Per essere riconciliati e scambiati, i record devono disporre di un Adobe Experience Cloud ID (&#39;ID visitatore&#39; o &#39;ID dichiarato&#39;). I record non riconciliati vengono ignorati durante l&#39;importazione e l&#39;esportazione di audience.

1. Per terminare, fare clic sul segno di spunta situato in alto a destra nella schermata.
1. Selezionare la **[!UICONTROL Shared Data Source]** voce corrispondente.
1. Se lo desiderate, selezionate la **[!UICONTROL Generate an outbound transition]** casella per utilizzare i profili esportati. Vengono esportati solo i profili che è possibile riconciliare.
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.
1. Avvia il flusso di lavoro per esportare il pubblico. La sincronizzazione tra  servizio di base Adobe Campaign e Persone può richiedere diverse ore

La sincronizzazione tra  servizio di base Persone e Adobe Campaign richiede 24-36 ore. Dopo questo periodo, potrai trovare il nuovo pubblico nel servizio di base Persone e riutilizzarlo in altre soluzioni Adobe Experience Cloud. Per ulteriori informazioni sull&#39;utilizzo di un&#39;audience condivisa  Adobe Campaign nel servizio di base Adobe People, consulta questa [documentazione](https://docs.adobe.com/content/help/en/core-services/interface/audiences/t-audience-create.html).

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Audiences](../../audiences/using/about-audiences.md)

