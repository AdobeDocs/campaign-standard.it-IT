---
title: Domande frequenti sull’integrazione di Adobe Experience Platform SDK e Adobe Campaign
description: Domande frequenti sull’integrazione di Adobe Experience Platform SDK e Adobe Campaign
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 6b3c189d-8ddd-4dc0-8831-65ae62e04c70
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 2%

---

# Domande frequenti sull’integrazione di Experience Platform SDK {#aep-faq}

Per inviare notifiche push e messaggi in-app con l’applicazione Experience Platform SDK, un’app mobile deve essere configurata in Adobe Experience Platform SDK e configurata in Adobe Campaign.

La sezione seguente elenca le domande comuni relative a questa sincronizzazione.

Per ulteriori informazioni su Push o In-App, consulta le seguenti Domande frequenti:

* [Domande frequenti sulle notifiche push](../../channels/using/about-push-notifications.md#push-faq)
* [Domande frequenti in-app](../../channels/using/in-app-faq.md)
* [Domande frequenti sulla sincronizzazione dei tag in Adobe Experience Platform](../../administration/using/syncwithlaunch-faq.md)

## Risorse utili prima di iniziare {#resource-mobile-property}

Consulta le risorse riportate di seguito per ulteriori informazioni sull’integrazione di Adobe Experience Platform SDK e Campaign Standard:

* Launch/Mobile [Video introduttivo](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Launch/Mobile [Guida ai suggerimenti](https://www.adobe.com/content/dam/dx/us/en/products/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## L’integrazione Adobe Experience Platform SDK è disponibile sia per Adobe Campaign Standard che per Adobe Campaign Classic? {#aep-validity}

Sì, [!DNL Adobe Experience Platform SDK] L’integrazione è disponibile sia per Adobe Campaign Standard che per Adobe Campaign Classic. È necessario installare il **[!UICONTROL Extension]** tramite [!DNL Data Collection UI] per abilitare l’integrazione.

Per ulteriori informazioni, consulta questo [page]https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).

## Quali funzionalità facilita l&#39;integrazione Adobe Experience Platform SDK in Adobe Campaign? {#aep-capabilities}

Per ulteriori informazioni su queste funzionalità, consulta la tabella seguente.

![](assets/faq.png)

>[!NOTE]
>
>[!DNL Places] l’integrazione include eventi place come trigger per i messaggi in-app (N/D per le notifiche push), arricchendo i profili con [!DNL Places] supporto di dati e notifiche locali. Fai riferimento a questo [page](../../channels/using/preparing-and-sending-an-in-app-message.md) per ulteriori informazioni. <br>[!DNL Places] l’integrazione limitata include l’arricchimento dei profili con [!DNL Places] dati.

## Quale caso d’uso facilita l’integrazione dell’SDK Adobe Experience Platform in Adobe Campaign Standard? {#aep-use-cases}

Sono supportati i seguenti casi d’uso:

* Acquisisci un **[!UICONTROL Mobile Profile]** in Campaign (identificato da ECID in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** scheda )
* Arricchisci **[!UICONTROL Mobile Profile]** in Adobe Campaign (richiede **[!UICONTROL Custom resource Extension]** della tabella appSubscriberRcp)
* Acquisire un token push per l’invio di messaggi push (richiede l’opt-in dell’utente per ricevere i messaggi push)
* Inviare messaggi push e in-app
* Monitora l’interazione dell’utente con i messaggi push e in-app e fornisci rapporti su di essa

## Cosa devo fare per acquisire un profilo mobile in Campaign? {#mobile-profile-campaign}

A questo scopo, segui i passaggi riportati qui sotto:

1. Configura un **[!UICONTROL Mobile property]** in [!DNL Launch].
1. Installa l&#39;estensione Adobe Campaign Standard. Tieni presente che l’estensione Adobe Campaign Standard richiede anche **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** e **[!UICONTROL Lifecycle]** estensioni installate per impostazione predefinita in [!DNL Launch].
   * Gli utenti devono configurare il timeout della sessione in **[!UICONTROL Mobile Core]** estensione che influisce sulla frequenza degli eventi del ciclo di vita.
   * Una volta configurata l’estensione, gli utenti devono aggiungere dipendenze appropriate nell’app mobile utilizzando Cocoapods per iOS e Gradle per Android. Seguire le indicazioni [qui](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard).
   * Prendi sempre le versioni più recenti delle librerie.
   * Nell’app mobile, registrati **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]**, **[!UICONTROL Lifecycle]** e **[!UICONTROL Signal]** estensioni. Seguire le indicazioni [qui](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#register-the-campaign-standard-extension-with-mobile-core).
   * Una volta registrate le estensioni, avvia ACPCore. Per Android, assicurati di impostareApplication onCreate(). Segui le istruzioni esatte fornite nelle istruzioni di installazione per dispositivi mobili per la tua proprietà mobile in Launch.
   * Saranno necessarie anche le seguenti API SDK. Implementare le API di avvio e pausa del ciclo di vita come descritto [qui](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android) per Android e qui per iOS.
1. Configura un **[!UICONTROL Mobile Property]** in Adobe Campaign Standard. Seguire la procedura [qui](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Cosa devo fare per arricchire un profilo mobile in Campaign? {#enrich-mobile-profile}

Devi configurare un postback CollectPII (consulta questo [page](../../administration/using/configuring-rules-launch.md#pii-postback)) e implementa l&#39;API CollectPII dall&#39;SDK (consulta questo [page](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference)).

## Con quale frequenza dovrebbe essere attivata una chiamata CollectPII? {#collect-pii}

L’obiettivo della chiamata CollectPII è di arricchire il profilo mobile in Campaign. Deve essere attivato ogni volta che sono presenti nuove informazioni significative che i clienti desiderano aggiungere al profilo in base ai casi d’uso e alle esigenze aziendali.

## Le chiamate CollectPII possono essere attivate in risposta a più eventi trigger? {#collect-pii-calls}

Sì. A seconda delle tue esigenze aziendali, puoi attivare le chiamate CollectPII in risposta all&#39;accesso degli utenti all&#39;app, o acquistare qualcosa o un evento del ciclo di vita o un utente che accede a un recinto geografico, ecc. In sintesi, un’interazione dell’utente con l’app che genera informazioni da utilizzare per l’arricchimento del profilo.

## Posso semplicemente attivare le chiamate CollectPII in risposta a tutti gli eventi Mobile? {#collect-pii-events}

La frequenza e la progettazione delle chiamate CollectPII devono essere dettate dalle esigenze aziendali e non devono essere attivate in modo cieco in quanto crea un carico aggiuntivo sul DB.

### Quando provo ad accedere alle app Adobe Experience Platform in Campaign o Launch, a volte ottengo un errore di proprietà non disponibile. {#aep-error}

Questo è un problema noto e si verifica a causa della scadenza del token. Prova ad accedere.

## Quali sono alcuni consigli utili sulle risorse per saperne di più sull’SDK di Adobe Experience Platform (precedentemente noto come SDK V5)?{#resource-aep}

Consulta le risorse seguenti:

* Experience Platform SDK [documentazione](https://developer.adobe.com/client-sdks/documentation/)
* Guida introduttiva a Launch e Experience Platform SDK [documentazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/)
* Aggiornamento ad Experience Platform SDK [documentazione](https://developer.adobe.com/client-sdks/documentation/upgrade-platform-sdks)
* SDK per Experience Platform Github [documentazione](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)

## Ricevo l’errore &quot;Non disponi dell’accesso in scrittura sulla consegna&quot; durante la creazione di una consegna di notifiche push. {#write-access-error}

Controlla quanto segue:

* L’app mobile deve essere mappata sull’unità organizzativa dell’utente che deve creare e inviare consegne push. L’utente di un’unità organizzativa figlio non può creare una consegna push utilizzando un’app mappata all’unità organizzativa principale.

* La campagna o il programma all’interno del quale viene creata la consegna push deve essere mappato all’unità organizzativa dell’utente che deve creare e inviare le consegne push. L’utente dell’unità organizzativa figlio non può creare una consegna push in una campagna o in un programma mappato all’unità organizzativa padre.
