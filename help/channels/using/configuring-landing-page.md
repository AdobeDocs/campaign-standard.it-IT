---
title: Configurazione di una pagina di destinazione
description: Scopri come configurare le proprietà di una pagina di destinazione.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Configurazione di una pagina di destinazione {#configuring-landing-page}

## Conferma invio pagina di destinazione {#confirm-a-landing-page-submission}

Quando una pagina di destinazione viene inviata da un visitatore, potete configurare le azioni attivate. Per eseguire questa operazione:

1. Modificate le proprietà della pagina di destinazione a cui accedete tramite l’ ![](assets/edit_darkgrey-24px.png) icona nel dashboard della pagina di destinazione e visualizzate i **[!UICONTROL Job]** parametri.

   ![](assets/lp_edit_properties_button.png)

1. Nella **[!UICONTROL Specific actions]** sezione , selezionare **[!UICONTROL Start sending message]** per determinare l'invio di un messaggio automatico, ad esempio per confermare l'iscrizione a un servizio. È quindi necessario selezionare un modello di consegna e-mail.

   Se a livello di servizio è già configurato un messaggio di conferma, non selezionarne uno in questa schermata per evitare l'invio di più messaggi di conferma. Fare riferimento a [Configurare un servizio](../../audiences/using/creating-a-service.md).

1. Crea **[!UICONTROL Additional data]** per abilitare la memorizzazione di dati aggiuntivi durante l'invio della pagina di destinazione. Questi dati non sono visibili agli utenti che visitano la pagina. Vengono presi in considerazione solo i valori costanti.

   ![](assets/lp_parameters_6.png)

## Collegamento di una pagina di destinazione a un servizio {#linking-a-landing-page-to-a-service}

È possibile collegare un modulo a un servizio in modo che i profili possano sottoscrivere un servizio specifico durante la convalida delle pagine di destinazione.

I parametri per collegare una pagina di destinazione consentono di specificare il tipo di azione eseguita e se la pagina di destinazione è specificamente collegata a un singolo servizio o se è generica.

Per selezionare il servizio da collegare, è necessario:

1. Modificate le proprietà della pagina di destinazione a cui accedete tramite l’ ![](assets/edit_darkgrey-24px.png) icona nel dashboard della pagina di destinazione e visualizzate i **[!UICONTROL Job]** parametri.

   ![](assets/lp_edit_properties_button.png)

1. Scegli **[!UICONTROL Subscription]** nell'elenco a **[!UICONTROL Specific actions]** discesa.

   ![](assets/lp_parameters_5.png)

1. Selezionate **[!UICONTROL Specific service]** per collegare la pagina di destinazione a un singolo servizio. Non selezionate questa opzione se desiderate utilizzare diversi servizi con la pagina di destinazione.

   Utilizzate l' **[!UICONTROL Specified service in the URL]** opzione per consentire l'utilizzo della pagina di destinazione per diversi servizi. È pertanto necessario fare riferimento alla pagina di destinazione al momento della configurazione del servizio.

## Impostazione delle autorizzazioni e precaricamento dei dati {#setting-permissions-and-pre-loading-data}

L'accesso a una pagina di destinazione può essere limitato ai visitatori identificati, che provengono da un collegamento in un messaggio inviato da Campaign, ad esempio, o a una specifica unità organizzativa.
Nel caso di visitatori identificati, potete precaricare i loro dati nella pagina di destinazione. Per eseguire questa operazione:

1. Modificate le proprietà della pagina di destinazione a cui accedete tramite l’ ![](assets/edit_darkgrey-24px.png) icona nel dashboard della pagina di destinazione e visualizzate i **[!UICONTROL Access & loading]** parametri.

   ![](assets/lp_edit_properties_button.png)

1. Selezionare **[!UICONTROL Preload visitor data]**.

   Se un visitatore della pagina corrisponde a un profilo nel database, i suoi dati vengono visualizzati nei campi del modulo che sono mappati con i dati del database e vengono presi in considerazione gli elementi di personalizzazione della pagina di destinazione.

   ![](assets/lp_parameters_3.png)

È inoltre possibile:

* Utilizzate i parametri URL per identificare i visitatori, utilizzando l' **[!UICONTROL Authorize visitor identification via URL parameters]** opzione: quindi dovete scegliere il tasto di caricamento e mappare i parametri del filtro con i parametri dell'URL corrispondente.
* Autorizzate qualsiasi visitatore ad accedere alla pagina di destinazione utilizzando l' **[!UICONTROL Authorize unidentified visitors]** opzione.

Le pagine di destinazione possono essere collegate a un’unità organizzativa. In questo modo verrà definito l'accesso degli utenti alle diverse pagine di destinazione. Per assegnare un'unità organizzativa:

1. Accedete alle proprietà della pagina di destinazione tramite l’ **[!UICONTROL Edit properties]** icona .

   ![](assets/lp_parameters_google3.png)

1. Spiega il **[!UICONTROL Access authorization]**.

1. Fare clic sul menu a discesa e selezionare l'unità organizzativa. Per ulteriori informazioni sulla creazione di un'unità organizzativa, consultare questa [pagina](../../administration/using/organizational-units.md).

   ![](assets/lp_org_unit_2.png)

1. I **[!UICONTROL Created by]**, **[!UICONTROL Created]****[!UICONTROL Access authorization]** e **[!UICONTROL Last modified]** i campi vengono completati automaticamente.

1. Fate clic **[!UICONTROL Confirm]** quindi **[!UICONTROL Save]**.

Ora è possibile accedere alla pagina di destinazione e gestirla solo dagli utenti nell’unità organizzativa selezionata.

![](assets/lp_org_unit_3.png)

## Impostazione di Google reCAPTCHA {#setting-google-recaptcha}

È possibile impostare Google reCAPTCHA V3 con la pagina di destinazione per proteggerlo dallo spam e dagli abusi causati dai bot. Per poterlo usare con la pagina di destinazione, dovete innanzitutto creare un account esterno. Per ulteriori informazioni su come configurarlo, consulta questa [sezione](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Una volta configurato il tuo account esterno Google reCAPTCHA V3, puoi aggiungerlo alla pagina di destinazione:

1. Prima di pubblicare la pagina di destinazione, accedete alle proprietà della pagina a cui si accede tramite l’ ![](assets/edit_darkgrey-24px.png) icona dal dashboard della pagina di destinazione.

   ![](assets/lp_parameters_google3.png)

1. Aprite il **[!UICONTROL Access & loading]** menu.
1. Selezionare l' **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]** opzione.
1. Selezionate l'account esterno Google reCAPTCHA creato in precedenza.

   ![](assets/lp_parameters_google.png)

1. Click **[!UICONTROL Confirm]**.

La pagina di destinazione è ora configurata con Google reCAPTCHA, visibile nella parte inferiore della pagina.

![](assets/lp_parameters_google2.png)

Google reCAPTCHA restituirà quindi un punteggio basato sulle interazioni degli utenti con la pagina. Per verificare il punteggio, collegatevi alla console [di amministrazione di](https://g.co/recaptcha/admin)Google.
