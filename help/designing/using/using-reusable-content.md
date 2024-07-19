---
title: Creazione e utilizzo di contenuto riutilizzabile
description: Inizia a creare contenuti e-mail riutilizzabili con E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 64c3d3dd-0c41-4dbc-abcd-9ddea23759f4
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1812'
ht-degree: 1%

---

# Creazione e utilizzo di contenuto riutilizzabile {#using-reusable-content}

Scopri come padroneggiare l’edizione dei contenuti delle e-mail. Con E-mail Designer, puoi creare modelli e frammenti con contenuti predefiniti e riutilizzarli per le consegne successive.

## Progettazione di e-mail tramite modelli {#designing-templates}

>[!NOTE]
>
> In Adobe Campaign Standard puoi creare diversi tipi di modelli accessibili dal menu **Risorse** > **Modelli**. I modelli utilizzati in E-mail Designer sono modelli di contenuto. Per ulteriori informazioni, vedere [Informazioni sui modelli](../../start/using/marketing-activity-templates.md).

![](assets/do-not-localize/how-to-video.png) [Scopri come creare modelli nel video](#video)

### Informazioni sui modelli di contenuto {#content-templates}

È possibile gestire i contenuti di HTML offerti nella scheda **[!UICONTROL Templates]** della home page di [Designer](../../designing/using/designing-content-in-adobe-campaign.md) tramite posta elettronica.

I modelli di contenuto e-mail predefiniti includono diciotto layout ottimizzati per dispositivi mobili e quattro modelli reattivi all’avanguardia progettati da artisti Behance. Corrispondono agli utilizzi più recenti, tra cui messaggi di benvenuto dei clienti, newsletter e e-mail di ricoinvolgimento. Possono essere facilmente personalizzati con il contenuto dei tuoi marchi per facilitare il processo di progettazione delle e-mail da zero.

![](assets/template_content.png)

I modelli di contenuto HTML sono accessibili dalla schermata **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** del [menu Avanzate](../../start/using/interface-description.md#advanced-menu). Da qui puoi gestire i modelli di contenuto della pagina di destinazione, i modelli di contenuto e-mail e anche i frammenti.

![](assets/content_templates_list.png)

I modelli di contenuto predefiniti sono di sola lettura. Per modificarne uno, devi prima duplicare il modello desiderato.

Puoi creare nuovi modelli o frammenti e definire contenuti personalizzati. Per ulteriori informazioni, vedere [Creazione di un modello di contenuto](#creating-a-content-template) e [Creazione di un frammento di contenuto](#creating-a-content-fragment).

Quando modifichi il contenuto con E-mail Designer, puoi anche creare modelli di contenuto salvando il contenuto come frammento o modello. Per ulteriori informazioni, vedere [Salvataggio del contenuto come modello](#saving-content-as-template) e [Salvataggio del contenuto come frammento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

**Argomenti correlati:**

* Per ulteriori informazioni sulla modifica del contenuto, vedere [Informazioni sulla progettazione del contenuto delle e-mail](../../designing/using/designing-content-in-adobe-campaign.md).

### Creazione di un modello di contenuto {#creating-a-content-template}

Puoi creare modelli di contenuto personalizzati per utilizzarli il numero di volte necessario.

L’esempio seguente mostra come creare un modello di contenuto e-mail.

1. Vai a **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** e fai clic su **[!UICONTROL Create]**.
1. Fare clic sull&#39;etichetta e-mail per accedere alla scheda **[!UICONTROL Properties]** di E-mail Designer.
1. Specifica un’etichetta riconoscibile e seleziona i seguenti parametri per poter utilizzare questo modello nelle e-mail:

   * Selezionare **[!UICONTROL Shared]** o **[!UICONTROL Delivery]** dall&#39;elenco a discesa **[!UICONTROL Content type]**.
   * Selezionare **[!UICONTROL Template]** dall&#39;elenco a discesa **[!UICONTROL HTML type]**.

   ![](assets/email_designer_create-template.png)

1. Se necessario, puoi impostare un’immagine da utilizzare come miniatura per il modello. Selezionala dalla scheda **[!UICONTROL Thumbnail]** delle proprietà del modello.

   ![](assets/email_designer_create-template_thumbnail.png)

   Questa miniatura verrà visualizzata nella scheda **[!UICONTROL Templates]** della home page di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Chiudere la scheda **[!UICONTROL Properties]** per tornare all&#39;area di lavoro principale.
1. Aggiungi componenti struttura e componenti contenuto che puoi personalizzare in base alle esigenze.
   >[!NOTE]
   >
   > Non è possibile inserire campi di personalizzazione o contenuto condizionale all’interno di un modello di contenuto.
1. Una volta modificato, salva il modello.

Questo modello può ora essere utilizzato in qualsiasi e-mail creata con E-mail Designer. Selezionala dalla scheda **[!UICONTROL Templates]** della home page di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

![](assets/content_template_new.png)

### Salvataggio del contenuto come modello {#saving-content-as-template}

Quando modifichi un’e-mail con E-mail Designer, puoi salvarne direttamente il contenuto come modello.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Selezionare **[!UICONTROL Save as template]** dalla barra degli strumenti principale di E-mail Designer.

   ![](assets/email_designer_save-as-template.png)

1. Aggiungere un&#39;etichetta e una descrizione, se necessario, quindi fare clic su **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-template_creation.png)

1. Per trovare il modello appena creato, passa a **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**.

1. Per utilizzare il nuovo modello, selezionarlo dalla scheda **[!UICONTROL Templates]** della home page di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/content_template_new.png)

### Creazione di un modello con frammenti e componenti {#template-fragments-components}

Ora puoi creare un modello e-mail con E-mail Designer. Utilizza i componenti di contenuto per riflettere le diverse sezioni dell’e-mail e regola le impostazioni per renderle il più possibile simili alla newsletter originale. Infine, inserisci i frammenti appena creati.

1. Crea un modello utilizzando E-mail Designer. Per ulteriori informazioni, consulta [Modelli di contenuto](#content-templates).
1. Inserisci nel modello diversi componenti struttura corrispondenti all’intestazione, al piè di pagina e al corpo del messaggio e-mail. Per ulteriori informazioni sull&#39;aggiunta di componenti struttura, vedere [Modifica della struttura delle e-mail con E-mail Designer](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Inserisci tutti i componenti di contenuto necessari per creare il corpo della newsletter. Si tratta del contenuto modificabile dell’e-mail che verrà aggiornato ogni mese.

   ![](assets/des_loading_compatible_fragment_5.png)

   Se hai familiarità con il codice HTML, Adobe consiglia di sfruttare i componenti **[!UICONTROL Html]** per copiare e incollare gli elementi più complessi dell&#39;e-mail originale. Utilizzare altri componenti come **[!UICONTROL Button]**, **[!UICONTROL Image]** o **[!UICONTROL Text]** per il resto del contenuto. Per ulteriori informazioni, consulta [Informazioni sui componenti di contenuto](../../designing/using/designing-from-scratch.md#about-content-components).

   >[!NOTE]
   >
   >L&#39;utilizzo del componente **[!UICONTROL Html]** determina la creazione di componenti modificabili con opzioni limitate. Prima di selezionare questo componente, assicurati di sapere come gestire il codice HTML.

1. Regola il più possibile i componenti di contenuto in modo che corrispondano all’e-mail originale.

   ![](assets/des_loading_compatible_fragment_6.png)

   Per ulteriori informazioni sulla gestione delle impostazioni di stile e degli attributi in linea, consulta [Modifica degli stili delle e-mail](../../designing/using/styles.md).

1. Inserisci i due frammenti (intestazione e piè di pagina) creati in precedenza nei componenti struttura desiderati.

   ![](assets/des_loading_compatible_fragment_10.png)

1. Salva il modello.

Ora puoi gestire completamente questo modello all’interno di E-mail Designer per creare e aggiornare la newsletter che invierai ogni mese ai destinatari.

Per utilizzarlo, crea un messaggio e-mail e seleziona il modello di contenuto appena creato.

**Argomento correlato**:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Video introduttivo all’E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

### Video tutorial {#video}

In questi video viene illustrato come creare un modello personalizzato.

>[!VIDEO](https://video.tv.adobe.com/v/23106?quality=12)

Sono disponibili altri video dimostrativi di Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).

## Informazioni sui frammenti {#about-fragments}

>[!CONTEXTUALHELP]
>id="ac_fragments"
>title="Informazioni sui frammenti"
>abstract="Un frammento è un blocco di contenuto riutilizzabile a cui è possibile fare riferimento in una o più e-mail."

Un frammento è un componente riutilizzabile a cui è possibile fare riferimento in una o più e-mail.
Sono disponibili nell&#39;interfaccia in **Risorse** > **Frammenti di contenuto e modelli**.

Per utilizzare al meglio i frammenti nel Designer e-mail:

* Crea frammenti personalizzati. Consulta [Creazione di un frammento di contenuto](#creating-a-content-fragment) e [Salvataggio del contenuto come frammento](#saving-content-as-a-fragment).
* Utilizzali il numero di volte necessario nelle e-mail. Vedi [Inserimento di elementi in un messaggio e-mail](#inserting-elements-into-an-email).
* Quando modifichi un frammento, le modifiche vengono sincronizzate: vengono propagate automaticamente a tutte le e-mail (purché non siano ancora state preparate o inviate) contenenti tale frammento.

I frammenti aggiunti a un messaggio e-mail vengono bloccati per impostazione predefinita. Se desideri modificare un frammento per un’e-mail specifica, puoi interrompere la sincronizzazione con il frammento originale sbloccandolo nell’e-mail in cui viene utilizzato. Le modifiche non verranno più sincronizzate.

Per sbloccare un frammento all’interno di un’e-mail, selezionalo e fai clic sull’icona a forma di lucchetto nella barra degli strumenti contestuale.

![](assets/des_unlocking_fragment.png)

Il frammento diventa un componente autonomo non più collegato al frammento originale. Può quindi essere modificato come qualsiasi altro componente di contenuto. Consulta [Informazioni sui componenti di contenuto](../../designing/using/designing-from-scratch.md#about-content-components).

### Inserimento di frammenti in un messaggio e-mail {#inserting-elements-into-an-email}

Per definire il contenuto dell’e-mail, puoi aggiungere elementi di contenuto nei componenti struttura precedentemente inseriti. Consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Accedere agli elementi di contenuto selezionando l&#39;icona **+** a sinistra. Selezionare [Frammenti](#about-fragments) o [Componenti contenuto](../../designing/using/designing-from-scratch.md#about-content-components).
1. Se conosci già l’etichetta o parte dell’etichetta del frammento che desideri aggiungere, puoi cercarla.

   ![](assets/email_designer_fragmentsearch.png)

1. Trascina e rilascia un frammento o un componente di contenuto dalla palette a un componente di struttura dell’e-mail.

   ![](assets/email_designer_addfragment.png)

   Una volta aggiunto all’e-mail, un elemento può essere spostato all’interno del componente struttura o in un altro componente struttura nell’e-mail.

   ![](assets/email_designer_movefragment.png)

1. Modifica l’elemento in modo che corrisponda esattamente alle esigenze di questa e-mail. È possibile aggiungere testo, collegamenti, immagini e così via.

   >[!NOTE]
   >
   >I frammenti vengono bloccati per impostazione predefinita quando vengono aggiunti a un messaggio e-mail. Puoi interrompere la sincronizzazione con il frammento originale se desideri modificare il frammento per un’e-mail specifica o apportare la modifica direttamente nel frammento. Vedi [Informazioni sui frammenti](#about-fragments).

1. Ripeti questa procedura per tutti gli elementi da aggiungere al messaggio e-mail.
1. Salva l’e-mail.

Ora che la struttura delle e-mail è compilata, puoi modificare lo stile di ciascun elemento di contenuto. Vedere [Modifica di un elemento](../../designing/using/styles.md).

>[!NOTE]
>
>Se un frammento viene modificato, le modifiche vengono propagate automaticamente nelle e-mail in cui viene utilizzato. Per ulteriori informazioni, consulta [Informazioni sui frammenti](#about-fragments).

### Creazione di un frammento di contenuto {#creating-a-content-fragment}

Puoi creare frammenti di contenuto personalizzati per utilizzarli in base alle esigenze in una o più e-mail.

1. Vai a **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** e fai clic su **[!UICONTROL Create]**.
1. Fare clic sull&#39;etichetta e-mail per accedere alla scheda **[!UICONTROL Properties]** di E-mail Designer.
1. Specifica un’etichetta riconoscibile e seleziona i seguenti parametri per trovare il frammento durante la modifica del contenuto dell’e-mail:

   * Poiché i frammenti sono compatibili solo con le e-mail, selezionare **[!UICONTROL Delivery]** dall&#39;elenco a discesa **[!UICONTROL Content type]**.
   * Selezionare **[!UICONTROL Fragment]** dall&#39;elenco a discesa **[!UICONTROL HTML type]** per utilizzare il contenuto come frammento.

   ![](assets/email_designer_createfragment.png)

1. Se necessario, puoi impostare un’immagine da utilizzare come miniatura per il frammento. Selezionala dalla scheda **[!UICONTROL Thumbnail]** delle proprietà del modello.

   ![](assets/email_designer_createfragment_thumbnail.png)

   Questa miniatura viene visualizzata accanto all’etichetta del frammento durante la modifica di un’e-mail.

1. Chiudere la scheda **[!UICONTROL Properties]** per tornare all&#39;area di lavoro principale.
1. Aggiungi componenti struttura e componenti contenuto che puoi personalizzare in base alle esigenze.

   >[!CAUTION]
   >
   >I frammenti non possono includere campi di personalizzazione, contenuto dinamico o un altro frammento.
   >
   >Evita di salvare come frammento il contenuto con componenti struttura vuoti. Una volta inserito il frammento >non sarà più possibile modificarlo.
   >
   >La [visualizzazione per dispositivi mobili](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view) non è disponibile nei frammenti.

1. Dopo la modifica, salva il frammento.

Questo frammento può ora essere utilizzato in qualsiasi e-mail creata con E-mail Designer. Viene visualizzato nella sezione **[!UICONTROL Fragments]** della tavolozza.

>[!NOTE]
>
>Non puoi inserire campi di personalizzazione all’interno di un frammento, a meno che non venga utilizzato in un messaggio e-mail e non sia sbloccato. Vedi [Informazioni sui frammenti](#about-fragments).

### Salvataggio di contenuto come frammento {#saving-content-as-a-fragment}

Quando modifichi un’e-mail con E-mail Designer, puoi salvarne direttamente una parte come frammento.

* Non puoi salvare come frammento una struttura contenente campi di personalizzazione, contenuto dinamico o un altro frammento.
* È possibile selezionare solo strutture adiacenti.
  <!-- - You cannot select an empty structure.-->

1. Durante la modifica di un&#39;e-mail nel Designer e-mail, selezionare **[!UICONTROL Save as fragment]** dalla barra degli strumenti principale.

   ![](assets/email_designer_save-as-fragment.png)

1. Dall’area di lavoro, seleziona le strutture che comporranno il frammento.

   ![](assets/email_designer_save-as-fragment_select.png)

   >[!NOTE]
   >
   >Accertati di selezionare strutture adiacenti che non includono campi di personalizzazione, contenuto dinamico o un altro frammento.
   <!--You cannot select an empty structure.-->

1. Fai clic su **[!UICONTROL Create]**.

1. Aggiungere un&#39;etichetta e una descrizione, se necessario, quindi fare clic su **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-fragment_popup.png)

1. Per trovare il frammento appena creato, passa a **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]**.

   ![](assets/email_designer_save-as-fragment_list.png)

1. Per utilizzare il nuovo frammento, apri qualsiasi contenuto e-mail e selezionalo dall’elenco dei frammenti.

![](assets/email_designer_save-as-fragment_in-new-email.png)

>[!NOTE]
>La [visualizzazione per dispositivi mobili](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view) non è disponibile nei frammenti. Se desideri modificare una visualizzazione per dispositivi mobili e-mail, esegui questa operazione prima di salvare il contenuto come frammento.

<!--You need to copy-paste the HTML corresponding to the section that you want to save into a new fragment.

>[!NOTE]
>
>To do this, you need to be familiar with HTML code.

To save as a fragment some email content that you created, follow the steps below.

1. When editing an email in the Email Designer, select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of that email.
1. Select and copy the HTML corresponding to the part that you want to save.
1. Go to **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** and click **[!UICONTROL Create]**.
1. Click the email label to access the **[!UICONTROL Properties]** tab of the Email Designer and select **[!UICONTROL Fragment]** from the **[!UICONTROL HTML type]** drop-down list.
1. Select **[!UICONTROL Edit]** > **[!UICONTROL HTML]** to open the HTML version of the fragment.
1. Paste the HTML that you copied where appropriate.
1. Switch back to the **[!UICONTROL Edit]** view to check the result and save the new fragment.-->

## Creazione di intestazioni e piè di pagina riutilizzabili tramite frammenti {#header-footer-fragments}

Con E-mail Designer, crea un frammento per ogni sezione riutilizzabile. In questo esempio verranno creati due frammenti: uno per l’intestazione e uno per il piè di pagina. Puoi quindi copiare le parti rilevanti dal contenuto esistente in questi frammenti.

A questo scopo, segui la procedura indicata di seguito:

1. In Adobe Campaign, vai a **[!UICONTROL Resources]** > **[!UICONTROL Content templates & fragments]** e crea un frammento per l&#39;intestazione. Per ulteriori informazioni, consulta [Creazione di un frammento di contenuto](#creating-a-content-fragment).
1. Aggiungi al frammento tutti i componenti struttura necessari.

   ![](assets/des_loading_compatible_fragment_1.png)

1. Inserisci i componenti immagine e testo nella struttura.

   ![](assets/des_loading_compatible_fragment_2.png)

1. Carica l’immagine corrispondente, immetti il testo e regola le impostazioni.

   ![](assets/des_loading_compatible_fragment_3.png)

1. Salva il frammento.
1. Procedere in modo simile per creare il piè di pagina e salvarlo.

   ![](assets/des_loading_compatible_fragment_4.png)

I frammenti sono ora pronti per essere utilizzati in un modello.
