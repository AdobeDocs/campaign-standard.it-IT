---
title: Utilizzo delle immagini
description: Scoprite come gestire le immagini nei messaggi e-mail con Designer e-mail.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7e300de836a74372e411b5b1d584851fac77aafe

---


# Utilizzo delle immagini {#images}

## Inserimento di immagini{#inserting-images}

Potete inserire immagini nei messaggi e-mail e nelle pagine di destinazione.

A seconda della configurazione, sono disponibili i seguenti tipi di immagini:

* Immagini locali
* Immagini condivise da Adobe Experience Cloud - fate riferimento a [Utilizzo del servizio](../../integrating/using/working-with-campaign-and-assets-core-service.md) core Campaign e Assets / Assets On Demand
* Immagini dinamiche da Adobe Target - consultate [Utilizzo di Campaign e Target](../../integrating/using/about-campaign-target-integration.md)

Se attivato, puoi modificare le immagini con Adobe Creative SDK. Consultate [Modifica delle immagini con Adobe Creative SDK](#modifying-images-with-the-adobe-creative-sdk).

>[!CAUTION]
>
>Se scegliete di aggiungere un&#39;immagine direttamente modificando la versione HTML dell&#39;e-mail, non dovete richiamare i file **esterni in un tag** &lt;script> della pagina HTML. Questi file non verranno importati nel server Adobe Campaign.

### Inserimento di immagini in un messaggio e-mail {#inserting-images-in-an-email}

1. Aggiungere un componente struttura. Per ulteriori informazioni, consultate [Modifica della struttura](../../designing/using/designing-from-scratch.md#defining-the-email-structure)delle e-mail.
1. All’interno di questo componente struttura, aggiungete un componente **[!UICONTROL Image]**contenuto.

   ![](assets/des_insert_images_1.png)

1. Clic **[!UICONTROL Browse]**. Trascinare un’immagine o fare clic per selezionare un file dal computer.

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
* Quando modificate una pagina di destinazione, **Dimensioni** consente di specificare le dimensioni dell’immagine in pixel.

L’editor consente di lavorare con **tutti i tipi** di immagini i cui formati sono compatibili con i browser. Per essere compatibili con l’editor, le animazioni **di tipo** &quot;Flash&quot; devono essere inserite in una pagina HTML come segue:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

## Modifica delle immagini con Adobe Creative SDK{#modifying-images-with-the-adobe-creative-sdk}

Potete modificare le immagini e utilizzare un set completo di funzioni basato su Adobe Creative SDK per migliorare le immagini direttamente nell’editor dei contenuti durante la modifica di e-mail o la destinazione di pagine.

L’editor di immagini offre un potente componente dell’interfaccia utente per la modifica delle immagini che consente di modificare le immagini e applicare effetti e fotogrammi, adesivi originali di alta qualità, sovrapposizioni fantastiche, funzioni divertenti come lo spostamento dell’inclinazione e l’iniziale del colore, regolazioni pro-livello e altro ancora.

Per modificare un’immagine con Adobe Creative SDK:

1. Selezionate l’immagine.
1. Nella barra degli strumenti, fate clic sull&#39;icona Creative Cloud.

   ![](assets/des_creative_sdk_icon.png)

1. Selezionate lo strumento da usare tramite le icone nella parte superiore della finestra per modificare l’immagine.

   ![](assets/email_designer_ccsdktoolbar.png)

1. Fate clic su **[!UICONTROL Save]**quando vengono apportate le modifiche. L&#39;immagine aggiornata viene salvata sul server di Adobe Campaign e pronta per essere utilizzata.

>[!NOTE]
Gli strumenti disponibili nell’editor di immagini non possono essere personalizzati.
