---
solution: Campaign Standard
product: campaign
title: Utilizzo delle immagini
description: Scoprite come gestire le immagini nei messaggi e-mail con Designer e-mail.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 3%

---


# Utilizzo delle immagini {#images}

## Inserimento di immagini{#inserting-images}

Potete inserire immagini nei messaggi e-mail e nelle pagine di destinazione.

A seconda della configurazione, sono disponibili i seguenti tipi di immagini:

* Immagini locali
* Immagini condivise da Adobe Experience Cloud - fate riferimento a [Utilizzo del servizio](../../integrating/using/working-with-campaign-and-assets-core-service.md) core Campaign and Assets / Assets On Demand
* Immagini dinamiche da  Adobe Target - fare riferimento a [Utilizzo di Campaign e Target](../../integrating/using/about-campaign-target-integration.md)

>[!CAUTION]
>
>Se scegliete di aggiungere un&#39;immagine direttamente modificando la versione HTML dell&#39;e-mail, non dovete richiamare i file **esterni in un tag** &lt;script> della pagina HTML. Questi file non verranno importati nel server Adobe Campaign .

### Inserimento di immagini in un messaggio e-mail {#inserting-images-in-an-email}

1. Aggiungere un componente struttura. Per ulteriori informazioni, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. All’interno di questo componente struttura, aggiungete un componente **[!UICONTROL Image]** contenuto.

   ![](assets/des_insert_images_1.png)

1. Fai clic su **[!UICONTROL Browse]**. Trascinare un’immagine o fare clic per selezionare un file dal computer.

   ![](assets/des_insert_images_2.png)

1. Selezionate il componente di contenuto appena aggiunto.
1. Controllate le proprietà dell’immagine e regolatele se necessario.

   ![](assets/des_insert_images_3.png)

## Impostazione delle proprietà immagine{#setting-up-image-properties}

Quando si seleziona un blocco che contiene un&#39;immagine, nella palette sono disponibili le seguenti proprietà:

* **Abilita la personalizzazione** consente di personalizzare l’origine delle immagini. Consultate [Personalizzazione di un’origine](../../designing/using/personalization.md#personalizing-an-image-source)immagine.
* **Titolo** immagine consente di definire un titolo per l’immagine.
* **Il testo** Alt (e-mail) o **Didascalia** (pagina di destinazione) consente di definire la didascalia collegata all’immagine (corrisponde all’attributo **HTML alt** ).
* Quando modificate un’e-mail, **Stile** consente di specificare la dimensione dell’immagine, lo sfondo e il bordo.
* Quando modificate una pagina di destinazione, **Dimension** consente di specificare le dimensioni dell’immagine in pixel.

L’editor consente di lavorare con **tutti i tipi** di immagini i cui formati sono compatibili con i browser. Per essere compatibile con l’editor, le animazioni **di tipo** &quot;Flash&quot; devono essere inserite in una pagina HTML come segue:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

<!--
## Modifying images with the Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

You can edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor when editing emails or landing pages.

The image editor offers a powerful, full-featured image editing UI component that allows you to edit images and apply effects and frames, original high-quality stickers, beautiful overlays, fun features like tilt shift and color splash, pro-level adjustments and more.

To modify an image with the Adobe Creative SDK:

1. Select the image.
1. In the toolbar, click the Creative Cloud icon.

   ![](assets/des_creative_sdk_icon.png)

1. Select the tool you want to use through the icons on the top of the window to modify the image.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Click **[!UICONTROL Save]** when modifications are done. The updated image is saved on Adobe Campaign server and ready to be used.

>[!NOTE]
>
>Tools offered in the image editor cannot be customized.
-->