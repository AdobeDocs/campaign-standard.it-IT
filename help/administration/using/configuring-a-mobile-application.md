---
title: Configurazione di un’app per dispositivi mobili
description: Scopri come configurare Adobe Campaign per l’invio di notifiche push o messaggi in-app tramite l’SDK di Experience Platform
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 5f9a8e84-a362-42b6-8bd2-e5d56214c1db
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1260'
ht-degree: 3%

---

# Configurazione di un’app per dispositivi mobili{#configuring-a-mobile-application}

## Configurazione di un’app mobile tramite gli SDK di Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!IMPORTANT]
>
> Adobe Experience Platform Launch è stato ridefinito come suite di tecnologie di raccolta dati in Adobe Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta la sezione [seguente documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html) per un riferimento consolidato delle modifiche terminologiche.

Tieni presente che le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Per assistenza, contatta il tuo responsabile dell’account Adobe o un partner di servizi professionali.

Per inviare notifiche push e messaggi in-app con l’applicazione SDK Experienci Platform, è necessario configurare un’app mobile nell’interfaccia utente di Data Collection e configurarla in Adobe Campaign.

Una volta configurata un’app mobile, puoi recuperare i dati PII raccolti per creare o aggiornare i profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle app mobili](../../channels/using/updating-profile-with-mobile-app-data.md).

Per ulteriori informazioni sui diversi casi d’uso per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK di Adobe Experience Platform, consulta questa [pagina](../../administration/using/supported-mobile-use-cases.md).

La procedura seguente illustra come completare la configurazione:

1. In Adobe Campaign, assicurati di poter accedere ai seguenti elementi:
   * **[!UICONTROL Push notification]**
   * **[!UICONTROL In-App message]**
   * **[!UICONTROL Adobe Places]**

   In caso contrario, contatta il team del tuo account.

1. Verifica che l’utente disponga delle autorizzazioni necessarie in Adobe Campaign Standard e nei tag in Adobe Experience Platform.
   * In Adobe Campaign Standard, accertati che l’utente IMS faccia parte dei profili di prodotto Utente standard e Amministratore. Questo passaggio consente all’utente di accedere ad Adobe Campaign Standard, passare alla pagina dell’app mobile SDK di Experienci Platform e visualizzare le proprietà dell’app mobile create nell’interfaccia utente di Data Collection.

   * Nell’interfaccia utente di Data Collection, accertati che l’utente IMS faccia parte di un profilo di prodotto Experience Platform Launch.
