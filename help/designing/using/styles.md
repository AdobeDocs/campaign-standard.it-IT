---
title: Gestione degli stili delle e-mail
description: Scopri come gestire gli stili delle e-mail in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 8daeb12d-4170-464f-ba33-afb681f72a91
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '1038'
ht-degree: 25%

---

# Gestione degli stili delle e-mail {#managing-styles}


Nel Designer e-mail, quando si seleziona un elemento, nel riquadro **[!UICONTROL Settings]** vengono visualizzate diverse opzioni specifiche per il tipo di contenuto selezionato. Puoi utilizzare queste opzioni per modificare facilmente lo stile dell’e-mail.

## Selezione di un elemento {#selecting-an-element}

Per selezionare un elemento nell’interfaccia E-mail Designer, puoi effettuare le seguenti operazioni:

* fai clic direttamente nell’e-mail,
* o sfoglia la struttura ad albero disponibile tra le opzioni disponibili nella **Tavolozza** a sinistra.

![](assets/des_tree_structure.png)

Esplorando la struttura ad albero potete effettuare una selezione più accurata. Puoi selezionare:

* l&#39;intera componente di struttura,
* una delle colonne che compongono il componente struttura,
* o solo un componente che si trova all’interno di una colonna.

![](assets/des_tree_structure_selection.png)

Per selezionare una colonna, è inoltre possibile effettuare le seguenti operazioni:

