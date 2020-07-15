---
title: ' Adobe Experience Platform SDK e  domande frequenti sull''integrazione dei Adobi Campaign'
description: ' Adobe Experience Platform SDK e  domande frequenti sull''integrazione dei Adobi Campaign'
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


#  Adobe Experience Platform SDK e  domande frequenti sull&#39;integrazione dei Adobi Campaign {#aep-faq}

## &#39;integrazione SDK di Adobe Experience Platform è disponibile per  Adobe Campaign Standard e  Adobe Campaign Classic? {#aep-validity}

Sì, [!DNL Adobe Experience Platform SDK] l&#39;integrazione è disponibile sia per  Adobe Campaign Standard che per  Adobe Campaign Classic. Per abilitare l&#39;integrazione, è necessario installare il **[!UICONTROL Extension]** metodo [!DNL Adobe Launch] corrispondente.

Per ulteriori informazioni, consultate questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic) per Campaign Classic e questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) per Campaign Standard.

## Quali funzionalità facilita &#39;integrazione SDK di Adobe Experience Platform in  Adobe Campaign? {#aep-capabilities}

Per ulteriori informazioni su queste funzionalità, fare riferimento alla tabella seguente.

![](assets/faq.png)

>[!Note]
>
>[!DNL Places] l&#39;integrazione include gli eventi come trigger per i messaggi in-app (N/D per le notifiche push), arricchendo i profili con il supporto di [!DNL Places] dati e notifiche locali. Per ulteriori informazioni, consultare questa [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md) . <br>[!DNL Places] l&#39;integrazione limitata include l&#39;arricchimento dei profili con [!DNL Places] i dati.

## Quali sono i casi d’uso ’integrazione SDK per Adobi Experience Platform facilita in  Adobe Campaign Standard? {#aep-use-cases}

Sono supportati i seguenti casi di utilizzo:

* Acquisisci una **[!UICONTROL Mobile Profile]** campagna (identificata da ECID in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (AEP SDK)]** > **[!UICONTROL Mobile Application subscribers]** scheda)
* Arricchimento di un **[!UICONTROL Mobile Profile]** Adobe Campaign  (richiede **[!UICONTROL Custom resource Extension]** la tabella appSubscriberRcp)
* Acquisire un token push per l&#39;invio di messaggi push (richiede all&#39;utente di acconsentire alla ricezione di messaggi push)
* Inviare messaggi push e in-app
* Monitora l&#39;interazione dell&#39;utente con i messaggi push e in-app e fornisci rapporti su di essa

## Cosa devo fare per acquisire un profilo mobile in Campaign? {#mobile-profile-campaign}

A tale scopo, attenetevi alla procedura seguente:

1. Configurare un **[!UICONTROL Mobile property]** in [!DNL Launch].
1. Installare &#39;estensione del Adobe Campaign Standard. Si noti che &#39;estensione di Adobe Campaign Standard richiede anche **[!UICONTROL Mobile Core]**, **[!UICONTROL Profile]** e **[!UICONTROL Lifecycle]** le estensioni installate per impostazione predefinita in [!DNL Launch].
   * Gli utenti devono configurare il timeout della sessione nell’ **[!UICONTROL Mobile Core]** estensione che influisce sulla frequenza degli eventi del ciclo di vita.
   * Una volta configurata l&#39;estensione, gli utenti devono aggiungere dipendenze appropriate nell&#39;app mobile utilizzando i cocodec per iOS e Gradle per Android. Seguite le indicazioni [qui](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard).
   * Prendete sempre le versioni più recenti delle librerie.
   * Nell&#39;app mobile, registrati **[!UICONTROL Campaign]**, **[!UICONTROL UserProfile]**, **[!UICONTROL Identity]****[!UICONTROL Lifecycle]** ed **[!UICONTROL Signal]** estensioni. Seguite le indicazioni [qui](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#register-the-campaign-standard-extension-with-mobile-core).
   * Una volta registrate le estensioni, avviate ACPCore. Per Android, accertatevi di setApplication onCreate(). Seguite le istruzioni esatte fornite in Istruzioni per l&#39;installazione mobile per la proprietà Mobile in Launch.
   * Saranno necessarie anche le seguenti API SDK. Implementa le API di avvio e pausa del ciclo di vita come descritto [qui](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android) per Android e qui per iOS.
1. Configurare un **[!UICONTROL Mobile Property]** Adobe Campaign Standard . Seguite la procedura [qui](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Cosa devo fare per arricchire un profilo mobile in Campaign? {#enrich-mobile-profile}

Devi configurare un postback CollectPII (fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback)) e implementare l’API CollectPII dall’SDK (consulta questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii)).

## Con quale frequenza dovrebbe essere attivata una chiamata CollectPII? {#collect-pii}

L&#39;obiettivo della chiamata CollectPII è di arricchire il profilo mobile in Campaign. Deve essere attivato ogni volta che vi sono nuove informazioni significative che i clienti vorrebbero aggiungere al profilo a seconda dei casi di utilizzo e delle esigenze aziendali.

## È possibile attivare le chiamate CollectPII in risposta a più eventi di attivazione? {#collect-pii-calls}

Sì. A seconda delle esigenze aziendali, puoi attivare le chiamate CollectPII in risposta all&#39;accesso degli utenti nell&#39;app, o acquistare qualcosa o un evento del ciclo di vita o l&#39;utente che accede a una determinata area geografica, ecc. In sintesi, un&#39;interazione dell&#39;utente con l&#39;app che genera informazioni da utilizzare per l&#39;arricchimento del profilo.

## Posso semplicemente attivare le chiamate CollectPII in risposta a tutti gli eventi Mobile? {#collect-pii-events}

La frequenza e la progettazione delle chiamate CollectPII devono essere dettate dalle esigenze aziendali e non devono essere eseguite in modo cieco, in quanto creano un carico aggiuntivo sul DB.

### Quando si tenta di accedere  app di Adobe Experience Platform in Campaign o Launch, a volte viene visualizzato un errore di proprietà non disponibile. {#aep-error}

Si tratta di un problema noto che si verifica a causa della scadenza del token. Provate a effettuare l&#39;accesso.

## Quali sono le raccomandazioni sulle risorse utili per ulteriori informazioni sulle proprietà Mobile configurate in  Adobe Experience Platform Launch? {#resource-mobile-property}

Consulta le risorse seguenti:

* Video introduttivo/ [Panoramica mobile](https://www.adobe.com/experience-platform/launch.html#acpl-mobile-video)
* Guida di [suggerimenti e trucchi per avvio/mobile](https://www.adobe.com/content/dam/www/us/en/experience-platform/launch-tag-manager/pdfs/adobe-cloud-platform-launch-tips-and-tricks-sheet.pdf)

## Quali sono le raccomandazioni sulle risorse utili per ottenere ulteriori informazioni  SDK per Adobi Experience Platform (precedentemente noto come SDK V5)?{#resource-aep}

Consulta le risorse seguenti:

*  [documentazione Experience Platform SDK](https://aep-sdks.gitbook.io/docs/)
* Guida introduttiva a Launch e  [documentazione SDK per Experience Platform](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)
* Aggiornamento alla  [documentazione SDK per Experience Platform](https://aep-sdks.gitbook.io/docs/resources/upgrading-to-aep)
* Github  [documentazione Experience Platform SDK](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)
