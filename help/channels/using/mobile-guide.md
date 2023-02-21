---
title: Guida a Campaign Standard per dispositivi mobili
description: Scopri le linee guida generali per le consegne su dispositivi mobili in Adobe Campaign Standard, ad esempio come configurare le app mobili o creare notifiche push e messaggi in-app.
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 25%

---

# Introduzione ai canali mobile {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>Scopri come configurare la tua app mobile per le notifiche push </br><a href="#configuration-push">Fai clic qui</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>Scopri come configurare la tua app mobile per i messaggi in-app </br><a href="#configuring-mobile-app">Fai clic qui</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>Ulteriori informazioni su come creare le notifiche push </br><a href="#create-push">Fai clic qui</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>Scopri come creare messaggi in-app</br><a href="#create-inapp">Fai clic qui</a></p></td></tr>
</table>

## Informazioni sulla distribuzione mobile {#about-mobile}

Adobe Campaign consente di creare e inviare messaggi personalizzati su vari canali e di misurarne l’efficacia tramite report dedicati.

Con Adobe Campaign Standard puoi inviare consegne su dispositivi mobili tramite tre diversi canali:

* SMS, presentato nella sezione Informazioni sui messaggi SMS .
* Notifiche push, presentate nella sezione Informazioni sulle notifiche push .
* Messaggi in-app, presentati nella sezione Informazioni sui messaggi in-app .

## Configurare l’app mobile per le notifiche push {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configurazione di un’app mobile tramite SDK per Adobe Experience Platform</strong></p>
    </div>
    <p>Per inviare messaggi in-app e notifiche push, le tue app mobili devono essere configurate in Adobe Campaign sfruttando gli SDK Adobe Experience Platform.Per ulteriori informazioni, </br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Struttura del payload per le notifiche push di Campaign Standard</strong></p>
    </div>
    <p>Ulteriori informazioni sulla struttura del payload ricevuto nelle applicazioni mobili quando una notifica push viene inviata correttamente a un’app da Adobe Campaign Standard.Per ulteriori informazioni, </br><a href="../../administration/using/push-payload.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Implementazione del tracciamento delle notifiche locali</strong></p>
    </div>
    <p>Scopri come garantire che il tracciamento delle notifiche locali sia stato implementato correttamente. Per ulteriori informazioni, </br><a href="../../administration/using/local-tracking.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementazione del tracciamento push</strong></p>
    </div>
    <p>Scopri come garantire che il tracciamento delle notifiche push sia stato implementato correttamente in iOS e Android.Per ulteriori informazioni, </br><a href="../../administration/using/push-tracking.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
</table>

## Configurare un’app mobile per i messaggi in-app {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configurazione di un’app mobile tramite SDK per Adobe Experience Platform</strong></p>
    </div>
    <p>Per inviare messaggi in-app e notifiche push, le tue app mobili devono essere configurate in Adobe Campaign sfruttando gli SDK Adobe Experience Platform.Per ulteriori informazioni, </br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Casi d’uso per dispositivi mobili supportati tramite SDK Adobe Experience Platform</strong></p>
    </div>
    <p>Ulteriori informazioni sui casi di utilizzo per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK Adobe Experience Platform.Per ulteriori informazioni, </br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Configurazione delle regole di tag per supportare casi d’uso di Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>Fai clic qui</strong></a> per iniziare a creare elementi dati e regole nell’interfaccia utente di raccolta dati per inviare dati PII e altri dati dalle applicazioni mobili ad Adobe Campaign Standard.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementazione del tracciamento delle notifiche locali</strong></p>
    </div>
    <p>Scopri come garantire che il tracciamento delle notifiche locali sia stato implementato correttamente. Per ulteriori informazioni, </br><a href="../../administration/using/local-tracking.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
</table>

## Creare una notifica push {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparazione e invio di una notifica push</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>Scopri qui</strong></a> come preparare la notifica push e quindi come inviarla al pubblico di destinazione.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalizzazione di una notifica push</strong></p>
    </div>
    <p>Per ottimizzare la consegna, Adobe Campaign ti consente di accedere a un set di opzioni durante la progettazione di una notifica push.Per ulteriori informazioni, </br><a href="../../channels/using/customizing-a-push-notification.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Creazione di una notifica push multilingue</strong></p>
    </div>
    <p>Personalizza il contenuto delle notifiche push inviando messaggi in base alle lingue e alle aree geografiche preferite dagli utenti.Per ulteriori informazioni, </br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Visualizzazione di un’immagine da una notifica push di Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>Scopri qui</strong></a> come visualizzare un’immagine da una notifica push di Adobe Campaign su un dispositivo iOS.</p>
    <br>
  </td>
</tr>
</table>

## Creare un messaggio in-app {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparazione e invio di un messaggio in-app</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>Scopri qui</strong></a> come preparare i messaggi in-app e quindi come inviarli al pubblico di destinazione.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalizzazione dei messaggi in-app</strong></p>
    </div>
    <p>Per ottimizzare la consegna, Adobe Campaign ti consente di accedere a un set di opzioni avanzate durante la progettazione in-app.Per ulteriori informazioni, </br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Personalizzazione di un tipo di messaggio di notifica locale</strong></p>
    </div>
    <p>Le notifiche locali possono essere attivate solo da un’app in un momento particolare e in base a un evento. Per ulteriori informazioni, </br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Rapporto in-app</strong></p>
    </div>
    <p>Il rapporto in-app fornisce dettagli relativi alle consegne in-app.Per ulteriori informazioni, </br><a href="../../reporting/using/in-app-report.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
</table>

## Creare messaggi SMS {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Creazione di un messaggio SMS</strong></p>
    </div>
    <p>Creare una consegna di SMS è una procedura molto simile a quella per una normale e-mail. </br>I passaggi <a href="../../channels/using/creating-an-sms-message.md"><strong>qui</strong></a> descrive la configurazione specifica di questo canale.</br></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalizzazione di un messaggio SMS
</strong></p>
    </div>
    <p>Per ottimizzare la consegna, Adobe Campaign ti consente di accedere a un set di opzioni avanzate durante la progettazione di un messaggio SMS.Per ulteriori informazioni, </br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>fai clic qui.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong></p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Gestione degli SMS in arrivo</strong></p>
    </div>
    <p>Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, puoi configurare i messaggi che vengono automaticamente ritrasmessi e l’azione da eseguire.Personalizzazione di un tipo di messaggio di notifica locale</br><a href="../../channels/using/managing-incoming-sms.md"><strong>Fai clic qui per ulteriori informazioni.</br><a href="../../channels/using/managing-incoming-sms.md"><strong></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Rapporto SMS</strong></p>
    </div>
    <p>Il rapporto SMS fornisce dettagli sulle consegne SMS, ad esempio consegne e tassi non recapitati.Per ulteriori informazioni, </br><a href="../../reporting/using/sms-report.md"><strong>fai clic qui</strong></a>.</p>
    <br>
  </td>
</tr>
</table>

## Risoluzione dei problemi di Mobile {#mobile-troubleshooting}

Le pagine seguenti sono utili per risolvere i problemi più comuni che si verificano quando si utilizza la distribuzione mobile in Adobe Campaign Classic.

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Domande frequenti sulle notifiche push</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>Per ulteriori informazioni, fai clic qui.</p>
  </td>
  <td>
    <div>
    <p><strong>Domande frequenti sulla sincronizzazione di Adobe Launch</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>Per ulteriori informazioni, fai clic qui.</p>
  </td>
  <td>
    <div>
    <p><strong>Domande frequenti in-app</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>Per ulteriori informazioni, fai clic qui.</p>
  </td>
</tr>
</table>
