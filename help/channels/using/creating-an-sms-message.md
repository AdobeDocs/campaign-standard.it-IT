---
title: Creazione di un messaggio SMS
description: Per creare un messaggio SMS inviato singolo in Adobe Campaign, procedi come indicato di seguito.
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Creazione di un messaggio SMS{#creating-an-sms-message}

Creare un SMS è molto simile a creare un&#39;e-mail regolare. I passaggi seguenti descrivono la configurazione specifica per questo canale. Per ulteriori informazioni sulle altre opzioni, consultate [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md) .

I parametri SMS avanzati sono descritti in dettaglio nella sezione relativa alla configurazione [di](../../administration/using/configuring-sms-channel.md) SMS.

Per creare e inviare messaggi SMS a un cellulare, è necessario:

* Account **[!UICONTROL Routing]**esterno configurato sul**[!UICONTROL Mobile (SMS)]** canale con la **[!UICONTROL Bulk delivery]**modalità. Per ulteriori informazioni, vedere la sezione[Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Un modello di consegna correttamente collegato a questo account esterno.

1. Creare una consegna SMS. Puoi farlo dalla [home page](../../start/using/interface-description.md#home-page)di Adobe Campaign, in una [campagna](../../start/using/marketing-activities.md#creating-a-marketing-activity) o nell&#39;elenco [delle attività di](../../start/using/programs-and-campaigns.md#creating-a-campaign)marketing.

   Potete anche aggiungere un&#39;attività SMS in un flusso di lavoro. Per ulteriori informazioni, consulta la guida [Flussi](../../automating/using/sms-delivery.md) di lavoro.

   Durante la creazione di un messaggio, viene visualizzata una procedura guidata che illustra i passaggi più importanti. I contenuti definiti dalla procedura guidata possono essere modificati successivamente dal dashboard dei messaggi.

1. Selezionate il modello da utilizzare. Potete scegliere il modello di SMS fornito o uno dei vostri modelli.

   ![](assets/sms_creation_1.png)

   Per effettuare la consegna a un telefono cellulare, il modello di consegna deve essere collegato correttamente all&#39;account esterno di routing SMS.

1. Immettere le proprietà generali dell&#39;SMS.

   ![](assets/sms_creation_2.png)

   Sia l&#39;etichetta dell&#39;attività che il relativo ID vengono visualizzati nell&#39;interfaccia, ma non sono visibili ai destinatari del messaggio.

1. Specificate l&#39;audience di cui desiderate eseguire il targeting. Potete selezionare un&#39;audience esistente o eseguire direttamente il targeting di una popolazione definendo e combinando le regole.

   ![](assets/sms_creation_3.png)

1. Aggiungi contenuto al tuo SMS. Potete anche definire il contenuto facendo clic sulla **[!UICONTROL Content]**sezione del dashboard di distribuzione, una volta completata la creazione di SMS. Consultate[La progettazione](../../channels/using/about-sms-and-push-content-design.md)di contenuti SMS.

   Se hai inserito campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, la lunghezza del messaggio può variare da un destinatario all&#39;altro. infatti, questi fattori possono introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Questo è il motivo per cui la lunghezza del messaggio deve essere valutata una volta effettuata la personalizzazione. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Conferma la creazione del messaggio. Viene visualizzata la dashboard.
1. Pianificare l’invio. L&#39;SMS può essere inviato manualmente subito dopo la preparazione del messaggio o automaticamente a una data pianificata. Vedere [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md).
1. Prepara il messaggio per analizzarne la validità, la personalizzazione e il target.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Potete impostare regole di affaticamento tra canali globali che escluderanno automaticamente i profili sollecitati dalle campagne. Consultate [Regole](../../administration/using/fatigue-rules.md)di fatica.

1. Inviare prove per controllare e convalidare il messaggio e controllarne il rendering nella inbox. Vedere la sezione [Invio della prova](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) .
1. Conferma l’invio del messaggio. L&#39;invio avrà inizio di conseguenza rispetto alla pianificazione definita.

   ![](assets/sms_creation_7.png)

Il messaggio viene inviato. Puoi controllarne la distribuzione tramite il dashboard e i registri dei messaggi.

Al termine dell&#39;invio, puoi iniziare a misurare l&#39;impatto del messaggio con rapporti di consegna predefiniti o personalizzati.

**Argomenti correlati:**

* [Informazioni sull&#39;edizione di SMS e contenuti push](../../channels/using/about-sms-and-push-content-design.md)
* [Gestione dei modelli](../../start/using/marketing-activity-templates.md)
* [Creare un video di consegna](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html) SMS

