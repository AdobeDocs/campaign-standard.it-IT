---
title: Utilizzo di Email Designer
description: Scoprite il Designer e-mail e come abilita il contenuto della progettazione e-mail.
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
source-wordcount: '929'
ht-degree: 88%

---


# Utilizzo di Email Designer {#email-designer}

## Panoramica di E-mail Designer {#about-the-email-designer}

E-mail designer consente di creare contenuti e modelli di contenuto per le e-mail. È compatibile con e-mail semplici, e-mail transazionali, e-mail di test A/B, e-mail in più lingue ed e-mail ricorrenti.

Per iniziare a utilizzare e-mail designer, guarda questi [video](https://docs.adobe.com/content/help/it-IT/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html#GettingStarted) che illustrano le funzionalità generiche di e-mail designer e mostrano come progettare un’e-mail da zero o utilizzando i modelli.

### Pagina Home di E-mail designer {#email-designer-home-page}

Durante la [creazione di un messaggio e-mail](../../channels/using/creating-an-email.md), la pagina Home viene visualizzata automaticamente selezionando il contenuto dell’e-mail **[!UICONTROL Email Designer]** .

![](assets/email_designer_home_page.png)

La scheda **[!UICONTROL Properties]** consente di modificare i dettagli dell’e-mail, come l’etichetta, l’indirizzo e il nome del mittente o l’oggetto dell’e-mail. È possibile accedere a questa scheda anche facendo clic sull’etichetta dell’e-mail nella parte superiore dello schermo.

![](assets/email_designer_home_properties.png)

La scheda **[!UICONTROL Templates]** consente di scegliere tra i contenuti HTML predefiniti o i modelli già creati per iniziare rapidamente a progettare l’e-mail. Consulta [Modelli di contenuto](../../designing/using/using-reusable-content.md#content-templates).

![](assets/email_designer_home_templates.png)

La scheda **[!UICONTROL Learn & support]** consente di accedere facilmente alla documentazione e alle esercitazioni correlate.

![](assets/email_designer_home_support.png)

Se non si seleziona un modello, la pagina Home di E-mail designer consente anche di scegliere come iniziare a progettare il contenuto:

* Fai clic sul pulsante **[!UICONTROL Create]** per creare un nuovo contenuto da zero. Consulta [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
* Fai clic sul pulsante **[!UICONTROL Upload]** per caricare un file dal computer. Consulta [Importazione di contenuto da un file](../../designing/using/using-existing-content.md#importing-content-from-a-file).
* Fai clic sul pulsante **[!UICONTROL Import from URL]** per recuperare il contenuto esistente da un URL. Consulta [Importazione di contenuto da un URL](../../designing/using/using-existing-content.md#importing-content-from-a-url).

### Interfaccia di E-mail designer {#email-designer-interface}

E-mail designer offre diverse opzioni che consentono di creare, modificare e personalizzare ogni aspetto del contenuto.

L’interfaccia è composta da diverse aree con diverse funzionalità:

![](assets/email_designer_overview.png)

Dagli elementi disponibili nella **Palette** (1), trascina i componenti struttura e i frammenti di contenuto nell’**Area di lavoro** principale (2). Seleziona un componente o un elemento nell’**Area di lavoro** (2) e personalizzane lo stile principale e le caratteristiche di visualizzazione dal riquadro **Impostazioni** (3).

Accedi alle opzioni e alle impostazioni generali dalla **barra degli strumenti** principale (4).

>[!NOTE]
>
>Il riquadro **Impostazioni** può spostarsi a sinistra in base alla risoluzione e alla visualizzazione dello schermo.

![](assets/email_designer_toolbar.png)

La **barra degli strumenti contestuale** dell’interfaccia dell’editor offre diverse funzionalità a seconda della zona selezionata. Contiene i pulsanti di azione e i pulsanti che ti consentono di modificare lo stile del testo. Le modifiche effettuate si applicano sempre alla zona selezionata.

### Terminologia {#terminology}

**Modelli**: i modelli sono strutture di e-mail che puoi creare e riutilizzare per diverse consegne.

**Frammenti**: un frammento è un componente riutilizzabile a cui è possibile fare riferimento in una o più e-mail.

**Componenti struttura**: elementi strutturali che definiscono il layout del messaggio e-mail

**Componenti contenuto**: i componenti contenuto sono componenti vuoti e non elaborati che possono essere modificati una volta inseriti in un messaggio e-mail.

### Best practice per la progettazione dei contenuti {#content-design-best-practices}

Per utilizzare in modo appropriato E-mail designer e creare le e-mail migliori nel modo più semplice possibile, si consiglia di procedere secondo i seguenti principi:

* Utilizza lo stile in linea anziché CSS e CSS separati nella sezione &lt;head> dell’HTML. Utilizzando lo stile in linea, è possibile ottimizzare il salvataggio e il riutilizzo dei frammenti di contenuto.

   Consulta [Aggiunta di attributi di stile in linea](../../designing/using/styles.md#adding-inline-styling-attributes).

* Se importi dei file ZIP contenenti contenuto HTML, utilizza i normali CSS. I fogli di stile SCSS non sono supportati.

* Puoi impostare facilmente il tuo marchio creando e riutilizzando frammenti di contenuto per mantenere la coerenza tra le campagne di marketing.

   Consulta [Creazione di un frammento di contenuto](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

* Durante la modifica del **contenuto e-mail**:

   Visualizza l’anteprima dei messaggi prima di inviarli.  Adobe Campaign offre un modo per testare il rendering delle e-mail tramite Litmus. Per ulteriori informazioni, consulta [Rendering e-mail](../../sending/using/email-rendering.md).

Una maggiore progettazione e best practice generali per i messaggi sono presentate nella sezione seguente: [Best practice di distribuzione](../../sending/using/delivery-best-practices.md)

### Limiti di E-mail Designer {#email-designer-limitations}

* Non è possibile utilizzare campi di personalizzazione in un frammento. Per ulteriori informazioni sui frammenti, consulta [questa sezione](../../designing/using/using-reusable-content.md#about-fragments).

<!--* You cannot save directly as a fragment some content of an email that you are editing within the Email Designer. You need to copy-paste the HTML corresponding to that content into a new fragment. For more on this, see [Saving content as a fragment](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).-->
* Durante la modifica degli stili, sono disponibili solo i font per web ufficialmente supportati dalla maggior parte dei client e-mail.
* Non è possibile salvare gli stili come tema da riutilizzare in futuro. Tuttavia, lo stile CSS può essere salvato in un modello di contenuto o in un messaggio e-mail. Per ulteriori informazioni sugli stili, consulta [questa sezione](../../designing/using/styles.md).
* Il tag meta del referente non è supportato nella finestra di progettazione e-mail.
* Le coppie sostitutive, i caratteri non inclusi nel piano multilingue di base del set di caratteri Unicode, non possono essere memorizzati in 2 byte (16 bit) e devono essere codificati in 2 caratteri UTF-16. Questi caratteri includono alcuni ideogrammi CJK, la maggior parte delle emoticon e alcune lingue.
Questi caratteri possono causare problemi di incompatibilità nel testo dinamico. Prima di inviare i messaggi è necessario eseguire dei test rigorosi.

### Aggiornamento dei frammenti {#email-designer-updates}

E-mail Designer è in continuo miglioramento. Se hai creato un contenuto e-mail da zero, da un modello preconfigurato o se hai creato dei frammenti, alla successiva apertura del contenuto potresti visualizzare il seguente messaggio di aggiornamento:

![](assets/email_designer_fragment_patch_message.png)

 Adobe consiglia di aggiornare il contenuto alla versione più recente per evitare problemi, come problemi di collisione CSS. Fai clic su **[!UICONTROL Update now]**.

Se si verifica un errore durante l’aggiornamento del contenuto, controlla il codice HTML e correggilo prima di eseguire di nuovo l’aggiornamento.

Per quanto riguarda i frammenti, tieni presente quanto segue:

* Se desideri aggiungere un frammento a una nuova e-mail o modello e se ricevi questo messaggio, è necessario aggiornare prima questo frammento.

* Se disponi di più frammenti, è necessario aggiornare ogni frammento che si desidera utilizzare in un contenuto e-mail.

* Per evitare un impatto sugli attuali messaggi e-mail non ancora preparati, puoi scegliere di non aggiornare alcuni frammenti.

* È comunque possibile inviare e-mail in cui un frammento non aggiornato è già utilizzato, ma non è possibile modificarlo.

* L’aggiornamento dei frammenti utilizzati nelle e-mail già preparate non ha alcun impatto su tali e-mail.