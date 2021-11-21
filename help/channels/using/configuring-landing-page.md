---
title: Configurazione di una pagina di destinazione
description: Scopri come configurare le proprietà di una pagina di destinazione.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,main
feature: Landing Pages
role: User
level: Intermediate
exl-id: 0b9795e9-83e6-4399-a3b1-fc69081f6a82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 97%

---

# Configurazione di una pagina di destinazione {#configuring-landing-page}

## Conferma dell’invio di una pagina di destinazione {#confirm-a-landing-page-submission}

Quando una pagina di destinazione viene inviata da un visitatore, puoi configurare le azioni attivate. Per eseguire questa operazione:

1. Modifica le proprietà della pagina di destinazione accessibili tramite l’icona ![](assets/edit_darkgrey-24px.png) presente nel dashboard della pagina di destinazione, quindi visualizza i parametri **[!UICONTROL Job]**.

   ![](assets/lp_edit_properties_button.png)

1. Nella sezione **[!UICONTROL Specific actions]**, seleziona **[!UICONTROL Start sending message]** per determinare l’invio di un messaggio automatico, ad esempio per confermare l’abbonamento a un servizio. A questo punto dovrai scegliere un modello di consegna e-mail.

   Se a livello di servizio è già configurato un messaggio di conferma, non sceglierne uno in questa schermata onde evitare l’invio di più messaggi di conferma. Consulta [Configurare un servizio](../../audiences/using/creating-a-service.md).

1. Crea **[!UICONTROL Additional data]** per abilitare la memorizzazione di dati aggiuntivi durante l’invio della pagina di destinazione. Questi dati non sono visibili agli utenti che visitano la pagina. Vengono presi in considerazione solo i valori costanti.

   ![](assets/lp_parameters_6.png)

## Collegamento di una pagina di destinazione a un servizio {#linking-a-landing-page-to-a-service}

Puoi collegare un modulo a un servizio in modo che i profili possano abbonarsi a un servizio specifico durante la convalida delle pagine di destinazione.

I parametri per il collegamento di una pagina di destinazione ti consentono di specificare il tipo di azione eseguita, oltre a indicare se la pagina di destinazione è collegata in modo specifico a un singolo servizio o se è generica.

Per selezionare il servizio da collegare, devi:

1. Modificare le proprietà della pagina di destinazione accessibili tramite l’icona ![](assets/edit_darkgrey-24px.png) presente nel dashboard della pagina di destinazione, quindi visualizzare i parametri **[!UICONTROL Job]**.

   ![](assets/lp_edit_properties_button.png)

1. Scegliere **[!UICONTROL Subscription]** nell’elenco a discesa **[!UICONTROL Specific actions]**.

   ![](assets/lp_parameters_5.png)

1. Selezionare **[!UICONTROL Specific service]** per collegare la pagina di destinazione a un singolo servizio. Non scegliere questa opzione se desideri utilizzare numerosi servizi insieme alla pagina di destinazione.

   Utilizza l’opzione **[!UICONTROL Specified service in the URL]** per consentire l’impiego della pagina di destinazione insieme a vari servizi. Pertanto, al momento della configurazione del servizio, dovrai fare riferimento alla pagina di destinazione.

## Impostazione delle autorizzazioni e precaricamento dei dati {#setting-permissions-and-pre-loading-data}

L’accesso a una pagina di destinazione può essere limitato ai visitatori identificati, ad esempio provenienti da un collegamento presente in un messaggio inviato da Campaign o da un’unità organizzativa specifica.
Nel caso dei visitatori identificati, puoi precaricare i loro dati nella pagina di destinazione. Per eseguire questa operazione:

1. Modifica le proprietà della pagina di destinazione accessibili tramite l’icona ![](assets/edit_darkgrey-24px.png) nel dashboard della pagina di destinazione e visualizza i parametri **[!UICONTROL Access & loading]**.

   ![](assets/lp_edit_properties_button.png)

1. Seleziona **[!UICONTROL Preload visitor data]**.

   Se un visitatore della pagina corrisponde a un profilo nel database, i suoi dati vengono visualizzati nei campi del modulo che sono mappati sui dati del database, di conseguenza verranno presi in considerazione gli elementi di personalizzazione della pagina di destinazione.

   ![](assets/lp_parameters_3_temp.png)

Puoi anche autorizzare qualsiasi visitatore ad accedere alla pagina di destinazione utilizzando **[!UICONTROL Authorize unidentified visitors]** opzione .

<!--Use the URL parameters to identify the visitors, using the **[!UICONTROL Authorize visitor identification via URL parameters]** option: then you must choose the loading key and map the filter parameters with the parameters of the corresponding URL.-->

Le pagine di destinazione possono essere anche collegate a un’unità organizzativa. In questo modo verrà definito l’accesso degli utenti alle varie pagine di destinazione. Per assegnare un’unità organizzativa:

1. Esegui l’accesso alle proprietà della pagina di destinazione tramite l’icona **[!UICONTROL Edit properties]**.

   ![](assets/lp_parameters_google3.png)

1. Espandi **[!UICONTROL Access authorization]**.

1. Fai clic sul menu a discesa e seleziona l’unità organizzativa. Per ulteriori informazioni sulla modalità di creazione di un’unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

   ![](assets/lp_org_unit_2.png)

1. I campi **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Access authorization]** e **[!UICONTROL Last modified]** vengono completati automaticamente.

1. Fai clic su **[!UICONTROL Confirm]**, quindi su **[!UICONTROL Save]**.

Adesso solo gli utenti all’interno dell’unità organizzativa selezionata possono accedere e gestire la tua pagina di destinazione.

![](assets/lp_org_unit_3.png)

## Impostazione di Google reCAPTCHA {#setting-google-recaptcha}

Puoi impostare Google reCAPTCHA V3 nella tua pagina di destinazione per proteggerla dallo spam e dagli abusi causati dai bot. Per poter usare questa funzionalità sulla pagina di destinazione, devi innanzitutto creare un account esterno. Per ulteriori informazioni su come configurare tale account, consulta questa [sezione](../../administration/using/external-accounts.md#google-recaptcha-external-account).

Una volta configurato il tuo account esterno Google reCAPTCHA V3, puoi aggiungerlo alla tua pagina di destinazione:

1. Prima di pubblicare la pagina di destinazione, visualizzane le proprietà accessibili dall’icona ![](assets/edit_darkgrey-24px.png) presente sul dashboard della pagina di destinazione.

   ![](assets/lp_parameters_google3.png)

1. Espandi il menu **[!UICONTROL Access & loading]**.
1. Seleziona l’opzione **[!UICONTROL Use reCAPTCHA to protect your site from spam and abuse]**.
1. Scegli l’account esterno Google reCAPTCHA che hai creato in precedenza.

   ![](assets/lp_parameters_google_temp.png)

1. Fai clic su **[!UICONTROL Confirm]**.

La pagina di destinazione è ora configurata con Google reCAPTCHA, il cui logo sarà visibile nella parte inferiore della pagina.

![](assets/lp_parameters_google2.png)

Google reCAPTCHA restituirà quindi un punteggio basato sulle interazioni degli utenti con la tua pagina. Per verificare il tuo punteggio, collegati alla [Console di amministrazione di Google](https://g.co/recaptcha/admin).
