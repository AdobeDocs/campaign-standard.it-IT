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
ht-degree: 23%

---

# Gestione degli stili delle e-mail {#managing-styles}


In E-mail Designer, quando selezioni un elemento, diverse opzioni specifiche per il tipo di contenuto selezionato vengono visualizzate nella finestra di dialogo **[!UICONTROL Settings]** riquadro. Puoi utilizzare queste opzioni per modificare facilmente lo stile dell’e-mail.

## Selezione di un elemento {#selecting-an-element}

Per selezionare un elemento nell’interfaccia di E-mail Designer, puoi effettuare le seguenti operazioni:

* fai clic direttamente nell’e-mail,
* oppure sfogliare la struttura ad albero disponibile dalle opzioni situate a sinistra **Palette**.

![](assets/des_tree_structure.png)

La navigazione nella struttura ad albero consente di effettuare una selezione più accurata. Puoi selezionare una delle seguenti opzioni:

* l&#39;intera componente della struttura,
* una delle colonne che compongono il componente struttura,
* o solo un componente che si trova all’interno di una colonna.

![](assets/des_tree_structure_selection.png)

Per selezionare una colonna, puoi anche effettuare le seguenti operazioni:

1. Seleziona un componente struttura (direttamente nel messaggio e-mail o utilizzando la struttura ad albero disponibile a sinistra **Palette**).
1. Da **barra degli strumenti contestuale**, fai clic su **[!UICONTROL Select a column]** per scegliere la colonna desiderata.

