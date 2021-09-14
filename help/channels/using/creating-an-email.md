---
title: Creazione di un messaggio e-mail
description: Segui questi passaggi per creare un’e-mail a invio singolo in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 19%

---

# Creazione di un messaggio e-mail{#creating-an-email}

Puoi creare un messaggio e-mail da una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity), dalla pagina Home di Adobe Campaign [a3/> o dall&#39; [elenco delle attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities). ](../../start/using/interface-description.md#home-page) Puoi anche creare e-mail a invio singolo e ricorrenti da un flusso di lavoro.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

1. Dopo aver iniziato la creazione di un’attività di marketing e-mail, seleziona il modello da utilizzare.

   Per impostazione predefinita, puoi scegliere tra diversi modelli per ogni attività di marketing. Questo ti consente di preconfigurare alcuni parametri in base alle tue esigenze e anche di assegnare un marchio alla consegna. Per ulteriori informazioni, consulta [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >I modelli di test A/B e di follow-up sono nascosti per impostazione predefinita. Per visualizzarle, seleziona le caselle a sinistra ( **[!UICONTROL Filter]** pannello laterale ).

1. Immetti le proprietà generali dell’e-mail. Puoi immettere un nome nel campo **Etichetta** e modificare l’ID. Sia il nome dell’attività che il relativo ID vengono visualizzati nell’interfaccia, ma non sono visibili ai destinatari del messaggio.

   Puoi aggiungere una descrizione che l’utente può visualizzare nel contenuto della campagna.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puoi creare il tuo messaggio e-mail all’interno di una campagna principale dalla home page o dall’elenco delle attività di marketing. Selezionala dalle campagne già create.

1. Definisci il target del messaggio in base ai criteri aziendali. Consulta [Informazioni sui profili](../../audiences/using/about-profiles.md).

   Puoi anche definire i profili di test che convalidano il messaggio. Consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Definisci e personalizza il contenuto del messaggio, il nome del mittente e l&#39;oggetto utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md). Per ulteriori informazioni, consulta [Informazioni sulla progettazione del contenuto delle e-mail](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Puoi progettare il messaggio direttamente utilizzando un modello di contenuto predefinito o utilizzando Dreamweaver o Adobe Experience Manager. Se non ti senti come un designer, puoi anche caricare un contenuto preparato per te o importare un contenuto esistente da un URL. Consulta [Selezione di un contenuto esistente](../../designing/using/using-existing-content.md).

1. Visualizza l’anteprima del messaggio. Consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).
1. Conferma la creazione dell’e-mail.

   >[!NOTE]
   >
   >Per poter salvare l’e-mail, devi prima apportare alcune modifiche al contenuto. Se a questo punto fai clic su **[!UICONTROL Cancel]** , non completerai la procedura guidata e il messaggio e-mail non verrà creato.

   Viene quindi visualizzato il dashboard e-mail. Ti consente di controllare il messaggio e [preparare l&#39;invio](../../sending/using/preparing-the-send.md).

   Il pulsante **[!UICONTROL Edit properties]** nell’angolo in alto a destra consente di modificare le proprietà dell’e-mail. Ad esempio, puoi configurare l’e-mail in modo che la relativa etichetta venga calcolata al momento della preparazione della consegna.  I parametri disponibili sono elencati in [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Pianifica l’invio. Consulta [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepara il messaggio per analizzarne il target. Consulta [Preparazione dell&#39;invio](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Puoi impostare regole di affaticamento globali cross-channel che escludono automaticamente i profili sollecitati eccessivamente dalle campagne. Per ulteriori informazioni, consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

1. Invia le bozze per la verifica e la convalida del messaggio e per monitorarne il rendering nella casella in entrata. Consulta [Invio di prove](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Invia il messaggio e controllane la consegna tramite il dashboard messaggi e i registri. Consulta [Invio di messaggi](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Misura l’impatto del messaggio con i rapporti di consegna. Per ulteriori informazioni sul reporting, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

**Argomenti correlati**:

* [Creazione di una guida ](https://helpx.adobe.com/it/campaign/kb/acs-get-started-with-emails.html) e-mail personalizzata dettagliata
* [Integrazione di Adobe Campaign e Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integrazione con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Video tutorial {#video}

Questo video mostra come creare un messaggio e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Sono disponibili ulteriori video dimostrativi su Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
