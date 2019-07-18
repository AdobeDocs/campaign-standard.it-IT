---
title: Best practice per la progettazione di contenuto
seo-title: Best practice per la progettazione di contenuto
description: Best practice per la progettazione di contenuto
seo-description: Leggere queste linee guida per garantire l'ottimizzazione ottimale dell'editor.
page-status-flag: never-activated
uuid: ad 74 f 49 d -999 f -4140-89 b 0-d 1 ead 8642 d 89
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: about-content-design
discoiquuid: d 33 f 5 f 14-a 4 e 3-4327-bd 16-eb 3135 a 32076
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Content design best practices{#content-design-best-practices}

Per garantire l'operazione ottimale dell'editor, consigliamo di osservare le seguenti linee guida:

* I fogli di stile SCSS non sono supportati. Utilizzate CSS regolare se importate file ZIP contenenti il contenuto HTML.
* When editing **email content**:

   Visualizzare l'anteprima dei messaggi prima di inviarli. Adobe Campaign offre un modo per testare il rendering tramite e-mail utilizzando Litmus. For more on this, see [Email rendering](../../sending/using/email-rendering.md).

* When editing **landing page content**:

   * Prima di importare un modello di pagina HTML in Adobe Campaign, assicurati che il modello si apre e venga visualizzato correttamente nei vari browser.
   * Se la pagina HTML contiene script javascript, questi devono essere eseguiti senza errori esterni all'editor. In generale, evitate di utilizzare gli script nel contenuto del messaggio per essere certi che vengano elaborati correttamente dai client e-mail.
   * When building a template, we recommend adding a **'type'** attribute to  tags. Queste informazioni saranno elaborate dall'editor e consentiranno all'utente di collegare un campo di database al campo modulo al momento della configurazione dell'applicazione Web.

      Esempio di codice HTML nel modello:

      ```
      <input id="email" type="email" name="email"/>
      ```

      The official list of 'type' attributes is available at the following address: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

More design and general best practices regarding messages are presented in the following Adobe Campaign step-by-step guide: [Delivery best practices with Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).
