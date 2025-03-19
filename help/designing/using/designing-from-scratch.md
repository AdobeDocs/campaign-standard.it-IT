---
title: Progettazione di e-mail da zero
description: Scopri come progettare e-mail da zero nel contenuto delle e-mail in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 052d24b7-d3e0-41d7-8b2c-92bd3addb3a2
source-git-commit: 0079a924db522de8afc628ef50aa2c861e5a12ee
workflow-type: tm+mt
source-wordcount: '1229'
ht-degree: 22%

---

# Progettazione di e-mail da zero {#designing-an-email-content-from-scratch}

Scopri come padroneggiare l’edizione dei contenuti delle e-mail. Con E-mail Designer puoi creare e-mail e modelli a partire da con o senza i contenuti predefiniti.

Di seguito sono riportati i passaggi principali per creare e progettare un contenuto e-mail da zero utilizzando E-mail Designer:

1. Crea un messaggio e-mail e apri il relativo contenuto.
1. Aggiungi componenti struttura per modellare l’e-mail. Consulta [Modifica della struttura delle e-mail](#defining-the-email-structure).
1. Inserire componenti di contenuto e frammenti nei componenti della struttura. Consulta [Aggiunta di frammenti e componenti di contenuto](#defining-the-email-structure).
1. Aggiungi le immagini e modifica il testo dell’e-mail. Vedere [Inserimento di immagini](../../designing/using/images.md#inserting-images).
1. Personalizza la tua e-mail aggiungendo campi di personalizzazione, collegamenti e così via. Consulta [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field), [Inserimento di un collegamento](../../designing/using/links.md#inserting-a-link) e [Definizione del contenuto dinamico in un messaggio e-mail](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).
1. Definisci l’oggetto dell’e-mail. Consulta [Personalizzazione dell&#39;oggetto di un&#39;e-mail](../../designing/using/subject-line.md#defining-the-subject-line-of-an-email).
1. Visualizza l’anteprima del messaggio e-mail.
1. Salva il contenuto e continua con il messaggio dopo esserti assicurato di aver definito un pubblico e pianificato correttamente l’invio.

Puoi anche guardare questo [video introduttivo](https://video.tv.adobe.com/v/22771/?autoplay=true&hidetitle=true).

>[!NOTE]
>
>Per evitare di progettare contenuti e-mail da zero, puoi utilizzare modelli di contenuto preconfigurati. Per ulteriori informazioni, consulta [Modelli di contenuto](../../designing/using/using-reusable-content.md#content-templates).

## Definizione della struttura delle e-mail {#defining-the-email-structure}

>[!CONTEXTUALHELP]
>id="ac_structure_components"
>title="Informazioni sui componenti struttura"
>abstract="I componenti struttura definiscono il layout del messaggio e-mail."

>[!CONTEXTUALHELP]
>id="ac_edition_columns"
>title="Definizione delle colonne nell’e-mail"
>abstract="E-mail Designer consente di definire facilmente il layout dell’e-mail definendone la struttura a colonne."

E-mail Designer consente di definire facilmente la struttura delle e-mail. Aggiungendo e spostando elementi strutturali con semplici azioni di trascinamento della selezione, puoi progettare la forma dell’e-mail in pochi secondi.

Per modificare la struttura di un messaggio e-mail:

1. Apri un contenuto esistente o creane uno nuovo.
1. Accedi a **[!UICONTROL Structure components]** selezionando l&#39;icona **+** a sinistra.

   ![](assets/email_designer_structure.png)

1. Trascina e rilascia i componenti struttura necessari per modellare l’e-mail.

   ![](assets/email_designer_structure_components.png)

   Una linea blu materializza l&#39;esatta posizione dei componenti della struttura prima di rilasciarla. Puoi rilasciarlo sopra, tra o sotto qualsiasi altro componente, ma non all’interno.

   >[!NOTE]
   >
   >La pila di colonne non è compatibile con tutti i programmi e-mail. Quando non è supportata, le colonne non vengono impilate.
   >
   >Una volta inseriti nell’e-mail, non puoi spostare o rimuovere i componenti a meno che non sia già presente un componente di contenuto o un frammento al suo interno.

1. Sono disponibili diversi componenti di struttura composti da una o più colonne.

   Seleziona il componente **[!UICONTROL n:n column]** per definire il numero di colonne desiderato (tra 3 e 10). Per definire la larghezza di ogni colonna, sposta le frecce nella parte inferiore di ciascuna colonna.

   ![](assets/email_designer_n-n-column.png)

   >[!NOTE]
   >
   >Le dimensioni di ogni colonna non possono essere inferiori al 10% della larghezza totale del componente struttura. Non è possibile rimuovere una colonna non vuota.

Una volta definita la struttura, puoi aggiungere frammenti di contenuto e componenti all’e-mail.

## Utilizzo di una pre-intestazione {#preheader}

>[!CONTEXTUALHELP]
>id="ac_edition_preheader"
>title="Utilizzo di una pre-intestazione"
>abstract="La pre-intestazione consente di configurare un breve testo di riepilogo che fornirà un tasso di apertura più alto dell’e-mail."

Un preheader è un breve testo di riepilogo che segue la riga dell’oggetto quando si visualizza un messaggio e-mail dalla casella in entrata. Il preheader fornisce un tasso di apertura più alto.

Selezionare la casella di modifica **[!UICONTROL Preheader]** e completare il contenuto.

![](assets/email_designer_preheader.png)

È possibile aggiungere **[!UICONTROL Content block]**, **[!UICONTROL Dynamic content]** o **[!UICONTROL Personalization fields]** nel contenuto del preheader.

>[!NOTE]
>
>La preintestazione non è compatibile con tutti i programmi e-mail. Quando non è supportata, non viene visualizzata.

## Utilizzo dei componenti per contenuti {#about-content-components}

>[!CONTEXTUALHELP]
>id="ac_content_components"
>title="Informazioni sui componenti per contenuti"
>abstract="I componenti per contenuti sono dei segnaposto di contenuto vuoti che possono essere modificati per creare un’email."

I componenti di contenuto sono componenti vuoti e non elaborati che possono essere modificati una volta inseriti in un messaggio e-mail.

In un componente struttura puoi aggiungere tutti i componenti di contenuto desiderati. Puoi anche spostarli all’interno del componente struttura o in un altro componente struttura.

Elenco dei componenti disponibili in E-mail Designer:

### **[!UICONTROL Button]**

Se è necessario utilizzare più pulsanti, anziché modificare ogni pulsante da zero, è possibile duplicare il componente **[!UICONTROL Button]** utilizzando la barra degli strumenti contestuale.

Puoi anche salvare i pulsanti in frammenti che possono essere riutilizzati. Per ulteriori informazioni, vedere [Creazione di un frammento di contenuto](../../designing/using/using-reusable-content.md#creating-a-content-fragment) e [Salvataggio del contenuto come frammento](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

Selezionare **[!UICONTROL Fallback view]** per visualizzare l&#39;immagine di fallback in E-mail Designer.

### **[!UICONTROL Text]**

Utilizza questo componente per inserire testo nell’e-mail. È possibile regolare il colore, lo stile e la dimensione del testo in **[!UICONTROL Component Settings]**.

### **[!UICONTROL Divider]**

Utilizza questo componente per inserire una linea di divisione nell’e-mail. È possibile selezionare il colore, lo stile e le dimensioni della linea di interruzione in **[!UICONTROL Component Settings]**.

### **[!UICONTROL HTML]**

Utilizza questo componente per copiare e incollare le diverse parti del HTML esistente. Questo consente di creare componenti HTML modulari gratuiti.

>[!NOTE]
>
>Un componente HTML gratuito è modificabile con opzioni limitate. Se tutti gli stili non sono allineati, assicurati di aggiungere il CSS corretto nella sezione **head** del codice HTML, altrimenti l&#39;e-mail non sarà reattiva. Utilizza il pulsante **[!UICONTROL Preview]** per verificare la reattività del contenuto (vedi [Anteprima dei messaggi](../../sending/using/previewing-messages.md)).

Per rendere semplicemente un contenuto esterno conforme a E-mail Designer, Adobe consiglia di creare un messaggio da zero e copiare il contenuto dall’e-mail esistente in frammenti e componenti.

Se il contenuto non può essere ricreato, è possibile copiare e incollare il codice HTML dall&#39;e-mail originale utilizzando il componente di contenuto **[!UICONTROL Html]**. Prima di procedere, accertarsi di avere familiarità con HTML.

>[!NOTE]
>
>Il nuovo contenuto non sarà la copia esatta dell’e-mail originale, ma i passaggi seguenti ti guideranno attraverso la creazione di un messaggio che sarà più simile possibile.

**Prima di copiare il contenuto**

1. Nell’e-mail originale, identifica le sezioni riutilizzabili dalle sezioni che saranno univoche per ogni e-mail che invierai.
1. Salva tutte le immagini e le risorse che desideri utilizzare.
1. Se hai familiarità con HTML, suddividi il contenuto originale di HTML in parti diverse.

### Video {#video-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_video"
>title="Impostazioni video"
>abstract="Utilizza questo componente per inserire un video nell’e-mail. Tieni presente che i video non funzionano su tutti i client e-mail. È consigliabile impostare un’immagine di fallback."

Inserire il componente video in un componente struttura del messaggio e-mail e immettere il collegamento video in **[!UICONTROL Component Settings]**.

>[!NOTE]
>
>Il video non è compatibile con tutti i programmi e-mail. Quando non è supportato, viene visualizzato il fallback.

### Immagine

Utilizza questo componente per inserire un’immagine nell’e-mail.

Inserisci il componente immagine in un componente struttura e fai clic su Sfoglia per caricare un file immagine dal computer.

### **[!UICONTROL Social]**

Utilizza questo componente per inserire collegamenti a pagine di social media nel messaggio e-mail. È possibile selezionare i collegamenti da visualizzare e le dimensioni della relativa icona in **[!UICONTROL Component Settings]**.

### Carosello {#carousel-settings}

>[!CONTEXTUALHELP]
>id="ac_edition_carousel"
>title="Impostazioni carosello"
>abstract="Scopri come inserire e configurare un carosello nel contenuto. Tieni presente che il carosello non funziona su tutti i client e-mail e, nel caso in cui non sia supportato, sarà visualizzata un’immagine di fallback."

1. Trascina e rilascia il componente **[!UICONTROL Carousel]** all&#39;interno di un componente struttura.
1. Sfoglia per selezionare le immagini dal computer.

   ![](assets/des_carousel_browse.png)

1. Nel riquadro **[!UICONTROL Settings]** impostare il numero di miniature desiderate nel carosello.
1. Seleziona un’immagine di fallback dal computer.

   ![](assets/des_carousel_fallback.png)

Il componente Carosello non è compatibile con tutti i programmi e-mail. Carica un fallback per visualizzare un’immagine quando il carosello non è supportato nell’e-mail.

>[!NOTE]
>
>Il componente Carosello è compatibile con le seguenti piattaforme e-mail: Apple Mail 7, Apple Mail 8, Outlook 2011 per Mac, Outlook 2016 per Mac, Mozilla Thunderbird, iPad e iPad mini iOS, iPhone iOS, Android, AOL (Chrome, Firefox e Safari).

**Argomenti correlati**:

- [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
- [Selezione di un pubblico in un messaggio](../../audiences/using/selecting-an-audience-in-a-message.md)
- [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)
- [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
- [Rendering di e-mail](../../sending/using/email-rendering.md)
