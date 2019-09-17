---
title: Informazioni sulla progettazione del contenuto della pagina di destinazione
seo-title: Informazioni sulla progettazione del contenuto della pagina di destinazione
description: Informazioni sulla progettazione del contenuto della pagina di destinazione
seo-description: Scopri le specificità dell’editor di contenuti per la pagina di destinazione.
page-status-flag: mai attivato
uuid: 8b230690-8a63-44da-b4ed-8e9d8fd84262
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: progettazione
content-type: reference
topic-tags: editing-landing-page-content
discoiquuid: 212720d2-5d57-4e7a-bb72-10512050e78c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---

# Informazioni sulla progettazione del contenuto della pagina di destinazione{#about-landing-page-content-design}

Utilizza l'editor di contenuti standard per creare e modificare il contenuto delle pagine di destinazione in Adobe Campaign.

Questa sezione descrive le specificità dell’editor di contenuti per la pagina di destinazione:

* [Interfaccia dell'editor del contenuto della pagina di destinazione](../../channels/using/landing-page-content-editor-interface.md)
* [Gestione della struttura e dello stile della pagina di destinazione](../../channels/using/managing-landing-page-structure-and-style.md)
* [Modifica delle proprietà dei dati del modulo di una pagina di destinazione](../../channels/using/changing-a-landing-page-form-data-properties.md)

Per ulteriori informazioni sulle azioni comuni a una o più attività di marketing, consulta le sezioni seguenti:

* Per ulteriori informazioni sulla personalizzazione del contenuto di una pagina di destinazione, consultate [Inserimento di un campo](../../designing/using/personalization.md#inserting-a-personalization-field) di personalizzazione e [Aggiunta di un blocco](../../designing/using/personalization.md#adding-a-content-block)di contenuto.
* Per ulteriori informazioni sulla definizione del contenuto dinamico in una pagina di destinazione, consultate [Definizione del contenuto dinamico in una pagina](../../channels/using/defining-dynamic-content-in-a-landing-page.md)di destinazione.
* Per ulteriori informazioni sull'inserimento di collegamenti in una pagina di destinazione, vedere [Inserimento di un collegamento](../../designing/using/links.md#inserting-a-link).
* Per ulteriori informazioni sull’inserimento di immagini in una pagina di destinazione, consultate [Inserimento di immagini](../../designing/using/images.md).

Controllate anche le procedure ottimali [generali per la progettazione](../../designing/using/overview.md#content-design-best-practices)dei contenuti.

>[!NOTE]
>
>Se l'istanza è stata installata prima della release di Adobe Campaign Standard 19.0, potete comunque accedere all'editor dei contenuti dell'e-mail legacy. L’interfaccia, i principi di utilizzo e configurazione sono principalmente gli stessi descritti di seguito per le pagine di destinazione. Tuttavia, tutte le funzioni potrebbero non essere disponibili o mantenute nell’editor dei contenuti e-mail legacy, che è diventato obsoleto a partire dalla versione 19.0. Per modificare rapidamente il contenuto delle e-mail mediante un'interfaccia a trascinamento con funzioni estese, utilizzare [Email Designer](../../designing/using/overview.md).

## Best practice per la progettazione delle pagine di destinazione {#landing-pages-best-practices-design}

* Durante la modifica del contenuto **della pagina di** destinazione:

   * Prima di importare un modello di pagina HTML in Adobe Campaign, accertatevi che il modello si apra e venga visualizzato correttamente nei vari browser.
   * Se la pagina HTML contiene script JavaScript, questi devono essere eseguiti senza errori all'esterno dell'editor. In generale, evitare di utilizzare gli script nel contenuto dei messaggi per essere certi che vengano elaborati correttamente dai client e-mail.
   * Durante la creazione di un modello, si consiglia di aggiungere un attributo **'type'** ai tag. Queste informazioni verranno elaborate dall'editor e aiuteranno l'utente a collegare un campo di database al campo del modulo durante la configurazione dell'applicazione Web.
   Esempio di codice HTML nel modello:

   ```
   <input id="email" type="email" name="email"/>
   ```

   L'elenco ufficiale degli attributi 'type' è disponibile al seguente indirizzo: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)