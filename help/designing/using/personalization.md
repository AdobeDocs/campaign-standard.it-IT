---
solution: Campaign Standard
product: campaign
title: Personalizzazione del contenuto delle e-mail
description: Scopri come personalizzare un’e-mail in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3ea58bcf-234e-4dac-b296-da3f57e18a7d
source-git-commit: 671fd9e7ff0551ae9ae5fec26cee0b4c4939ab2f
workflow-type: tm+mt
source-wordcount: '2583'
ht-degree: 4%

---

# Personalizzazione del contenuto delle e-mail {#personalization}

Il contenuto e la visualizzazione dei messaggi inviati da Adobe Campaign possono essere personalizzati in diversi modi. Questi modi possono essere combinati in base a criteri a seconda dei profili. In generale, Adobe Campaign ti consente di:

* Inserire campi di personalizzazione dinamici. Consulta [Inserimento di un campo di personalizzazione](#inserting-a-personalization-field).
* Inserire blocchi di personalizzazione predefiniti. Consulta [Aggiunta di un blocco di contenuto](#adding-a-content-block).
* Personalizza il mittente di un’e-mail. Consulta [Personalizzazione del mittente](#personalizing-the-sender).
* Personalizza l’oggetto di un’e-mail. Consulta [Personalizzazione dell’oggetto di un messaggio e-mail](../../designing/using/subject-line.md#subject-line).
* Creare contenuto condizionale. Consulta [Definizione del contenuto dinamico in un messaggio e-mail](#defining-dynamic-content-in-an-email).

## Personalizzazione del mittente {#personalizing-the-sender}

Per definire il nome del mittente che verrà visualizzato nell’intestazione dei messaggi inviati, vai alla scheda **[!UICONTROL Properties]** della home page di E-mail Designer (accessibile tramite l’icona Home). Per ulteriori informazioni, consulta [Definizione del mittente di un’e-mail](../../designing/using/subject-line.md#email-sender).

Puoi modificare il nome del mittente facendo clic sul blocco **Nome mittente** . Il campo diventa quindi modificabile e puoi immettere il nome che desideri utilizzare.

Questo campo può essere personalizzato. A questo scopo, fai clic sulle icone sotto il nome del mittente per aggiungere campi di personalizzazione, blocchi di contenuto e contenuto dinamico.

>[!NOTE]
>
>I parametri di intestazione non devono essere vuoti. L’indirizzo del mittente è obbligatorio per consentire l’invio di un’e-mail (standard RFC). Adobe Campaign controlla la sintassi degli indirizzi e-mail immessi.

## Personalizzazione degli URL{#personalizing-urls}

Adobe Campaign ti consente di personalizzare uno o più URL nel messaggio aggiungendo campi di personalizzazione, blocchi di contenuto o contenuti dinamici. Per eseguire questa operazione:

1. Inserisci un URL esterno e specifica i relativi parametri. Consulta [Inserimento di un collegamento](../../designing/using/links.md#inserting-a-link).
1. Se non viene visualizzato, fai clic sulla matita accanto all’URL selezionato nel riquadro Impostazioni per accedere alle opzioni di personalizzazione.
1. Aggiungi i campi di personalizzazione, i blocchi di contenuto e il contenuto dinamico che desideri utilizzare.

   ![](assets/des_personalize_links.png)

1. Salva le modifiche.

>[!NOTE]
>
>Quando il meccanismo di firma URL per i collegamenti di tracciamento è disattivato, la personalizzazione degli URL non può essere applicata né al nome di dominio né all’estensione URL. Se la personalizzazione non è corretta, durante l’analisi dei messaggi viene visualizzato un messaggio di errore.
>
>Quando selezioni un blocco di contenuto, non puoi selezionare elementi come **Collega a pagina speculare**. Questo tipo di blocchi è vietato all’interno di un collegamento.

## Inserimento di un campo di personalizzazione{#inserting-a-personalization-field}

Adobe Campaign consente di inserire nella pagina un campo del database, ad esempio il nome del profilo.

>[!NOTE]
>
>Le immagini seguenti mostrano come inserire un campo di personalizzazione utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) per un messaggio e-mail.

Per aggiungere un campo di personalizzazione al contenuto:

1. Fai clic all’interno di un blocco di testo, fai clic sull’icona **[!UICONTROL Personalize]** nella barra degli strumenti contestuale e seleziona **[!UICONTROL Insert personalization field]**. Per ulteriori informazioni sull’interfaccia di E-mail Designer, consulta [questa sezione](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_perso_field_1.png)

1. Seleziona il campo da inserire nel contenuto della pagina.

   ![](assets/email_perso_field_2.png)

1. Fai clic su **[!UICONTROL Confirm]**.

Il nome del campo viene visualizzato nell’editor ed è evidenziato.

![](assets/email_perso_field_3.png)

Una volta generata la personalizzazione (ad esempio, durante l’anteprima e la preparazione dell’e-mail), questo campo verrà sostituito dal valore corrispondente al profilo di destinazione.

>[!NOTE]
>
>Se l’e-mail viene creata da un flusso di lavoro, i dati aggiuntivi calcolati nel flusso di lavoro sono disponibili anche nei campi di personalizzazione. Per ulteriori informazioni sull’aggiunta di dati aggiuntivi da un flusso di lavoro, consulta la sezione [Arricchimento dei dati](../../automating/using/about-targeting-activities.md#enriching-data) .

## Aggiunta di un blocco di contenuto{#adding-a-content-block}

Adobe Campaign offre un elenco di blocchi di contenuto preconfigurati. Questi blocchi di contenuto sono dinamici, personalizzati e hanno un rendering specifico. Ad esempio, puoi aggiungere un saluto o un collegamento alla pagina speculare.

>[!NOTE]
>
>Le immagini seguenti mostrano come inserire un blocco di contenuto utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) per un messaggio e-mail.

Per aggiungere un blocco di contenuto:

1. Fai clic all’interno di un blocco di testo, fai clic sull’icona **[!UICONTROL Personalize]** nella barra degli strumenti contestuale e seleziona **[!UICONTROL Insert content block]**. Per ulteriori informazioni sull’interfaccia di E-mail Designer, consulta [questa sezione](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Seleziona il blocco di contenuto da inserire. I blocchi disponibili variano a seconda del contesto (e-mail o pagina di destinazione).

   ![](assets/email_content_block_2.png)

1. Fai clic su **[!UICONTROL Save]**.

Il nome del blocco di contenuto viene visualizzato nell’editor ed è evidenziato in giallo. Si adatta automaticamente al profilo quando viene generata la personalizzazione.

![](assets/email_content_block_3.png)

I blocchi di contenuto predefiniti sono:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**: Questo blocco di contenuto può essere utilizzato solo in una  **pagina** di destinazione.
* **[!UICONTROL Default sender name (DefaultSenderName)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**: Questo blocco di contenuto può essere utilizzato solo in una  **consegna**.
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

### Creazione di blocchi di contenuto personalizzati {#creating-custom-content-blocks}

Puoi definire nuovi blocchi di contenuto che verranno inseriti in un messaggio o in una pagina di destinazione.

Per creare un blocco di contenuto, effettua le seguenti operazioni:

1. Fai clic su **[!UICONTROL Resources > Content blocks]** nel menu avanzato per accedere all’elenco dei blocchi di contenuto.
1. Fai clic sul pulsante **[!UICONTROL Create]** o duplica un blocco di contenuto preesistente.

   ![](assets/content_bloc_01.png)

1. Immetti un’etichetta.
1. Seleziona il **[!UICONTROL Content type]** del blocco. Sono disponibili tre opzioni:

   * **[!UICONTROL Shared]**: Il blocco di contenuto può essere utilizzato in una consegna o in una pagina di destinazione.
   * **[!UICONTROL Delivery]**: Il blocco di contenuto può essere utilizzato solo in una consegna.
   * **[!UICONTROL Landing page]**: Il blocco di contenuto può essere utilizzato solo in una pagina di destinazione.

   ![](assets/content_bloc_02.png)

1. È possibile selezionare un **[!UICONTROL Targeting dimension]**. Per ulteriori informazioni, consulta [Informazioni sulla dimensione di targeting](#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. Puoi selezionare l’opzione **[!UICONTROL Depends on format]** per definire due blocchi diversi: uno per le e-mail HTML e uno per le e-mail in formato testo. Verranno quindi visualizzate due schede nell’editor (HTML e testo) per definire il contenuto corrispondente.

   ![](assets/content_bloc_03.png)

1. Inserisci il contenuto dei blocchi di contenuto e fai clic sul pulsante **[!UICONTROL Create]** .

Il blocco di contenuto può ora essere utilizzato nell’editor del contenuto di un messaggio o di una pagina di destinazione.

>[!CAUTION]
>
>Durante la modifica del contenuto di un blocco, accertati che non vi siano spazi bianchi aggiuntivi tra l’inizio e la fine delle istruzioni *if* . In HTML gli spazi bianchi vengono visualizzati sullo schermo e avranno quindi un impatto sul layout del contenuto.

### Informazioni sulla dimensione di targeting {#about-targeting-dimension}

La dimensione di targeting ti consente di definire in quale tipo di messaggio puoi utilizzare il blocco di contenuto. In questo modo si evita l’uso di blocchi non appropriati in un messaggio, il che può causare errori.

Infatti, quando modifichi un messaggio, puoi selezionare solo i blocchi di contenuto con una dimensione di targeting compatibile con la dimensione di targeting del messaggio.

Ad esempio, la dimensione di targeting del blocco **[!UICONTROL Unsubscription link]** è **[!UICONTROL Profiles]** perché contiene campi di personalizzazione specifici per la risorsa **[!UICONTROL Profiles]**. Pertanto, non puoi utilizzare un blocco **[!UICONTROL Unsubscription link]** in un messaggio transazionale di evento [](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types), perché la dimensione di targeting di quel tipo di messaggio è **[!UICONTROL Real-time events]**. Tuttavia, puoi utilizzare il blocco **Annulla abbonamento** in un messaggio transazionale di profilo [](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types), perché la dimensione di targeting di quel tipo di messaggio è **Profili**. Infine, il blocco **[!UICONTROL Link to mirror page]** non ha una dimensione di targeting, pertanto puoi utilizzarla in qualsiasi messaggio.

Se lasci vuoto questo campo, il blocco di contenuto sarà compatibile con tutti i messaggi, indipendentemente dalla dimensione di targeting. Se imposti una dimensione di targeting, quel blocco sarà compatibile solo con messaggi che hanno la stessa dimensione di targeting.

Per ulteriori informazioni, consulta [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).

**Argomenti correlati:**

* [Inserimento di un campo di personalizzazione](#inserting-a-personalization-field)
* [Aggiunta di un blocco di contenuto](#adding-a-content-block)
* [Definizione del contenuto dinamico in un messaggio e-mail](#defining-dynamic-content-in-an-email)

## Personalizzazione di un’origine immagine{#personalizing-an-image-source}

Adobe Campaign ti consente di personalizzare una o più immagini nel messaggio in base a un particolare criterio o di utilizzare il tracciamento. A questo scopo, inserisci campi di personalizzazione, blocchi di contenuto o contenuti dinamici nell’origine immagine. Per eseguire questa operazione:

1. Inserisci un’immagine nel contenuto del messaggio oppure seleziona un’immagine già presente.
1. Nella palette Proprietà immagine, seleziona l’opzione **[!UICONTROL Enable personalization]** .

   ![](assets/des_personalize_images_1.png)

   Il campo **[!UICONTROL Source]** viene visualizzato e l&#39;immagine selezionata viene visualizzata come **personalizzata** nell&#39;editor.

1. Fai clic sulla matita accanto al pulsante del campo **[!UICONTROL Source]** per accedere alle opzioni di personalizzazione.
1. Dopo aver aggiunto l’origine immagine, aggiungi i campi di personalizzazione, i blocchi di contenuto e il contenuto dinamico desiderati.

   ![](assets/des_personalize_images_2.png)

   >[!NOTE]
   >
   >Il nome di dominio (http://mydomain.com) non può essere personalizzato, deve essere immesso manualmente. Il resto dell’URL può essere personalizzato. Ad esempio: http://mydomain.com/ `[Gender]` .jpg

1. Conferma le modifiche.

## Contenuto condizionale {#conditional-content}

### Definizione di una condizione di visibilità{#defining-a-visibility-condition}

Puoi specificare una condizione di visibilità su qualsiasi elemento. Sarà visibile solo se la condizione viene rispettata.

Per aggiungere una condizione di visibilità, seleziona un blocco e immetti la condizione da rispettare nel campo **[!UICONTROL Visibility condition]** delle relative impostazioni.

![](assets/delivery_content_5.png)

Questa opzione è disponibile solo per i seguenti elementi: INDIRIZZO, BLOCCO, CENTRO, DIR, DIV, DL, SET DI CAMPI, MODULO, H1, H2, H3, H4, H5, H6, NOSCRIPT, OL, P, PRE, UL, TR, TD.

L’editor di espressioni viene presentato nella sezione [Modifica avanzata delle espressioni](../../automating/using/editing-queries.md#about-query-editor) .

Queste condizioni adottano la sintassi dell&#39;espressione XTK (ad esempio **context.profile.email !=&#39;&#39;** o **context.profile.status=&#39;0&#39;**). Per impostazione predefinita, tutti i campi sono visibili.

>[!NOTE]
>
>Non è possibile definire una condizione per un blocco che contiene già un sottoelemento con un contenuto dinamico o un blocco che costituisce già un contenuto dinamico. Non è possibile modificare i blocchi dinamici non visibili, come gli elenchi a discesa.

### Definizione del contenuto dinamico in un messaggio e-mail{#defining-dynamic-content-in-an-email}

>[!CONTEXTUALHELP]
>id="ac_dynamic_content"
>title="Definizione del contenuto dinamico"
>abstract="Definisci contenuti diversi che verranno visualizzati in alcuni profili solo in base alle condizioni da definire."

In un’e-mail, puoi definire contenuti diversi che verranno visualizzati dinamicamente ai destinatari in base alle condizioni definite tramite l’editor di espressioni. Ad esempio, dalla stessa e-mail, puoi assicurarti che ogni profilo riceva un messaggio diverso a seconda della sua fascia di età.

La definizione del contenuto dinamico è diversa dalla definizione delle condizioni di visibilità ](#defining-a-visibility-condition).[

1. Seleziona un frammento, un componente o un elemento. In questo esempio, seleziona un’immagine.
1. Fai clic sull’icona **[!UICONTROL Dynamic content]** nella barra degli strumenti contestuale.

   ![](assets/dynamic_content_2.png)

   La sezione **[!UICONTROL Dynamic content]** viene visualizzata nella palette a sinistra.

   ![](assets/dynamic_content_3.png)

   Per impostazione predefinita, questa sezione contiene due elementi: la variante predefinita e una nuova variante.

   >[!NOTE]
   >
   >Il contenuto deve sempre avere una variante predefinita. Non è possibile eliminarlo.

1. Fai clic sul pulsante **[!UICONTROL Edit]** per definire le condizioni di visualizzazione della prima variante alternativa.

   ![](assets/dynamic_content_4.png)

1. Specifica un’etichetta e seleziona i campi che desideri impostare come condizioni. Ad esempio, dal nodo **[!UICONTROL General]**, seleziona il campo **[!UICONTROL Age]**

   ![](assets/dynamic_content_5.png)

1. Imposta le condizioni di filtro. Ad esempio, desideri che venga visualizzato un contenuto diverso per le persone di età compresa tra i 18 e i 25 anni.

   ![](assets/dynamic_content_6.png)

1. Una volta impostate tutte le condizioni, definisci l’ordine di priorità in cui verrà applicata la condizione e salva le modifiche.

   ![](assets/dynamic_content_7.png)

   Il contenuto verrà visualizzato nella palette in ordine di priorità, dall’alto verso il basso. Per ulteriori informazioni sulle priorità, consulta [questa sezione](#defining-dynamic-content-in-an-email).

1. Carica una nuova immagine per la variante appena definita.

   ![](assets/dynamic_content_8.png)

   I destinatari di età compresa tra i 18 e i 25 anni vedranno la nuova immagine.

   ![](assets/dynamic_content_10.png)

1. Fai clic su **[!UICONTROL Add a condition]** per aggiungere un nuovo contenuto e la relativa regola collegata.

   ![](assets/dynamic_content_9.png)

   Ad esempio, puoi aggiungere un’immagine diversa da visualizzare alle persone di età compresa tra i 26 e i 35 anni.

1. Procedi in modo simile per qualsiasi altro elemento dell’e-mail che desideri venga visualizzato in modo dinamico. Può essere testo, pulsante, frammento, ecc. Salva le modifiche.

>[!CAUTION]
>
>Dopo aver preparato il messaggio e prima di inviarlo, verificalo utilizzando una bozza. In caso contrario, potrebbero non essere rilevati alcuni errori e l’e-mail potrebbe non essere inviata.

**Argomenti correlati:**

* [Invio di bozze](../../sending/using/sending-proofs.md)
* [Modifica avanzata delle espressioni](../../automating/using/editing-queries.md#about-query-editor)

### Ordine di priorità {#order-of-priority}

Nell’editor espressioni, quando definisci un contenuto dinamico, l’ordine di priorità è il seguente.

1. Definisci due contenuti dinamici diversi con **due condizioni diverse**, ad esempio:

   **Condizione 1:** il genere del profilo è maschile,

   **Condizione 2:** il profilo ha tra i 20 e i 30 anni.

   ![](assets/delivery_content_61.png)

   Alcuni profili nel database corrispondono alle due condizioni, ma è possibile inviare una sola e-mail con un contenuto dinamico.

1. È quindi necessario definire la priorità per il contenuto dinamico. Una condizione con un ordine di priorità di **1** (e quindi il contenuto dinamico corrispondente) verrà inviata a un profilo anche se un’altra condizione il cui ordine di priorità è **2** o **3** viene soddisfatta anche da questo profilo.

   ![](assets/delivery_content_62.png)

Puoi definire un solo ordine di priorità per contenuto dinamico.

## Esempio: Personalizzazione e-mail{#example-email-personalization}

In questo esempio, un membro del team del servizio marketing ha creato un messaggio e-mail per informare alcuni dei suoi clienti che esiste un’offerta speciale solo per loro. Il membro del team ha deciso di personalizzare l’e-mail in base alle rispettive età dei clienti. I clienti di età compresa tra i 18 e i 27 anni riceveranno un&#39;e-mail contenente un&#39;immagine e uno slogan diversi a quelli che riceveranno i clienti di età superiore ai 27 anni.

L’e-mail viene creata come segue:

* I contenuti dinamici vengono applicati all’immagine e questi sono configurati in base all’intervallo di età.

   ![](assets/delivery_content_43.png)

   L’aggiunta e la configurazione del contenuto dinamico sono descritte in dettaglio nella sezione [Definizione del contenuto dinamico in un messaggio e-mail](#defining-dynamic-content-in-an-email) .

* I campi di personalizzazione e il contenuto dinamico vengono applicati al testo. A seconda dell’intervallo di età del profilo, l’e-mail inizia con il nome del profilo o con il titolo e il cognome del profilo.

   ![](assets/delivery_content_44.png)

   L’aggiunta e la configurazione dei campi di personalizzazione sono descritti in dettaglio nella sezione [Inserimento di un campo di personalizzazione](#inserting-a-personalization-field) .

### Configurazione delle immagini {#configuring-images}

>[!CONTEXTUALHELP]
>id="ac_dynamic_image"
>title="Gestione delle immagini dinamiche"
>abstract="Personalizza l’e-mail con immagini dinamiche in base alle condizioni da definire."

In questo esempio, il contenuto dinamico applicato alle immagini è configurato come segue:

**Per raggiungere il 18-27-year-old:**

1. Selezionare il contenuto dinamico nella palette **[!UICONTROL Properties]** e fare clic sul pulsante **[!UICONTROL Edit]**.

   ![](assets/delivery_content_48.png)

1. Modifica l’etichetta, quindi seleziona il campo **[!UICONTROL Age]** dal nodo **[!UICONTROL Profile]** .

   ![](assets/delivery_content_49.png)

1. Seleziona l&#39;operatore **Maggiore o uguale a** , quindi immetti **18** per creare l&#39;espressione **precedente a 18**.

   ![](assets/delivery_content_50.png)

1. Aggiungi una nuova condizione **[!UICONTROL Age]** .

   Seleziona l’operatore **Minore o uguale a** seguito da 27 nel campo del valore per creare l’espressione **inferiore a 27**.

   ![](assets/delivery_content_51.png)

1. Conferma le modifiche.

**Per eseguire il targeting dei profili di età pari o superiore a 27 anni:**

1. Seleziona il contenuto dinamico dalla palette e modificalo.
1. Modifica l’etichetta, quindi seleziona il campo **[!UICONTROL Age]** dal nodo **[!UICONTROL Profile]** .
1. Aggiungi l’operatore **Maggiore di** seguito da 27 nel campo del valore per creare l’espressione **precedente a 27**.

   ![](assets/delivery_content_52.png)

1. Conferma le modifiche.

Il contenuto dinamico è configurato correttamente.

### Configurazione del testo {#configuring-text}

In questo esempio, il contenuto dinamico applicato ai testi è configurato come segue:

**Per eseguire il targeting dei profili di età compresa tra i 18 e i 27 anni:**

1. Seleziona il componente struttura desiderato e aggiungi un contenuto dinamico.
1. Modifica il contenuto dinamico e configura le espressioni di targeting. Fai riferimento a [Configurazione delle immagini](#configuring-images).
1. Nel componente struttura, nella posizione desiderata, fai clic sull’icona **[!UICONTROL Personalize]** nella barra degli strumenti contestuale e seleziona **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. Nell’elenco visualizzato, seleziona il campo **[!UICONTROL First name]** e conferma.

   ![](assets/delivery_content_54.png)

1. Il campo di personalizzazione viene quindi inserito perfettamente nel contenuto dinamico selezionato.

**Per eseguire il targeting dei profili di età pari o superiore a 27 anni:**

1. Seleziona il componente struttura desiderato e aggiungi un contenuto dinamico.
1. Modifica il contenuto dinamico e configura le espressioni di targeting. Fai riferimento a [Configurazione delle immagini](#configuring-images).
1. Nel componente struttura, nella posizione desiderata, fai clic sull’icona **[!UICONTROL Personalize]** nella barra degli strumenti contestuale e seleziona **[!UICONTROL Insert personalization field]**.
1. Seleziona **[!UICONTROL Title]** dall’elenco a discesa.
1. Procedi in modo simile per aggiungere il campo **[!UICONTROL Last name]** .

   ![](assets/delivery_content_56.png)

I campi di personalizzazione devono ora essere inseriti perfettamente nel contenuto dinamico scelto.

### Anteprima delle e-mail {#previewing-emails}

L’anteprima ti consente di verificare che i campi di personalizzazione e il contenuto dinamico siano configurati correttamente prima di inviare il **[!UICONTROL Proofs]**. Durante l’anteprima, puoi selezionare diversi profili di test corrispondenti alle destinazioni e-mail.

Senza profili di test, l’e-mail visualizzata per impostazione predefinita è:

![](assets/delivery_content_45.png)

L’e-mail non contiene campi di personalizzazione nello slogan e viene utilizzata l’immagine predefinita.

Il primo profilo di test corrisponde a un cliente di età compresa tra i 18 e i 27 anni. Selezionando questo profilo, viene visualizzato il seguente messaggio e-mail:

![](assets/delivery_content_46.png)

Il campo di personalizzazione che corrisponde all’espressione 18-27 anni, in particolare il nome del profilo, è configurato correttamente e l’immagine è stata modificata anche in base al profilo.

Il secondo profilo corrisponde a un client di oltre 27 anni e genera il seguente messaggio e-mail:

![](assets/delivery_content_47.png)

L&#39;immagine è cambiata grazie al contenuto dinamico, e lo slogan che appare è lo slogan più formale definito per questo pubblico mirato.

**Argomenti correlati:**

* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)
* [Preparazione dell’invio](../../sending/using/preparing-the-send.md)
