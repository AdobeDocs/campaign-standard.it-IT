---
title: Informazioni sulla messaggistica in-app
description: La messaggistica in-app ti consente di visualizzare i messaggi o gli avvisi all’interno dell’app mobile.
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
source-git-commit: df7fce6f2fd98688e5a1fb5bc84603e6b3df5cd4
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 100%

---

# Informazioni sulla messaggistica in-app{#about-in-app-messaging}

La messaggistica in-app rappresenta un canale di messaggistica che consente di visualizzare un messaggio quando l’utente è attivo all’interno dell’app mobile. Questo tipo di messaggio è complementare alle notifiche push inviate al centro di notifica del telefono degli utenti. Per ulteriori informazioni sul canale di notifica push, consulta questa [sezione](../../channels/using/about-push-notifications.md).

Il canale richiede l’integrazione delle app mobili all’interno dell’SDK di Adobe Experience Platform. Queste app devono essere attivate all’interno di Adobe Experience Platform Launch prima di essere disponibili su Adobe Campaign per le consegne in-app.

![](assets/launch_campaign.png)

Per iniziare a inviare messaggi in-app sulle app mobili che utilizzano l’SDK di Experience Platform, devi soddisfare i seguenti prerequisiti:

1. In Adobe Campaign, assicurati di poter accedere al canale **[!UICONTROL In-App]**. Se non riesci ad accedere a questi canali, contatta il team dell’account.

1. Per sfruttare i casi d’uso per dispositivi mobili all’interno di Adobe Campaign Standard con un’applicazione Experience Cloud SDK, devi creare un’app mobile in Adobe Experience Platform Launch e configurarla all’interno di Adobe Campaign Standard. Per la guida dettagliata, fai riferimento a questa [pagina](../../administration/using/configuring-a-mobile-application.md).

1. Una volta effettuata la configurazione, potrai preparare il messaggio in-app. Per ulteriori informazioni, consulta questa [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Puoi quindi decidere di inviare un [messaggio in-app](../../channels/using/customizing-an-in-app-message.md) o una [Personalizzazione di un tipo di messaggio di notifica locale](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

1. Adesso la consegna è pronta per essere inviata. Per ulteriori informazioni, fai riferimento a questa [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenuto correlato:**

* [Rapporto in-app](../../reporting/using/in-app-report.md)
* [Casi d’uso per dispositivi mobili supportati in Adobe Campaign Standard](../../administration/using/configuring-rules-launch.md)
* [Guida a Campaign Standard per dispositivi mobili](../../channels/using/get-started-communication-channels.md)

## Gestione dei campi del profilo mobile con dati personali e sensibili {#handling-mobile-profile-fields-with-personal-and-sensitive-data}

In Adobe Campaign, i dati degli attributi del profilo mobile inviati da dispositivi mobili sono memorizzati nella risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** che ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni.

Questa risorsa deve essere estesa per raccogliere i dati che intendi inviare dal dispositivo mobile ad Adobe Campaign. A tale scopo, consulta questa [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) per i passaggi dettagliati.

Per abilitare la personalizzazione dei messaggi in-app in modo più sicuro, i campi del profilo mobile di questa risorsa devono essere configurati di conseguenza. In **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, quando crei i nuovi campi dei profili mobili, seleziona **[!UICONTROL Personal and Sensitive]** per renderli non disponibili durante la personalizzazione dei messaggi in-app.

>[!NOTE]
>
>Se disponi di un’implementazione esistente con estensione di risorse personalizzata in questa tabella, è consigliabile etichettare i campi in modo appropriato prima di sfruttarli per la personalizzazione dei messaggi in-app.

![](assets/in_app_personal_data_2.png)

Una volta configurata e pubblicata la risorsa personalizzata **[!UICONTROL Subscriptions to an application]**, puoi iniziare a preparare la consegna in-app utilizzando il modello **[!UICONTROL Target users based on their Mobile profile (inApp)]**. Solo i campi non personali e non riservati della risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** saranno disponibili per la personalizzazione.

Se desideri poter personalizzare i campi **Personali e riservati**, è consigliabile utilizzare il modello **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** che offre un meccanismo di sicurezza aggiuntivo per garantire la protezione dei dati PII degli utenti.