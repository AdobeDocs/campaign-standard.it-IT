---
title: Creazione di un'e-mail
seo-title: Creazione di un'e-mail
description: Creazione di un'e-mail
seo-description: Segui questi passaggi per creare un'e-mail di invio singolo in Adobe Campaign.
page-status-flag: never-activated
uuid: 74 c 7 ef 35-82 c 0-4 bc 4-b 1 f 6-8 e 74 fdcaea 3 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: email-messages
discoiquuid: b 27 e 0170-e 73 f -4782-8568-02927 fb 374 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f4c849adf1852d8a23c5ff5252da25c175faa84

---


# Creating an email{#creating-an-email}

You can create an email from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), or in the [marketing activity list](../../start/using/marketing-activities.md#about-marketing-activities). Potete anche creare e-mail a singolo invio e ricorrenti da un flusso di lavoro.

1. Dopo aver creato un'attività di marketing e-mail, selezionate il modello che desiderate utilizzare.

   Per impostazione predefinita, potete scegliere tra diversi modelli per ogni attività di marketing. Questo consente di preconfigurare alcuni parametri in base alle esigenze e di assegnare un marchio alla distribuzione. For more on this, see [Managing templates](../../start/using/about-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >I modelli di test A/B sono nascosti per impostazione predefinita. Check the boxes on the left side ( **[!UICONTROL Filter]** lateral panel) if you want to display them.

1. Immettete le proprietà generali dell'e-mail. You can enter a name in the **Label** field and edit the ID. Sia il nome dell'attività che il relativo ID compaiono nell'interfaccia, ma non sono visibili ai destinatari del messaggio.

   Potete aggiungere una descrizione che l'utente può vedere nel contenuto della campagna.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Potete creare l'e-mail all'interno di una campagna principale dalla home page o dall'elenco delle attività di marketing. Selezionatela dalle campagne che sono già state create.

1. Definite la destinazione del messaggio in base ai criteri di business. See [Managing profiles](../../audiences/using/about-profiles.md).

   Potete inoltre definire i profili di prova che convalidano il messaggio. See [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

   ![](assets/email_creation_3.png)

1. Define and personalize the message content, sender name and subject using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer). For more on this, see [About email content design](../../designing/using/about-email-content-design.md).

   ![](assets/email_creation_4.png)

   Potete progettare direttamente il messaggio utilizzando un modello di contenuto predefinito oppure utilizzando Dreamweaver o Adobe Experience Manager. Se non si sente un designer, è anche possibile caricare un contenuto preparato per voi o importare un contenuto esistente da un URL. See [Selecting an existing content](../../designing/using/selecting-an-existing-content.md).

1. Visualizzate l'anteprima del messaggio. See [Previewing messages](../../sending/using/previewing-messages.md).
1. Confermate la creazione dell'e-mail.

   >[!NOTE]
   >
   >Per poter salvare l'e-mail, occorre innanzitutto apportare alcune modifiche al contenuto. If you click **[!UICONTROL Cancel]** at this point, you will not complete the wizard and your email will not be created.

   Viene quindi visualizzato il dashboard e-mail. It allows you to check your message and [prepare the send](../../sending/using/preparing-the-send.md).

   The **[!UICONTROL Edit properties]** button in the upper-right corner allows you to edit the properties of the email. Potete, ad esempio, configurare l'e-mail in modo che la sua etichetta venga calcolata al momento della preparazione della distribuzione. Available parameters are listed in [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Pianificate l'invio. See [Scheduling messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepara il messaggio per analizzarne la destinazione. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Potete impostare regole globali di affaticamento cross-channel che escluderanno automaticamente i profili superflui dalle campagne. For more on this, see [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Invia le prove per controllare e convalidare il messaggio e controllare il rendering della inbox. See [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   ![](assets/bat_select.png)

1. Invia il messaggio e controllane la consegna tramite il dashboard e i registri del messaggio. See [Sending messages](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Misura l'impatto del messaggio con i rapporti sulla distribuzione. For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**Argomenti correlati**:

* [Creazione di](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) un video e-mail
* [Creazione di una guida dettagliata per un'e-](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GettingStartedEmail.html) mail
* [Video sull'integrazione](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) di Adobe Campaign e Dreamweaver
* [Integrazione con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

