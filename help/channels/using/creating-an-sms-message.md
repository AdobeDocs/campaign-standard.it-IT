---
title: Creazione di un messaggio SMS
seo-title: Creazione di un messaggio SMS
description: Creazione di un messaggio SMS
seo-description: Segui questi passaggi per creare un messaggio SMS con un solo invio in Adobe Campaign.
page-status-flag: never-activated
uuid: 591 ae 97 e -2 d 19-4 f 93-be 4 b-d 8 d 20 f 1 d 2 d 12
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: sms-messages
discoiquuid: b 27381 a 9-19 e 5-4 b 65-b 194-c 72 f 475 ba 54 d
delivercontext-tags: Deliverycreation, procedura guidata
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Creating an SMS message{#creating-an-sms-message}

La creazione di una distribuzione SMS è molto simile alla creazione di un messaggio e-mail. Nei passaggi seguenti viene descritta la configurazione specifica di questo canale. Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

Advanced SMS parameters are detailed in the [SMS configuration](../../administration/using/configuring-sms-channel.md) section.

Per creare e inviare messaggi SMS a un cellulare, devi:

* A **[!UICONTROL Routing]** external account configured on the **[!UICONTROL Mobile (SMS)]** channel with the **[!UICONTROL Bulk delivery]** mode. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Un modello di consegna correttamente collegato a questo account esterno.

1. Creare una distribuzione SMS. You can do it from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in the [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   Potete anche aggiungere un'attività SMS in un flusso di lavoro. For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   Quando si crea un messaggio, viene visualizzata una procedura guidata per illustrare i passaggi più importanti. Il contenuto della procedura guidata può comunque essere modificato successivamente dal dashboard messaggio.

1. Selezionate il modello da utilizzare. Potete scegliere il modello SMS fornito o uno dei vostri modelli.

   ![](assets/sms_creation_1.png)

   Per distribuire un telefono cellulare, il modello di consegna deve essere collegato correttamente all'account esterno di indirizzamento SMS.

1. Immettete le proprietà generali dell'SMS.

   ![](assets/sms_creation_2.png)

   L'etichetta dell'attività e il relativo ID compaiono nell'interfaccia, ma non sono visibili ai destinatari del messaggio.

1. Specificate il pubblico di destinazione. Potete selezionare un'audience esistente o eseguire direttamente il targeting di una popolazione definendone e combinando le regole.

   ![](assets/sms_creation_3.png)

1. Aggiungete contenuto al SMS. You can also define the content by clicking the **[!UICONTROL Content]** section of the delivery dashboard, once the SMS creation is finalized. See [About SMS content design](../../designing/using/about-sms-and-push-content-design.md).

   Se hai inserito campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, la lunghezza del messaggio può variare da un destinatario all'altro. Tali fattori possono infatti introdurre caratteri non considerati in base alla codifica GSM. Per questo motivo, la lunghezza del messaggio deve essere valutata una volta eseguita la personalizzazione. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Conferma la creazione del messaggio. Viene quindi visualizzata la dashboard.
1. Pianificate l'invio. L'SMS può essere inviato manualmente subito dopo la preparazione del messaggio o automaticamente in una data pianificata. See [Scheduling messages](../../sending/using/about-scheduling-messages.md).
1. Prepara il messaggio per analizzarne validità, personalizzazione e destinazione.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Potete impostare regole globali di affaticamento cross-channel che escluderanno automaticamente i profili superflui dalle campagne. See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Invia le prove per controllare e convalidare il messaggio e controllare il rendering della inbox. See the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Conferma l'invio del messaggio. L'invio verrà avviato di conseguenza alla pianificazione definita.

   ![](assets/sms_creation_7.png)

Il messaggio viene inviato. Puoi controllarne la consegna tramite il dashboard messaggio e i registri.

Al termine dell'invio, potete iniziare a misurare l'impatto del messaggio con i report predefiniti o personalizzati.

**Argomenti correlati:**

* [Informazioni sulla versione SMS e push](../../designing/using/about-sms-and-push-content-design.md)
* [Gestione dei modelli](../../start/using/about-templates.md)
* [Creare un video di distribuzione](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html) SMS

