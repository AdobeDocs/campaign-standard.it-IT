---
title: Inserimento di immagini
seo-title: Inserimento di immagini
description: Inserimento di immagini
seo-description: Scoprite come aggiungere immagini al contenuto.
page-status-flag: never-activated
uuid: ac 42 b 1 d 3-50 ad -4323-b 474-1 e 50 e 468901 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: utilizzo di immagini
discoiquuid: ede 832 ac -96 e 5-41 e 1-8390-6669 ba 30 d 4 d 8
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Inserting images{#inserting-images}

Potete inserire delle immagini nelle e-mail e nelle pagine di destinazione.

Sono disponibili i seguenti tipi di immagini, a seconda della configurazione:

* Immagini locali
* Images shared from Adobe Experience Cloud - refer to [Working with Campaign and Assets Core Service](../../integrating/using/working-with-campaign-and-assets-core-service.md) / Assets On Demand
* Dynamic images from Adobe Target - refer to [Working with Campaign and Target](../../integrating/using/about-campaign-target-integration.md)

Se abilitata, potete modificare le immagini con Adobe Creative SDK. See [Modifying images with the Adobe Creative SDK](../../designing/using/modifying-images-with-the-adobe-creative-sdk.md).

>[!CAUTION]
>
>If you choose to add an image directly by editing the HTML version of the email, you must not call up **external files in a &lt;script&gt; tag** of the HTML page. Questi file non verranno importati sul server Adobe Campaign.

## Inserting images in an email {#inserting-images-in-an-email}

1. Aggiungere un componente struttura. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inside this structure component, add an **[!UICONTROL Image]** content component.

   ![](assets/des_insert_images_1.png)

1. Click **[!UICONTROL Browse]**. Trascinate un'immagine o fate clic per selezionare un file dal computer.

   ![](assets/des_insert_images_2.png)

1. Selezionate il componente contenuto appena aggiunto.
1. Controllate le proprietà dell'immagine e regolatele, se necessario.

   ![](assets/des_insert_images_3.png)

## Inserting images in a landing page {#inserting-images-in-a-landing-page}

1. In una pagina di destinazione, selezionate un blocco contenente un'immagine.
1. Select the **[!UICONTROL Insert]** button.

   ![](assets/des_insert_images_lp_1.png)

1. Choose **[!UICONTROL Local image]** from the contextual toolbar.

   ![](assets/des_insert_images_lp_2.png)

1. Selezionate un file.

   ![](assets/des_insert_images_lp_3.png)

1. Regolare le proprietà dell'immagine in base alle esigenze.

   ![](assets/des_insert_images_lp_4.png)

