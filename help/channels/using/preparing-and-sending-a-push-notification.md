---
title: Creare e inviare una notifica push
description: Per creare una notifica push a invio singolo in Adobe Campaign, segui la procedura riportata di seguito.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 41b83014-aea9-4ec2-b20e-c0a05bcad503
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '841'
ht-degree: 3%

---

# Preparazione e invio di una notifica push{#preparing-and-sending-a-push-notification}

## Preparazione della notifica {#preparing-the-notification}

I passaggi per la creazione di una notifica push con Adobe Campaign sono i seguenti:

1. Dalla finestra **[!UICONTROL Marketing activities]**, [crea una nuova attività di marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   È inoltre possibile creare una singola notifica push da una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity) o dalla [home page](../../start/using/interface-description.md#home-page) di Adobe Campaign.

   Puoi anche utilizzare un’attività di consegna di notifiche push all’interno di un flusso di lavoro. Questa attività è presentata nella sezione [Consegna notifiche push](../../automating/using/push-notification-delivery.md).

1. Seleziona **[!UICONTROL Push notification]**.
1. Seleziona un modello.

   ![](assets/push_notif_type.png)

   Per impostazione predefinita, puoi selezionare uno dei due modelli seguenti:

   * **[!UICONTROL Send push to Campaign profiles]**: utilizzare questo modello per eseguire il targeting dei profili Adobe Campaign CRM che si sono abbonati alla tua app mobile e hanno acconsentito alla ricezione di notifiche push. Puoi inserire campi di [personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) nella notifica push, ad esempio il nome del destinatario.
   * **[!UICONTROL Send push to app subscribers]**: utilizzare questo modello per inviare una notifica push a tutti gli utenti noti e anonimi di app mobili che hanno acconsentito alla ricezione di notifiche dall&#39;applicazione. Puoi personalizzare questi messaggi con i dati raccolti dalla tua app mobile.

   Puoi anche selezionare modelli multilingue. Per ulteriori informazioni, vedere [Creazione di una notifica push multilingue](../../channels/using/creating-a-multilingual-push-notification.md).

   Per ulteriori informazioni sui modelli, consulta la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

1. Immetti le proprietà della notifica push e seleziona la tua app mobile nel campo **[!UICONTROL Associate a Mobile App to a delivery]**.

   Tieni presente che nel menu a discesa verranno visualizzate sia le applicazioni SDK V4 che SDK Experience Platform.

   ![](assets/push_notif_properties.png)

   Puoi collegare la notifica push a una campagna. A questo scopo, selezionala tra le campagne già create.

1. Nella schermata seguente puoi specificare un pubblico, ad esempio tutti i clienti VIP che si sono abbonati a una specifica app mobile. Per ulteriori informazioni, consulta [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).

   Il pubblico verrà filtrato automaticamente in base all’app mobile selezionata nel passaggio precedente.

   ![](assets/push_notif_audience.png)

1. Ora puoi personalizzare la notifica push. Scegliere innanzitutto lo stile del messaggio: **[!UICONTROL Alert/Message/Badge]** o **[!UICONTROL Silent push]**. I tipi di notifica push sono descritti nella sezione [Informazioni sulle notifiche push](../../channels/using/about-push-notifications.md).

   Modifica il contenuto della notifica push e definisci le opzioni avanzate. Vedi [Personalizzazione di una notifica push](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   Il contenuto e le opzioni della notifica push qui configurati vengono passati all’app mobile sotto forma di payload. La struttura dettagliata del payload è descritta nella nota tecnica [Informazioni sulla struttura del payload per le notifiche push di Campaign Standard](../../administration/using/push-payload.md).

1. Fai clic su **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Prima di inviare la notifica, puoi testarla con profili di test e quindi visualizzare esattamente ciò che i destinatari vedranno prima di inviare la consegna. Seleziona **[!UICONTROL Audiences]** dal riepilogo della consegna e fai clic sulla scheda **[!UICONTROL Test profiles]**.

   Per ulteriori informazioni sull&#39;invio di test, fare riferimento a [Profili di test](../../sending/using/sending-proofs.md).

1. Seleziona i profili di test e fai clic su **[!UICONTROL Preview]** per visualizzare la notifica: il contenuto è personalizzato con i dati del profilo di test.
1. Controlla il layout delle notifiche push su diversi dispositivi: seleziona iPhone, telefono Android, iPad o tablet Android per visualizzare l’anteprima del rendering.

   ![](assets/push_notif_preview.png)

1. **[!UICONTROL Estimated Payload Size]** è una stima basata sui dati del profilo di test. La dimensione effettiva del payload può variare. Il limite del messaggio è di 4 KB.

   >[!CAUTION]
   >
   >Se la dimensione del payload supera il limite di 4 KB, il messaggio non verrà recapitato.

Tieni presente che i dati di personalizzazione influiscono sulle dimensioni del messaggio.

## Invio della notifica {#sending-the-notification}

Le notifiche push possono essere inviate a un pubblico selezionato in Adobe Campaign definendo i criteri di pubblico. Nell’esempio seguente, il pubblico selezionato è composto da 4 abbonati a app mobili specifici.

1. Fare clic su **[!UICONTROL Prepare]** per calcolare la destinazione e generare le notifiche.

   ![](assets/push_send_1.png)

1. Una volta completata la preparazione, la finestra **[!UICONTROL Deployment]** presenta i KPI seguenti: **[!UICONTROL Target]** e **[!UICONTROL To deliver]**. Tieni presente che il conteggio di **[!UICONTROL To deliver]** è inferiore a quello di **[!UICONTROL Targeted]** a causa di esclusioni che possono essere visualizzate facendo clic sul pulsante ![](assets/lp_link_properties.png) nella parte inferiore della finestra di **[!UICONTROL Deployment]**.

   ![](assets/push_send_2.png)

1. Nella scheda **[!UICONTROL Exclusion logs]** è possibile trovare l&#39;elenco di tutti i messaggi esclusi dal target inviato e il motivo di questa esclusione.

   Qui, possiamo vedere che uno dei nostri abbonati alle app mobili è stato escluso perché l’indirizzo era nel inserisco nell&#39;elenco Bloccati di e gli altri abbonati perché il profilo era un duplicato.

   ![](assets/push_send_5.png)

1. Fare clic sulla scheda **[!UICONTROL Exclusion causes]** per visualizzare il volume dei messaggi esclusi.

   ![](assets/push_send_7.png)

1. Ora puoi fare clic su **[!UICONTROL Confirm]** per iniziare a inviare notifiche push.
1. Controlla lo stato della consegna attraverso il dashboard messaggi e i registri. Per ulteriori informazioni, consulta [Invio di messaggi](../../sending/using/confirming-the-send.md) e [Registri di consegna](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   In questo esempio, nel dashboard dei messaggi viene visualizzato che Adobe Campaign ha tentato di inviare due notifiche push: una è stata recapitata correttamente al dispositivo e un’altra non è riuscita. Per sapere il motivo degli errori di consegna, fare clic sul pulsante ![](assets/lp_link_properties.png) nella parte inferiore della finestra **[!UICONTROL Deployment]**.

   ![](assets/push_send_4.png)

1. Dalla finestra **[!UICONTROL Deployment]**, fai clic sulla scheda **[!UICONTROL Sending logs]** per accedere all&#39;elenco delle notifiche push inviate e dei relativi stati. Per questa consegna, una notifica push è stata inviata correttamente, mentre l’altra non è riuscita a causa di un token dispositivo non valido. Questo abbonato verrà quindi aggiunto al elenco Bloccati di da ulteriori consegne.

   >[!NOTE]
   >
   >Le ragioni possono essere un errore a valle di Adobe Campaign. In caso di guasti da parte di fornitori come apns e fcm, la ragione rifletterà anche quello. Per ulteriori informazioni sugli errori del provider, consulta la documentazione di [Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) e [Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref).

   ![](assets/push_send_6.png)

Ora puoi misurare l’impatto della consegna delle notifiche push con i rapporti dinamici.

**Argomenti correlati:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all’interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)
