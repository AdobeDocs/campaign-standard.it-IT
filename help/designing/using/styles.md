---
title: Gestione degli stili e-mail
description: Scoprite come gestire gli stili delle e-mail in Designer e-mail.
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
source-git-commit: 796490350855213578808651cd18df24b1d3f2d1
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Gestione degli stili e-mail {#managing-styles}


In Designer e-mail, quando si seleziona un elemento, nel **[!UICONTROL Settings]** riquadro vengono visualizzate diverse opzioni specifiche per il tipo di contenuto selezionato. Potete usare queste opzioni per cambiare facilmente lo stile dell’e-mail.

## Selezione di un elemento {#selecting-an-element}

Per selezionare un elemento nell&#39;interfaccia di Designer e-mail, è possibile:

* fai clic direttamente nell’e-mail,
* oppure sfogliare la struttura ad albero disponibile dalle opzioni presenti nella **palette** sinistra.

![](assets/des_tree_structure.png)

L’esplorazione della struttura ad albero consente di effettuare una selezione più accurata. Potete selezionare una delle seguenti opzioni:

* l’intero componente della struttura,
* una delle colonne che compongono il componente struttura,
* o solo un componente che si trova all’interno di una colonna.

![](assets/des_tree_structure_selection.png)

Per selezionare una colonna, potete anche effettuare le seguenti operazioni:

1. Selezionate un componente struttura (direttamente nel messaggio e-mail o utilizzando la struttura ad albero disponibile nella **palette** sinistra).
1. Dalla barra degli strumenti **** contestuale, fate clic **[!UICONTROL Select a column]** per scegliere la colonna desiderata.

Vedere un esempio in [questa sezione](#example--adjusting-vertical-alignment-and-padding).

## Regolazione delle impostazioni di stile {#adjusting-style-settings}

1. Selezionate un elemento nel messaggio e-mail. For more on this, see [Selecting an element](#selecting-an-element).
1. Regolate le impostazioni in base alle vostre esigenze. Ogni elemento selezionato offre un set di impostazioni diverso.

   Potete inserire sfondi, modificare le dimensioni, modificare l’allineamento orizzontale o verticale, gestire i colori, aggiungere [spaziatura o margini](#selecting-an-element)e così via.

   A tal fine, utilizzate le opzioni visualizzate nel **[!UICONTROL Settings]** riquadro o [aggiungete gli attributi](#adding-inline-styling-attributes)di stile in linea.

   ![](assets/des_settings_pane.png)

1. Salvate il contenuto.

## Regolazione della spaziatura e del margine {#about-padding-and-margin}

L&#39;interfaccia di Designer e-mail consente di regolare rapidamente le impostazioni di spaziatura e margini.

**[!UICONTROL Padding]**: questa impostazione consente di gestire lo spazio che si trova all&#39;interno del bordo di un elemento.

![](assets/des_padding.png)

Ad esempio:

* Usate la spaziatura per impostare i margini a sinistra e a destra di un’immagine.
* Usate la spaziatura superiore e inferiore per aggiungere più spaziatura a un **[!UICONTROL Text]** componente o a un **[!UICONTROL Divider]** componente.
* Per impostare i bordi tra le colonne all&#39;interno di un elemento struttura, definire la spaziatura per ciascuna colonna.

**[!UICONTROL Margin]**: questa impostazione consente di gestire lo spazio tra il bordo dell&#39;elemento e l&#39;elemento successivo.

![](assets/des_margin.png)

>[!NOTE]
>
>A seconda della selezione (componente struttura, colonna o componente contenuto), il risultato non sarà lo stesso.  Adobe consiglia di impostare i **[!UICONTROL Padding]** parametri e **[!UICONTROL Margin]** a livello di colonna.

Per entrambe **[!UICONTROL Padding]** e **[!UICONTROL Margin]**, fate clic sull&#39;icona Blocca per interrompere la sincronizzazione tra i parametri superiore e inferiore o destra e sinistra. Questo consente di regolare ciascun parametro separatamente.

![](assets/des_padding_lock_icon.png)

## Allineamento stile {#about-alignment}

* **Allineamento** del testo: posizionare il cursore del mouse su un testo e utilizzare la barra degli strumenti contestuale per allinearlo.

   ![](assets/des_text_alignment.png)

* **L&#39;allineamento** orizzontale può essere applicato a testo, immagini e pulsanti, attualmente non ai **[!UICONTROL Divider]** componenti e **[!UICONTROL Social]** ai componenti.

   ![](assets/des_horizontal_alignment.png)

* Per impostare l’allineamento **** verticale, selezionate una colonna all’interno di un componente struttura e scegliete un’opzione dal riquadro Impostazioni.

   ![](assets/des_set_vertical_alignment.png)

## Impostazione degli sfondi {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Impostazioni di sfondo"
>abstract="Designer e-mail consente di personalizzare il colore di sfondo o l&#39;immagine di sfondo per il contenuto."

Per impostare gli sfondi con Designer e-mail,  Adobe consiglia quanto segue:

1. Se necessario, applicate un colore di sfondo al corpo del messaggio e-mail.
1. Nella maggior parte dei casi, impostate i colori di sfondo a livello di colonna.
1. Cercate di non utilizzare i colori di sfondo sui componenti immagine o testo, in quanto sono difficili da gestire.

Di seguito sono riportate le impostazioni di sfondo disponibili che potete usare.

* Impostate un **[!UICONTROL Background color]** valore per l’intero messaggio e-mail. Accertarsi di selezionare le impostazioni del corpo nella struttura di navigazione accessibile dalla palette a sinistra.

   ![](assets/des_background_body.png)

* Per impostare lo stesso colore di sfondo per tutti i componenti struttura, selezionare **[!UICONTROL Viewport background color]**. Questa opzione consente di selezionare un’impostazione diversa dal colore di sfondo.

   ![](assets/des_background_viewport.png)

* Impostare un colore di sfondo diverso per ciascun componente struttura. Selezionare una struttura nella struttura ad albero di navigazione accessibile dalla palette a sinistra per applicare un colore di sfondo specifico solo a tale struttura.

   ![](assets/des_background_structure.png)

   Accertatevi di non impostare un colore di sfondo della finestra in quanto potrebbe nascondere i colori di sfondo della struttura.

* Impostare un **[!UICONTROL Background image]** valore per il contenuto di un componente struttura.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Alcuni programmi e-mail non supportano le immagini di sfondo. Se non è supportato, verrà utilizzato il colore di sfondo della riga. Accertatevi di selezionare un colore di sfondo di fallback appropriato nel caso in cui l&#39;immagine non possa essere visualizzata.

* Impostate un colore di sfondo a livello di colonna.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Questo è il caso d&#39;uso più comune.  Adobe consiglia di impostare i colori di sfondo a livello di colonna in quanto ciò consente una maggiore flessibilità nella modifica dell’intero contenuto dell’e-mail.

   Potete anche impostare un&#39;immagine di sfondo a livello di colonna, ma questa impostazione viene utilizzata raramente.

### Esempio: regolazione dell&#39;allineamento verticale e della spaziatura {#example--adjusting-vertical-alignment-and-padding}

È necessario regolare la spaziatura e l&#39;allineamento verticale all&#39;interno di un componente struttura composto da tre colonne. Per farlo, segui la procedura indicata di seguito:

1. Selezionate il componente struttura direttamente nel messaggio e-mail o utilizzando la struttura ad albero disponibile nella **palette** sinistra.
1. Dalla barra degli strumenti **** contestuale, fate clic su **[!UICONTROL Select a column]** e scegliete quello da modificare. È inoltre possibile selezionarlo dalla struttura ad albero.

   ![](assets/des_selecting_column.png)

   I parametri modificabili per quella colonna vengono visualizzati nel **[!UICONTROL Settings]** riquadro a destra.

1. In **[!UICONTROL Vertical alignment]**, selezionare **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   Il componente di contenuto viene visualizzato sopra la colonna.

1. In **[!UICONTROL Padding]**, definite la spaziatura superiore all&#39;interno della colonna. Fate clic sull’icona Blocca per interrompere la sincronizzazione con la spaziatura inferiore.

   Definite la spaziatura sinistra e destra per la colonna.

   ![](assets/des_adjusting_padding.png)

1. Procedere in modo simile per regolare l&#39;allineamento e la spaziatura delle altre colonne.

   ![](assets/des_adjusting_columns.png)

1. Salva le modifiche.

## Collegamenti stile {#about-styling-links}

È possibile sottolineare un collegamento e selezionarne il colore e la destinazione in Designer e-mail.

1. In un componente in cui è inserito un collegamento, seleziona il testo dell’etichetta del collegamento.

1. Nelle impostazioni del componente, verificate **[!UICONTROL Underline link]** di sottolineare il testo dell’etichetta del collegamento.

   ![](assets/stylelinks-selecttext.png)

1. Per selezionare il contesto di navigazione in cui verrà aperto il collegamento, seleziona una **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Per cambiare il colore del collegamento, fai clic su **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Scegliete il colore desiderato.

   ![](assets/stylelinks-colorchanged.png)

1. Salva le modifiche.

## Aggiunta di attributi di stile in linea {#adding-inline-styling-attributes}

Nell&#39;interfaccia di Designer e-mail, quando si seleziona un elemento e ne vengono visualizzate le impostazioni nel pannello laterale, è possibile personalizzare gli attributi in linea e il relativo valore per tale elemento specifico.

1. Selezionate un elemento nel contenuto.
1. Nel pannello laterale, cercate le **[!UICONTROL Styles Inline]** impostazioni.

   ![](assets/email_designer_inlineattributes.png)

1. Modificate i valori degli attributi esistenti o aggiungetene di nuovi utilizzando il pulsante **+** . Potete aggiungere qualsiasi attributo e valore conforme con CSS.

Lo stile viene quindi applicato all&#39;elemento selezionato. Se gli elementi secondari non dispongono di attributi di stile specifici definiti, lo stile dell&#39;elemento padre viene ereditato.
