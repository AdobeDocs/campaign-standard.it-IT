---
solution: Campaign Standard
product: campaign
title: Configurazione di un’applicazione mobile
description: Scopri come configurare  Adobe Campaign per l'invio di notifiche push o messaggi in-app tramite SDK V4 o  Experience Platform SDK.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1283'
ht-degree: 7%

---


# Configurazione di un’applicazione mobile{#configuring-a-mobile-application}

## Configurazione di un&#39;applicazione mobile tramite Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
>Le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Se hai bisogno di assistenza, contatta il responsabile dell’account di Adobe o un partner di servizi professionali.

Per inviare notifiche push e messaggi in-app con ’applicazione SDK per Experienci Platform, un’applicazione mobile deve essere configurata in Adobe Experience Platform  Experience Platform Launch Experience Platform e configurata in  Adobe Campaign.

Per ulteriori informazioni sulla funzione obsoleta SDK per dispositivi mobili versione 4, fare riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4-deprecated.html).

Una volta impostata l’applicazione per dispositivi mobili, è possibile recuperare i dati PII raccolti per creare o aggiornare i profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento delle informazioni sul profilo in base ai dati dell&#39;applicazione mobile](../../channels/using/updating-profile-with-mobile-app-data.md).

Per ulteriori informazioni sui diversi casi di utilizzo per dispositivi mobili supportati in  Adobe Campaign Standard mediante gli SDK Adobe Experience Platform, fare riferimento a [page](https://helpx.adobe.com/it/campaign/kb/configure-launch-rules-acs-use-cases.html).

Per completare la configurazione, effettua i seguenti passaggi:

1. In  Adobe Campaign, assicurati di poter accedere ai seguenti elementi:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   In caso contrario, contattate il team di account.

1. Verificate che l&#39;utente disponga delle autorizzazioni necessarie in  Adobe Campaign Standard e Experience Platform Launch.
   * In  Adobe Campaign Standard, accertatevi che l&#39;utente IMS faccia parte dei profili di prodotto standard per l&#39;utente e l&#39;amministratore. Questo passaggio consente all&#39;utente di accedere a  Adobe Campaign Standard, passare alla pagina dell&#39;app mobile SDK del Experience Platform  e visualizzare le proprietà dell&#39;app mobile che hai creato Experience Platform Launch.

   * Ad Experience Platform Launch, accertatevi che l&#39;utente IMS faccia parte di un profilo di prodotto di Experience Platform Launch.
Questo passaggio consente all&#39;utente di accedere al Experience Platform Launch per creare e visualizzare le proprietà. Per ulteriori informazioni sui profili di prodotto nell&#39;Experience Platform Launch, consulta Creazione del profilo di prodotto. Nel profilo di prodotto non dovrebbero essere impostate autorizzazioni per la società o le proprietà, ma l&#39;utente dovrebbe essere ancora in grado di effettuare l&#39;accesso.

   Per completare altre attività come l&#39;installazione di un&#39;estensione, la pubblicazione di un&#39;app, la configurazione di ambienti e così via, è necessario impostare le autorizzazioni nel profilo di prodotto.

1. Nell&#39;Experience Platform Launch, creare un **[!UICONTROL Mobile property]**. Per ulteriori informazioni, consulta [Configurare una proprietà mobile](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).

1. Nell&#39;Experience Platform Launch, fare clic sulla scheda **[!UICONTROL Extensions]**, passare a **[!UICONTROL Catalog]** e cercare l&#39;estensione **[!UICONTROL Adobe Campaign Standard]**. Per ulteriori informazioni, vedere [ Adobe Campaign Standard](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).

1. Per supportare i casi di utilizzo della posizione in Campaign Standard, installare l&#39;estensione **[!UICONTROL Places]** e l&#39;estensione **[!UICONTROL Places Monitor]**.
   * Installate l&#39;estensione **[!UICONTROL Places]** nel Experience Platform Launch. Fare riferimento a questa [pagina](https://docs.adobe.com/content/help/it-IT/places/using/places-ext-aep-sdks/places-extension/places-extension.html).
   * Installate l&#39;estensione **[!UICONTROL Places Monitor]** nel Experience Platform Launch. Fare riferimento a questa [pagina](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html)

1. In Adobe Campaign Standard, configura la proprietà mobile creata in Experience Platform Launch. Fare riferimento a [Configurazione dell&#39;applicazione Adobe Experience Platform Launch  in  Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Aggiungi la configurazione specifica per il canale alla configurazione dell’app mobile.
Per ulteriori informazioni, consulta [Configurazione dell’applicazione specifica per il canale in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessario, è possibile eliminare la proprietà Experience Platform Launch.
Per ulteriori informazioni, vedere [Eliminazione dell&#39;applicazione di Experience Platform Launch](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronizza AEPSDK app mobile dal flusso di lavoro tecnico di Launch {#aepsdk-workflow}

Dopo aver creato e configurato la proprietà mobile nel Experience Platform Launch, il flusso di lavoro tecnico **[!UICONTROL Sync Mobile app AEPSDK from Launch]** sincronizzerà le proprietà mobili del  Adobe Launch importate in  Adobe Campaign Standard.

Per impostazione predefinita, il flusso di lavoro tecnico inizia ogni 15 minuti. Se necessario, può essere riavviato manualmente:

1. In  Adobe Campaign Standard, dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Aprire il flusso di lavoro **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**.

   ![](assets/launch_10.png)

1. Fare clic sull&#39;attività **[!UICONTROL Scheduler]**.

1. Seleziona **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Il flusso di lavoro verrà ora riavviato e sincronizzato le proprietà  Adobe Launch mobile importate in  Adobe Campaign Standard.

## Impostazione dell&#39;applicazione Adobe Experience Platform Launch  in  Adobe Campaign {#set-up-campaign}

Per utilizzare una proprietà mobile Experience Platform Launch in Campaign, devi anche configurare questa proprietà in  Adobe Campaign. In  Adobe Campaign, accertatevi che l&#39;utente IMS faccia parte dei profili di prodotto standard per l&#39;utente e l&#39;amministratore.

È necessario attendere l&#39;esecuzione del flusso di lavoro tecnico e sincronizzare la proprietà Launch mobile a  Adobe Campaign. Potete quindi configurarlo in  Adobe Campaign.

Per ulteriori informazioni sul flusso di lavoro tecnico di sincronizzazione AEPSDK dell&#39;app mobile, consulta la sezione [](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Per impostazione predefinita, gli amministratori con unità organizzativa impostata su ALL possono modificare l’applicazione mobile.

1. Dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Selezionate l’applicazione mobile creata nel Experience Platform Launch.
Il valore **[!UICONTROL Property Status]** deve essere **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Per impostazione predefinita, per recuperare l&#39;elenco delle applicazioni mobili create in  Adobe Launch, Campaign Standard utilizza il valore definito nell&#39;opzione NmsServer_URL per cercare le proprietà corrispondenti.
   >
   >In alcuni casi, l&#39;endpoint della campagna per un&#39;applicazione mobile può essere diverso da quello definito in NmsServer_URL. In tal caso, definite l’endpoint nell’opzione Launch_URL_Campaign. Campaign utilizzerà il valore di questa opzione per cercare le proprietà corrispondenti in  Adobe Launch.

   ![](assets/launch_4.png)

1. È possibile modificare l&#39;unità organizzativa dell&#39;applicazione mobile nella sezione **[!UICONTROL Access Authorization]** per limitare l&#39;accesso a questa applicazione mobile a unità aziendali specifiche. Per ulteriori informazioni, consulta questa pagina.

   In questo caso, l’amministratore può assegnare unità organizzative secondarie selezionandole dall’elenco a discesa.

   ![](assets/launch_12.png)

1. Per stabilire la connessione tra Campaign e Experience Platform Launch, fare clic su **[!UICONTROL Save]**.

1. Verifica che lo stato dell&#39;app mobile sia cambiato da **[!UICONTROL Ready to Configure]** a **[!UICONTROL Configured]**.

   Quando l&#39;estensione Campagna di Experience Platform Launch mostra che la chiave è stata configurata correttamente, puoi anche verificare che la proprietà sia stata configurata correttamente in Campaign.

   ![](assets/launch_5.png)

1. Affinché questa configurazione abbia effetto, le modifiche devono essere pubblicate in Experience Platform Launch.

   Per ulteriori informazioni, vedere [Configurazione pubblicazione](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-configuration).

## Configurazione dell&#39;applicazione specifica per il canale in  Adobe Campaign {#channel-specific-config}

L&#39;applicazione mobile ora è pronta per essere utilizzata in Campaign per le notifiche push o le consegne in-app. Ora puoi configurarlo ulteriormente se necessario per creare eventi che attivino i messaggi in-app e/o che caricino i certificati push.

1. Dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleziona l’applicazione mobile creata e configurata nel Experience Platform Launch.

1. Nella scheda **[!UICONTROL Mobile application properties]** puoi iniziare ad aggiungere gli eventi disponibili nell&#39;applicazione mobile per i messaggi in-app.

1. Per configurare gli eventi, fate clic su **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digitate un nome e una descrizione.

   ![](assets/launch_7.png)

1. Fai clic su **[!UICONTROL Add]**.

   L&#39;evento è ora disponibile nella scheda Triggers quando crei un messaggio in-app. Per ulteriori informazioni, vedi [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. Nella sezione **[!UICONTROL Device-specific settings]** di un dashboard di applicazione mobile, per ciascun dispositivo, fornite i dettagli dell&#39;applicazione, incluso il certificato per iOS e la chiave server per Android.

   Dopo il caricamento del certificato, un messaggio notifica l’avvenuta riuscita del caricamento e visualizza la data di scadenza del certificato.

   >[!NOTE]
   >
   >Dopo l&#39;aggiunta del certificato in  Adobe Campaign Standard, non sarà più possibile modificare le impostazioni perché è possibile aggiungere una sola piattaforma APNS (produzione o sandbox) all&#39;app MCPNS.

   ![](assets/launch_8.png)

1. Fate clic sulla scheda **[!UICONTROL Mobile application subscribers]** per visualizzare un elenco di sottoscrittori e altre informazioni su questi sottoscrittori, ad esempio se hanno rinunciato alle notifiche.

## Eliminazione dell&#39;applicazione Adobe Experience Platform Launch  {#delete-app}

L&#39;eliminazione dell&#39;applicazione di Experience Platform Launch non può essere annullata.

>[!CAUTION]
>
>L&#39;eliminazione dell&#39;applicazione di Experience Platform Launch non può essere annullata.

Per eliminare l&#39;applicazione di Experience Platform Launch, completare i passaggi descritti in [Eliminazione delle proprietà mobili](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#deleting-mobile-properties-in-experience-platform-launch).

Dopo che l&#39;applicazione è stata eliminata, in  Adobe Campaign, verificate che lo stato delle proprietà dell&#39;applicazione sia stato aggiornato correttamente in Eliminato in Launch.

Facendo clic sull&#39;applicazione in  Adobe Campaign, puoi scegliere di rimuovere completamente questa applicazione da  Adobe Campaign facendo clic su Elimina da Campaign.

![](assets/launch_9.png)
