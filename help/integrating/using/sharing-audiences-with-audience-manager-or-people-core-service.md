---
title: Condivisione di audience con Audience Manager o il servizio di base Persone
description: Scopri come importare o esportare il pubblico nelle diverse soluzioni Adobe Experience Cloud.
page-status-flag: mai attivato
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: lavoro con campagna e pubblico-manager o persone-servizio di base
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Condivisione di audience con Audience Manager o il servizio di base Persone{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importazione di un'audience {#importing-an-audience}

L'integrazione dei servizi di base per le persone consente di importare direttamente un'audience in Adobe Campaign tramite un flusso di lavoro tecnico per arricchire il database. Per ulteriori informazioni sulla condivisione di audience nel servizio di base Persone, consulta questa [documentazione](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

L'importazione di audience/segmenti dal servizio di base Persone in Adobe Campaign può essere eseguita dal **[!UICONTROL Audiences]** menu solo dagli utenti connessi tramite IMS (autenticazione tramite Adobe ID).

1. Vai al **[!UICONTROL Audiences]** menu.
1. Nella barra delle azioni, selezionate **[!UICONTROL Create]** da portare sullo schermo per creare un pubblico.
1. Specifica l'etichetta della nuova audience.
1. Impostate l'audience **[!UICONTROL Type]** per **[!UICONTROL Experience Cloud]** indicare che l'audience creata è un'audience importata dal servizio di base Persone.
1. Dal **[!UICONTROL Name of the shared audience]** campo, selezionate il pubblico da importare. È possibile importare solo i segmenti. I dati granulari, incluse coppie chiave-valore, caratteristiche e regole, non sono supportati.

   ![](assets/aam_import_audience.png)

1. Selezionare la **[!UICONTROL Shared Data Source]** voce corrispondente.

   Se l'origine dati selezionata è configurata per l'utilizzo di un algoritmo di cifratura, un'ulteriore opzione vi offre la possibilità di **[!UICONTROL Force reconciliation with a profile]**. Selezionare questa opzione se il **[!UICONTROL Channel]** campo dell'origine dati è impostato su E-mail o Mobile (SMS) e se si desidera sfruttare i dati del profilo.

   Se non si seleziona l' **[!UICONTROL Force reconciliation with a profile]** e se **[!UICONTROL Channel]** è impostato in Origine dati AMC su E-mail o Mobile (SMS), tutti gli ID dichiarati crittografati vengono decrittografati. Viene creato/aggiornato un pubblico di tipo **File** con un elenco di tutti gli indirizzi e-mail/numeri di telefono cellulare. In questo modo, durante l'importazione di un'audience condivisa tramite questa integrazione non viene perso alcun indirizzo e-mail/numero di telefono cellulare, anche se tale profilo non esiste in Campaign. Questo tipo di pubblico non può essere utilizzato direttamente perché deve essere riconciliato manualmente tramite i flussi di lavoro.

1. Confermate la creazione dell'audience.

   Il pubblico viene quindi importato tramite un flusso di lavoro tecnico. È composta da record di cui l'ID ('ID visitatore' o 'ID dichiarato') è stato in grado di riconciliarsi con la dimensione del profilo. Gli ID dai segmenti del servizio di base Persone non riconosciuti da Adobe Campaign non vengono importati.

Il pubblico ora viene importato nel database Adobe Campaign. La sincronizzazione del processo di importazione richiede 24-36 ore, quando i segmenti vengono importati direttamente dal servizio di base Persone o da Audience Manager. Dopo questo periodo, potrai trovare e utilizzare la nuova audience in Adobe Campaign.

>[!NOTE]
>
>Se importate audience da Adobe Analytics ad Adobe Campaign, queste audience devono prima essere condivise in Servizio di base Persone o Audience Manager. Questo processo richiede 12-24 ore, che devono essere aggiunte alla sincronizzazione di 24-36 ore con Campaign. In questo caso specifico, il periodo di condivisione dell'audience può essere fino a 60 ore. Per ulteriori informazioni sulla condivisione dell'audience di Adobe Analytics nel servizio People Core e nel gestore dell'audience, consulta questa [documentazione](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Esportazione di un'audience {#exporting-an-audience}

Un'audience può essere esportata da Adobe Campaign ad Audience Manager o al servizio di base Persone utilizzando un flusso di lavoro e l' **[!UICONTROL Save audience]** attività.

Può essere eseguito in un nuovo flusso di lavoro e solo dagli utenti connessi tramite IMS (autenticazione tramite Adobe ID).

1. Crea un nuovo flusso di lavoro da un programma, una campagna o un elenco di attività di marketing.
1. Utilizzando le diverse attività disponibili, eseguite il targeting di un set di profili.
1. Dopo il targeting, trascinate e rilasciate un' **[!UICONTROL Save audience]** attività nel flusso di lavoro, quindi apritela.
1. Selezionare **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specificate l'audience utilizzando il **[!UICONTROL Shared audience]** campo. Nella finestra visualizzata, potete scegliere se selezionare un'audience esistente o crearne una nuova:

   * Se selezionate un'audience esistente, solo i nuovi record verranno aggiunti all'audience.
   * Per esportare l'elenco dei profili in una nuova audience, completa il **[!UICONTROL Segment name]** campo e fai clic **[!UICONTROL Create]** prima di selezionare l'audience appena creata.
   ![](assets/aam_save_audience_segment_picker.png)

   Per essere riconciliati e scambiati, i record devono disporre di un Adobe Experience Cloud ID ('ID visitatore' o 'ID dichiarato'). I record non riconciliati vengono ignorati durante l'importazione e l'esportazione di audience.

1. Per terminare, fare clic sul segno di spunta situato in alto a destra nella schermata.
1. Selezionare la **[!UICONTROL Shared Data Source]** voce corrispondente.
1. Se lo desiderate, selezionate la **[!UICONTROL Generate an outbound transition]** casella per utilizzare i profili esportati. Vengono esportati solo i profili che è possibile riconciliare.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.
1. Avvia il flusso di lavoro per esportare il pubblico. La sincronizzazione tra Adobe Campaign e il servizio di base Persone può richiedere diverse ore

La sincronizzazione tra Adobe Campaign e il servizio di base Persone richiede 24-36 ore. Dopo questo periodo, potrai trovare il nuovo pubblico nel servizio di base Persone e riutilizzarlo in altre soluzioni Adobe Experience Cloud. Per ulteriori informazioni sull'utilizzo di un'audience condivisa di Adobe Campaign nel servizio di base Adobe People, consulta questa [documentazione](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/workflow-data-and-processes.md)
* [Audiences](../../audiences/using/about-audiences.md)