Vedi un esempio in [questa sezione](#example--adjusting-vertical-alignment-and-padding).

## Regolazione delle impostazioni di stile {#adjusting-style-settings}

1. Seleziona un elemento nel messaggio e-mail. Per ulteriori informazioni, consulta [Selezione di un elemento](#selecting-an-element).
1. Regola le impostazioni in base alle tue esigenze. Ogni elemento selezionato offre un set di impostazioni diverso.

   È possibile inserire sfondi, modificare le dimensioni, modificare l&#39;allineamento orizzontale o verticale, gestire i colori, aggiungere [margine](#selecting-an-element)e così via.

   A questo scopo, utilizza le opzioni visualizzate nella **[!UICONTROL Settings]** riquadro o [aggiungere attributi di stile in linea](#adding-inline-styling-attributes).

   ![](assets/des_settings_pane.png)

1. Salva il contenuto.

## Regolazione della spaziatura e del margine {#about-padding-and-margin}

L’interfaccia di E-mail Designer consente di regolare rapidamente le impostazioni di spaziatura e margini.

**[!UICONTROL Padding]**: questa impostazione consente di gestire lo spazio che si trova all’interno del bordo di un elemento.

![](assets/des_padding.png)

Ad esempio:

* Utilizza la spaziatura per impostare i margini a sinistra e a destra di un’immagine.
* Utilizza la spaziatura superiore e inferiore per aggiungere più spazio a una **[!UICONTROL Text]** o **[!UICONTROL Divider]** componente.
* Per impostare i bordi tra le colonne all’interno di un elemento struttura, definire la spaziatura per ciascuna colonna.

**[!UICONTROL Margin]**: questa impostazione consente di gestire lo spazio tra il bordo dell’elemento e l’elemento successivo.

![](assets/des_margin.png)

>[!NOTE]
>
>A seconda della selezione (componente struttura, colonna o componente contenuto), il risultato non sarà lo stesso. L&#39;Adobe consiglia di impostare **[!UICONTROL Padding]** e **[!UICONTROL Margin]** a livello di colonna.

Per entrambi **[!UICONTROL Padding]** e **[!UICONTROL Margin]**, fai clic sull’icona Blocca per interrompere la sincronizzazione tra i parametri superiore e inferiore o tra quelli destro e sinistro. Questo consente di regolare separatamente ogni parametro.

![](assets/des_padding_lock_icon.png)

## Allineamento dello stile {#about-alignment}

* **Allineamento testo**: posizionare il cursore del mouse su un testo e utilizzare la barra degli strumenti contestuale per allinearlo.

   ![](assets/des_text_alignment.png)

* **Allineamento orizzontale** può essere applicata a testo, immagini e pulsanti; al momento non al **[!UICONTROL Divider]** e **[!UICONTROL Social]** componenti.

   ![](assets/des_horizontal_alignment.png)

* Per impostare **allineamento verticale**, seleziona una colonna all’interno di un componente struttura e scegli un’opzione dal riquadro Impostazioni .

   ![](assets/des_set_vertical_alignment.png)

## Impostazione degli sfondi {#about-backgrounds}

>[!CONTEXTUALHELP]
>id="ac_edition_backgroundimage"
>title="Impostazioni dello sfondo"
>abstract="E-mail Designer consente di personalizzare il colore di sfondo o l’immagine di sfondo per il contenuto. L’immagine di sfondo non è supportata da tutti i client e-mail."

Per impostare lo sfondo con E-mail Designer, Adobe consiglia quanto segue:

1. Se richiesto dal tuo design, applica un colore di sfondo al corpo dell’e-mail.
1. Nella maggior parte dei casi, imposta i colori di sfondo a livello di colonna.
1. Evita di utilizzare i colori di sfondo su componenti immagine o testo, poiché sono difficili da gestire.

Di seguito sono riportate le impostazioni di sfondo disponibili.

* Imposta un **[!UICONTROL Background color]** per l&#39;intera e-mail. Assicurati di selezionare le impostazioni del corpo nella struttura di navigazione accessibile dalla palette a sinistra.

   ![](assets/des_background_body.png)

* Per impostare lo stesso colore di sfondo per tutti i componenti struttura, seleziona **[!UICONTROL Viewport background color]**. Questa opzione consente di selezionare un’impostazione diversa dal colore di sfondo.

   ![](assets/des_background_viewport.png)

* Imposta un colore di sfondo diverso per ciascun componente della struttura. Selezionare una struttura nell&#39;albero di navigazione accessibile dalla palette a sinistra per applicare un colore di sfondo specifico solo a tale struttura.

   ![](assets/des_background_structure.png)

   Assicurati di non impostare un colore di sfondo del riquadro di visualizzazione, in quanto questo potrebbe nascondere i colori di sfondo della struttura.

* Imposta un **[!UICONTROL Background image]** per il contenuto di un componente struttura.

   ![](assets/des_background_image.png)

   >[!NOTE]
   >
   >Alcuni programmi e-mail non supportano le immagini di sfondo. Se non supportato, verrà utilizzato il colore di sfondo della riga. Assicurati di selezionare un colore di sfondo di fallback appropriato nel caso in cui l’immagine non possa essere visualizzata.

* Imposta un colore di sfondo a livello di colonna.

   ![](assets/des_background_column.png)

   >[!NOTE]
   >
   >Questo è il caso d’uso più comune. Adobe consiglia di impostare i colori di sfondo a livello di colonna, in quanto ciò consente una maggiore flessibilità nella modifica dell’intero contenuto dell’e-mail.

   Puoi anche impostare un’immagine di sfondo a livello di colonna, ma questa viene utilizzata raramente.

### Esempio: regolazione dell&#39;allineamento verticale e della spaziatura {#example--adjusting-vertical-alignment-and-padding}

È necessario regolare la spaziatura e l’allineamento verticale all’interno di un componente struttura composto da tre colonne. A tale scopo, segui la procedura indicata di seguito:

1. Seleziona il componente struttura direttamente nel messaggio e-mail o utilizza la struttura ad albero disponibile a sinistra **Palette**.
1. Da **barra degli strumenti contestuale**, fai clic su **[!UICONTROL Select a column]** e scegli quello da modificare. È inoltre possibile selezionarlo dalla struttura ad albero.

   ![](assets/des_selecting_column.png)

   I parametri modificabili per quella colonna vengono visualizzati nella **[!UICONTROL Settings]** a destra.

1. Sotto **[!UICONTROL Vertical alignment]**, seleziona **[!UICONTROL Up]**.

   ![](assets/des_vertical_alignment.png)

   Il componente contenuto viene visualizzato sopra la colonna .

1. Sotto **[!UICONTROL Padding]**, definisci la spaziatura superiore all’interno della colonna. Fai clic sull’icona Blocca per interrompere la sincronizzazione con la spaziatura inferiore.

   Definisci la spaziatura sinistra e destra per la colonna.

   ![](assets/des_adjusting_padding.png)

1. Procedi in modo simile per regolare l’allineamento e la spaziatura delle altre colonne.

   ![](assets/des_adjusting_columns.png)

1. Salva le modifiche.

## Collegamenti di stile {#about-styling-links}

In E-mail Designer è possibile sottolineare un collegamento e selezionarne il colore e la destinazione.

1. In un componente in cui viene inserito un collegamento, seleziona il testo dell’etichetta del collegamento.

1. Nelle impostazioni del componente, seleziona **[!UICONTROL Underline link]** per sottolineare il testo dell’etichetta del collegamento.

   ![](assets/stylelinks-selecttext.png)

1. Per selezionare il contesto di navigazione in cui verrà aperto il collegamento, seleziona una **[!UICONTROL Target]**.

   ![](assets/stylelinks-target.png)

1. Per modificare il colore del collegamento, fai clic su **[!UICONTROL Link color]**.

   ![](assets/stylelinks-colorpicker.png)

1. Scegli il colore di cui hai bisogno.

   ![](assets/stylelinks-colorchanged.png)

1. Salva le modifiche.

## Aggiunta di attributi di stile in linea {#adding-inline-styling-attributes}

Nell’interfaccia di E-mail Designer, quando selezioni un elemento e ne visualizzi le impostazioni nel pannello laterale, puoi personalizzare gli attributi in linea e il relativo valore per quell’elemento specifico.

1. Seleziona un elemento nel contenuto.
1. Nel pannello laterale, cerca il **[!UICONTROL Styles Inline]** impostazioni.

   ![](assets/email_designer_inlineattributes.png)

1. Modificare i valori degli attributi esistenti o aggiungerne di nuovi utilizzando il **+** pulsante . Puoi aggiungere qualsiasi attributo e valore conforme a CSS.

Lo stile viene quindi applicato all’elemento selezionato. Se per gli elementi secondari non sono definiti attributi di stile specifici, viene ereditato lo stile dell’elemento principale.
