---
title: Creazione di un messaggio e-mail
description: Per creare un'e-mail con invio singolo in Adobe Campaign, procedi come indicato di seguito.
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# Creazione di un messaggio e-mail{#creating-an-email}

Puoi creare un'e-mail da una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity), dalla [home page](../../start/using/interface-description.md#home-page)di Adobe Campaign o dall'elenco [delle attività di](../../start/using/marketing-activities.md#about-marketing-activities)marketing. Potete anche creare e-mail singole e ricorrenti da un flusso di lavoro.

1. Dopo aver iniziato a creare un'attività di e-mail marketing, seleziona il modello da utilizzare.

   Per impostazione predefinita, potete scegliere tra diversi modelli per ogni attività di marketing. Questo consente di preconfigurare alcuni parametri in base alle esigenze e di assegnare un marchio alla consegna. Per ulteriori informazioni, consultate [Gestione dei modelli](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >I modelli di test A/B e di follow-up sono nascosti per impostazione predefinita. Per visualizzarle, selezionate le caselle a sinistra (pannello **[!UICONTROL Filter]** laterale).

1. Immettete le proprietà generali del messaggio e-mail. Potete immettere un nome nel campo **Etichetta** e modificare l’ID. Sia il nome dell'attività che il relativo ID vengono visualizzati nell'interfaccia, ma non sono visibili ai destinatari del messaggio.

   Potete aggiungere una descrizione che l'utente può visualizzare nel contenuto della campagna.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puoi creare l'e-mail all'interno di una campagna padre dalla pagina principale o dall'elenco delle attività di marketing. Selezionatela dalle campagne già create.

1. Definisci la destinazione del messaggio in base ai criteri aziendali. Consultate [Gestione dei profili](../../audiences/using/about-profiles.md).

   Puoi anche definire i profili di test che convalideranno il messaggio. Consultate [Gestione dei profili](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)di test.

   ![](assets/email_creation_3.png)

1. Definite e personalizzate il contenuto del messaggio, il nome del mittente e l'oggetto utilizzando [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md). Per ulteriori informazioni, consultate [Informazioni sulla progettazione](../../designing/using/designing-content-in-adobe-campaign.md)del contenuto delle e-mail.

   ![](assets/email_creation_4.png)

   Potete progettare il messaggio direttamente utilizzando un modello di contenuto predefinito oppure Dreamweaver o Adobe Experience Manager. Se non siete designer, potete anche caricare un contenuto preparato per voi, oppure importare un contenuto esistente da un URL. Consultate [Selezione di un contenuto](../../designing/using/using-existing-content.md)esistente.

1. Visualizza in anteprima il messaggio. Consultate [Anteprima dei messaggi](../../sending/using/previewing-messages.md).
1. Confermate la creazione del messaggio e-mail.

   >[!NOTE]
   >
   >Per poter salvare l’e-mail, è innanzitutto necessario apportare alcune modifiche al contenuto. Se fate clic **[!UICONTROL Cancel]** a questo punto, la procedura guidata non verrà completata e il messaggio e-mail non verrà creato.

   Viene quindi visualizzato il dashboard e-mail. Consente di controllare il messaggio e [preparare l'invio](../../sending/using/preparing-the-send.md).

   Il **[!UICONTROL Edit properties]** pulsante in alto a destra consente di modificare le proprietà del messaggio e-mail. Ad esempio, potete configurare l’e-mail in modo che la relativa etichetta venga calcolata al momento della preparazione della consegna.  I parametri disponibili sono elencati in [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Pianificare l’invio. Vedere [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepara il messaggio per analizzarne la destinazione. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Potete impostare regole di affaticamento tra canali globali che escluderanno automaticamente i profili sollecitati dalle campagne. Per ulteriori informazioni, consultate [Regole](../../administration/using/fatigue-rules.md)di Fatigue.

1. Inviare prove per controllare e convalidare il messaggio e controllarne il rendering nella inbox. Vedere [Invio della prova](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. Invia il messaggio e controllane la distribuzione tramite il dashboard e i registri dei messaggi. Vedere [Invio di messaggi](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Misura l'impatto del messaggio con i report di consegna. Per ulteriori informazioni sui rapporti, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

**Argomenti** correlati:

* [Creazione di un video e-mail](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html)
* [Creazione di una guida dettagliata sull’e-mail](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) personalizzata
* [Video sull'integrazione](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) di Adobe Campaign e Dreamweaver
* [Integrazione con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

