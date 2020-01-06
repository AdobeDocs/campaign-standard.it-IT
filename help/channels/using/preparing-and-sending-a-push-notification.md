---
title: Preparazione e invio di una notifica push
description: Segui questi passaggi per creare una notifica push con invio singolo in Adobe Campaign.
page-status-flag: never-activated
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Preparazione e invio di una notifica push{#preparing-and-sending-a-push-notification}

## Preparazione della notifica {#preparing-the-notification}

I passaggi per creare una notifica push con Adobe Campaign sono:

1. Dalla **[!UICONTROL Marketing activities]**finestra,[crea una nuova attività](../../start/using/marketing-activities.md#creating-a-marketing-activity)di marketing.

   Puoi anche creare una singola notifica push da una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity) o dalla [home page](../../start/using/interface-description.md#home-page)di Adobe Campaign.

   Potete anche utilizzare un&#39;attività di consegna delle notifiche push in un flusso di lavoro. Questa attività viene presentata nella sezione relativa alla consegna [delle notifiche](../../automating/using/push-notification-delivery.md) push.

1. Selezionare **[!UICONTROL Push notification]**.
1. Selezionate un modello.

   ![](assets/push_notif_type.png)

   Per impostazione predefinita, potete selezionare uno dei due modelli seguenti:

   * **[!UICONTROL Send push to Campaign profiles]**: utilizza questo modello per eseguire il targeting dei profili Adobe Campaign CRM che si sono abbonati all&#39;applicazione mobile e hanno acconsentito alla ricezione di notifiche push. Puoi inserire campi di[personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)nella notifica push, ad esempio il nome del destinatario.
   * **[!UICONTROL Send push to app subscribers]**: utilizzate questo modello per inviare una notifica push a tutti gli utenti noti e anonimi di applicazioni mobili che hanno acconsentito alla ricezione di notifiche dall’applicazione. Puoi personalizzare questi messaggi con i dati raccolti dall’applicazione mobile.
   Potete anche selezionare modelli multilingue. Per ulteriori informazioni, consultate [Creazione di una notifica](../../channels/using/creating-a-multilingual-push-notification.md)push multilingue.

   Per ulteriori informazioni sui modelli, consultare la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md) .

1. Immettete le proprietà di notifica push e selezionate l&#39;app mobile nel **[!UICONTROL Associate a Mobile App to a delivery]**campo.

   Il menu a discesa mostrerà le applicazioni SDK SDK V4 e Experience Platform.

   ![](assets/push_notif_properties.png)

   Potete collegare la notifica push a una campagna. A questo scopo, selezionatela dalle campagne già create.

1. Nella schermata seguente, potete specificare un&#39;audience, ad esempio tutti i clienti VIP che si sono abbonati a una specifica applicazione mobile. Per ulteriori informazioni, consultate [Creazione di audience](../../audiences/using/creating-audiences.md).

   Il pubblico verrà filtrato automaticamente in base all&#39;applicazione mobile selezionata nel passaggio precedente.

   ![](assets/push_notif_audience.png)

1. Ora potete personalizzare la notifica push. Innanzitutto, scegliete lo stile del messaggio: **[!UICONTROL Alert/Message/Badge]**o**[!UICONTROL Silent push]**. I tipi di notifica push sono descritti nella sezione [Informazioni sulle notifiche](../../channels/using/about-push-notifications.md) push.

   Modificate il contenuto della notifica push e definite le opzioni avanzate. See [Customizing a push notification](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   Il contenuto e le opzioni della notifica push configurate qui vengono passati all&#39;app mobile sotto forma di payload. La struttura dettagliata del payload è descritta nella [nota tecnica sulla struttura](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) del payload delle notifiche push ACS.

1. Clic **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Prima di inviare la notifica, potete testarla con i profili di test e vedere esattamente cosa vedranno i destinatari prima di inviare la consegna. Seleziona **[!UICONTROL Audiences]**dal riepilogo della consegna e fai clic sulla**[!UICONTROL Test profiles]** scheda.

   Per ulteriori informazioni sull&#39;invio dei test, vedere Profili [di](../../sending/using/managing-test-profiles-and-sending-proofs.md)test.

1. Selezionate i profili di test e fate clic **[!UICONTROL Preview]**per visualizzare la notifica: il contenuto è personalizzato con i dati del profilo di test.
1. Controllate il layout della notifica push su diversi dispositivi: selezionate iPhone, telefono Android, iPad o tablet Android per visualizzare l&#39;anteprima del rendering.

   ![](assets/push_notif_preview.png)

1. La stima **[!UICONTROL Estimated Payload Size]**è basata sui dati del profilo di test. Le dimensioni effettive del payload possono variare. Il limite del messaggio è di 4 KB.

   >[!CAUTION]
   >
   >Se la dimensione del payload supera il limite di 4 KB, il messaggio non verrà recapitato. I dati di personalizzazione influiscono sulle dimensioni del messaggio.

## Invio della notifica {#sending-the-notification}

Le notifiche push possono essere inviate a un&#39;audience selezionata in Adobe Campaign definendo i criteri per l&#39;audience. Per l&#39;esempio seguente, il pubblico selezionato è composto da 4 sottoscrittori di app mobili con targeting.

1. Fate clic **[!UICONTROL Prepare]**per calcolare la destinazione e generare le notifiche.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]**window presents the following KPIs:**[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the**[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]**one due to exclusions which can be viewed by clicking![](assets/lp_link_properties.png)button at the bottom of the**[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. Nella **[!UICONTROL Exclusion logs]**scheda è possibile trovare l&#39;elenco di tutti i messaggi esclusi dalla destinazione inviata e il motivo di tale esclusione.

   Qui, possiamo vedere che uno dei nostri abbonati alle app mobili è stato escluso perché l&#39;indirizzo è stato inserito in blacklist e gli altri abbonati perché il profilo era un duplicato.

   ![](assets/push_send_5.png)

1. Fare clic sulla **[!UICONTROL Exclusion causes]**scheda per visualizzare il volume dei messaggi esclusi.

   ![](assets/push_send_7.png)

1. Ora puoi fare clic **[!UICONTROL Confirm]**per iniziare a inviare le notifiche push.
1. Controlla lo stato della distribuzione tramite il dashboard e i registri dei messaggi. Per ulteriori informazioni, consulta [Invio di messaggi](../../sending/using/confirming-the-send.md) e log [di](../../sending/using/monitoring-a-delivery.md#delivery-logs)consegna.

   In questo esempio, il pannello dei messaggi mostra che Adobe Campaign ha tentato di inviare due notifiche push: uno è stato consegnato correttamente al dispositivo e un altro non è riuscito. Per sapere perché la consegna presenta errori, fate clic sul ![](assets/lp_link_properties.png) pulsante in fondo alla **[!UICONTROL Deployment]**finestra.

   ![](assets/push_send_4.png)

1. Dalla **[!UICONTROL Deployment]**finestra, fate clic sulla**[!UICONTROL Sending logs]** scheda per accedere all&#39;elenco delle notifiche push inviate e ai relativi stati. Per questa consegna, una notifica push è stata inviata correttamente mentre l&#39;altra non è riuscita a causa di un token dispositivo non valido. Questo utente verrà quindi inserito in una blacklist a partire da ulteriori consegne.

   >[!NOTE]
   >
   >I motivi possono essere qualsiasi errore verificatosi a valle di Adobe Campaign. In caso di guasti da parte di fornitori come apns e fcm, il motivo riflette anche questo. Per ulteriori informazioni sugli errori del fornitore, consultate la documentazione di [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref) .

   ![](assets/push_send_6.png)

Ora puoi misurare l&#39;impatto della consegna delle notifiche push con report dinamici.

**Argomenti correlati:**

* [Report notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push in un flusso di lavoro](../../automating/using/push-notification-delivery.md)

