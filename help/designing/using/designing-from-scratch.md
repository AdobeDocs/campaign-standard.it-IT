---
title: 'Progettazione di e-mail da zero '
description: Scoprite come progettare e-mail da contenuti e-mail nuovi in Designer e-mail.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 2%

---


# Progettazione di e-mail da zero {#designing-an-email-content-from-scratch}

Scopri come gestire l’edizione del contenuto delle e-mail. Designer e-mail consente di creare e-mail e modelli a partire dal contenuto predefinito.

Di seguito sono riportati i passaggi principali per creare e progettare un contenuto di e-mail da zero tramite Designer e-mail:

1. Create un’e-mail e apritene il contenuto.
1. Aggiungete componenti struttura per dare forma al messaggio e-mail. Consultate [Modifica della struttura](#defining-the-email-structure)delle e-mail.
1. Inserire componenti e frammenti di contenuto nei componenti della struttura. Vedere [Aggiunta di frammenti e componenti](#defining-the-email-structure)di contenuto.
1. Aggiungete le immagini e modificate il testo del messaggio e-mail. Consultate [Inserimento di immagini](../../designing/using/images.md#inserting-images).
1. Personalizza la tua e-mail aggiungendo campi di personalizzazione, collegamenti e così via. Consultate [Inserimento di un campo](../../designing/using/personalization.md#inserting-a-personalization-field)di personalizzazione, [Inserimento di un collegamento](../../designing/using/links.md#inserting-a-link) e [Definizione di contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Definite l’oggetto del messaggio e-mail. See [Personalizing the subject line of an email](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Visualizzare l’anteprima del messaggio e-mail.
1. Salvate il contenuto e continuate con il messaggio dopo aver definito un&#39;audience e pianificato correttamente l&#39;invio.

Potete anche guardare questo video [](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true&captions=ita)introduttivo.

>[!NOTE]
>
>Per evitare di progettare contenuti per e-mail da zero, potete utilizzare modelli di contenuto pronti per l’uso. Per ulteriori informazioni, consulta Modelli [di](../../designing/using/using-reusable-content.md#content-templates)contenuto.

## Definizione struttura e-mail {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Informazioni sui componenti Struttura"
>abstract="I componenti della struttura definiscono il layout del messaggio e-mail."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definizione delle colonne e-mail"
>abstract="Designer e-mail consente di definire facilmente il layout dell&#39;e-mail definendo la struttura delle colonne."

Designer e-mail consente di definire facilmente la struttura dell&#39;e-mail. Aggiungendo e spostando elementi strutturali con semplici azioni di trascinamento, potete progettare la forma dell’e-mail in pochi secondi.

Per modificare la struttura di un messaggio e-mail:

1. Aprite un contenuto esistente o create un nuovo contenuto e-mail.
1. Per accedere al modulo, **[!UICONTROL Structure components]** selezionate l’icona **+** a sinistra.

   ![](assets/email_designer_structure.png)

1. Trascinate e rilasciate i componenti della struttura necessari per modellare il messaggio e-mail.

   ![](assets/email_designer_structure_components.png)

   Una linea blu materializza la posizione esatta dei componenti della struttura prima di rilasciarla. È possibile rilasciarlo sopra, tra o sotto qualsiasi altro componente, ma non all’interno.

   >[!NOTE]
   >
   >Lo stack di colonne non è compatibile con tutti i programmi e-mail. Se non è supportato, le colonne non verranno sovrapposte.
   >
   >Una volta inserito nell’e-mail, non è possibile spostare né rimuovere i componenti a meno che non sia già presente un componente di contenuto o un frammento all’interno.

1. Sono disponibili diversi componenti di struttura composti da una o più colonne.

   Selezionate il **[!UICONTROL n:n column]** componente per definire il numero di colonne desiderato (tra 3 e 10). È inoltre possibile definire la larghezza di ciascuna colonna spostando le frecce nella parte inferiore di ciascuna colonna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Ciascuna dimensione di colonna non può essere inferiore al 10% della larghezza totale del componente struttura. Non è possibile rimuovere una colonna non vuota.

Una volta definita la struttura, potete aggiungere frammenti di contenuto e componenti all’e-mail.

## Utilizzo di una preintestazione {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Utilizzo di una preintestazione"
>abstract="La preintestazione consente di configurare un breve testo di riepilogo che fornirà una frequenza di apertura più elevata per l’e-mail."

Un preintestazione è un breve testo di riepilogo che segue l’oggetto quando visualizzate un’e-mail dalla inbox. La preintestazione offre una frequenza di apertura più elevata.

Selezionate la casella di **[!UICONTROL Preheader]** modifica e completate il contenuto.

![](assets/email_designer_preheader.png)

Potete aggiungere un **[!UICONTROL Content block]**, un **[!UICONTROL Dynamic content]** o un **[!UICONTROL Personalization fields]** elemento nel contenuto della preintestazione.

>[!NOTE]
>
>Preheader non è compatibile con tutti i programmi e-mail. Se non è supportato, preheader non viene visualizzato.


## Utilizzo dei componenti di contenuto {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Informazioni sui componenti Contenuto"
>abstract="I componenti contenuto sono segnaposto vuoti che potete modificare per creare un messaggio e-mail."

I componenti contenuto sono componenti vuoti e non elaborati che possono essere modificati una volta inseriti in un messaggio e-mail.

È possibile aggiungere tutti i componenti di contenuto desiderati in un componente struttura. È inoltre possibile spostarle all’interno del componente struttura o in un altro componente struttura.

Elenco dei componenti disponibili in Designer e-mail:

### **[!UICONTROL Button]**

Se è necessario utilizzare più pulsanti, anziché modificare ciascun pulsante da zero, è possibile duplicare il **[!UICONTROL Button]** componente utilizzando la barra degli strumenti contestuale.

È inoltre possibile salvare i pulsanti nei frammenti da riutilizzare. Per ulteriori informazioni, vedere [Creazione di un frammento](../../designing/using/using-reusable-content.md#creating-a-content-fragment) di contenuto e [Salvataggio del contenuto come frammento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Selezionare **[!UICONTROL Fallback view]** per visualizzare l&#39;immagine di fallback in Designer e-mail.

### **[!UICONTROL Text]**

    Usate questo componente per inserire del testo nel messaggio e-mail. È possibile regolare colore, stile e dimensione del testo in **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

    Usate questo componente per inserire una linea di divisione nell’e-mail. È possibile selezionare il colore, lo stile e la dimensione della linea di rottura in **[!UICONTROL Component Settings]**.

### **[!UICONTROL Html]**

Usate questo componente per copiare e incollare le diverse parti dell’HTML esistente. Questo consente di creare componenti HTML modulari gratuiti.

>[!NOTE]
>
>Un componente HTML gratuito può essere modificato con opzioni limitate. Se tutti gli stili non sono allineati, accertatevi di aggiungere il CSS appropriato nella sezione **head** del codice HTML, altrimenti l&#39;e-mail non sarà reattiva. Utilizzate il **[!UICONTROL Preview]** pulsante per verificare la reattività del contenuto (consultate [Anteprima dei messaggi](../../sending/using/previewing-messages.md)).

Per rendere un contenuto esterno conforme a E-mail Designer,  Adobe consiglia di creare un messaggio da zero e di copiare il contenuto del messaggio e-mail esistente in frammenti e componenti.

Se un contenuto non può essere ricreato, potete copiare e incollare il codice HTML dall’e-mail originale utilizzando il componente **[!UICONTROL Html]** contenuto. Prima di continuare, assicuratevi di avere familiarità con il codice HTML.

<!-- A full example is presented below. -->

>[!NOTE]
>
>Il nuovo contenuto non sarà la copia esatta dell&#39;e-mail originale, ma i passaggi seguenti vi guideranno attraverso la creazione di un messaggio che sarà il più vicino possibile.

    **Prima di copiare il contenuto**
    
    1. Nel messaggio e-mail originale, identificate le sezioni riutilizzabili dalle sezioni che saranno univoche per ogni e-mail che invierete.
    1. Salvate tutte le immagini e le risorse da usare.
    1. Se avete familiarità con l’HTML, dividete il contenuto HTML originale in parti diverse.

### Video {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Impostazioni video"
>abstract="Usate questo componente per inserire un video nel messaggio e-mail. I video non funzionano su tutti i client e-mail. Consigliamo di impostare un&#39;immagine di fallback."
>additional-url="https://www.emailonacid.com/blog/article/email-development/a_how_to_guide_to_embedding_html5_video_in_email/" text="Informazioni aggiuntive"


Inserite il componente video in un componente struttura del messaggio e-mail e inserite il collegamento video nel **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Il video non è compatibile con tutti i programmi e-mail. Se non è supportato, verrà visualizzato il fallback.

### Immagine

Usate questo componente per inserire un’immagine nel messaggio e-mail.

Inserite il componente immagine in un componente struttura e fate clic su Sfoglia per caricare un file immagine dal computer.

### **[!UICONTROL Social]**

Usate questo componente per inserire i collegamenti alle pagine dei social media nel messaggio e-mail. Potete selezionare i collegamenti da visualizzare e le dimensioni della relativa icona in **[!UICONTROL Component Settings]**.

### Carosello {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Impostazioni carosello"
>abstract="Scoprite come inserire e configurare un carosello nel contenuto.Notate che il carosello non funziona su tutti i client di posta elettronica e che l&#39;immagine di fallback verrà visualizzata nel caso in cui non sia supportata."

1. Trascinare il **[!UICONTROL Carousel]** componente all’interno di un componente struttura.
1. Consente di selezionare le immagini dal computer.

   ![](assets/des_carousel_browse.png)

1. Nel **[!UICONTROL Settings]** riquadro, impostare il numero di miniature desiderato.
1. Selezionate un’immagine di fallback dal computer.

   ![](assets/des_carousel_fallback.png)

Il componente carosello non è compatibile con tutti i programmi e-mail. Caricate un fallback per visualizzare un&#39;immagine invece quando il carosello non è supportato nell&#39;e-mail.

>[!NOTE]
>
>Il componente carosello è compatibile con le seguenti piattaforme di posta elettronica: Apple Mail 7, Apple Mail 8, Outlook 2011 per Mac, Outlook 2016 per Mac, Mozilla Thunderbird, iPad e iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox e Safari).

**Argomenti correlati**:

- [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
- [Selezione di un pubblico in un messaggio](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)
- [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
- [Rendering di e-mail](../../sending/using/email-rendering.md)
