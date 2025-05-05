---
title: Configurazione di un’app per dispositivi mobili
description: Scopri come configurare Adobe Campaign per l’invio di notifiche push o messaggi in-app tramite l’SDK di Experience Platform
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 58b07f023f52e2bf4972b4a86bf4412f613f38da
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 2%

---

# Configurazione di un’app per dispositivi mobili{#configuring-a-mobile-application}

## Configurazione di un’app mobile tramite gli SDK di Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> Adobe Experience Platform Launch è stato ridefinito come suite di tecnologie di raccolta dati in Adobe Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta il [documento seguente](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html){target="_blank"} per un riferimento consolidato delle modifiche terminologiche.

Tieni presente che le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Per assistenza, contatta il tuo responsabile dell’account Adobe o un partner di servizi professionali.

Per inviare notifiche push e messaggi in-app con l’applicazione SDK Experience Platform, è necessario configurare un’app mobile nell’interfaccia utente di Data Collection e configurarla in Adobe Campaign.

Una volta configurata un’app mobile, puoi recuperare i dati PII raccolti per creare o aggiornare i profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle app mobili](../../channels/using/updating-profile-with-mobile-app-data.md).

Per ulteriori informazioni sui diversi casi d&#39;uso per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK di Adobe Experience Platform, consulta questa [pagina](../../administration/using/supported-mobile-use-cases.md).

La procedura seguente illustra come completare la configurazione:

1. In Adobe Campaign, assicurati di poter accedere ai seguenti elementi:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   In caso contrario, contatta il team del tuo account.

1. Verifica che l’utente disponga delle autorizzazioni necessarie in Adobe Campaign Standard e nei tag in Adobe Experience Platform.

   * In Adobe Campaign Standard, accertati che l’utente IMS faccia parte dei profili di prodotto Utente standard e Amministratore. Questo passaggio consente all’utente di accedere ad Adobe Campaign Standard, passare alla pagina dell’app mobile SDK di Experience Platform e visualizzare le proprietà dell’app mobile create nell’interfaccia utente di Data Collection.

   * Nell’interfaccia utente di Data Collection, accertati che l’utente IMS faccia parte di un profilo di prodotto Experience Platform Launch.
Questo passaggio consente all’utente di accedere all’interfaccia utente di Data Collection per creare e visualizzare le proprietà. Per ulteriori informazioni sui profili di prodotto nell&#39;interfaccia utente di Data Collection, vedi [Creare il tuo profilo di prodotto](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html#gain-admin-rights-for-a-tags-product-profile). Nel profilo prodotto non dovrebbero essere impostate autorizzazioni per l’azienda o le proprietà, ma l’utente dovrebbe essere comunque in grado di accedere.

   Per completare attività aggiuntive come l’installazione di un’estensione, la pubblicazione di un’app, la configurazione di ambienti e così via, è necessario impostare le autorizzazioni nel profilo di prodotto.

1. Nell&#39;interfaccia utente di Data Collection, creare un **[!UICONTROL Mobile property]**. Per ulteriori informazioni, consulta [Configurare una proprietà mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property).

1. Nell&#39;interfaccia utente di Data Collection, fare clic sulla scheda **[!UICONTROL Extensions]**, passare a **[!UICONTROL Catalog]** e cercare l&#39;estensione **[!UICONTROL Adobe Campaign Standard]**. Per ulteriori informazioni, vedere [Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

1. Per supportare i casi di utilizzo della posizione in Campaign Standard, installa l&#39;estensione **[!UICONTROL Places]** nell&#39;interfaccia utente di Data Collection. Fai riferimento a questa [pagina](https://developer.adobe.com/client-sdks/solution/places).

