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
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Creazione di un messaggio e-mail{#creating-an-email}

Puoi creare un&#39;e-mail da una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity), dalla [home page](../../start/using/interface-description.md#home-page)di Adobe Campaign o dall&#39;elenco [delle attività di](../../start/using/marketing-activities.md#about-marketing-activities)marketing. Potete anche creare e-mail singole e ricorrenti da un flusso di lavoro.

1. Dopo aver iniziato a creare un&#39;attività di e-mail marketing, seleziona il modello da utilizzare.

   Per impostazione predefinita, potete scegliere tra diversi modelli per ogni attività di marketing. Questo consente di preconfigurare alcuni parametri in base alle esigenze e di assegnare un marchio alla consegna. Per ulteriori informazioni, consultate [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >I modelli di test A/B e di follow-up sono nascosti per impostazione predefinita. Per visualizzarle, selezionare le caselle a sinistra (pannello **[!UICONTROL Filter]** laterale).

1. Immettete le proprietà generali del messaggio e-mail. Potete immettere un nome nel campo **Etichetta** e modificare l’ID. Sia il nome dell&#39;attività che il relativo ID vengono visualizzati nell&#39;interfaccia, ma non sono visibili ai destinatari del messaggio.

   Potete aggiungere una descrizione che l&#39;utente può visualizzare nel contenuto della campagna.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puoi creare l&#39;e-mail all&#39;interno di una campagna padre dalla pagina principale o dall&#39;elenco delle attività di marketing. Selezionatela dalle campagne già create.

1. Definisci la destinazione del messaggio in base ai criteri aziendali. Consultate [Gestione dei profili](../../audiences/using/about-profiles.md).

   Puoi anche definire i profili di test che convalideranno il messaggio. Consultate [Gestione dei profili](../../audiences/using/managing-test-profiles.md)di prova.

   ![](assets/email_creation_3.png)

1. Definite e personalizzate il contenuto del messaggio, il nome del mittente e l&#39;oggetto utilizzando [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md). Per ulteriori informazioni, consultate [Informazioni sulla progettazione](../../designing/using/designing-content-in-adobe-campaign.md)del contenuto delle e-mail.

   ![](assets/email_creation_4.png)

   Potete progettare il messaggio direttamente utilizzando un modello di contenuto predefinito oppure Dreamweaver o Adobe Experience Manager. Se non siete designer, potete anche caricare un contenuto preparato per voi, oppure importare un contenuto esistente da un URL. Consultate [Selezione di un contenuto](../../designing/using/using-existing-content.md)esistente.

1. Visualizza in anteprima il messaggio. Consultate [Anteprima dei messaggi](../../sending/using/previewing-messages.md).
1. Confermate la creazione del messaggio e-mail.

   >[!NOTE]
   >
   >Per poter salvare l’e-mail, è innanzitutto necessario apportare alcune modifiche al contenuto. Se fate clic **[!UICONTROL Cancel]** a questo punto, la procedura guidata non verrà completata e il messaggio e-mail non verrà creato.

   Viene quindi visualizzato il dashboard e-mail. Consente di controllare il messaggio e [preparare l&#39;invio](../../sending/using/preparing-the-send.md).

   Il **[!UICONTROL Edit properties]** pulsante in alto a destra consente di modificare le proprietà del messaggio e-mail. Ad esempio, potete configurare l’e-mail in modo che la relativa etichetta venga calcolata al momento della preparazione della consegna.  I parametri disponibili sono elencati in [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Pianificare l’invio. Vedere [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepara il messaggio per analizzarne la destinazione. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Potete impostare regole di affaticamento tra canali globali che escluderanno automaticamente i profili sollecitati dalle campagne. Per ulteriori informazioni, consultate [Regole](../../sending/using/fatigue-rules.md)di Fatigue.

1. Inviate prove per verificare e convalidare il messaggio e controllarne il rendering nella inbox. Vedere [Invio della prova](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Invia il messaggio e controllane la distribuzione tramite il dashboard e i registri dei messaggi. Consulta [Invio di messaggi](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Misura l&#39;impatto del messaggio con i report di consegna. Per ulteriori informazioni sui rapporti, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

**Argomenti** correlati:

* [Creazione di un video e-mail](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)
* [Creazione di una guida dettagliata sull’e-mail](https://helpx.adobe.com/campaign/kb/acs-get-started-with-emails.html) personalizzata
* [Video sull&#39;integrazione](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html) di Adobe Campaign e Dreamweaver
* [Integrazione con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)
