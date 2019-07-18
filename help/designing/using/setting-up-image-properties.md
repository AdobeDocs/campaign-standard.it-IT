---
title: Impostazione delle proprietà dell'immagine
seo-title: Impostazione delle proprietà dell'immagine
description: Impostazione delle proprietà dell'immagine
seo-description: Scopri come gestire le proprietà delle immagini incluse nel contenuto.
page-status-flag: never-activated
uuid: 1 a 439105-d 9 aa -4 b 30-a 00 d-bcf 731 a 04 e 08
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: utilizzo di immagini
discoiquuid: 80 c 9 c 1 a 5-6050-443 d -810 a -6 bb 755 d 39 dca
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Setting up image properties{#setting-up-image-properties}

Quando si seleziona un blocco contenente un'immagine, nella palette vengono offerte le seguenti proprietà:

* **Abilitare la personalizzazione** consente di personalizzare l'origine dell'immagine. See [Personalizing an image source](../../designing/using/personalizing-an-image-source.md).
* **Titolo immagine** consente di definire un titolo per l'immagine.
* **Testo Alt** (e-mail) o **Didascalia** (pagina di destinazione) consente di definire la didascalia collegata all'immagine (corrisponde all' **attributo** HTML alt).
* When editing an email, **Style** lets you specify the image size, background, and border.
* When editing a landing page, **Dimensions** lets you specify the image size in pixels.

The editor allows you to work with **all image types** whose formats are compatible with browsers. To be compatible with the editor, the **"Flash" type animations** have to be inserted in an HTML page as follows:

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