1. In Adobe Campaign Standard, configura la proprietà mobile creata nell’interfaccia utente di Data Collection. Consulta [Configurazione dell&#39;applicazione Adobe Experience Platform Launch in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Aggiungi la configurazione specifica per il canale alla configurazione dell’app mobile.
Per ulteriori informazioni, consulta [Configurazione dell’applicazione specifica per il canale in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessario, puoi eliminare la proprietà tag.
Per ulteriori informazioni, vedere [Eliminazione dell&#39;applicazione](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronizzare l’app mobile AEPSDK dal flusso di lavoro tecnico di Launch {#aepsdk-workflow}

Dopo aver creato e configurato la proprietà mobile nell&#39;interfaccia utente di Data Collection, il flusso di lavoro tecnico **[!UICONTROL Sync Mobile app AEPSDK from Launch]** sincronizzerà le proprietà mobili dei tag importate in Adobe Campaign Standard.

Per impostazione predefinita, il flusso di lavoro tecnico viene avviato ogni 15 minuti. Se necessario, può essere riavviato manualmente:

1. In Adobe Campaign Standard, dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Apri il flusso di lavoro **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]**.

   ![](assets/launch_10.png)

1. Fai clic sull&#39;attività **[!UICONTROL Scheduler]**.

1. Seleziona **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Ora il flusso di lavoro viene riavviato e sincronizzato con le proprietà importate dei tag per dispositivi mobili in Adobe Campaign Standard.

## Configurazione dell’applicazione in Adobe Campaign {#set-up-campaign}

Per utilizzare una proprietà mobile di tag in Campaign, è necessario configurare anche questa proprietà in Adobe Campaign. In Adobe Campaign, accertati che l’utente IMS faccia parte dei profili di prodotto Utente standard e Amministratore.

Devi attendere l’esecuzione del flusso di lavoro tecnico e sincronizzare la proprietà mobile dei tag con Adobe Campaign. Puoi quindi configurarlo in Adobe Campaign.

Per ulteriori informazioni su Sync Mobile app AEPSDK from Launch technical workflow, consulta questa [sezione](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Per impostazione predefinita, gli amministratori con unità organizzativa impostata su ALL possono modificare l’app mobile.

1. Dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Seleziona l’app mobile creata nell’interfaccia utente di Data Collection.
Il valore **[!UICONTROL Property Status]** deve essere **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Per impostazione predefinita, per recuperare l’elenco delle app mobili create nell’interfaccia utente di Data Collection, Campaign Standard utilizza il valore definito nell’opzione NmsServer_URL per cercare le proprietà corrispondenti.
   >
   >In alcuni casi, l’endpoint Campaign per un’app mobile potrebbe essere diverso da quello definito in NmsServer_URL. In tal caso, definire l&#39;endpoint nell&#39;opzione `Launch_URL_Campaign`. Campaign utilizzerà il valore di questa opzione per cercare le proprietà corrispondenti nell’interfaccia utente di Data Collection.

   ![](assets/launch_4.png)

1. È possibile modificare l&#39;unità organizzativa dell&#39;app mobile nella sezione **[!UICONTROL Access Authorization]** per limitare l&#39;accesso a questa app mobile a unità organizzative specifiche. Per ulteriori informazioni, consulta questa pagina.

   In questo caso, l’amministratore può assegnare unità organizzative secondarie selezionandole dall’elenco a discesa.

   ![](assets/launch_12.png)

1. Per stabilire la connessione tra Campaign e i tag in Adobe Experience Platform, fare clic su **[!UICONTROL Save]**.

1. Verificare che lo stato dell&#39;app mobile sia cambiato da **[!UICONTROL Ready to Configure]** a **[!UICONTROL Configured]**.

   Quando l’estensione Campaign mostra che la chiave è stata configurata correttamente, puoi anche verificare che la proprietà sia stata configurata correttamente in Campaign.

   ![](assets/launch_5.png)

1. Affinché questa configurazione diventi effettiva, le modifiche devono essere pubblicate nell’interfaccia utente di Data Collection.

   Per ulteriori informazioni, vedere [Configurazione Publish](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## Configurazione dell’applicazione specifica per il canale in Adobe Campaign {#channel-specific-config}

L’app mobile è ora pronta per essere utilizzata in Campaign per le notifiche push o le consegne in-app. Ora puoi configurarlo ulteriormente se necessario per creare eventi che attiveranno i messaggi in-app e/o il caricamento di certificati push.

1. Dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleziona l’app mobile creata e configurata nell’interfaccia utente di Data Collection.

1. Nella scheda **[!UICONTROL Mobile application properties]** puoi iniziare ad aggiungere gli eventi disponibili nella tua app mobile per i messaggi in-app.

1. Per configurare gli eventi, fare clic su **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digita un nome e una descrizione.

   ![](assets/launch_7.png)

1. Fai clic su **[!UICONTROL Add]**.

   Il tuo evento è ora disponibile nella scheda Attivatori quando crei un messaggio in-app. Per ulteriori informazioni, vedere [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. Nella sezione **[!UICONTROL Device-specific settings]** del dashboard di un&#39;app mobile, specifica i dettagli dell&#39;applicazione per ciascun dispositivo.

   +++*  Per iOS

     Immettere i dettagli dell&#39;applicazione riportati di seguito.

      * **ID app (ID bundle iOS)**: per ulteriori informazioni sull&#39;ID bundle, consulta la [documentazione di Apple](https://developer.apple.com/documentation/appstoreconnectapi/bundle_ids){target="_blank"}.
      * **File certificato iOS (P8)**: trascina e rilascia la chiave di autenticazione .p8. Per istruzioni su come generare il file di autenticazione .p8, fai riferimento al tuo [account sviluppatore Apple](https://developer.apple.com/account/ios/authkey/create){target="_blank"}.
      * **ID chiave**: per ulteriori informazioni sull&#39;ID chiave, consulta la [documentazione di Apple](https://developer.apple.com/help/account/manage-keys/get-a-key-identifier/){target="_blank"}.
      * **ID team iOS**: per ulteriori informazioni sull&#39;ID team iOS, consulta la [documentazione Apple](https://developer.apple.com/help/account/manage-your-team/locate-your-team-id/){target="_blank"}.

        ![](assets/mobile_app_ios_config.png)
   +++

   +++*  Per Android

     Immettere i dettagli dell&#39;applicazione riportati di seguito.

      * **ID app (nome pacchetto Android)**: per ulteriori informazioni sul nome del pacchetto, consulta la [documentazione di Android](https://support.google.com/admob/answer/9972781?hl=en#:~:text=The%20package%20name%20of%20an,supported%20third%2Dparty%20Android%20stores){target="_blank"}.
      * **File chiave Android (Json)**: trascina e rilascia il file della chiave privata .json. Per istruzioni su come generare il file della chiave privata .json, consulta la [documentazione per gli sviluppatori di Firebase](https://firebase.google.com/docs/admin/setup#initialize_the_sdk_in_non-google_environments){target="_blank"}.

        ![](assets/mobile_app_android_config.png)
   +++

1. Dopo il caricamento del certificato, un messaggio notifica che il caricamento è riuscito e visualizza la data di scadenza del certificato.

1. Fare clic sulla scheda **[!UICONTROL Mobile application subscribers]** per visualizzare un elenco degli abbonati e altre informazioni su questi abbonati, ad esempio se hanno rinunciato alle notifiche.

## Eliminazione dell’applicazione {#delete-app}

>[!CAUTION]
>
>L’eliminazione dell’applicazione non può essere annullata.

Per eliminare l&#39;applicazione, completare i passaggi in [Eliminazione delle proprietà mobili](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui).

Dopo aver eliminato l’applicazione, in Adobe Campaign verifica se lo stato di Proprietà dell’applicazione è stato aggiornato correttamente a Eliminato in Launch.

Facendo clic sull’applicazione in Adobe Campaign, puoi scegliere di rimuoverla completamente da Adobe Campaign facendo clic su Elimina da Campaign.

![](assets/launch_9.png)
