---
title: Interfaccia dell'editor del contenuto della pagina di destinazione
seo-title: Interfaccia dell'editor del contenuto della pagina di destinazione
description: Interfaccia dell'editor del contenuto della pagina di destinazione
seo-description: Scoprite come utilizzare le diverse sezioni dell'editor, come la barra delle azioni, per modificare il contenuto della pagina di destinazione.
page-status-flag: mai attivato
uuid: 53729a68-eed2-4c5d-bc14-02c80e897c44
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: progettazione
content-type: reference
topic-tags: editing-landing-page-content
discoiquuid: 08e2bbda-e409-467f-b462-d74256dc6ebc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68d96b23f34f505c0a47a74a5e33bc3530fc4d72

---


# Interfaccia dell'editor del contenuto della pagina di destinazione{#landing-page-content-editor-interface}

L'editor del contenuto della pagina di destinazione consente di definire, modificare e personalizzare facilmente il contenuto in Adobe Campaign. Per accedervi, fate clic sul **[!UICONTROL Content]** blocco in una dashboard della pagina di destinazione.

L'editor dei contenuti è organizzato in tre diverse sezioni. Queste sezioni consentono di visualizzare e modificare il contenuto.

![](assets/des_lp_content_8.png)

1. La **palette** a sinistra dello schermo consente di modificare le opzioni generali collegate a un blocco selezionato. Le opzioni che è possibile modificare sono: colore di sfondo, bordo, allineamento del testo, condizione di visibilità, ecc. Consultate [Inserimento di un campo](../../designing/using/personalization.md#inserting-a-personalization-field)di personalizzazione.
1. La barra **delle** azioni contiene le opzioni generali per la pagina. Potete selezionare un modello e modificare la modalità di visualizzazione. Consultate Barra delle azioni dell’editor [pagina di destinazione](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-action-bar).
1. La zona **di** modifica principale consente di interagire direttamente con il contenuto tramite la barra degli strumenti contestuale: inserire un collegamento in un'immagine, modificare il font, eliminare un campo e così via. Consultate Barra degli strumenti [dell’editor della pagina di](../../channels/using/landing-page-content-editor-interface.md#landing-page-editor-toolbar)destinazione.

## Barra delle azioni dell'editor pagina di destinazione {#landing-page-editor-action-bar}

La barra delle azioni contiene diversi pulsanti che consentono di interagire con il contenuto creato.

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

## Barra degli strumenti dell’editor pagina di destinazione {#landing-page-editor-toolbar}

La barra degli strumenti è un elemento **** contestuale dell'interfaccia dell'editor che offre diverse funzionalità a seconda della zona selezionata. Contiene pulsanti di azione e pulsanti che consentono di modificare lo stile del testo. Le modifiche effettuate si applicano sempre alla zona selezionata. Dopo aver selezionato un blocco, è possibile eliminarlo o duplicarlo, ad esempio. Dopo aver selezionato il testo all’interno di un blocco, è possibile convertirlo in un collegamento o renderlo in grassetto.

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
   <td> Consente di aggiungere un blocco di personalizzazione al contenuto. Fare riferimento a <a href="../../designing/using/personalization.md#adding-a-content-block">Aggiunta di un blocco</a>di contenuto.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Abilita contenuto</span> dinamico <br /> </td> 
   <td> Elemento testo<br /> </td> 
   <td> Consente di inserire contenuto dinamico nel contenuto. Fare riferimento a <a href="../../channels/using/defining-dynamic-content-in-a-landing-page.md">Definizione del contenuto</a>dinamico.<br /> </td> 
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

