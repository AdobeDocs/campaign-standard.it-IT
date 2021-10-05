---
title: Domande frequenti in-app
description: Domande frequenti sulla messaggistica in-app
audience: channels
content-type: reference
topic-tags: in-app-messaging
context-tags: delivery,triggers,back
feature: In App
role: User
exl-id: 986646b1-42d5-4169-ac38-d8e612a9a6d3
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 2%

---


# Domande frequenti in-app {#in-app-faq}

## Quali sarebbero alcuni consigli utili per le risorse per ulteriori informazioni sul canale in-app in Adobe Campaign Standard? {#resources-inapp}

Consulta le risorse seguenti:

* [Tutorial video](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/in-app/in-app-message-overview.html)
* [Post del blog](https://theblog.adobe.com/get-more-out-of-the-new-in-app-message-channel-from-adobe-campaign/)
* [Pagina community](https://experienceleaguecommunities.adobe.com/it/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

## Qual è lo scopo delle API delle estensioni Campaign setLinkageField e resetLinkageField? {#extensions-apis}

Poiché i messaggi in-app vengono richiamati dall’SDK da Campaign, vogliamo fornire un meccanismo di sicurezza per garantire che i messaggi in-app contenenti dati PII non finiscano in mani malevoli. In quanto tale, abbiamo il seguente meccanismo in atto per garantire la consegna sicura dei messaggi al dispositivo:

* I clienti contrassegnano i campi del profilo mobile (tabella appSubscriberRcp) come Personali e riservati se desiderano garantire che queste informazioni particolari vengano fornite in modo sicuro.
* I campi contrassegnati come tali possono essere utilizzati solo nel modello di profilo (non nel modello appSubscriber o nel modello Broadcast) che ha un meccanismo di sicurezza aggiuntivo integrato.
* I messaggi generati utilizzando il modello di profilo possono essere serviti solo quando l’utente ha effettuato l’accesso all’app.
* Per facilitare questo handshake sicuro, gli sviluppatori di app mobili devono trasmettere ulteriori dettagli di autenticazione utilizzando l’API setLinkageField . Tieni presente che il campo di collegamento sono quelli identificati come collegamento tra profilo mobile e profilo CRM durante l’estensione della tabella appSubscriberRcp.
* Devono eseguire il flush dei messaggi in-app memorizzati sul dispositivo e resetLinkagefields quando l&#39;utente si disconnette dall&#39;app utilizzando resetLinkageField. In questo modo, se un utente diverso accede all’app, non vede i messaggi destinati all’utente precedente.
* Per implementare questo meccanismo di sicurezza lato client, fai riferimento a [API SDK per dispositivi mobili](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference) .

## Cosa devo fare per abilitare il reporting in-app in Campaign? {#enable-inapp-reporting}

Devi configurare il postback di tracciamento in-app. Le istruzioni sono disponibili [qui](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback).

Per implementare il tracciamento delle notifiche locali, fai riferimento a questa [pagina](../../administration/using/local-tracking.md).

## Quali rapporti sono disponibili per il canale in-app? {#report-inapp}

Un rapporto preconfigurato è disponibile in Adobe Campaign per il canale in-app. Fai riferimento a questa [documentazione](../../reporting/using/in-app-report.md).

Consulta questa [pagina](../../reporting/using/indicator-calculation.md#in-app-delivery) per capire come vengono calcolate le metriche in-app.

## Supporta varianti di contenuto multilingue per in-app simili a push? {#multilingual-inapp}

Non sono ora disponibili modelli multilingue per i messaggi in-app.

Tuttavia, se l’obiettivo è quello di inviare un messaggio in-app in una lingua diversa dall’inglese, il contenuto può essere incollato direttamente nelle caselle di testo disponibili.

![](assets/faq_inapp.png)

## I campi di personalizzazione di Campaign possono essere aggiunti all’HTML personalizzato? {#custom-html-inapp}

No, non è ancora supportato.

## Ho configurato un messaggio di avviso ma non viene visualizzato sul dispositivo. {#alert-message}

Per i messaggi di avviso, è necessario almeno un pulsante di disattivazione (primario o secondario con chiusura dell’azione). In caso contrario, è possibile salvare il messaggio ma non verrà ricevuto.

## Se le notifiche locali l&#39;audio personalizzato iOS non viene riprodotto; verrà invece riprodotto il suono predefinito? {#local-notification-sound}

Per l&#39;audio personalizzato su iOS, è necessario fornire un nome file con estensione durante la creazione di una notifica locale (ad esempio, sound.caf). Se questa estensione non viene fornita, viene utilizzato l&#39;audio predefinito.

## I collegamenti profondi sono supportati nei messaggi in-app? {#inapp-deeplinks}

Sì, i collegamenti profondi sono supportati nei messaggi in-app. I collegamenti profondi dovrebbero includere:

* che indica che il tracciamento della consegna deve essere disabilitato per far funzionare i collegamenti profondi.
* Applicare un flyer con Branch come partner in grado di eseguire il tracciamento del deep link. Per ulteriori informazioni sull&#39;integrazione di Branch e Adobe Campaign Standard, consulta questa [pagina](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).

## È possibile attivare un messaggio in-app quando l’utente avvia l’app da una notifica push? {#inapp-push-trigger}

Sì, questi messaggi sono anche denominati messaggi a catena margherita. Segui la procedura seguente:

1. Crea un messaggio in-app.

1. Definisci un evento personalizzato e selezionalo come attivatore di eventi per questo IAM, ad esempio &quot;Trigger da push di anteprima in caduta&quot;.

1. Quando crei il messaggio push, definisci una variabile personalizzata il cui valore può essere impostato come evento utilizzato per attivare IAM, ad esempio Key = &quot;inappkey&quot; e value = &quot;Trigger from fall preview Push&quot; (Attiva da push di anteprima).

1. Nel codice dell’app mobile, implementa l’attivatore evento come segue:

   ![](assets/faq_inapp_2.png)