1. Seleziona un componente struttura (direttamente nell&#39;e-mail o utilizzando la struttura ad albero disponibile nella **palette** a sinistra).
1. Dalla **barra degli strumenti contestuale**, fare clic su **[!UICONTROL Select a column]** per scegliere la colonna desiderata.

Vedi un esempio in [questa sezione](#example--adjusting-vertical-alignment-and-padding).

## Regolazione delle impostazioni di stile {#adjusting-style-settings}

1. Seleziona un elemento nell’e-mail. Per ulteriori informazioni, vedere [Selezione di un elemento](#selecting-an-element).
1. Regola le impostazioni in base alle tue esigenze. Ogni elemento selezionato offre un diverso set di impostazioni.

   È possibile inserire sfondi, modificare le dimensioni, modificare l&#39;allineamento orizzontale o verticale, gestire i colori, aggiungere [spaziatura interna o margine](#selecting-an-element) e così via.

   A tale scopo, utilizzare le opzioni visualizzate nel riquadro **[!UICONTROL Settings]** o [aggiungere attributi di stile in linea](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Salva il contenuto.

## Regolazione della spaziatura interna e del margine {#about-padding-and-margin}

L’interfaccia di E-mail Designer consente di regolare rapidamente le impostazioni di spaziatura interna e margine.

**[!UICONTROL Padding]**: questa impostazione consente di gestire lo spazio disponibile all&#39;interno del bordo di un elemento.

![](assets/des_padding.png)

Ad esempio:

* Utilizzare la spaziatura per impostare i margini sul lato sinistro e destro di un&#39;immagine.
* Utilizzare la spaziatura superiore e inferiore per aggiungere ulteriore spaziatura a un componente **[!UICONTROL Text]** o **[!UICONTROL Divider]**.
* Per impostare i bordi tra le colonne all&#39;interno di un elemento struttura, definire la spaziatura per ogni colonna.

**[!UICONTROL Margin]**: questa impostazione consente di gestire lo spazio tra il bordo dell&#39;elemento e l&#39;elemento successivo.

![](assets/des_margin.png)

>[!NOTE]
>
>A seconda della selezione (componente struttura, colonna o componente contenuto), il risultato non sarà lo stesso. Adobe consiglia di impostare i parametri **[!UICONTROL Padding]** e **[!UICONTROL Margin]** a livello di colonna.

Per **[!UICONTROL Padding]** e **[!UICONTROL Margin]**, fare clic sull&#39;icona del lucchetto per interrompere la sincronizzazione tra i parametri superiore e inferiore o destro e sinistro. Questo consente di regolare ogni parametro separatamente.

![](assets/des_padding_lock_icon.png)

## Allineamento stile {#about-alignment}

* **Allineamento testo**: posizionare il cursore del mouse su un testo e utilizzare la barra degli strumenti contestuale per allinearlo.

  ![](assets/des_text_alignment.png)

* **L&#39;allineamento orizzontale** può essere applicato a testo, immagini e pulsanti, attualmente non ai componenti **[!UICONTROL Divider]** e **[!UICONTROL Social]**.

  ![](assets/des_horizontal_alignment.png)

* Per impostare **l&#39;allineamento verticale**, selezionare una colonna all&#39;interno di un componente struttura e scegliere un&#39;opzione nel riquadro Impostazioni.

  ![](assets/des_set_vertical_alignment.png)

## Impostazione degli sfondi {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Impostazioni dello sfondo"
>abstract="E-mail Designer consente di personalizzare il colore di sfondo o l’immagine di sfondo per il contenuto. Tieni presente che l’immagine di sfondo non è supportata da tutti i client e-mail."

Per impostare lo sfondo con E-mail Designer, Adobe consiglia quanto segue:

1. Se richiesto dal tuo design, applica un colore di sfondo al corpo dell’e-mail.
1. Nella maggior parte dei casi, impostare i colori di sfondo a livello di colonna.
1. Evita di utilizzare i colori di sfondo su componenti immagine o testo, poiché sono difficili da gestire.

Di seguito sono riportate le impostazioni di sfondo disponibili.

* Imposta **[!UICONTROL Background color]** per l&#39;intero messaggio e-mail. Assicurati di selezionare le impostazioni del corpo nella struttura di navigazione accessibile dalla palette a sinistra.

  ![](assets/des_background_body.png)

* Impostare lo stesso colore di sfondo per tutti i componenti della struttura selezionando **[!UICONTROL Viewport background color]**. Questa opzione consente di selezionare un’impostazione diversa dal colore di sfondo.

  ![](assets/des_background_viewport.png)

* Imposta un colore di sfondo diverso per ciascun componente della struttura. Selezionare una struttura nell&#39;albero di navigazione accessibile dalla tavolozza a sinistra per applicare un colore di sfondo specifico solo a tale struttura.

  ![](assets/des_background_structure.png)

  Assicurati di non impostare un colore di sfondo del riquadro di visualizzazione, in quanto questo potrebbe nascondere i colori di sfondo della struttura.

* Imposta **[!UICONTROL Background image]** per il contenuto di un componente struttura.

  ![](assets/des_background_image.png)

  >[!NOTE]
  >
  >Alcuni programmi e-mail non supportano le immagini di sfondo. Se non è supportato, verrà utilizzato il colore di sfondo della riga. Assicurati di selezionare un colore di sfondo di fallback appropriato nel caso in cui l’immagine non possa essere visualizzata.

* Imposta un colore di sfondo a livello di colonna.

  ![](assets/des_background_column.png)

  >[!NOTE]
  >
  >Questo è il caso d’uso più comune. Adobe consiglia di impostare i colori di sfondo a livello di colonna, in quanto ciò consente una maggiore flessibilità nella modifica dell’intero contenuto dell’e-mail.

  Puoi anche impostare un’immagine di sfondo a livello di colonna, ma questa viene utilizzata raramente.

### Esempio: regolazione dell’allineamento verticale e della spaziatura {#example--adjusting-vertical-alignment-and-padding}

Desideri regolare la spaziatura interna e l’allineamento verticale all’interno di un componente struttura composto da tre colonne. A questo scopo, segui la procedura indicata di seguito:

1. Seleziona il componente struttura direttamente nel messaggio e-mail o utilizzando la struttura ad albero disponibile nella **palette** a sinistra.
1. Dalla **barra degli strumenti contestuale**, fare clic su **[!UICONTROL Select a column]** e scegliere quello che si desidera modificare. Puoi anche selezionarla dall’albero della struttura.

   ![](assets/des_selecting_column.png)

   I parametri modificabili per tale colonna vengono visualizzati nel riquadro **[!UICONTROL Settings]** a destra.

1. In **[!UICONTROL Vertical alignment]**, selezionare **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   Il componente contenuto viene visualizzato sopra la colonna.

1. In **[!UICONTROL Padding]**, definisci la spaziatura interna superiore nella colonna. Fai clic sull’icona del lucchetto per interrompere la sincronizzazione con la spaziatura inferiore.

   Definisci la spaziatura sinistra e destra per quella colonna.

   ![](assets/des_adjusting_padding.png)

1. Procedi in modo simile per regolare l’allineamento e la spaziatura delle altre colonne.

   ![](assets/des_adjusting_columns.png)

1. Salva le modifiche.

## Collegamenti di stile {#about-styling-links}

In E-mail Designer è possibile sottolineare un collegamento e selezionarne il colore e la destinazione.

1. In un componente in cui viene inserito un collegamento, seleziona il testo dell’etichetta del collegamento.

1. Nelle impostazioni del componente, selezionare **[!UICONTROL Underline link]** per sottolineare il testo dell&#39;etichetta del collegamento.

   ![](assets/stylelinks-selecttext.png)

1. Per selezionare il contesto di esplorazione in cui verrà aperto il collegamento, selezionare **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Per cambiare il colore del collegamento, fare clic su **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Scegliete il colore desiderato.

   ![](assets/stylelinks-colorchanged.png)

1. Salva le modifiche.

## Aggiunta di attributi di stile in linea {#adding-inline-styling-attributes}

Nell’interfaccia di E-mail Designer, quando selezioni un elemento e visualizzane le impostazioni nel pannello laterale, puoi personalizzare gli attributi in linea e il loro valore per quell’elemento specifico.

1. Seleziona un elemento nel contenuto.
1. Nel pannello laterale, cerca le impostazioni **[!UICONTROL Styles Inline]**.

   ![](assets/email_designer_inlineattributes.png)

1. Modificare i valori degli attributi esistenti o aggiungerne di nuovi utilizzando il pulsante **+**. Puoi aggiungere qualsiasi attributo e valore conforme a CSS.

Lo stile viene quindi applicato all’elemento selezionato. Se per gli elementi secondari non sono definiti attributi di stile specifici, viene ereditato lo stile dell’elemento principale.
