---
title: Progettazione di una pagina di destinazione
description: Scoprite come progettare il contenuto di una pagina di destinazione.
page-status-flag: never-activated
uuid: de6fe190-835c-40fd-8101-a809b430b423
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: bd77d6f0-3143-4030-a91b-988a2bebc534
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Progettazione di una pagina di destinazione{#designing-a-landing-page}

## Informazioni sulla progettazione del contenuto della pagina di destinazione {#about-content-design}

Le pagine di destinazione vengono create come qualsiasi attività [di](../../start/using/marketing-activities.md#about-marketing-activities)marketing.

Durante la progettazione di una pagina di destinazione, è necessario definire il contenuto della pagina stessa, la pagina di conferma e la pagina di errore. Utilizzate lo switcher sotto la barra delle azioni per visualizzare e configurare ciascuna di queste pagine.

Il contenuto delle pagine di destinazione è progettato tramite l'editor di contenuti di Campaign.

>[!NOTE]
>
>Se l'istanza è stata installata prima della release di Adobe Campaign Standard 19.0, potete comunque accedere all'editor dei contenuti dell'e-mail legacy. L’interfaccia, i principi di utilizzo e configurazione sono principalmente gli stessi descritti di seguito per le pagine di destinazione. Tuttavia, tutte le funzioni potrebbero non essere disponibili o mantenute nell’editor dei contenuti e-mail legacy, che è diventato obsoleto a partire dalla versione 19.0. Per modificare rapidamente il contenuto delle e-mail mediante un'interfaccia a trascinamento con funzioni estese, utilizzare [Email Designer](../../designing/using/overview.md).

Questa pagina descrive le specificità dell’editor dei contenuti della pagina di destinazione. Per ulteriori informazioni sulle azioni comuni a una o più attività di marketing, consulta queste sezioni dalla guida **Progettazione del contenuto** delle e-mail:

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco](../../designing/using/personalization.md#adding-a-content-block)di contenuto.
* [Inserimento di un collegamento](../../designing/using/links.md#inserting-a-link).
* [Inserimento di immagini](../../designing/using/images.md).
* [Best practice generali per la progettazione](../../designing/using/overview.md#content-design-best-practices)dei contenuti.

>[!NOTE]
>Se la pagina di destinazione è già predefinita in formato HTML, potete importarla direttamente utilizzando il **[!UICONTROL Change content]** pulsante.
>
>Prima di importare una pagina HTML in Adobe Campaign, accertatevi che si apra e venga visualizzata correttamente nei vari browser. Se la pagina HTML contiene script JavaScript, questi devono essere eseguiti senza errori all'esterno dell'editor. In generale, evitare di utilizzare gli script nel contenuto dei messaggi per essere certi che vengano elaborati correttamente dai client e-mail.

## Interfaccia dell'editor del contenuto della pagina di destinazione{#landing-page-content-editor-interface}

L'editor del contenuto della pagina di destinazione consente di definire, modificare e personalizzare facilmente il contenuto in Adobe Campaign. Per accedervi, fate clic sul **[!UICONTROL Content]** blocco in una dashboard della pagina di destinazione.

L'editor dei contenuti è organizzato in tre diverse sezioni. Queste sezioni consentono di visualizzare e modificare il contenuto.

![](assets/des_lp_content_8.png)

1. La **palette** a sinistra dello schermo consente di modificare le opzioni generali collegate a un blocco selezionato. Le opzioni che è possibile modificare sono: colore di sfondo, bordo, allineamento del testo, condizione di visibilità, ecc. Consultate [Inserimento di un campo](../../designing/using/personalization.md#inserting-a-personalization-field)di personalizzazione.
1. La barra **delle** azioni contiene le opzioni generali per la pagina. Potete selezionare un modello e modificare la modalità di visualizzazione.
1. La zona **di** modifica principale consente di interagire direttamente con il contenuto tramite la barra degli strumenti contestuale: inserire un collegamento in un'immagine, modificare il font, eliminare un campo e così via.

La barra **delle** azioni contiene diversi pulsanti che consentono di interagire con il contenuto in fase di creazione.

![](assets/des_lp_content_9.png)

<table> 
 <thead> 
  <tr> 
   <th> Icona<br /> </th> 
   <th> Nome pulsante<br /> </th> 
   <th> Canale<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/download_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Modifica del contenuto</span><br /> </td> 
   <td> Pagina di destinazione ed e-mail<br /> </td> 
   <td> Consente di selezionare il contenuto out-of-the-box o importare il proprio contenuto HTML. Fare riferimento a <a href="../../designing/using/using-existing-content.md">Caricamento di un contenuto</a>esistente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Annulla</span><br /> </td> 
   <td> Tutto<br /> </td> 
   <td> Annulla l’ultima azione eseguita.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ripristina</span><br /> </td> 
   <td> Tutto<br /> </td> 
   <td> Ripristina l’ultima azione annullata.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostra blocchi</span><br /> </td> 
   <td> Pagina di destinazione ed e-mail<br /> </td> 
   <td> Consente di visualizzare le caselle intorno ai blocchi di contenuto (corrisponde al tag <strong>&lt;div&gt;</strong> HTML).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostra origine</span><br /> </td> 
   <td> Pagina di destinazione ed e-mail<br /> </td> 
   <td> Consente di visualizzare il codice sorgente HTML della pagina.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La **barra degli strumenti** è un elemento contestuale dell’interfaccia dell’editor che offre diverse funzionalità a seconda della zona selezionata. Contiene pulsanti di azione e pulsanti che consentono di modificare lo stile del testo. Le modifiche effettuate si applicano sempre alla zona selezionata. Dopo aver selezionato un blocco, è possibile eliminarlo o duplicarlo, ad esempio. Dopo aver selezionato il testo all’interno di un blocco, è possibile convertirlo in un collegamento o renderlo in grassetto.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Alcune funzioni della barra degli strumenti consentono di formattare il contenuto HTML. Tuttavia, se la pagina contiene un foglio di stile CSS, le **istruzioni** del foglio di stile potrebbero risultare **prioritarie** rispetto alle istruzioni specificate tramite la barra degli strumenti.

<table> 
 <thead> 
  <tr> 
   <th> Icona<br /> </th> 
   <th> Nome pulsante<br /> </th> 
   <th> Contesto<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/link_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento a un URL</span> esterno <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Consente di aggiungere un collegamento a un URL. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento a una pagina</span> di destinazione <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Consente di accedere a una pagina di destinazione di Adobe Campaign. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento</span> iscrizione <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Consente di inserire un collegamento di iscrizione al servizio. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unsubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento</span> di annullamento sottoscrizione <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Consente di inserire un collegamento per l’annullamento dell’iscrizione di un servizio. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Rimuovi collegamento</span><br /> </td> 
   <td> Collegamento<br /> </td> 
   <td> Consente di eliminare il collegamento, così come tutte le configurazioni ad esso collegate, dopo la conferma.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserire un campo</span> di personalizzazione <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di aggiungere al contenuto un campo dal database. Fare riferimento a <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Inserimento di un campo</a>di personalizzazione.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserire un blocco</span> di contenuto <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di aggiungere al contenuto un blocco di personalizzazione. Fare riferimento a <a href="../../designing/using/personalization.md#adding-a-content-block">Aggiunta di un blocco</a>di contenuto.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Abilita contenuto</span> dinamico <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di inserire contenuto dinamico nel contenuto. Fare riferimento a <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">Definizione del contenuto</a>dinamico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Disattivazione del contenuto</span> dinamico <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di eliminare il contenuto dinamico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ingrandisci font</span><br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Aumenta le dimensioni del testo selezionato (aggiunge <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ridurre il font</span><br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Riduce la dimensione del testo selezionato (aggiunge <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Grassetto</span><br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Aggiunge lo stile grassetto al testo selezionato (applica al testo i tag <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong> ).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Corsivo</span><br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Aggiunge lo stile corsivo al testo selezionato (applica al testo i <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Sottolineato</span><br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Sottolinea il testo selezionato (racchiude il testo selezionato con <strong>&lt;span style="text-decoration: underline;"&gt;</strong> tag).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambia colore</span> di sfondo <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di modificare il colore di sfondo del blocco selezionato (aggiunge style="background-color: rgba(170, 86, 255, 0.87).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambia colore</span> font <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di modificare il colore di tutto il testo nel blocco o solo del testo selezionato nel blocco (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Immagine</span><br /> </td> 
   <td> Blocco contenente un'immagine<br /> </td> 
   <td> Consente di inserire un'immagine da un file salvato localmente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Elimina</span><br /> </td> 
   <td> Qualsiasi blocco<br /> </td> 
   <td> Elimina il blocco e il relativo contenuto.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Duplica</span><br /> </td> 
   <td> Qualsiasi blocco<br /> </td> 
   <td> Duplica il blocco, inclusi eventuali stili ad esso collegati.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Gestione della struttura e dello stile della pagina di destinazione{#managing-landing-page-structure-and-style}

### Gestione dei blocchi nell’editor dei contenuti {#managing-blocks-in-the-content-editor}

I diversi elementi di contenuto HTML vengono visualizzati nella pagina di destinazione come blocchi, corrispondenti al tag **&lt;div&gt;** **&lt;/div&gt;** . Selezionare un blocco per interagire con esso. Sarà quindi circondata da una scatola blu.

![](assets/des_lp_content_1.png)

Se è selezionato un blocco, gli oggetti principali dell'elemento HTML corrispondente verranno visualizzati in una breadcrumb situata nella parte inferiore della zona di modifica.

Quando il mouse passa sopra uno degli elementi di breadcrumb, l'elemento interessato viene evidenziato. È quindi possibile spostarsi facilmente tra i diversi blocchi e selezionare esattamente l'elemento HTML da modificare.

![](assets/des_lp_content_2.png)

Utilizzare le opzioni della palette e della barra degli strumenti contestuale per modificare, eliminare o duplicare il blocco.

Per i blocchi contenenti testo, fare di nuovo clic nel blocco per attivare la modalità di modifica del testo. La cornice intorno al blocco diventa verde. Potete quindi selezionare o immettere del testo. Utilizzare le opzioni della palette e della barra degli strumenti contestuale per aggiungere un collegamento o modificare la formattazione del testo.

![](assets/des_lp_content_3.png)

Parametri definiti per un elemento in un blocco (collegamenti, campi di personalizzazione, blocchi di contenuto, ecc.) può essere modificato in qualsiasi momento dalla palette.

![](assets/des_lp_content_4.png)

### Aggiunta di un bordo e uno sfondo nell'editor contenuti {#adding-a-border-and-a-background-in-the-content-editor}

È inoltre possibile definire un colore **di** sfondo selezionando un colore dal grafico. Questo colore viene applicato al blocco selezionato.

![](assets/des_lp_content_5.png)

È possibile aggiungere un **bordo** al blocco selezionato.

![](assets/des_lp_content_6.png)

### Modifica dello stile del testo nell’editor del contenuto {#changing-the-text-style-in-the-content-editor}

Per modificare lo stile del testo, è necessario fare clic all'interno di un blocco di testo.

Per modificare l'allineamento del testo, selezionare una delle tre icone seguenti nella palette a sinistra:

![](assets/des_lp_content_7.png)

* **Allinea a sinistra**: allinea il testo a sinistra del blocco selezionato (aggiunge stile="text-align: left;").
* **Centro**: centra il testo nel blocco selezionato (aggiunge stile="text-align: center;").
* **Allinea a destra**: allinea il testo a destra del blocco selezionato (aggiunge stile="text-align: right;").

È inoltre possibile utilizzare la barra degli strumenti per modificare gli attributi del font: adattare le dimensioni del font, rendere il testo in grassetto o corsivo, sottolineare o modificare il colore del testo. Fare riferimento a [questa sezione](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### Inserimento di immagini in una pagina di destinazione {#inserting-images-in-a-landing-page}

1. Nel contenuto di una pagina di destinazione, selezionate un blocco contenente un’immagine.
1. Selezionare il **[!UICONTROL Insert]** pulsante.

   ![](assets/des_insert_images_lp_1.png)

1. Scegliere **[!UICONTROL Local image]** dalla barra degli strumenti contestuale.

   ![](assets/des_insert_images_lp_2.png)

1. Selezionare un file.

   ![](assets/des_insert_images_lp_3.png)

1. Regolate le proprietà dell’immagine in base alle esigenze.

   ![](assets/des_insert_images_lp_4.png)

## Definizione del contenuto dinamico in una pagina di destinazione{#defining-dynamic-content-in-a-landing-page}

Per definire il contenuto dinamico in una pagina di destinazione, selezionate un blocco utilizzando la breadcrumb o facendo clic direttamente su un elemento.

![](assets/dynamic_content_lp_1.png)

Alcuni blocchi, come le immagini, non possono essere selezionati direttamente. In questo caso, selezionare il blocco principale utilizzando la breadcrumb. Potete quindi modificare tutti gli elementi inclusi in questo elemento padre, incluse le immagini. La condizione verrà applicata a tutti gli elementi secondari all'interno del blocco principale.

La breadcrumb viene presentata nella sezione [Gestione dei blocchi](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style) .

I passaggi successivi per definire il contenuto dinamico in una pagina di destinazione sono simili ai passaggi da seguire per un messaggio e-mail. Vedere [questa sezione](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Se un elemento variante è evidenziato in rosso, significa che non è ancora stata definita un'espressione.

È possibile spostarsi tra i diversi contenuti dinamici di un blocco. Per eseguire questa operazione:

1. Selezionare il blocco.

   Le frecce sono visualizzate sui lati destro e sinistro dell’immagine.

1. Fate clic sulla freccia destra per sfogliare i contenuti dinamici disponibili.

   ![](assets/dynamic_content_lp_2.png)

   Le frecce su ciascun lato si attenuano a seconda che sia stato raggiunto l'ultimo o il primo contenuto dinamico disponibile.

   ![](assets/dynamic_content_lp_3.png)

1. Per eliminare tutte le condizioni applicate a un blocco, selezionarlo e fare clic sull' **[!UICONTROL Disable dynamic content]** icona.
1. Selezionate il contenuto dinamico da mantenere.

   ![](assets/dynamic_content_lp_5.png)

Nella palette:

* I contenuti con un'espressione immessa non sono più evidenziati in rosso, ma sono visualizzati in grigio.
* Il contenuto attualmente selezionato viene visualizzato in blu.

![](assets/dynamic_content_lp_4.png)
