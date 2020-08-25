---
title: Conferma dell’abbonamento a un servizio
description: Segui questi passaggi per impostare un messaggio di conferma per i profili che si abbonano a un servizio in Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 100%

---


# Conferma dell’abbonamento a un servizio{#confirming-subscription-to-a-service}

## Informazioni sull’invio della conferma dell’abbonamento {#sending-subscription-confirmation}

Questa sezione descrive come inviare automaticamente un messaggio e-mail di conferma personalizzato ai profili che si abbonano a un servizio specifico.

Se desideri inviare un messaggio di conferma per un abbonamento (o l’annullamento) a un servizio, puoi utilizzare il messaggio predefinito o personalizzato. I passaggi per selezionare un messaggio di conferma sono descritti nella sezione [Creazione di un servizio](../../audiences/using/creating-a-service.md).

Se scegli di utilizzare il messaggio predefinito, puoi modificarne il contenuto con le seguenti limitazioni:
* Puoi personalizzare il contenuto del messaggio solo con campi limitati dal contesto dell’evento.
* Questo messaggio è lo stesso per tutti i servizi che utilizzano la modalità predefinita.

Per inviare un’e-mail di conferma specifica per un determinato servizio, puoi creare un messaggio personalizzato sfruttando anche i campi di personalizzazione di altre risorse. A questo scopo, devi creare e configurare un messaggio transazionale. È possibile visualizzare questo messaggio:
* Dal servizio stesso. Per ulteriori informazioni al riguardo, consulta [Configurazione del messaggio di conferma da un servizio](#configuring-confirmation-message-from-service).
* Da una pagina di destinazione dell’abbonamento. Per ulteriori informazioni al riguardo, consulta [Configurazione del messaggio di conferma da una pagina di destinazione](#configuring-confirmation-message-from-landing-page).

## Configurazione del messaggio di conferma da un servizio {#configuring-confirmation-message-from-service}

Ad esempio, desideri inviare automaticamente un messaggio di conferma ai visitatori del sito web quando si abbonano alla newsletter del brand.

Devi configurare un’e-mail transazionale e fare riferimento a quel messaggio dal servizio desiderato (in questo caso, l’abbonamento alla newsletter del brand). Per arricchire il messaggio transazionale con le informazioni del servizio, puoi definire una riconciliazione durante la creazione dell’evento.

Al momento di configurarlo dal servizio, il messaggio transazionale di conferma viene inviato solo la prima volta che il visitatore si abbona al relativo servizio. Se un profilo risulta già abbonato, non viene più inviato alcun messaggio di conferma a quel profilo.

### Passaggio 1: creare il messaggio e-mail di conferma {#step-1--create-the-confirmation-email-1}

Un messaggio e-mail di conferma viene inviato automaticamente a ogni profilo che si abbona alla newsletter (tramite una pagina di destinazione o in altri modi). L’abbonamento viene considerato un evento e l’e-mail è un [messaggio transazionale](../../channels/using/getting-started-with-transactional-msg.md) destinato a ogni profilo che si abbona al servizio.

I passaggi per creare il messaggio e-mail di conferma sono descritti di seguito. Poiché nel servizio viene fatto riferimento al messaggio transazionale, devi prima crearlo.

#### Creare l’evento {#create-the-event-1}

Il messaggio e-mail di conferma è un messaggio transazionale che reagisce a un evento: l’abbonamento a un servizio. Questo messaggio viene inviato per confermare l’abbonamento alla newsletter.

1. Crea un evento dal menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**, accessibile dal logo di Adobe Campaign.
1. Immetti un’etichetta, seleziona una dimensione di targeting e fai clic su **[!UICONTROL Create]**.

   I passaggi di configurazione sono descritti nella sezione [Configurazione di messaggi transazionali](../../administration/using/configuring-transactional-messaging.md).

1. Nella sezione **[!UICONTROL Fields]**, fai clic su **[!UICONTROL Create element]** e aggiungi **[!UICONTROL publicLabel]** alla struttura dati per abilitare la riconciliazione.

   ![](assets/confirmation_publicLabel-field.png)

   >[!NOTE]
   >
   >Il campo **[!UICONTROL publicLabel]** è obbligatorio. Se non lo aggiungi alla struttura dati dell’evento, Adobe Campaign non può eseguire la riconciliazione con il servizio. Con l’abbonamento a un servizio, questo campo viene compilato con il **[!UICONTROL Service label]** del relativo servizio.

1. Nella sezione **[!UICONTROL Enrichment]**, fai clic su **[!UICONTROL Create element]** e seleziona la risorsa target **[!UICONTROL Service]**.

   ![](assets/confirmation_enrichment-service.png)

1. Nella sezione **[!UICONTROL Join definition]**, mappa il campo **[!UICONTROL publicLabel]** della risorsa **[!UICONTROL Service]** con il campo **[!UICONTROL publicLabel]** della configurazione dell’evento.

   ![](assets/confirmation_publicLabel-join.png)

   >[!NOTE]
   >
   >In questo modo puoi usare i campi di personalizzazione della risorsa **[!UICONTROL Service]** nel messaggio transazionale.

1. Salva la configurazione dell’evento e fai clic su **[!UICONTROL Publish]** per pubblicarlo.

L’evento è pronto. Ora puoi progettare il messaggio e-mail transazionale.

#### Progettare il messaggio di conferma {#design-the-confirmation-message-1}

L’e-mail di conferma è un messaggio transazionale basato sull’evento appena pubblicato.

1. Dal logo di Adobe Campaign, seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** e fai clic su **[!UICONTROL Transactional messages]**.
1. Seleziona l’e-mail transazionale corrispondente all’evento appena pubblicato.

1. Fai clic sulla sezione **[!UICONTROL Content]** e seleziona un modello di e-mail. Per ulteriori informazioni sulla modifica di un contenuto di messaggi transazionali, consulta [Messaggi transazionali di eventi](../../channels/using/event-transactional-messages.md).
1. Poiché hai accesso diretto a tutti i campi della risorsa **[!UICONTROL Service]**, puoi selezionare qualsiasi campo dal nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event (rtEvent)]** > **[!UICONTROL Event context (ctx)]** >**[!UICONTROL Service]** per personalizzare il contenuto.

   ![](assets/confirmation_personalization-service.png)

   Per ulteriori informazioni sulla personalizzazione di un messaggio transazionale, consulta [questa sezione](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

1. Visualizza l’anteprima del messaggio utilizzando un profilo di test. Per ulteriori informazioni al riguardo, consulta [Definizione di un profilo di test in un messaggio transazionale](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

1. Fai clic su **[!UICONTROL Save & close]** per salvare il contenuto.
1. Pubblica il messaggio transazionale. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

### Passaggio 2: creare e configurare il servizio {#step-2--create-and-configure-the-service-1}

1. Crea un servizio dal menu avanzato **Profiles &amp; audiences** > **Services**, accessibile dal logo di Adobe Campaign.
1. Vai alla sezione **[!UICONTROL Service properties]**, accessibile tramite il pulsante ![](assets/edit_darkgrey-24px.png) nel dashboard del servizio.
1. Compila il campo **[!UICONTROL Service label]**.

   ![](assets/confirmation_service-label.png)

   >[!NOTE]
   >
   >Devi compilare questo campo per abilitare la riconciliazione con il messaggio transazionale.

1. Nella sezione **[!UICONTROL Confirmation messages]**, seleziona **[!UICONTROL Custom message]**: questa modalità ti consente di fare riferimento a un messaggio di conferma specifico per i profili che si abbonano al servizio.
1. Seleziona la **[!UICONTROL Custom subscription event configuration]** associata al messaggio transazionale creato.

   ![](assets/confirmation_service-confirmation-message.png)

1. Fai clic su **[!UICONTROL Confirm]** e salva il servizio.

Ogni volta che un profilo si abbona a questo servizio, riceve il messaggio transazionale definito da te, con campi di personalizzazione mappati sul servizio selezionato.

>[!NOTE]
>
>La prima volta che l’utente si abbona, gli viene inviato un messaggio.

## Configurazione del messaggio di conferma da una pagina di destinazione {#configuring-confirmation-message-from-landing-page}

Puoi anche fare riferimento al messaggio di conferma da una pagina di destinazione di abbonamento utilizzando l’opzione **[!UICONTROL Start sending messages]** presente nella sezione **[!UICONTROL Job]** della pagina di destinazione.

Quando si fa riferimento al messaggio di conferma dalla pagina di destinazione, a ogni invio della pagina di destinazione viene inviato un messaggio (anche se il profilo risulta già abbonato).

### Passaggio 1: creare il messaggio e-mail di conferma {#step-1--create-the-confirmation-email-2}

Un messaggio e-mail di conferma viene inviato automaticamente a ogni profilo che si abbona alla newsletter tramite una pagina di destinazione. L’abbonamento viene considerato un evento e l’e-mail è un [messaggio transazionale](../../channels/using/getting-started-with-transactional-msg.md) destinato a ciascun profilo che si abbona al servizio.

I passaggi per creare questi elementi sono descritti di seguito. Poiché nella pagina di destinazione viene fatto riferimento al messaggio transazionale, devi prima crearlo.

#### Creare l’evento {#create-the-event-2}

Il messaggio e-mail di conferma è un [messaggio transazionale](../../channels/using/getting-started-with-transactional-msg.md) che reagisce a un evento: l’abbonamento a un servizio. Questo messaggio viene inviato per confermare l’abbonamento alla newsletter.

1. Crea un evento dal menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**, accessibile dal logo di Adobe Campaign.
1. Immetti un’etichetta, seleziona una dimensione di targeting e fai clic su **[!UICONTROL Create]**.

   I passaggi di configurazione sono descritti nella sezione [Configurazione di messaggi transazionali](../../administration/using/configuring-transactional-messaging.md).

1. Nella sezione **[!UICONTROL Fields]**, fai clic su **[!UICONTROL Create element]** e aggiungi **[!UICONTROL serviceName]** alla struttura dati per abilitare la riconciliazione.

   ![](assets/confirmation_serviceName-field.png)

   >[!NOTE]
   >
   >Il campo **[!UICONTROL serviceName]** è obbligatorio. Se non lo aggiungi alla struttura dati dell’evento, Adobe Campaign non può eseguire la riconciliazione con il servizio in abbonamento.

1. Nella sezione **[!UICONTROL Enrichment]**, fai clic su **[!UICONTROL Create element]** e seleziona la risorsa target **[!UICONTROL Service]**.
1. Nella sezione **[!UICONTROL Join definition]**, mappa il campo **[!UICONTROL serviceName]** della risorsa **[!UICONTROL Service]** con il campo **[!UICONTROL name]** della configurazione dell’evento.

   ![](assets/confirmation_serviceName-join.png)

   >[!NOTE]
   >
   >In questo modo puoi usare i campi di personalizzazione della risorsa [!UICONTROL Service] nel messaggio transazionale.

#### Progettare il messaggio di conferma {#design-the-confirmation-message-2}

I passaggi per progettare il messaggio transazionale sono descritti in questa [sezione](#design-the-confirmation-message-1).

### Passaggio 2: creare e configurare il servizio {#step-2--create-and-configure-the-service-2}

1. Crea un servizio dal menu avanzato **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Services]**, accessibile dal logo di Adobe Campaign.
1. Vai alla sezione **[!UICONTROL Service properties]**, accessibile tramite il pulsante ![](assets/edit_darkgrey-24px.png) nel dashboard del servizio.
1. Compila il campo **[!UICONTROL Service label]**. Questa etichetta viene visualizzata nel messaggio di conferma e nella pagina di destinazione dell’abbonamento.
1. Fai clic su **[!UICONTROL Confirm]** e salva il servizio.

### Passaggio 3: creare e configurare la pagina di destinazione {#step-3--create-and-configure-the-landing-page}

Crea una pagina di destinazione dell’abbonamento da pubblicare sul sito web.

Per creare e configurare questa pagina di destinazione, segui questi passaggi:

1. Progetta una [nuova pagina di destinazione](../../channels/using/getting-started-with-landing-pages.md) basata sul modello **[!UICONTROL Subscription]**.
1. Modifica le proprietà della pagina di destinazione. Nella sezione **[!UICONTROL Job]** > **[!UICONTROL Specific actions]**, seleziona l’opzione **[!UICONTROL Specific service]** e scegli il servizio appena creato dall’elenco a discesa.

   ![](assets/confirmation_lp-specific-service.png)

1. Seleziona l’opzione **[!UICONTROL Start sending message]** e scegli il messaggio transazionale appena creato dall’elenco a discesa.

   ![](assets/confirmation_lp-start-sending-message.png)

1. Personalizza il contenuto della pagina di destinazione.

1. [Verifica e pubblica](../../channels/using/testing-publishing-landing-page.md) la pagina di destinazione.

Ogni volta che un profilo si abbona alla newsletter inviando la pagina di destinazione, riceve il messaggio di conferma definito con campi di personalizzazione mappati sul servizio.

>[!NOTE]
>
>A ogni invio della pagina di destinazione viene inviato un messaggio, anche se il profilo risulta già abbonato.
