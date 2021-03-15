---
solution: Campaign Standard
product: campaign
title: Configurazione di un'app mobile
description: Scopri come configurare Adobe Campaign per l’invio di notifiche push o messaggi in-app tramite SDK V4 o Experience Platform SDK.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Impostazioni delle istanze
role: Amministratore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1287'
ht-degree: 7%

---


# Configurazione di un&#39;app mobile{#configuring-a-mobile-application}

## Configurazione di un’app mobile tramite gli SDK Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Se hai bisogno di assistenza, contatta il responsabile dell’account di Adobe o un partner di servizi professionali.

Per inviare notifiche push e messaggi in-app con Experience Platform SDK, un’app mobile deve essere configurata in Adobe Experience Platform Experience Platform Experience Platform Launch e configurata in Adobe Campaign.

Per ulteriori informazioni sulla funzione obsoleta SDK di Mobile versione 4, consulta questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

Una volta configurata un’app mobile, puoi recuperare i dati PII raccolti per creare o aggiornare profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle applicazioni mobili](../../channels/using/updating-profile-with-mobile-app-data.md).

Per ulteriori informazioni sui diversi casi d’uso per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK Adobe Experience Platform, consulta questa [pagina](https://helpx.adobe.com/it/campaign/kb/configure-launch-rules-acs-use-cases.html).

Per completare la configurazione, completa i seguenti passaggi:

1. In Adobe Campaign, assicurati di poter accedere ai seguenti elementi:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   In caso contrario, contatta il team del tuo account.

1. Verifica che l’utente disponga delle autorizzazioni necessarie in Adobe Campaign Standard e Experience Platform Launch.
   * In Adobe Campaign Standard, assicurati che l’utente IMS faccia parte dei profili di prodotto per l’utente e l’amministratore standard. Questo passaggio consente all’utente di accedere ad Adobe Campaign Standard, passare alla pagina dell’app mobile Experience Platform SDK e visualizzare le proprietà dell’app mobile create nel Experience Platform Launch.

   * Al Experience Platform Launch, assicurati che l’utente IMS faccia parte di un profilo di prodotto di Experience Platform Launch.
Questo passaggio consente all’utente di accedere al Experience Platform Launch per creare e visualizzare le proprietà. Per ulteriori informazioni sui profili di prodotto nel Experience Platform Launch, consulta Creare il profilo di prodotto . Nel profilo di prodotto non dovrebbero essere impostate autorizzazioni per l’azienda o per le proprietà, ma l’utente dovrebbe comunque essere in grado di effettuare l’accesso.

   Per completare attività aggiuntive come l’installazione di un’estensione, la pubblicazione di un’app, la configurazione di ambienti e così via, devi impostare le autorizzazioni nel profilo di prodotto.

1. Nel Experience Platform Launch, crea un **[!UICONTROL Mobile property]**. Per ulteriori informazioni, consulta [Configurare una proprietà mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. In Experience Platform Launch, fai clic sulla scheda **[!UICONTROL Extensions]** , vai a **[!UICONTROL Catalog]** e cerca l&#39;estensione **[!UICONTROL Adobe Campaign Standard]**. Per ulteriori informazioni, consulta [Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Per supportare i casi d’uso relativi alla posizione in Campaign Standard, installa l’ estensione **[!UICONTROL Places]** e l’ estensione **[!UICONTROL Places Monitor]** .
   * Installa l&#39;estensione **[!UICONTROL Places]** in Experience Platform Launch. Fai riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installa l&#39;estensione **[!UICONTROL Places Monitor]** in Experience Platform Launch. Fai riferimento a questa [pagina](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. In Adobe Campaign Standard, configura la proprietà mobile creata in Experience Platform Launch. Consulta [Configurazione dell&#39;applicazione Adobe Experience Platform Launch in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Aggiungi la configurazione specifica per il canale alla configurazione dell’app mobile.
Per ulteriori informazioni, consulta [Configurazione dell’applicazione specifica per il canale in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessario, puoi eliminare la proprietà Experience Platform Launch.
Per ulteriori informazioni, vedere [Eliminazione dell&#39;applicazione di Experience Platform Launch](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronizza l’app mobile AEPSDK dal flusso di lavoro tecnico Launch {#aepsdk-workflow}

Dopo aver creato e configurato la proprietà mobile in Experience Platform Launch, il flusso di lavoro tecnico **[!UICONTROL Sync Mobile app AEPSDK from Launch]** sincronizza ora le proprietà mobili Adobe Launch importate in Adobe Campaign Standard.

Per impostazione predefinita, il flusso di lavoro tecnico viene avviato ogni 15 minuti. Se necessario, può essere riavviato manualmente:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Apri il flusso di lavoro **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** .

   ![](assets/launch_10.png)

1. Fai clic sull’attività **[!UICONTROL Scheduler]** .

1. Seleziona **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Il flusso di lavoro verrà ora riavviato e sincronizzato le proprietà mobili di Adobe Launch importate in Adobe Campaign Standard.

## Configurazione dell&#39;applicazione Adobe Experience Platform Launch in Adobe Campaign {#set-up-campaign}

Per utilizzare una proprietà mobile di Experience Platform Launch in Campaign, devi anche configurare questa proprietà in Adobe Campaign. In Adobe Campaign, assicurati che l’utente IMS faccia parte dei profili di prodotto per l’utente e l’amministratore standard.

È necessario attendere l’esecuzione del flusso di lavoro tecnico e sincronizzare la proprietà Launch mobile ad Adobe Campaign. Puoi quindi configurarlo in Adobe Campaign.

Per ulteriori informazioni sul flusso di lavoro tecnico di Launch per l’app AEPSDK di Sync Mobile, consulta questa [sezione](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Per impostazione predefinita, gli amministratori con l’unità organizzativa impostata su ALL possono modificare l’app mobile.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Seleziona l’app mobile creata in Experience Platform Launch.
Il valore **[!UICONTROL Property Status]** deve essere **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Per impostazione predefinita, per recuperare l’elenco delle applicazioni mobili create in Adobe Launch, Campaign Standard utilizza il valore definito nell’opzione NmsServer_URL per cercare le proprietà corrispondenti.
   >
   >In alcuni casi, l’endpoint Campaign per un’app mobile può essere diverso da quello definito in NmsServer_URL. In questo caso, definisci l’endpoint nell’opzione Launch_URL_Campaign . Campaign utilizza il valore di questa opzione per cercare le proprietà corrispondenti in Adobe Launch.

   ![](assets/launch_4.png)

1. Puoi modificare l’unità organizzativa dell’app mobile nella sezione **[!UICONTROL Access Authorization]** per limitare l’accesso a questa app mobile a unità organizzative specifiche. Per ulteriori informazioni, consulta questa pagina.

   In questo caso, l’amministratore può assegnare unità organizzative secondarie selezionandole dall’elenco a discesa.

   ![](assets/launch_12.png)

1. Per stabilire la connessione tra Campaign e il Experience Platform Launch, fai clic su **[!UICONTROL Save]**.

1. Verifica che lo stato dell’app mobile sia cambiato da **[!UICONTROL Ready to Configure]** a **[!UICONTROL Configured]**.

   Quando l’estensione Experience Platform Launch Campaign mostra che la chiave è stata configurata correttamente, puoi anche verificare che la proprietà sia stata impostata correttamente in Campaign.

   ![](assets/launch_5.png)

1. Affinché questa configurazione abbia effetto, le modifiche devono essere pubblicate in Experience Platform Launch.

   Per ulteriori informazioni, consulta [Configurazione di pubblicazione](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Configurazione dell&#39;applicazione specifica per il canale in Adobe Campaign {#channel-specific-config}

L’app mobile è ora pronta per essere utilizzata in Campaign per le notifiche push o per le consegne in-app. Ora puoi configurarlo ulteriormente, se necessario, per creare eventi che attivino i messaggi in-app e/o caricino i certificati push.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleziona l’app mobile creata e configurata in Experience Platform Launch.

1. Nella scheda **[!UICONTROL Mobile application properties]** puoi iniziare ad aggiungere gli eventi disponibili nell’app mobile per i messaggi in-app.

1. Per configurare gli eventi, fai clic su **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digita un nome e una descrizione.

   ![](assets/launch_7.png)

1. Fai clic su **[!UICONTROL Add]**.

   L’evento è ora disponibile nella scheda Triggers quando crei un messaggio in-app. Per ulteriori informazioni, consulta [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. Nella sezione **[!UICONTROL Device-specific settings]** di un dashboard di un’app mobile, specifica per ogni dispositivo i dettagli dell’applicazione, compreso il certificato per iOS e la chiave server per Android.

   Dopo il caricamento del certificato, un messaggio ti notifica che il caricamento è andato a buon fine e visualizza la data di scadenza del certificato.

   >[!NOTE]
   >
   >Dopo aver aggiunto correttamente il certificato in Adobe Campaign Standard, non potrai più ripristinare le impostazioni perché è possibile aggiungere una sola piattaforma APNS (produzione o sandbox) all’app MCPNS.

   ![](assets/launch_8.png)

1. Fai clic sulla scheda **[!UICONTROL Mobile application subscribers]** per visualizzare un elenco di abbonati e altre informazioni su questi abbonati, ad esempio, se hanno rinunciato alle notifiche.

## Eliminazione dell&#39;applicazione Adobe Experience Platform Launch {#delete-app}

Impossibile annullare l&#39;eliminazione dell&#39;applicazione di Experience Platform Launch.

>[!CAUTION]
>
>Impossibile annullare l&#39;eliminazione dell&#39;applicazione di Experience Platform Launch.

Per eliminare l&#39;applicazione di Experience Platform Launch, completa i passaggi descritti in [Eliminazione delle proprietà mobili](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

Dopo l’eliminazione dell’applicazione, in Adobe Campaign verifica se lo stato di Proprietà dell’applicazione è stato aggiornato correttamente in Eliminato in Launch.

Facendo clic sull’applicazione in Adobe Campaign, puoi scegliere di rimuovere completamente l’applicazione da Adobe Campaign facendo clic su Elimina da Campaign.

![](assets/launch_9.png)
