---
title: Modifica degli stili e-mail
seo-title: Modifica degli stili e-mail
description: Modifica degli stili e-mail
seo-description: Modificare rapidamente lo stile del contenuto tramite E-mail Designer con impostazioni facilmente accessibili.
page-status-flag: never-activated
uuid: 1 fac 228 d-c 02 c -410 a-a 4 bd -0 c 3 b 163 ab 5 f 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: editing-email-content
discoiquuid: 09 c 66 cd 5-2 bbf -4846-ac 8 a -312 ab 5 c 18473
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Editing email styles{#editing-email-styles}

## Editing an element {#editing-an-element}

In the Email Designer, when selecting an element, several options specific to the type of content selected are displayed in the **[!UICONTROL Settings]** pane. È possibile utilizzare queste opzioni per modificare facilmente lo stile dell'e-mail.

### Selecting an element {#selecting-an-element}

Per selezionare un elemento nell'interfaccia di Designer e-mail, è possibile:

* fate clic direttamente nell'e-mail,
* or browse the structure tree available from the options located in the left **Palette**.

![](assets/des_tree_structure.png)

La navigazione nella struttura ad albero permette di effettuare una selezione più accurata. Potete selezionare:

* il componente struttura intera,
* una delle colonne che compongono il componente struttura,
* o solo un componente che si trova all'interno di una colonna.

![](assets/des_tree_structure_selection.png)

Per selezionare una colonna, potete anche effettuare le seguenti operazioni:

1. Select a structure component (directly in the email or using the structure tree available from the left **Palette**).
1. From the **contextual toolbar**, click **[!UICONTROL Select a column]** to choose the desired column.

See an example in [this section](../../designing/using/editing-email-styles.md#example--adjusting-vertical-alignment-and-padding).

### Adjusting style settings {#adjusting-style-settings}

1. Seleziona un elemento nell'e-mail. For more on this, see [Selecting an element](../../designing/using/editing-email-styles.md#selecting-an-element).
1. Regolare le impostazioni in base alle esigenze. Ogni elemento selezionato offre un set diverso di impostazioni.

   You can insert backgrounds, change sizes, modify horizontal or vertical alignment, manage colors, add [padding or margin](../../designing/using/editing-email-styles.md#about-padding-and-margin), and so on.

   To do this, use the options displayed in the **[!UICONTROL Settings]** pane or [add inline styling attributes](../../designing/using/editing-email-styles.md#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Salvate i contenuti.

### About padding and margin {#about-padding-and-margin}

L'interfaccia di Designer di e-mail consente di regolare rapidamente le impostazioni di spaziatura e margini.

**[!UICONTROL Padding]**: Questa impostazione consente di gestire lo spazio situato all'interno del bordo di un elemento.

![](assets/des_padding.png)

Ad esempio:

* Usate la spaziatura per impostare i margini a sinistra e a destra di un'immagine.
* Use top and bottom padding to add more spacing to a **[!UICONTROL Text]** or a **[!UICONTROL Divider]** component.
* Per impostare bordi tra colonne all'interno di un elemento struttura, definire la spaziatura per ogni colonna.

**[!UICONTROL Margin]**: Questa impostazione consente di gestire lo spazio tra il bordo dell'elemento e l'elemento successivo.

![](assets/des_margin.png)

>[!NOTE]
>
>A seconda della selezione (componente struttura, colonna o componente di contenuto), il risultato non sarà lo stesso. Adobe recommends setting the **[!UICONTROL Padding]** and **[!UICONTROL Margin]** parameters at the column level.

For both **[!UICONTROL Padding]** and **[!UICONTROL Margin]**, click the lock icon to break synchronization between top and bottom or right and left parameters. Questo consente di regolare separatamente ogni parametro.

![](assets/des_padding_lock_icon.png)

### About alignment {#about-alignment}

* **Allineamento testo**: posizionate il cursore del mouse su un testo e utilizzate la barra degli strumenti contestuale per allinearlo.

   ![](assets/des_text_alignment.png)

* **L'allineamento orizzontale** può essere applicato a testo, immagini e pulsanti, al momento non ai componenti **[!UICONTROL Divider]** e **[!UICONTROL Social]** ai componenti.

   ![](assets/des_horizontal_alignment.png)

* To set **vertical alignment**, select a column inside a structure component and choose an option from the Settings pane.

   ![](assets/des_set_vertical_alignment.png)

### About backgrounds {#about-backgrounds}

Per l'impostazione di sfondi con E-mail Designer, Adobe consiglia di:

1. Se necessario, applicate un colore di sfondo al corpo dell'e-mail.
1. Nella maggior parte dei casi, imposta i colori di sfondo a livello di colonna.
1. Cercate di non usare i colori di sfondo sui componenti immagine o di testo, poiché sono difficili da gestire.

Di seguito sono riportate le impostazioni di sfondo disponibili.

* Set a **[!UICONTROL Background color]** for the whole email. Accertarsi di selezionare le impostazioni corpo nella struttura di navigazione accessibile dalla palette a sinistra.

   ![](assets/des_background_body.png)

* Set the same background color for all structure components by selecting **[!UICONTROL Viewport background color]**. Questa opzione consente di selezionare un'impostazione diversa dal colore di sfondo.

   ![](assets/des_background_viewport.png)

* Imposta un colore di sfondo diverso per ciascun componente struttura. Selezionare una struttura nella struttura di navigazione accessibile dalla palette a sinistra per applicare un colore di sfondo specifico solo a tale struttura.

   ![](assets/des_background_structure.png)

   Verificate di non impostare un colore di sfondo della porta di visualizzazione in quanto potrebbe nascondere i colori dello sfondo della struttura.

* Set a **[!UICONTROL Background image]** for the content of a structure component.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Alcuni programmi e-mail non supportano le immagini di sfondo. Accertatevi di selezionare un colore di sfondo di fallback appropriato nel caso in cui l'immagine non possa essere visualizzata.

* Impostate un colore di sfondo a livello di colonna.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Questo è il caso più comune. Adobe consiglia di impostare i colori di sfondo a livello di colonna, così da offrire maggiore flessibilità durante la modifica dell'intero contenuto e-mail.

   Potete anche impostare un'immagine di sfondo a livello di colonna, ma questo viene raramente utilizzato.

### Example: adjusting vertical alignment and padding {#example--adjusting-vertical-alignment-and-padding}

Desiderate regolare la spaziatura e l'allineamento verticale all'interno di un componente struttura composto da tre colonne. A tal fine, attenetevi alla procedura seguente:

1. Select the structure component directly in the email or using the structure tree available from the left **Palette**.
1. From the **contextual toolbar**, click **[!UICONTROL Select a column]** and choose the one that you want to edit. Potete anche selezionarlo dalla struttura ad albero.

   ![](assets/des_selecting_column.png)

   The editable parameters for that column are displayed in the **[!UICONTROL Settings]** pane on the right.

1. Under **[!UICONTROL Vertical alignment]**, select **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   Il componente Contenuto viene visualizzato sopra alla colonna.

1. Under **[!UICONTROL Padding]**, define the top padding inside the column. Fate clic sull'icona a forma di lucchetto per interrompere la sincronizzazione con la spaziatura inferiore.

   Definire la spaziatura sinistra e destra per quella colonna.

   ![](assets/des_adjusting_padding.png)

1. Procedete in modo simile per regolare l'allineamento e la spaziatura delle altre colonne.

   ![](assets/des_adjusting_columns.png)

1. Salvate le modifiche.

## Adding inline styling attributes {#adding-inline-styling-attributes}

Nell'interfaccia di Designer e-mail, quando selezionate un elemento e ne visualizzate le impostazioni nel pannello laterale, potete personalizzare gli attributi inline e il relativo valore per quell'elemento specifico.

1. Selezionate un elemento nel contenuto.
1. On the side panel, look for the **[!UICONTROL Styles Inline]** settings.

   ![](assets/email_designer_inlineattributes.png)

1. Modify the values of the existing attributes, or add new ones using the **+** button. Potete aggiungere qualsiasi attributo e valore conforme con CSS.

Lo stile viene quindi applicato all'elemento selezionato. Se gli elementi secondari non hanno attributi di stile specifici definiti, viene ereditato lo stile dell'elemento principale.
