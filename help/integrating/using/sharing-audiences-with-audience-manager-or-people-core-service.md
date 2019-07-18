---
title: Condivisione di audience con il servizio di base Audience Manager o Persone
seo-title: Condivisione di audience con il servizio di base Audience Manager o Persone
description: Condivisione di audience con il servizio di base Audience Manager o Persone
seo-description: Scopri come importare o esportare il pubblico nelle diverse soluzioni Adobe Experience Cloud.
page-status-flag: never-activated
uuid: a 3701 e 72-5846-4241-afee-d 713 b 499 a 27 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77 af 0772-52 b 5-46 bc-a 964-675 b 45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Sharing audiences with Audience Manager or People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importing an audience {#importing-an-audience}

L'integrazione del servizio di base Persone consente di importare direttamente un pubblico in Adobe Campaign tramite un flusso di lavoro tecnico per arricchire il database. For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Importing audiences/segments from People core service in Adobe Campaign can be carried out from the **[!UICONTROL Audiences]** menu only by users connected via IMS (authentication via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. In the action bar, select **[!UICONTROL Create]** to be taken to the screen to create an audience.
1. Specificate l'etichetta della nuova audience.
1. Set the audience **[!UICONTROL Type]** to **[!UICONTROL Experience Cloud]** to indicate that the audience being created is an audience that was imported from People core service.
1. From the **[!UICONTROL Name of the shared audience]** field, select the audience to import. È possibile importare solo segmenti. I dati granulari quali coppie chiave-valore, caratteristiche e regole non sono supportati.

   ![](assets/aam_import_audience.png)

1. Select the corresponding **[!UICONTROL Shared Data Source]**.

   If the selected data source is configured to use an encryption algorithm, an additional option offers you the possibility to **[!UICONTROL Force reconciliation with a profile]**. Check this option if the **[!UICONTROL Channel]** field of the data source is set to Email or Mobile (SMS) and if you want to leverage profile data.

   If you do not select the **[!UICONTROL Force reconciliation with a profile]** and if **[!UICONTROL Channel]** is set in AMC Data source to Email or Mobile (SMS) then all the encrypted declared IDs are decrypted. An audience of type **File** with a list of all the email addresses/mobile phone numbers is created/updated. In questo modo, non viene perso nessun indirizzo e-mail/numero di telefono cellulare durante l'importazione di un pubblico condiviso tramite questa integrazione, anche se tale profilo non esiste in Campaign. Questo tipo di audience non può essere utilizzato direttamente perché deve essere riconciliato manualmente tramite flussi di lavoro.

1. Confermate la creazione dell'audience.

   L'audience viene quindi importata tramite un flusso di lavoro tecnico. È composto di record per i quali è possibile riconciliare l'ID ('Visitor ID'o'Dichiarato ID ') con la dimensione del profilo. Gli ID dai segmenti di servizio di base Persone non riconosciuti da Adobe Campaign non vengono importati.

Il pubblico viene ora importato nel database Adobe Campaign. Il processo di importazione dura 24-36 ore per la sincronizzazione, quando i segmenti vengono importati direttamente dal servizio di base Persone o Audience Manager. Dopo questo periodo, potrai trovare e utilizzare il nuovo pubblico in Adobe Campaign.

>[!NOTE]
>
>Se importate tipi di pubblico da Adobe Analytics ad Adobe Campaign, questi tipi di pubblico devono essere condivisi prima nel servizio core Persone o Audience Manager. Questo processo richiede 12-24 ore, da aggiungere alla sincronizzazione 24-36 ore con Campaign. In questo caso specifico, la durata temporale dell'audience può essere di 60 ore. For more information on Adobe Analytics audience sharing in People Core service and Audience manager, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exporting an audience {#exporting-an-audience}

An audience can be exported from Adobe Campaign to Audience Manager or People core service using a workflow and the **[!UICONTROL Save audience]** activity.

Può essere eseguita in un nuovo flusso di lavoro e solo dagli utenti connessi tramite IMS (autenticazione tramite Adobe ID).

1. Crea un nuovo flusso di lavoro da un programma, una campagna o un elenco di attività di marketing.
1. Utilizzando le diverse attività disponibili, eseguite il targeting di un set di profili.
1. After the targeting, drag and drop a **[!UICONTROL Save audience]** activity into the workflow, then open it.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specify the audience using the **[!UICONTROL Shared audience]** field. Nella finestra visualizzata, potete scegliere se selezionare un'audience esistente o creare un nuovo pubblico:

   * Se selezionate un'audience esistente, al pubblico verranno aggiunti solo i nuovi record.
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   Per essere riconciliati e scambiati, i record devono disporre di un Adobe Experience Cloud ID ("Visitor ID" o "Dichiarato ID"). I record non riconciliati vengono ignorati durante l'importazione ed esportazione di audience.

1. Per terminare, fate clic sul segno di spunta situato in alto a destra nella schermata.
1. Select the corresponding **[!UICONTROL Shared Data Source]**.
1. If you like, check the **[!UICONTROL Generate an outbound transition]** box to use the profiles that were exported. Vengono esportati solo i profili che possono essere riconciliati.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.
1. Avviate il flusso di lavoro per esportare il pubblico. La sincronizzazione tra il servizio di base Adobe Campaign e Persone può richiedere diverse ore

La sincronizzazione tra il servizio di base Adobe Campaign e Persone dura 24-36 ore. Dopo questo periodo, potrai trovare il nuovo pubblico nel servizio di base Persone e riutilizzarlo in altre soluzioni Adobe Experience Cloud. For more information on using an Adobe Campaign shared audience in Adobe People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/workflow-data-and-processes.md)
* [Audience](../../audiences/using/about-audiences.md)

