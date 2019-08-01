---
title: Informazioni sulla progettazione di contenuto e-mail
seo-title: Informazioni sulla progettazione di contenuto e-mail
description: Informazioni sulla progettazione di contenuto e-mail
seo-description: Scoprite come utilizzare Designer Designer per progettare contenuti per le e-mail.
page-status-flag: never-activated
uuid: 571 ffc 01-6 e 41-4501-9094-2 f 812 b 041 a 10
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: editing-email-content
discoiquuid: 39 b 86 fda -7766-4 e 5 f-ab 48-bcn 536 ab 66 b 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f85995fc5a331b57e42a58d979940751dbe7ce97

---


# About email content design{#about-email-content-design}

Utilizzate l'interfaccia di trascinamento e rilascio di Designer per creare e modificare il contenuto delle e-mail in Adobe Campaign.

Questa sezione descrive le specificità di E-mail Designer:

* [Informazioni su Designer Designer](../../designing/using/about-email-content-design.md#about-the-email-designer)
* [Definizione della struttura e-mail](../../designing/using/defining-the-email-structure.md)
* [Modifica degli stili e-mail](../../designing/using/editing-email-styles.md)

Per ulteriori informazioni sulle azioni comuni a una o più attività di marketing, consultare le sezioni seguenti:

* For more on personalizing an email content, see [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) and [Adding a content block](../../designing/using/adding-a-content-block.md).
* For more on importing another email content, see [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).
* For more on defining dynamic content in an email, see [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md).
* For more on inserting links in an email, see [Inserting a link](../../designing/using/inserting-a-link.md).
* For more on inserting images in an email, see [Inserting images](../../designing/using/inserting-images.md).

Also check the [general best practices for content design](../../designing/using/content-design-best-practices.md).

## About the Email Designer {#about-the-email-designer}

Designer consente di creare e-mail e modelli per contenuto e-mail. È compatibile con indirizzi e-mail semplici, e-mail transazionali, e-mail di test A/B, e-mail in più lingue e e-mail ricorrenti.

To get started with the Email Designer, watch this [set of videos](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#GettingStarted) that explain the general functionality of the Email Designer and how to design an email from scratch or using templates.

### Email Designer home page {#email-designer-home-page}

[Quando si crea un'e-mail](../../channels/using/creating-an-email.md), la pagina **[!UICONTROL Email Designer]** principale viene visualizzata automaticamente quando si seleziona il contenuto dell'e-mail.

![](assets/email_designer_home_page.png)

**[!UICONTROL Properties]** La scheda consente di modificare i dettagli e-mail quali l'etichetta, l'indirizzo e il nome del mittente o l'oggetto dell'e-mail. Potete anche accedere a questa scheda facendo clic sull'etichetta e-mail nella parte superiore dello schermo.

![](assets/email_designer_home_properties.png)

**[!UICONTROL Templates]** La scheda consente di scegliere tra i contenuti HTML forniti e quelli già creati per iniziare rapidamente a progettare l'e-mail. See [Content templates](../../start/using/about-templates.md#content-templates).

![](assets/email_designer_home_templates.png)

The **[!UICONTROL Learn & support]** tab gives you easy access to the related documentation and tutorials.

![](assets/email_designer_home_support.png)

Se non si seleziona un modello, la home page di Designer di e-mail consente anche di scegliere la modalità di avvio del contenuto:

* Click the **[!UICONTROL Create]** button to start a new content from scratch. See [Designing an email content from scratch](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
* Click the **[!UICONTROL Upload]** button to upload a file from your computer. See [Importing content from a file](../../designing/using/importing-content-from-a-file.md).
* Click the **[!UICONTROL Import from URL]** button to retrieve existing content form a URL. See [Importing content from a URL](../../designing/using/importing-content-from-a-url.md).

### Email Designer interface {#email-designer-interface}

Designer Designer offre numerose opzioni che consentono di creare, modificare e personalizzare ogni aspetto del contenuto.

L'interfaccia è composta da diverse aree che offrono diverse funzionalità:

![](assets/email_designer_overview.png)

From the elements available in the **Palette** (1), drag and drop structure components and content fragments into the main **Workspace** (2). Select a component or element in the **Workspace** (2) and customize its main styling and display characteristics from the **Settings** pane (3).

Access more general options and settings from the main **Toolbar** (4).

>[!NOTE]
>
>The **Settings** pane can move to the left according to your screen resolution and display.

![](assets/email_designer_toolbar.png)

The **Contextual toolbar** of the editor interface offers various functionalities depending on the zone selected. Contiene pulsanti di azione e pulsanti che consentono di modificare lo stile del testo. Le modifiche apportate vengono applicate sempre alla zona selezionata.

### General recommendations for using the Email Designer {#general-recommendations-for-using-the-email-designer}

Per utilizzare correttamente Designer Designer e creare le migliori e-mail il più semplicemente possibile, è consigliabile applicare i seguenti principi:

* Utilizzate lo stile in linea anziché un CSS separato e CSS nella sezione &lt; head &gt; dell'HTML. L'utilizzo di stili in linea consente di ottimizzare il salvataggio e il riutilizzo dei frammenti di contenuto.

   See [Adding inline styling attributes](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes).

* Regola facilmente il tuo marchio creando e riutilizzando frammenti di contenuto per mantenere coerenza nelle campagne di marketing.

   See [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).

Also check the [general best practices for content design](../../designing/using/content-design-best-practices.md).

### Email Designer compatibility mode {#email-designer-compatibility-mode}

Quando caricate un contenuto, esso deve contenere tag specifici per essere completamente conforme e modificabile con l'editor WYSIWYG di Email Designer.

Se tutto o parte dell'HTML caricato non è conforme ai tag previsti, il contenuto viene caricato in modalità di compatibilità, che limita le possibilità di edizione tramite l'interfaccia utente.

Quando un contenuto viene caricato in modalità di compatibilità, potete comunque eseguire le seguenti modifiche tramite l'interfaccia (le azioni non disponibili sono nascoste):

* Modifica del testo o modifica di un'immagine
* Inserimento di collegamenti e campi di personalizzazione
* Modifica alcune opzioni di stile nel blocco HTML selezionato
* Definizione di contenuto condizionale

![](assets/email_designer_compatibility.png)

Altre modifiche, ad esempio l'aggiunta di nuove sezioni al messaggio e-mail o lo stile avanzato, devono essere eseguite direttamente nel codice sorgente del messaggio e-mail tramite la modalità HTML.

For more on converting an existing email into an Email Designer-compatible email, see [this section](../../designing/using/about-email-content-design.md#designing-an-email-using-existing-contents).

### Email Designer limitations {#email-designer-limitations}

* Non è possibile utilizzare i campi di personalizzazione in un frammento. For more on fragments, see [this section](../../designing/using/defining-the-email-structure.md#about-fragments).
* Non è possibile salvare direttamente come frammento alcuni contenuti di un'e-mail che si sta modificando in Email Designer. È necessario copiare e incollare il codice HTML corrispondente a tale contenuto in un nuovo frammento. For more on this, see [Saving content as a fragment](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).
* Quando si modificano gli stili, sono disponibili solo i font Web ufficialmente supportati dalla maggior parte dei client e-mail.
* Gli stili non possono essere salvati come tema per riuso futuro. Tuttavia, lo stile CSS può essere salvato in un modello di contenuto o in un messaggio e-mail. For more on styles, see [this section](../../designing/using/editing-email-styles.md).

### Email Designer updates {#email-designer-updates}

Il miglioramento continuo di Designer Designer è migliorato. Se è stato creato un contenuto e-mail da zero, da un modello out-of-the-box o se avete creato dei frammenti, al successivo apertura del contenuto potrebbe essere visualizzato il seguente messaggio di aggiornamento:

![](assets/email_designer_fragment_patch_message.png)

Adobe consiglia di aggiornare i contenuti alla versione più recente per evitare problemi quali problemi di collisione CSS. Click **[!UICONTROL Update now]**.

Se si verifica un errore durante l'aggiornamento del contenuto, controllate il codice HTML e correggetelo prima di eseguire nuovamente questo aggiornamento.

Per i frammenti, tenete presente quanto segue:

* Se si desidera aggiungere un frammento a una nuova e-mail o a un modello e se si riceve questo messaggio, è necessario aggiornare prima il frammento.

* Se si dispone di più frammenti, è necessario aggiornare ciascun frammento che si desidera utilizzare in un contenuto e-mail.

* Per evitare l'impatto sui messaggi e-mail correnti, poiché alcuni possono essere all'interno della fase di preparazione o in una campagna specifica in cui non si desidera apportare modifiche, è possibile non aggiornare alcuni frammenti.

* È comunque possibile inviare e-mail in cui un frammento non aggiornato è già utilizzato, ma tale frammento non è modificabile.

## Designing an email content from scratch {#designing-an-email-content-from-scratch}

Di seguito sono descritti i passaggi principali per creare e progettare da zero un contenuto e-mail utilizzando l'e-mail Designer:

1. Create un'e-mail e apritene il contenuto.
1. Aggiungete componenti struttura per formare l'e-mail. See [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inserire componenti di contenuto e frammenti nei componenti struttura. See [Adding fragments and content components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).
1. Aggiungete immagini e modificate il testo dell'e-mail. See [Inserting images](../../designing/using/inserting-images.md).
1. Personalizza l'e-mail aggiungendo campi personalizzati, collegamenti e così via. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md), [Inserting a link](../../designing/using/inserting-a-link.md) and [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md).
1. Definire l'oggetto dell'e-mail. See [Personalizing the subject line of an email](../../designing/using/personalizing-the-subject-line-of-an-email.md).
1. Visualizzate l'anteprima dell'e-mail.
1. Salvate i contenuti e continuate con il messaggio, dopo aver definito un pubblico e pianificato l'invio.

You can also check out this [introduction video](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=ita).

>[!NOTE]
>
>Per evitare di progettare contenuti e-mail da zero, potete utilizzare i modelli di contenuto forniti. For more on this, see [Content templates](../../start/using/about-templates.md#content-templates).

**Argomenti correlati**:

* [Creazione di un'e-mail](../../channels/using/creating-an-email.md)
* [Selezione di un contenuto esistente](../../designing/using/selecting-an-existing-content.md)
* [Selezione di un'audience in un messaggio](../../audiences/using/selecting-an-audience-in-a-message.md)
* [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Rendering e-mail](../../sending/using/email-rendering.md)

## Designing an email using existing contents {#designing-an-email-using-existing-contents}

In questa sezione viene illustrato come convertire un messaggio e-mail esistente in un messaggio e-mail compatibile con Designer.

By default, if you just upload any HTML (see [Importing content from a file](../../designing/using/importing-content-from-a-file.md)), the content is loaded in '[compatibility mode](../../designing/using/about-email-content-design.md#email-designer-compatibility-mode)', which limits the edition possibilities through the UI (only in-place edition, no drag-and-drop).

Tuttavia, se si desidera creare un framework di modelli modulari e frammenti che possono essere combinati per riutilizzarli in più e-mail, è consigliabile convertire l'HTML e-mail in un modello di Designer e-mail.

Quando si progettano contenuti con E-mail Designer, sono disponibili tre opzioni:

* [Creazione di contenuto da un modello out-of-the-box](../../designing/using/about-email-content-design.md#building-content-from-an-out-of-the-box-template)
* [Uso di frammenti e componenti](../../designing/using/about-email-content-design.md#using-fragments-and-components), avvio da zero e creazione di una struttura HTML
* [Conversione di un'e-mail di contenuto](../../designing/using/about-email-content-design.md#converting-an-html-content) HTML in un contenuto modulare di Designer

### Building content from an out-of-the-box template {#building-content-from-an-out-of-the-box-template}

1. Create un'e-mail e apritene il contenuto. For more on this, see [Creating an email](../../channels/using/creating-an-email.md).
1. Click the home icon to access the **[!UICONTROL Email Designer]** home page.
1. Click the **[!UICONTROL Templates]** tab.
1. Scegliete un modello HTML out-of-the-box.

   I diversi modelli presentano diverse combinazioni di diversi tipi di elementi. Ad esempio, i modelli «Sfumatura» hanno margini mentre i modelli «Astro» non sono disponibili. For more on this, see [Content templates](../../start/using/about-templates.md#content-templates).

1. È possibile combinare questi elementi per creare diverse varianti di e-mail. For example, you can duplicate an email section by selecting a structure component and clicking **[!UICONTROL Duplicate]** from the contextual toolbar.
1. Potete spostare gli elementi intorno utilizzando la freccia blu a sinistra per trascinare un componente struttura sotto o sopra un altro. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Potete anche spostare i componenti per modificare l'organizzazione di ogni elemento struttura. For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).
1. Modificate il contenuto di ogni elemento in base alle vostre esigenze: immagini, testo, collegamenti.
1. Adattare le opzioni di stile al contenuto, se necessario. For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).

### Using fragments and components {#using-fragments-and-components}

Per creare semplicemente un contenuto esterno conforme a Designer Designer, Adobe consiglia di creare un messaggio da zero e copiare il contenuto dell'e-mail esistente in frammenti e componenti.

When you have a content that cannot be recreated, you can copy-paste the HTML code from the original email using the **[!UICONTROL Html]** content component. Prima di continuare, accertatevi di disporre di HTML.

Di seguito viene presentato un esempio completo.

>[!NOTE]
>
>Il nuovo contenuto non sarà la copia esatta dell'e-mail originale, ma i passaggi indicati di seguito guideranno la creazione di un messaggio che sarà il più vicino possibile.

Supponiamo di voler utilizzare una newsletter esistente creata all'esterno di Adobe Campaign.

Vuoi avere la stessa intestazione e il medesimo piè di pagina in tutte le e-mail che invierai con Adobe Campaign. Il corpo dell'e-mail cambia a seconda del contenuto che si intende visualizzare in ogni newsletter.

**Prerequisiti**

1. Nell'e-mail originale, individua le sezioni riutilizzabili dalle sezioni che saranno univoche per ogni e-mail inviata.
1. Salvate tutte le immagini e le risorse che desiderate usare.
1. Se avete familiarità con HTML, suddivide il contenuto HTML originale in parti diverse.

**Creazione di frammenti per il contenuto riutilizzabile**

Utilizzando Designer Designer, creare un frammento per ogni sezione riutilizzabile. In questo esempio verranno creati due frammenti: uno per l'intestazione e uno per il piè di pagina. Potete quindi copiare le parti pertinenti dal contenuto esistente in questi frammenti.

A tal fine, attenetevi alla procedura seguente:

1. In Adobe Campaign, go to **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** and create a fragment for your header. For more on this, see [Creating a content fragment](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).
1. Aggiungere tutti i componenti struttura necessari al frammento.

   ![](assets/des_loading_compatible_fragment_1.png)

1. Inserire componenti di immagine e testo nella struttura.

   ![](assets/des_loading_compatible_fragment_2.png)

1. Caricate l'immagine corrispondente, inserite il testo e regolate le impostazioni.

   For more on managing style settings and inline attributes, see [Editing email styles](../../designing/using/editing-email-styles.md).

   ![](assets/des_loading_compatible_fragment_3.png)

1. Salvare il frammento.
1. Procedere in modo simile per creare il piè di pagina e salvarlo.

   ![](assets/des_loading_compatible_fragment_4.png)

   If you are familiar with HTML, you can copy-paste the HTML code from the original footer using the **[!UICONTROL Html]** content component. For more on this, see [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

   ![](assets/des_loading_compatible_fragment_9.png)

I frammenti sono ora pronti per essere utilizzati in un modello.

**Inserimento di frammenti e componenti nel modello**

È ora possibile creare un modello e-mail con E-mail Designer. Utilizzare i componenti di contenuto per riflettere le diverse sezioni dell'e-mail e modificare le impostazioni per avvicinarle il più possibile alla newsletter originale. Infine, inserire i frammenti appena creati.

1. Utilizzando Designer Designer, creare un modello. For more on this, see [Content templates](../../start/using/about-templates.md#content-templates).
1. Inserire diversi componenti struttura nel modello, corrispondente all'intestazione, al piè di pagina e al corpo dell'e-mail. For more on adding structure components, see [Editing the email structure with the Email Designer](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Inserite tutti i componenti di contenuto necessari per creare il corpo della newsletter. Questo sarà il contenuto modificabile dell'e-mail che verrà aggiornato ogni mese.

   ![](assets/des_loading_compatible_fragment_5.png)

   If you are familiar with HTML code, Adobe recommends leveraging **[!UICONTROL Html]** components where you can copy-paste the more complex elements of the original email. Use other components such as **[!UICONTROL Button]**, **[!UICONTROL Image]** or **[!UICONTROL Text]** for the rest of the content. For more on this, see [About content components](../../designing/using/defining-the-email-structure.md#about-content-components).

   >[!NOTE]
   >
   >Using the **[!UICONTROL Html]** component results in creating components that are editable with limited options. Prima di selezionare questo componente, assicuratevi di saper gestire il codice HTML.

1. Regolate i componenti di contenuto in modo che corrispondano al numero di messaggi e-mail originali.

   ![](assets/des_loading_compatible_fragment_6.png)

   For more on managing style settings and inline attributes, see [Editing email styles](../../designing/using/editing-email-styles.md).

1. Inserire i due frammenti (intestazione e piè di pagina) creati in precedenza nei componenti struttura desiderati.

   ![](assets/des_loading_compatible_fragment_10.png)

1. Salvate il modello.

È ora possibile gestire completamente questo modello all'interno di E-mail Designer per creare e aggiornare la newsletter inviata ogni mese ai destinatari.

Per utilizzarlo, create un'e-mail e selezionate il modello di contenuto appena creato.

**Argomento** correlato:

* [Creazione di un'e-mail](../../channels/using/creating-an-email.md)
* [Video introduttivo su Email Designer](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=ita)
* [Progettazione di un contenuto e-mail da zero](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch)

### Converting an HTML content {#converting-an-html-content}

Questo caso d'uso consente di convertire rapidamente un'e-mail HTML in componenti e-mail di Designer.

>[!CAUTION]
>
>Questa sezione è destinata agli utenti esperti che hanno familiarità con il codice HTML.

>[!NOTE]
>
>Come la modalità di compatibilità, un componente HTML è modificabile con opzioni limitate: è possibile eseguire solo la versione locale.

All'esterno di Designer Designer, accertarsi che l'HTML originale sia diviso in sezioni riutilizzabili.

In caso contrario, tagliate i diversi blocchi dal codice HTML. Ad esempio:

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

Dopo aver identificato tutti i blocchi, in Designer e-mail ripetete la procedura seguente per ogni sezione dell'e-mail esistente:

1. Aprire E-mail Designer per creare un contenuto e-mail vuoto.
1. Impostate gli attributi del livello del corpo: colori di sfondo, larghezza, ecc. For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. Aggiungere un componente struttura. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).
1. Aggiungere un componente HTML. For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).
1. Copiate il codice HTML in tale componente.
1. Passa alla visualizzazione mobile. For more on this, see [this section](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

   La visualizzazione reattiva è interrotta perché il CSS è mancante.

1. Per risolvere questo problema, passate alla modalità codice sorgente e copiate la sezione dello stile in una nuova sezione di stile. Ad esempio:

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Do not modify the CSS generated by the Email Designer: `<style acrite-template-css="true">` and `<style acrite-custom-styles="" type="text/css">`. Accertatevi di aggiungere lo stile dopo questo.

1. Torna alla visualizzazione mobile per verificare che il contenuto sia visualizzato correttamente e salvi le modifiche.

## Switching to mobile view {#switching-to-mobile-view}

Potete regolare la progettazione reattiva di un'e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile. Ad esempio, potete adattare i margini e la spaziatura, utilizzare dimensioni di font più piccole o più grandi, cambiare i pulsanti o applicare diversi colori di sfondo che saranno specifici della versione per dispositivi mobili dell'e-mail.

Tutte le opzioni di stile sono disponibili nella visualizzazione mobile. The Email Designer style settings are presented in the [Editing email styles](../../designing/using/editing-email-styles.md) section.

1. Create un'e-mail e iniziate a modificarne il contenuto. For more on this, see [Designing an email content from scratch](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. To access the dedicated mobile view, select the **[!UICONTROL Switch to mobile view]** button.

   ![](assets/email_designer_mobile_view_switch.png)

   Viene visualizzata la versione per dispositivi mobili. Contiene tutti i componenti e gli stili definiti nella visualizzazione desktop.

1. Modificare in modo indipendente tutte le impostazioni di stile come colore di sfondo, allineamento, spaziatura, margine, famiglia di font, colore del testo e così via.

   ![](assets/email_designer_mobile_view.png)

1. Quando si modifica un'impostazione di stile nella visualizzazione mobile, le modifiche vengono applicate solo al display mobile.

   Ad esempio, riducete le dimensioni di un'immagine, aggiungete uno sfondo verde e modificate la spaziatura nella visualizzazione mobile.

   ![](assets/email_designer_mobile_view_change.png)

1. Potete nascondere un componente quando viene visualizzato su un dispositivo mobile. To do this, select **[!UICONTROL Show only on desktop devices]** from the **[!UICONTROL Display options]**.
Potete anche scegliere di nascondere questo componente sui dispositivi desktop, che significa che verrà visualizzato solo sui dispositivi mobili. To do this, select **[!UICONTROL Show only on mobile devices]**.
Ad esempio, questa opzione consente di visualizzare un'immagine specifica sui dispositivi mobili e su un'altra immagine sui dispositivi desktop.
Puoi impostare questa opzione tramite la visualizzazione mobile o desktop.

   ![](assets/email_designer_mobile_hide.png)

1. Click again the **[!UICONTROL Switch to mobile view]** button to go back to the standard desktop view. Le modifiche dello stile apportate non vengono applicate.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >The only exception is the **[!UICONTROL Style inline]** settings. Qualsiasi modifica di stile in linea viene applicata anche alla visualizzazione desktop standard.

1. Qualsiasi altra modifica alla struttura o al contenuto dell'e-mail, ad esempio modifiche testuali, caricamento di una nuova immagine, aggiunta di un nuovo componente, ecc. viene applicata anche alla visualizzazione standard.

   Ad esempio, tornate alla visualizzazione mobile, modificate qualche testo e sostituite un'immagine.

   ![](assets/email_designer_mobile_view_change_content.png)

   Click again the **[!UICONTROL Switch to mobile view]** button to go back to the standard desktop view. Le modifiche vengono riflesse.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. La rimozione di uno stile nella visualizzazione mobile consente di tornare allo stile applicato in modalità desktop.

   Ad esempio, in visualizzazione mobile, applicate un colore di sfondo verde a un pulsante.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Passate alla visualizzazione desktop e applicate uno sfondo grigio allo stesso pulsante.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Switch again to mobile view, and now disable the **[!UICONTROL Background color]** setting.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   Ora viene applicato il colore di sfondo definito nella visualizzazione desktop: diventa grigio (non vuoto).

   The only exception is the **[!UICONTROL Border color]** setting. Se disattivato nella visualizzazione mobile, non viene più applicato alcun bordo, anche se nella visualizzazione desktop è definito un colore del bordo.

## Plain text and HTML modes {#plain-text-and-html-modes}

### Generating a text version of the email {#generating-a-text-version-of-the-email}

By default, the **[!UICONTROL Plain text]** version of your email is automatically generated and synchronized with the **[!UICONTROL Edit]** version.

Anche i campi di personalizzazione e i blocchi di contenuto aggiunti alla versione HTML vengono sincronizzati con la versione di testo normale.

>[!NOTE]
>
>Per utilizzare blocchi di contenuto in una versione di testo normale, accertatevi che non contengano codice HTML.

To have a plain text version different from the HTML version, you can disable this synchronization by clicking the **[!UICONTROL Sync with HTML]** switch from the **[!UICONTROL Plain text]** view of your email.

![](assets/email_designer_textversion.png)

Potete quindi modificare la versione di testo normale come desiderato.

>[!NOTE]
>
>If you edit the **[!UICONTROL Plain text]** version while synchronization is disabled, the next time you enable the **[!UICONTROL Sync with HTML]** option, all the changes you made in the plain text version will be replaced with the HTML version. The changes made in **[!UICONTROL Plain text]** view cannot be reflected in **[!UICONTROL HTML]** view.

### Editing an email content source in HTML {#editing-an-email-content-source-in-html}

Per gli utenti più avanzati e il debug, puoi visualizzare e modificare il contenuto e-mail direttamente in HTML.

Potete modificare la versione HTML del messaggio e-mail in due modi:

* Select **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** to open the HTML version of the entire email.

   ![](assets/email_designer_html1.png)

* From the WYSIWYG interface, select an element and click the **[!UICONTROL Source code]** icon.

   Viene visualizzata solo l'origine dell'elemento selezionato. You can edit the source code if the selected element is a **[!UICONTROL HTML]** content component. Altri componenti sono in modalità di sola lettura, ma possono comunque essere modificati nella versione HTML completa dell'e-mail.

   ![](assets/email_designer_html2.png)

Se modificate il codice HTML, la capacità di risposta dell'e-mail potrebbe risultare danneggiata. Make sure to test it using the **[!UICONTROL Preview]** button. See [Previewing messages](../../sending/using/previewing-messages.md).

## Design through Adobe Campaign integrations {#design-through-adobe-campaign-integrations}

### Editing content in Dreamweaver {#editing-content-in-dreamweaver}

L'integrazione di Adobe Campaign Standard con Dreamweaver consente di modificare il contenuto di un'e-mail nell'interfaccia di Dreamweaver. Potete accedere alla potente interfaccia di Dreamweaver per progettare e sviluppare contenuti e-mail reattivi.

* **Sincronizzazione bidirezionale**

   Ogni volta che viene effettuata una modifica in un prodotto, viene aggiornata in tempo reale nell'altro. Se desiderate modificare il colore del testo in Dreamweaver, non appena viene modificato viene visualizzato il colore del testo in Campaign. Inoltre, quando selezionate il codice in Dreamweaver o Campaign, poiché i numeri di riga sono identici, la selezione rimane tra i due prodotti, molto utile quando si ricercano elementi specifici nel codice.

* **Caricare immagini locali in AC tramite Dreamweaver**

   Quando create o modificate un'e-mail in Dreamweaver, potete semplicemente selezionare un'immagine dal desktop o dal computer locale. Mentre Dreamweaver è sempre stato consentito, quando sono connesse Dreamweaver e Campaign, il file locale viene caricato immediatamente sul server Adobe Campaign: non è necessario caricare manualmente le immagini in seguito alla modifica del contenuto. Inoltre, garantisce che le immagini più recenti siano sempre live in Campaign.

* **Aggiungere la personalizzazione delle campagne in Dreamweaver**

   For the email developer there is no longer a need to add text like ```[[FIRSTNAME_PLACEHOLDER]]``` nor to look up the syntax of your data model’s tables. La barra degli strumenti Campagna di Dreamweaver si collega direttamente al modello dati dell'istanza Campaign. Ciò significa che puoi inserire tutti i dati che desideri personalizzare da un qualcosa come Nome a Indirizzo. Se avete creato blocchi di contenuto in Campaign, potete anche estrarre quelli direttamente in Dreamweaver.

This capability is detailed in the Dreamweaver Documentation accessible [here](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). A demonstration [video](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) is also available.

### Editing content in Experience Manager {#editing-content-in-experience-manager}

Il contenuto e-mail può essere modificato in Experience Manager e quindi utilizzato per uno o più messaggi e-mail in Adobe Campaign Standard. Refer to [this document](../../integrating/using/integrating-with-experience-manager.md).

### Email design options comparison {#email-design-options-comparison}

Adobe Campaign offre diverse opzioni di authoring e-mail. La tabella seguente mostra le possibilità, i vantaggi e le limitazioni principali per ciascuno di essi.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Avvio e-mail vuoto</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Scrivere HTML</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aggiorna HTML</strong><br /> </td> 
   <td> Only inside an HTML component<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalizzazione di base</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
   <td> Supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalizzazione avanzata</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Test/Anteprima</strong><br /> </td> 
   <td> Supported<br /> </td> 
   <td> Preview in AEM<br /> Proof in Campaign<br /> </td> 
   <td> Preview and proof in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Elenchi prodotti</strong><br /> </td> 
   <td> Supported in email transactional messages<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Vantaggi</strong><br /> </td> 
   <td> 
     - Easy email building through drag-and-drop experience<br/>
     - Functionalities similar to legacy content editor<br/>
     - Reusable content with fragments
  </td> 
   <td> 
     - Reusing assets from website in emails<br/>
     - Leveraging the power of Experience Manager in email contents
    </td> 
   <td> 
    - Capability for a developer to directly code an email<br/>
    - Bi-directional synchronization<br/>
    - Editing offline in Dreamweaver and synchronizing later<br/>
    - Uploading images to Adobe Campaign through Dreamweaver
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitazioni</strong><br /> </td> 
   <td> 
     - No conditional content within fragments<br/>
     - Using Experience Manager fragments not possible
  </td> 
   <td> 
     - Advanced personalization difficult to implement<br/>
     - Need to send tests in Adobe Campaign
  </td> 
   <td> Dynamic content not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Pubblico</strong><br /> </td> 
   <td> Marketers who want to keep the flexibility to use HTML components in combination with drag-and-drop features<br /> </td> 
   <td> Marketers already using Experience Manager who want to use standard email templates with little personalization<br /> </td> 
   <td> Developers who want to code email contents and integrate directly with Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Per saperne di più</strong><br /> </td> 
   <td> See <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">About the Email Designer</a><br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a><br /> </td> 
   <td> See <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver and Campaign</a> and watch this <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">video</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

