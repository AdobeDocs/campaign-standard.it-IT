---
solution: Campaign Standard
product: campaign
title: Creazione di un messaggio e-mail
description: Per creare un messaggio e-mail per invio singolo in  Adobe Campaign, effettuate le seguenti operazioni.
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 19%

---


# Creazione di un messaggio e-mail{#creating-an-email}

È possibile creare un&#39;e-mail da una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity), dalla  pagina principale di Adobe Campaign [](../../start/using/interface-description.md#home-page) o nell&#39; [elenco delle attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities). Puoi anche creare e-mail a invio singolo e ricorrenti da un flusso di lavoro.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

1. Dopo aver iniziato a creare un&#39;attività di e-mail marketing, seleziona il modello da utilizzare.

   Per impostazione predefinita, potete scegliere tra diversi modelli per ogni attività di marketing. Questo consente di preconfigurare alcuni parametri in base alle esigenze e di assegnare un marchio alla consegna. Per ulteriori informazioni, vedere [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >I modelli di test A/B e di follow-up sono nascosti per impostazione predefinita. Per visualizzarle, selezionare le caselle a sinistra ( **[!UICONTROL Filter]** pannello laterale).

1. Immettete le proprietà generali del messaggio e-mail. È possibile immettere un nome nel campo **Label** e modificare l&#39;ID. Sia il nome dell&#39;attività che il relativo ID vengono visualizzati nell&#39;interfaccia, ma non sono visibili ai destinatari del messaggio.

   Puoi aggiungere una descrizione che l’utente può visualizzare nel contenuto della campagna.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puoi creare l&#39;e-mail all&#39;interno di una campagna padre dalla pagina principale o dall&#39;elenco delle attività di marketing. Selezionatela dalle campagne già create.

1. Definisci la destinazione del messaggio in base ai criteri aziendali. Vedere [Informazioni sui profili](../../audiences/using/about-profiles.md).

   Puoi anche definire i profili di test che convalideranno il messaggio. Consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Definisci e personalizza il contenuto del messaggio, il nome del mittente e l&#39;oggetto utilizzando [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md). Per ulteriori informazioni, vedere [Informazioni sulla progettazione del contenuto delle e-mail](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Potete progettare il messaggio direttamente utilizzando un modello di contenuto predefinito oppure utilizzando Dreamweaver o Adobe Experience Manager. Se non siete designer, potete anche caricare un contenuto preparato per voi, oppure importare un contenuto esistente da un URL. Consulta [Selezione di un contenuto esistente](../../designing/using/using-existing-content.md).

1. Visualizza in anteprima il messaggio. Consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).
1. Conferma la creazione dell’e-mail.

   >[!NOTE]
   >
   >Per poter salvare l’e-mail, è innanzitutto necessario apportare alcune modifiche al contenuto. Se a questo punto si fa clic su **[!UICONTROL Cancel]**, la procedura guidata non verrà completata e l&#39;e-mail non verrà creata.

   Viene quindi visualizzato il dashboard e-mail. Consente di controllare il messaggio e [preparare l&#39;invio](../../sending/using/preparing-the-send.md).

   Il pulsante **[!UICONTROL Edit properties]** nell&#39;angolo superiore destro consente di modificare le proprietà dell&#39;e-mail. Ad esempio, potete configurare l’e-mail in modo che la relativa etichetta venga calcolata al momento della preparazione della consegna.  I parametri disponibili sono elencati in [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Pianifica l’invio. Consulta [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepara il messaggio per analizzarne la destinazione. Vedere [Preparazione dell&#39;invio](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Puoi impostare regole di affaticamento globali cross-channel che escludono automaticamente i profili sollecitati eccessivamente dalle campagne. Per ulteriori informazioni, vedere [Regole di Fatigue](../../sending/using/fatigue-rules.md).

1. Invia le bozze per la verifica e la convalida del messaggio e per monitorarne il rendering nella casella in entrata. Vedere [Invio della prova](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Invia il messaggio e controllane la distribuzione tramite il dashboard e i registri dei messaggi. Vedere [Invio di messaggi](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Misura l&#39;impatto del messaggio con i report di consegna. Per ulteriori informazioni sui rapporti, vedere [questa sezione](../../reporting/using/about-dynamic-reports.md).

**Argomenti correlati**:

* [Creazione di una guida dettagliata ](https://helpx.adobe.com/it/campaign/kb/acs-get-started-with-emails.html) e-mail personalizzata
* [Integrazione  con Adobe Campaign e Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integrazione con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Video di esercitazione {#video}

In questo video viene illustrato come creare un messaggio e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Ulteriori video dimostrativi sui Campaign Standard sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