Questo passaggio consente all’utente di accedere all’interfaccia utente di Data Collection per creare e visualizzare le proprietà. Per ulteriori informazioni sui profili di prodotto nell’interfaccia utente di Data Collection, consulta [Creare il profilo di prodotto](https://experienceleague.adobe.com/docs/experience-platform/tags/admin/manage-permissions.html#gain-admin-rights-for-a-tags-product-profile). Nel profilo prodotto non dovrebbero essere impostate autorizzazioni per l’azienda o le proprietà, ma l’utente dovrebbe essere comunque in grado di accedere.

   Per completare attività aggiuntive come l’installazione di un’estensione, la pubblicazione di un’app, la configurazione di ambienti e così via, è necessario impostare le autorizzazioni nel profilo di prodotto.

1. Nell’interfaccia utente di Data Collection, crea un’ **[!UICONTROL Mobile property]**. Per ulteriori informazioni, consulta [Configurare una proprietà mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property).

1. Nell’interfaccia utente di Data Collection, fai clic su **[!UICONTROL Extensions]** , vai a **[!UICONTROL Catalog]**, e cercare **[!UICONTROL Adobe Campaign Standard]** estensione. Per ulteriori informazioni, consulta [Adobe Campaign Standard](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

1. Per supportare i casi di utilizzo della posizione in Campaign Standard, installa **[!UICONTROL Places]** nell’interfaccia utente di Data Collection. Fai riferimento a questo [pagina](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html).

1. In Adobe Campaign Standard, configura la proprietà mobile creata nell’interfaccia utente di Data Collection. Fai riferimento a [Configurazione dell’applicazione Adobe Experience Platform Launch in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Aggiungi la configurazione specifica per il canale alla configurazione dell’app mobile.
Per ulteriori informazioni, consulta [Configurazione dell’applicazione specifica per il canale in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Se necessario, puoi eliminare la proprietà tag.
Per ulteriori informazioni, consulta [Eliminazione dell’applicazione](../../administration/using/configuring-a-mobile-application.md#delete-app).

## Sincronizzare l’app mobile AEPSDK dal flusso di lavoro tecnico di Launch {#aepsdk-workflow}

Dopo aver creato e configurato la proprietà mobile nell’interfaccia utente di Data Collection, il **[!UICONTROL Sync Mobile app AEPSDK from Launch]** il flusso di lavoro tecnico sincronizzerà ora le proprietà mobili dei tag importate in Adobe Campaign Standard.

Per impostazione predefinita, il flusso di lavoro tecnico viene avviato ogni 15 minuti. Se necessario, può essere riavviato manualmente:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.
1. Apri **[!UICONTROL Sync Mobile app AEPSDK from Launch (syncWithLaunch)]** flusso di lavoro.

   ![](assets/launch_10.png)

1. Fai clic sul pulsante **[!UICONTROL Scheduler]** attività.

1. Seleziona **[!UICONTROL Immediate execution]**.

   ![](assets/launch_11.png)

Ora il flusso di lavoro viene riavviato e sincronizzato con le proprietà importate dei tag per dispositivi mobili in Adobe Campaign Standard.

## Configurazione dell’applicazione in Adobe Campaign {#set-up-campaign}

Per utilizzare una proprietà mobile di tag in Campaign, è necessario configurare anche questa proprietà in Adobe Campaign. In Adobe Campaign, accertati che l’utente IMS faccia parte dei profili di prodotto Utente standard e Amministratore.

Devi attendere l’esecuzione del flusso di lavoro tecnico e sincronizzare la proprietà mobile dei tag con Adobe Campaign. Puoi quindi configurarlo in Adobe Campaign.

Per ulteriori informazioni su Sync Mobile app AEPSDK from Launch technical workflow (Sincronizza app mobile AEPSDK da flusso di lavoro tecnico di Launch), consulta questa [sezione](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow).

>[!NOTE]
>
>Per impostazione predefinita, gli amministratori con unità organizzativa impostata su ALL possono modificare l’app mobile.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

   ![](assets/launch.png)

1. Seleziona l’app mobile creata nell’interfaccia utente di Data Collection.
I suoi **[!UICONTROL Property Status]** dovrebbe essere **[!UICONTROL Ready to configure]**.

   >[!NOTE]
   >
   >Per impostazione predefinita, per recuperare l’elenco delle app mobili create nell’interfaccia utente di Data Collection, Campaign Standard utilizza il valore definito nell’opzione NmsServer_URL per cercare le proprietà corrispondenti.
   >
   >In alcuni casi, l’endpoint Campaign per un’app mobile potrebbe essere diverso da quello definito in NmsServer_URL. In tal caso, definisci il punto finale in `Launch_URL_Campaign` opzione. Campaign utilizzerà il valore di questa opzione per cercare le proprietà corrispondenti nell’interfaccia utente di Data Collection.

   ![](assets/launch_4.png)

1. Puoi modificare l’unità organizzativa della tua app mobile in **[!UICONTROL Access Authorization]** sezione per limitare l’accesso a questa app mobile a specifiche unità organizzative. Per ulteriori informazioni, consulta questa pagina.

   In questo caso, l’amministratore può assegnare unità organizzative secondarie selezionandole dall’elenco a discesa.

   ![](assets/launch_12.png)

1. Per stabilire la connessione tra Campaign e i tag in Adobe Experience Platform, fai clic su **[!UICONTROL Save]**.

1. Verifica che lo stato dell’app mobile sia cambiato da **[!UICONTROL Ready to Configure]** a **[!UICONTROL Configured]**.

   Quando l’estensione Campaign mostra che la chiave è stata configurata correttamente, puoi anche verificare che la proprietà sia stata configurata correttamente in Campaign.

   ![](assets/launch_5.png)

1. Affinché questa configurazione diventi effettiva, le modifiche devono essere pubblicate nell’interfaccia utente di Data Collection.

   Per ulteriori informazioni, consulta [Configurazione di pubblicazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration)

## Configurazione dell’applicazione specifica per il canale in Adobe Campaign {#channel-specific-config}

L’app mobile è ora pronta per essere utilizzata in Campaign per le notifiche push o le consegne in-app. Ora puoi configurarlo ulteriormente se necessario per creare eventi che attiveranno i messaggi in-app e/o il caricamento di certificati push.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]**.

1. Seleziona l’app mobile creata e configurata nell’interfaccia utente di Data Collection.

1. Il giorno **[!UICONTROL Mobile application properties]** , puoi iniziare ad aggiungere gli eventi disponibili nella tua app mobile per i messaggi in-app.

1. Per configurare gli eventi, fai clic su **[!UICONTROL Create Element]**.

   ![](assets/launch_6.png)

1. Digita un nome e una descrizione.

   ![](assets/launch_7.png)

1. Fai clic su **[!UICONTROL Add]**.

   Il tuo evento è ora disponibile nella scheda Attivatori quando crei un messaggio in-app. Per ulteriori informazioni, consulta [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md).

1. In **[!UICONTROL Device-specific settings]** sezione del dashboard di un’app mobile, per ogni dispositivo, fornisci i dettagli dell’applicazione, tra cui il certificato per iOS e la chiave del server per Android.

   Dopo il caricamento del certificato, un messaggio notifica che il caricamento è riuscito e visualizza la data di scadenza del certificato.

   >[!NOTE]
   >
   >Dopo l’aggiunta del certificato in Adobe Campaign Standard, non potrai più ripristinare le impostazioni poiché è possibile aggiungere una sola piattaforma APNS (produzione o sandbox) all’app MCPNS.

   ![](assets/launch_8.png)

1. Fai clic su **[!UICONTROL Mobile application subscribers]** per visualizzare un elenco degli abbonati e altre informazioni su tali abbonati, ad esempio se hanno rinunciato alle notifiche.

## Eliminazione dell’applicazione {#delete-app}

>[!CAUTION]
>
>L’eliminazione dell’applicazione non può essere annullata.

Per eliminare l’applicazione, completa i passaggi descritti in [Eliminazione delle proprietà dei dispositivi mobili](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#deleting-mobile-properties-in-the-data-collection-ui).

Dopo aver eliminato l’applicazione, in Adobe Campaign verifica se lo stato di Proprietà dell’applicazione è stato aggiornato correttamente a Eliminato in Launch.

Facendo clic sull’applicazione in Adobe Campaign, puoi scegliere di rimuoverla completamente da Adobe Campaign facendo clic su Elimina da Campaign.

![](assets/launch_9.png)
