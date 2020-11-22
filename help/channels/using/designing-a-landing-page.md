---
solution: Campaign Standard
product: campaign
title: Progettazione di una pagina di destinazione
description: Scopri in che modo progettare il contenuto di una pagina di destinazione.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 100%

---


# Progettazione di una pagina di destinazione{#designing-a-landing-page}

## Informazioni sulla progettazione del contenuto di una pagina di destinazione {#about-content-design}

Le pagine di destinazione vengono create come qualsiasi altra [attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities).

Durante la progettazione di una pagina di destinazione, dovrai definire il contenuto della pagina stessa, della pagina di conferma e della pagina di errore. Per visualizzare e configurare ciascuna di queste pagine, utilizza il commutatore posto sotto la barra delle azioni.

Il contenuto delle pagine di destinazione è progettato tramite l’editor di contenuti di Campaign.

>[!NOTE]
>
>Se la tua istanza è stata installata prima del rilascio di Adobe Campaign Standard 19.0, puoi comunque accedere all’editor dei contenuti delle e-mail legacy. In generale, per quanto riguarda le pagine di destinazione, l’interfaccia, i principi di utilizzo e di configurazione sono per lo più i medesimi illustrati di seguito. Tuttavia, non tutte le funzioni potrebbero essere disponibili o presenti nell’editor dei contenuti e-mail legacy, che è diventato obsoleto a partire dalla versione 19.0. Per modificare rapidamente il contenuto delle e-mail mediante un’interfaccia a trascinamento dotata di funzioni estese, puoi utilizzare [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

Questa pagina descrive le specificità dell’editor dei contenuti delle pagine di destinazione. Per ulteriori informazioni sulle azioni comuni a una o più attività di marketing, consulta le sezioni seguenti della guida **Progettazione di contenuti delle e-mail**:

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block).
* [Inserimento di un collegamento](../../designing/using/links.md#inserting-a-link).
* [Inserimento di immagini](../../designing/using/images.md).
* [Best practice generali per la progettazione di contenuti](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

>[!NOTE]
>Se la pagina di destinazione è già predefinita in formato HTML, puoi importarla direttamente utilizzando il pulsante **[!UICONTROL Change content]**.
>
>Prima di importare una pagina HTML all’interno di Adobe Campaign, accertati che si apra e venga visualizzata correttamente nei vari browser. Se la pagina HTML contiene script di JavaScript, questi devono essere eseguiti senza errori all’esterno dell’editor. In generale, evita di utilizzare gli script nel contenuto dei messaggi per avere la certezza che siano elaborati correttamente dai client di posta elettronica.

## Interfaccia dell’editor dei contenuti delle pagine di destinazione{#landing-page-content-editor-interface}

L’editor dei contenuti delle pagine di destinazione consente di definire, modificare e personalizzare facilmente il contenuto all’interno di Adobe Campaign. Per accedervi, fai clic sul blocco **[!UICONTROL Content]** del dashboard di una pagina di destinazione.

L’editor dei contenuti è organizzato in tre sezioni distinte. Tali sezioni ti consentono di visualizzare e modificare il contenuto.

![](assets/des_lp_content_8.png)

1. La **palette** a sinistra dello schermo ti consente di modificare le opzioni generali collegate a un blocco selezionato. Le opzioni che è possibile modificare sono le seguenti: colore di sfondo, bordo, allineamento del testo, condizione di visibilità e così via. Consulta [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field).
1. La **barra delle azioni** contiene le opzioni generali della pagina. Puoi selezionare un modello e modificare la modalità di visualizzazione.
1. La **zona di modifica** principale ti consente di interagire direttamente con il contenuto tramite la barra degli strumenti contestuale: puoi inserire un collegamento in un’immagine, modificare il font, eliminare un campo e così via.

La **barra delle azioni** contiene vari pulsanti che ti permettono di interagire con il contenuto in fase di creazione.

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
   <td> <span class="uicontrol">Modifica il contenuto</span> <br /> </td> 
   <td> Pagina di destinazione ed e-mail<br /> </td> 
   <td> Ti consente di selezionare il contenuto predefinito o importare il tuo contenuto HTML personale. Fai riferimento a <a href="../../designing/using/using-existing-content.md">Caricamento di un contenuto esistente</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Annulla</span> <br /> </td> 
   <td> Tutto<br /> </td> 
   <td> Annulla l’ultima azione eseguita.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ripeti</span> <br /> </td> 
   <td> Tutto<br /> </td> 
   <td> Ripete l’ultima azione annullata.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/display_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostra blocchi</span> <br /> </td> 
   <td> Pagina di destinazione ed e-mail<br /> </td> 
   <td> Ti consente di visualizzare le caselle intorno ai blocchi di contenuto (corrisponde al tag HTML <strong>&lt;div&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/code_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Mostra sorgente</span> <br /> </td> 
   <td> Pagina di destinazione ed e-mail<br /> </td> 
   <td> Ti permette di visualizzare il codice sorgente HTML della pagina.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La **barra degli strumenti** è un elemento contestuale dell’interfaccia dell’editor che offre varie funzionalità a seconda della zona selezionata. Contiene i pulsanti di azione e i pulsanti che ti consentono di modificare lo stile del testo. Le modifiche effettuate si applicano sempre alla zona selezionata. Dopo aver selezionato un blocco, puoi per esempio eliminarlo o duplicarlo. Dopo aver selezionato il testo all’interno di un blocco, puoi convertirlo in un collegamento o renderlo in grassetto.

![](assets/delivery_content_17.png)

>[!CAUTION]
>
>Alcune funzioni della barra degli strumenti ti consentono di formattare il contenuto HTML. Tuttavia, se la pagina contiene un foglio di stile CSS, le **istruzioni** del foglio di stile potrebbero avere la **priorità** rispetto a quelle specificate tramite la barra degli strumenti.

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
   <td> <span class="uicontrol">Collegamento a un URL esterno</span> <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Consente di aggiungere un collegamento a un URL. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkpage_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento a una pagina di destinazione</span> <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Consente di accedere a una pagina di destinazione di Adobe Campaign. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_Subscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento di abbonamento</span> <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Permette di inserire un collegamento di abbonamento a un servizio. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/link_unSubscribe_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Collegamento di annullamento dell’abbonamento</span> <br /> </td> 
   <td> Qualsiasi elemento<br /> </td> 
   <td> Permette di inserire un collegamento di annullamento dell’abbonamento a un servizio. I dettagli sulla configurazione di un collegamento sono riportati nella sezione <a href="../../designing/using/links.md#inserting-a-link">Inserimento di un collegamento</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/linkoff_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Rimuovi collegamento</span> <br /> </td> 
   <td> Collegamento<br /> </td> 
   <td> Dopo la conferma, potrai eliminare il collegamento, oltre a tutte le configurazioni correlate.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserisci un campo di personalizzazione</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Ti consente di aggiungere al contenuto un campo del database. Fai riferimento a <a href="../../designing/using/personalization.md#inserting-a-personalization-field">Inserimento di un campo di personalizzazione</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserisci un blocco di contenuto</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Ti consente di aggiungere al contenuto un blocco di personalizzazione. Fai riferimento a <a href="../../designing/using/personalization.md#adding-a-content-block">Aggiunta di un blocco di contenuto</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Abilita il contenuto dinamico</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Consente di inserire contenuto dinamico all’interno del contenuto. Fai riferimento a <a href="../../channels/using/designing-a-landing-page.md#defining-dynamic-content-in-a-landing-page">Definizione del contenuto dinamico</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Disabilita il contenuto dinamico</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Permette di eliminare il contenuto dinamico.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/increase_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Ingrandisci font</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Aumenta le dimensioni del testo selezionato (aggiunge <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/decrease_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Riduci font</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Riduce le dimensioni del testo selezionato (aggiunge <strong>&lt;span style="font-size:"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textbold_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Grassetto</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Aggiunge lo stile grassetto al testo selezionato (applica al testo i tag <strong>&lt;strong&gt;</strong><strong>&lt;/strong&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textitalic_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Corsivo</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Aggiunge lo stile corsivo al testo selezionato (applica al testo i tag <strong>&lt;em&gt;</strong><strong>&lt;/em&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textunderline_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Sottolineato</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Sottolinea il testo selezionato (applica al testo selezionato il tag <strong>&lt;span style="text-decoration: underline;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/colorselector_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambia colore di sfondo</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Consente di modificare il colore di sfondo del blocco selezionato (aggiunge style="background-color: rgba(170, 86, 255, 0.87)).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/textcolor_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Cambia colore del font</span> <br /> </td> 
   <td> Elemento di testo<br /> </td> 
   <td> Consente di modificare il colore di tutto il testo nel blocco o solo del testo selezionato al suo interno (<strong>&lt;span style="color: #56ff56;"&gt;</strong>).<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/image_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Immagine</span> <br /> </td> 
   <td> Blocco contenente un’immagine<br /> </td> 
   <td> Permette di inserire un’immagine da un file salvato localmente.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/delete_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Elimina</span> <br /> </td> 
   <td> Qualsiasi blocco<br /> </td> 
   <td> Elimina il blocco e il relativo contenuto.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/duplicate_fontsize_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Duplica</span> <br /> </td> 
   <td> Qualsiasi blocco<br /> </td> 
   <td> Duplica il blocco, compresi eventuali stili ad esso collegati.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Gestione della struttura e dello stile della pagina di destinazione{#managing-landing-page-structure-and-style}

### Gestione dei blocchi nell’editor dei contenuti {#managing-blocks-in-the-content-editor}

I diversi elementi di contenuto HTML vengono visualizzati nella pagina di destinazione sotto forma di blocchi, corrispondenti al tag **&lt;div>** **&lt;/div>**. Seleziona un blocco per interagire con esso, che sarà poi circondato da una casella blu.

![](assets/des_lp_content_1.png)

Se è stato selezionato un blocco, gli oggetti principali dell’elemento HTML corrispondente verranno visualizzati in una breadcrumb situata nella parte inferiore dell’area di modifica.

Al passaggio del mouse passa sopra uno degli elementi della breadcrumb, viene evidenziato l’elemento interessato. Puoi quindi spostarti facilmente tra i diversi blocchi e selezionare con precisione l’elemento HTML che desideri modificare.

![](assets/des_lp_content_2.png)

Per modificare, eliminare o duplicare il blocco, utilizza le opzioni della palette e della barra degli strumenti contestuale.

Per i blocchi contenenti testo, fai di nuovo clic sul blocco per attivare la modalità di modifica del testo. La cornice intorno al blocco diventa verde. A quel punto, potrai selezionare o immettere il testo. Per aggiungere un collegamento o modificare la formattazione del testo, utilizza le opzioni della palette e della barra degli strumenti contestuale.

![](assets/des_lp_content_3.png)

I parametri definiti per un elemento in un blocco, quali collegamenti, campi di personalizzazione, blocchi di contenuto e così via, possono essere modificati dalla palette in qualsiasi momento.

![](assets/des_lp_content_4.png)

### Aggiunta di un bordo e uno sfondo nell’editor dei contenuti {#adding-a-border-and-a-background-in-the-content-editor}

È inoltre possibile definire un **colore di sfondo** selezionandone uno dal grafico. Questo colore viene quindi applicato al blocco selezionato.

![](assets/des_lp_content_5.png)

Puoi aggiungere anche un **bordo** al blocco.

![](assets/des_lp_content_6.png)

### Modifica dello stile del testo nell’editor dei contenuti {#changing-the-text-style-in-the-content-editor}

Per modificare lo stile del testo, è necessario fare clic all’interno di un blocco di testo.

Per cambiare l’allineamento del testo, seleziona una delle tre icone seguenti nella palette a sinistra:

![](assets/des_lp_content_7.png)

* **Allinea a sinistra**: allinea il testo a sinistra del blocco selezionato (aggiunge style=&quot;text-align: left;&quot;).
* **Centra**: centra il testo nel blocco selezionato (aggiunge style=&quot;text-align: center;&quot;).
* **Allinea a destra**: allinea il testo a destra del blocco selezionato (aggiunge style=&quot;text-align: right;&quot;).

Puoi inoltre utilizzare la barra degli strumenti per modificare gli attributi del font: adattarne le dimensioni, rendere il testo in grassetto o corsivo, sottolineare o modificare il colore del testo. Fai riferimento a [questa sezione](../../channels/using/designing-a-landing-page.md#landing-page-content-editor-interface).

### Inserimento di immagini in una pagina di destinazione {#inserting-images-in-a-landing-page}

1. All’interno del contenuto di una pagina di destinazione, seleziona un blocco contenente un’immagine.
1. Fai clic sul pulsante **[!UICONTROL Insert]**.

   ![](assets/des_insert_images_lp_1.png)

1. Dalla barra degli strumenti contestuale, seleziona **[!UICONTROL Local image]** .

   ![](assets/des_insert_images_lp_2.png)

1. Scegli un file.

   ![](assets/des_insert_images_lp_3.png)

1. Regola le proprietà dell’immagine in base alle esigenze.

   ![](assets/des_insert_images_lp_4.png)

## Definizione del contenuto dinamico in una pagina di destinazione{#defining-dynamic-content-in-a-landing-page}

Per definire il contenuto dinamico di una pagina di destinazione, seleziona un blocco utilizzando la breadcrumb o facendo clic direttamente su un elemento.

![](assets/dynamic_content_lp_1.png)

Alcuni blocchi non possono essere selezionati direttamente, ad esempio le immagini. In tal caso, seleziona il blocco principale tramite la breadcrumb. Puoi quindi modificare tutti gli elementi inclusi in questo elemento principale, incluse le immagini. La condizione verrà applicata a tutti gli elementi secondari all’interno del blocco principale.

La breadcrumb viene presentata nella sezione [Gestione dei blocchi](../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style).

I passaggi successivi per la definizione del contenuto dinamico in una pagina di destinazione sono simili a quelli per la creazione di un’e-mail. Vedi [questa sezione](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Se un elemento variante è evidenziato in rosso, ciò significa che non è ancora stata definita un’espressione.

Puoi spostarti tra i diversi contenuti dinamici di un blocco. Per eseguire questa operazione:

1. Seleziona il blocco.

   Le frecce sono visualizzate sul lato destro e sinistro dell’immagine.

1. Per sfogliare i contenuti dinamici disponibili, fai clic sulla freccia destra.

   ![](assets/dynamic_content_lp_2.png)

   In base al raggiungimento dell’ultimo o del primo contenuto dinamico disponibile, le frecce su ciascun lato si attenuano.

   ![](assets/dynamic_content_lp_3.png)

1. Per eliminare tutte le condizioni applicate a un blocco, selezionalo e fai clic sull’icona **[!UICONTROL Disable dynamic content]**.
1. Seleziona il contenuto dinamico che desideri mantenere.

   ![](assets/dynamic_content_lp_5.png)

Nella palette:

* I contenuti con un’espressione inserita non sono più evidenziati in rosso, ma sono visualizzati in grigio.
* Il contenuto attualmente selezionato viene visualizzato in blu.

![](assets/dynamic_content_lp_4.png)
