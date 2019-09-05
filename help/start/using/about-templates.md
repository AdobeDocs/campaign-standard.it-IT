---
title: Informazioni sui modelli
seo-title: Informazioni sui modelli
description: Informazioni sui modelli
seo-description: '" I modelli di Adobe Campaign consentono di preconfigurare i parametri in base alle esigenze: possono contenere una configurazione completa o parziale dell''attività di marketing, per semplificare l''utilizzo di Adobe Campaign per utenti finali non tecnici».'
page-status-flag: never-activated
uuid: 018534 b 6-61 a 3-433 e-bb 60-49883 c 8 b 9386
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: riferimento
topic-tags: gestione dei modelli
discoiquuid: 95218 ebe -5430-42 a 2-b 900-1 dadbbc 92 d 99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e2766bb9fef619142d3ee59cb8aa8ed20424a3f

---


# Informazioni sui modelli{#about-templates}

## Modelli di attività di marketing {#marketing-activity-templates}

Quando create una nuova attività di marketing, la prima schermata della procedura guidata richiede di selezionare un tipo o un modello. I modelli consentono di preconfigurare alcuni parametri in base alle esigenze. Il modello può contenere una configurazione completa o parziale dell'attività di marketing. La gestione dei modelli viene eseguita dall'amministratore funzionale.

L'utente finale dispone di un'interfaccia semplificata. Quando create una nuova attività di marketing, dovete semplicemente selezionare il modello che desiderate utilizzare. Non è necessario preoccuparsi di configurazioni tecniche. Questo è già stato preconfigurato dall'amministratore funzionale nel modello.

Ad esempio, nel caso di un modello e-mail, potete precompilare il contenuto HTML, il pubblico e qualsiasi altro parametro della distribuzione: pianificazione, profili di test, proprietà generali della distribuzione, parametri avanzati, ecc. Questo consente di risparmiare tempo durante la creazione di una nuova attività.

![](assets/template_1.png)

Per ogni tipo di attività di marketing, sono disponibili uno o più modelli forniti con configurazione minima. Questi modelli forniti non possono essere modificati o eliminati.

Sono disponibili modelli per le attività di marketing seguenti:

* Programmi
* Campagne
* Consegne e-mail
* Comunicazioni SMS
* Notifiche push
* Pagine di destinazione
* Flussi di lavoro
* Servizi
* Importa
* Messaggi transazionali

Questi modelli vengono gestiti dalla schermata **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** .

>[!NOTE]
>
>La configurazione del marchio può essere predefinita in un modello e-mail o in una pagina di destinazione. Per ulteriori informazioni, consulta la sezione [Branding](../../administration/using/branding.md) .

## Modelli di contenuto {#content-templates}

