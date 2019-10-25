---
title: I modelli
seo-title: I modelli
description: I modelli
seo-description: '"I modelli di Adobe Campaign consentono di preconfigurare i parametri in base alle esigenze: i modelli possono contenere una configurazione completa o parziale dell''attività di marketing, per semplificare l''utilizzo di Adobe Campaign per gli utenti finali non tecnici."'
page-status-flag: mai attivato
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: gestione dei modelli
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# I modelli{#about-templates}

## Modelli di attività di marketing {#marketing-activity-templates}

Quando crei una nuova attività di marketing, nella prima schermata della procedura guidata viene richiesto di selezionare un tipo o un modello. I modelli consentono di preconfigurare alcuni parametri in base alle esigenze. Il modello può contenere una configurazione completa o parziale dell'attività di marketing. La gestione dei modelli viene eseguita dall'amministratore funzionale.

L'utente finale ha un'interfaccia semplificata. Quando crei una nuova attività di marketing, devi solo selezionare il modello da utilizzare. Non c'è bisogno di preoccuparsi di configurazioni tecniche. Questo è già stato preconfigurato dall'amministratore funzionale nel modello.

Ad esempio, nel caso di un modello e-mail, potete precompilare il contenuto HTML, il pubblico e qualsiasi altro parametro per la distribuzione: pianificazione, profili di test, proprietà generali della consegna, parametri avanzati, ecc. Questo consente di risparmiare tempo durante la creazione di una nuova attività.

![](assets/template_1.png)

Per ogni tipo di attività di marketing, sono disponibili uno o più modelli out-of-the-box con una configurazione minima. Non è possibile modificare o eliminare questi modelli predefiniti.

I modelli sono disponibili per le seguenti attività di marketing:

* Programmi
* Campagne
* Consegne e-mail
* Consegne mediante SMS
* Notifiche push
* Pagine di destinazione
* Flussi di lavoro
* Servizi
* Importa
* Messaggi transazionali

Questi modelli vengono gestiti da **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** schermata.

>[!NOTE]
>
>La configurazione del marchio può essere preconfigurata in un modello di e-mail o di pagina di destinazione. Per ulteriori informazioni, consulta la sezione [Branding](../../administration/using/branding.md) .

## Modelli di contenuto {#content-templates}

I modelli di contenuto HTML sono accessibili dalla schermata **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** del menu [](../../start/using/interface-description.md#advanced-menu)Avanzate. Da qui è possibile gestire i modelli di contenuto della pagina di destinazione, i modelli di contenuto e-mail e anche i frammenti.

![](assets/content_templates_list.png)

I modelli di contenuto forniti sono di sola lettura. Per modificarne uno, dovete prima duplicare il modello desiderato.

È possibile creare nuovi modelli o frammenti e definire contenuti personalizzati. Per ulteriori informazioni, consultate [Creazione di un modello](#creating-a-content-template) di contenuto e [Creazione di un frammento](../../designing/using/using-reusable-content.md#creating-a-content-fragment)di contenuto.

Quando si modifica il contenuto con Designer e-mail, è anche possibile creare modelli di contenuto salvando il contenuto come frammento o modello. Per ulteriori informazioni, consultate [Salvataggio di contenuti come modelli](#saving-content-as-template) e [Salvataggio di contenuti come frammenti](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment).

### Modelli per contenuti e-mail forniti con i prodotti {#email-content-templates}

È possibile gestire il contenuto HTML offerto nella **[!UICONTROL Templates]** scheda della home page di [Email Designer](../../designing/using/overview.md) .

I modelli di contenuto e-mail forniti con il prodotto includono diciotto layout ottimizzati per dispositivi mobili e quattro modelli reattivi all’avanguardia creati dagli artisti di Behance. Corrispondono, tra l'altro, agli usi più recenti, come messaggi di benvenuto, newsletter ed e-mail di nuovo coinvolgimento. Possono essere facilmente personalizzati con i contenuti dei marchi per semplificare il processo di progettazione di e-mail da zero.

![](assets/content_templates.png)

**Argomenti correlati:**

* Scoprite come personalizzare i modelli di contenuto [in questo video](https://helpx.adobe.com/campaign/kt/acs/using/acs-email_content_templates-feature-video-use.html).
* Per ulteriori informazioni sulla modifica dei contenuti, consultate [Informazioni sulla progettazione](../../designing/using/overview.md)dei contenuti e-mail.

### Creating a content template {#creating-a-content-template}

Potete creare modelli di contenuto personalizzati da usare il maggior numero di volte necessario.

L’esempio seguente mostra come creare un modello di contenuto per e-mail.

1. Vai a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]** e fai clic su **[!UICONTROL Create]**.
1. Fare clic sull'etichetta e-mail per accedere alla **[!UICONTROL Properties]** scheda di Designer e-mail.
1. Specificate un'etichetta riconoscibile e selezionate i seguenti parametri per poter utilizzare questo modello nelle e-mail:

   * Selezionate **[!UICONTROL Shared]** o **[!UICONTROL Delivery]** dall'elenco a **[!UICONTROL Content type]** discesa.
   * Selezionate **[!UICONTROL Template]** dall’elenco a **[!UICONTROL HTML type]** discesa.
   ![](assets/email_designer_create-template.png)

1. Se necessario, potete impostare un’immagine che verrà utilizzata come miniatura per il modello. Selezionatela dalla **[!UICONTROL Thumbnail]** scheda delle proprietà del modello.

   ![](assets/email_designer_create-template_thumbnail.png)

   Questa miniatura verrà visualizzata nella **[!UICONTROL Templates]** scheda della home page di [Email Designer](../../designing/using/overview.md) .

1. Chiudete la **[!UICONTROL Properties]** scheda per tornare all'area di lavoro principale.
1. Aggiungere componenti di struttura e contenuti personalizzabili in base alle esigenze.
   >[!NOTE]
   >
   > Non potete inserire campi di personalizzazione o contenuto condizionale all'interno di un modello di contenuto.
1. Dopo aver modificato il modello, salvatelo.

Questo modello può essere utilizzato in qualsiasi e-mail creata con Designer e-mail. Selezionatela dalla **[!UICONTROL Templates]** scheda della home page di [Email Designer](../../designing/using/overview.md) .

![](assets/content_template_new.png)

### Salvataggio del contenuto come modello {#saving-content-as-template}

Quando modificate un'e-mail con Designer e-mail, potete salvare direttamente il contenuto di tale e-mail come modello.

<!--[!CAUTION]
>
>You cannot save as template a structure containing personalization fields or dynamic content.-->

1. Selezionare **[!UICONTROL Save as template]** dalla barra degli strumenti principale di Designer e-mail.

   ![](assets/email_designer_save-as-template.png)

1. Aggiungi un'etichetta e una descrizione, se necessario, quindi fai clic su **[!UICONTROL Save]**.

   ![](assets/email_designer_save-as-template_creation.png)

1. Per trovare il modello appena creato, passate a **[!UICONTROL Resources]** &gt; **[!UICONTROL Content templates & fragments]**.

1. Per utilizzare il nuovo modello, selezionarlo dalla **[!UICONTROL Templates]** scheda della home page di [Email Designer](../../designing/using/overview.md) .

   ![](assets/content_template_new.png)

