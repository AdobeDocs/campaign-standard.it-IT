---
title: Creazione di un messaggio e-mail
description: Per creare un’e-mail a invio singolo in Adobe Campaign, segui la procedura riportata di seguito.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 18%

---

# Creazione di un messaggio e-mail{#creating-an-email}

Puoi creare un messaggio e-mail da un [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity), da Adobe Campaign [home page](../../start/using/interface-description.md#home-page), o nella [elenco delle attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities). Puoi anche creare e-mail a invio singolo e ricorrenti da un flusso di lavoro.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

1. Dopo aver iniziato a creare un’attività di e-mail marketing, seleziona il modello da utilizzare.

   Per impostazione predefinita, puoi scegliere tra diversi modelli per ogni attività di marketing. Questo ti consente di preconfigurare alcuni parametri in base alle tue esigenze e di assegnare un brand alla consegna. Per ulteriori informazioni, consulta [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >I modelli di test A/B e di follow-up sono nascosti per impostazione predefinita. Seleziona le caselle a sinistra ( **[!UICONTROL Filter]** laterale) se si desidera visualizzarli.

1. Immetti le proprietà generali dell’e-mail. È possibile immettere un nome in **Etichetta** e modificare l&#39;ID.

   >[!NOTE]
   >
   >Sia il nome dell’attività che il relativo ID vengono visualizzati nell’interfaccia, ma non sono visibili ai destinatari del messaggio.
   >
   >Assicurati che il campo ID non contenga spazi vuoti per evitare discrepanze, ad esempio durante l’integrazione con Adobe Analytics.

   Puoi aggiungere una descrizione che l’utente può visualizzare nel contenuto della campagna.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puoi creare il messaggio e-mail all’interno di una campagna principale dalla pagina Home o dall’elenco delle attività di marketing. Selezionala tra le campagne già create.

1. Definisci il target del messaggio in base ai criteri aziendali. Consulta [Informazioni sui profili](../../audiences/using/about-profiles.md).

   Puoi anche definire i profili di test che convalideranno il messaggio. Consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Definisci e personalizza il contenuto del messaggio, il nome del mittente e l’oggetto utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md). Per ulteriori informazioni, consulta [Informazioni sulla progettazione di contenuti e-mail](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Puoi progettare il messaggio direttamente utilizzando un modello di contenuto predefinito oppure Dreamweaver o Adobe Experience Manager. Se non sei un designer, puoi anche caricare un contenuto preparato per te o importare un contenuto esistente da un URL. Consulta [Selezione di un contenuto esistente](../../designing/using/using-existing-content.md).

1. Visualizza l’anteprima del messaggio. Consulta [Anteprima dei messaggi](../../sending/using/previewing-messages.md).
1. Conferma la creazione dell’e-mail.

   >[!NOTE]
   >
   >Per poter salvare l’e-mail, devi prima apportare alcune modifiche al contenuto. Se si fa clic su **[!UICONTROL Cancel]** a questo punto, la procedura guidata non verrà completata e l’e-mail non verrà creata.

   Viene quindi visualizzato il dashboard e-mail. Ti consente di controllare il messaggio e [preparare l’invio](../../sending/using/preparing-the-send.md).

   Il **[!UICONTROL Edit properties]** nell’angolo in alto a destra consente di modificare le proprietà dell’e-mail. Ad esempio, puoi configurare l’e-mail in modo che la relativa etichetta venga calcolata al momento della preparazione della consegna.  I parametri disponibili sono elencati in [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Pianifica l’invio. Consulta [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepara il messaggio per analizzarne la destinazione. Consulta [Preparazione dell’invio](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Puoi impostare regole di affaticamento globali cross-channel che escludono automaticamente i profili sollecitati eccessivamente dalle campagne. Per ulteriori informazioni, consulta [Regole di astenia](../../sending/using/fatigue-rules.md).

1. Invia le bozze per la verifica e la convalida del messaggio e per monitorarne il rendering nella casella in entrata. Consulta [Invio bozza in corso](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Invia il messaggio e controllane la consegna tramite il dashboard e i registri dei messaggi. Consulta [Invio di messaggi](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Misura l’impatto del messaggio con i rapporti di consegna. Per ulteriori informazioni sul reporting, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

**Argomenti correlati**:

* [Creazione di un messaggio e-mail personalizzato](../../channels/using/key-steps-to-send-a-message.md) guida dettagliata
* [Integrazione tra Adobe Campaign e Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integrazione con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Video tutorial {#video}

Questo video mostra come creare un messaggio e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Sono disponibili altri video dimostrativi sui Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