I modelli di contenuto HTML sono accessibili dalla schermata **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** del menu [Avanzate](../../start/using/interface-description.md#advanced-menu). Da qui è possibile gestire modelli di contenuto delle pagine di destinazione, modelli di contenuto e-mail e frammenti.

![](assets/content_templates_list.png)

I modelli di contenuto forniti sono di sola lettura. Per modificarne uno, occorre prima duplicarlo.

È possibile creare nuovi modelli o frammenti e definire i propri contenuti. Per ulteriori informazioni, vedere [Creazione di un modello di contenuto](../../start/using/about-templates.md#creating-a-content-template) e [Creazione di un frammento di contenuto](../../designing/using/defining-the-email-structure.md#creating-a-content-fragment).

Quando si modificano i contenuti con E-mail Designer, è inoltre possibile creare dei modelli di contenuto salvando i contenuti come frammento o modello. Per ulteriori informazioni, vedere [Salvataggio del contenuto come modello](../../start/using/about-templates.md#saving-content-as-template) e [Salvataggio del contenuto come frammento](../../designing/using/defining-the-email-structure.md#saving-content-as-a-fragment).

### Modelli di contenuto e-mail forniti tramite e-mail {#email-content-templates}

È possibile gestire i contenuti HTML disponibili nella **[!UICONTROL Templates]** scheda della [home page di Designer di](../../designing/using/about-email-content-design.md#about-the-email-designer) e-mail.

I modelli di contenuto e-mail forniti includono diciotto layout ottimizzati per dispositivi mobili e quattro modelli reattivi di alta classe progettati dagli artisti Behance. Corrispondono agli utilizzi più recenti quali messaggi di benvenuto clienti, newsletter e e-mail di ripartecipazione. Possono essere personalizzati con il contenuto dei marchi per semplificare il processo di progettazione e-mail da zero.

![](assets/content_templates.png)

**Argomenti correlati:**

* Scopri come personalizzare i modelli di contenuto [in questo video](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Per ulteriori informazioni sulla modifica del contenuto, consultate [Informazioni sulla progettazione di contenuto e-mail](../../designing/using/about-email-content-design.md).

### Creazione di un modello di contenuto {#creating-a-content-template}

Potete creare modelli di contenuto personalizzati per utilizzarli tutte le volte necessarie.

L'esempio seguente mostra come creare un modello di contenuto e-mail.

1. Vai a **[!UICONTROL Resources]** &gt; e **[!UICONTROL Content templates & fragments]** fai clic **[!UICONTROL Create]** su.
1. Fare clic sull'etichetta e-mail per accedere alla **[!UICONTROL Properties]** scheda di Email Designer.
1. Specificate un'etichetta riconoscibile e selezionate i seguenti parametri per utilizzare il modello nelle e-mail:

   * Seleziona **[!UICONTROL Shared]** o **[!UICONTROL Delivery]** dall'elenco **[!UICONTROL Content type]** a discesa.
   * Seleziona **[!UICONTROL Template]** dall'elenco **[!UICONTROL HTML type]** a discesa.
   ![](assets/email_designer_create-template.png)

1. Se necessario, potete impostare un'immagine che verrà usata come miniatura per il modello. Selezionarlo dalla **[!UICONTROL Thumbnail]** scheda delle proprietà del modello.

   ![](assets/email_designer_create-template_thumbnail.png)

   Questa miniatura verrà visualizzata nella **[!UICONTROL Templates]** scheda della [home page di Designer di](../../designing/using/about-email-content-design.md#about-the-email-designer) e-mail.

1. Chiudete **[!UICONTROL Properties]** la scheda per tornare all'area di lavoro principale.
1. Aggiungere componenti struttura e componenti di contenuto personalizzabili in base alle esigenze.
   >[!NOTE]
   >
   > Non puoi inserire campi di personalizzazione o contenuto condizionale all'interno di un modello di contenuto.
1. Una volta modificato, salvate il modello.

Questo modello può essere utilizzato in qualsiasi messaggio e-mail creato con E-mail Designer. Selezionarlo dalla **[!UICONTROL Templates]** scheda della [home page di Designer di](../../designing/using/about-email-content-design.md#about-the-email-designer) e-mail.

![](assets/content_template_new.png)

### Salvataggio del contenuto come modello {#saving-content-as-template}

Quando si modifica un'e-mail con Email Designer, è possibile salvare direttamente il contenuto dell'e-mail come modello.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Selezionare **[!UICONTROL Save as template]** dalla barra degli strumenti principale di Designer di Designer.

   ![](assets/email_designer_save-as-template.png)

1. Aggiungi un'etichetta e una descrizione, se necessario, quindi fai clic **[!UICONTROL Save]** su.

   ![](assets/email_designer_save-as-template_creation.png)

1. Per trovare il modello appena creato, passate a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

1. Per utilizzare il nuovo modello, selezionarlo dalla **[!UICONTROL Templates]** scheda della [home page di Designer di](../../designing/using/about-email-content-design.md#about-the-email-designer) e-mail.

   ![](assets/content_template_new.png)

