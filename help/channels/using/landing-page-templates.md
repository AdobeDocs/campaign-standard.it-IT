---
title: Modelli per pagine di destinazione
seo-title: Modelli per pagine di destinazione
description: Modelli per pagine di destinazione
seo-description: Ulteriori informazioni sui modelli delle pagine di destinazione.
page-status-flag: mai attivato
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaite
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: landing page
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,procedura guidata;landingPage,panoramica;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9cdfafad7a2ac2db59b037962a84aa03568a55e6

---


# Informazioni sui modelli di pagina di destinazione {#landing-page-templates}

Campaign viene fornito con un set di modelli di pagina di destinazione incorporati:

* **[!UICONTROL Acquisition]**: questo è il modello predefinito per le pagine di destinazione, che consente di acquisire e aggiornare i dati nel database Campaign.
* **[!UICONTROL Subscription]**: questo modello deve essere utilizzato per offrire iscrizioni a un servizio.
* **[!UICONTROL Unsubscription]**: questo modello può essere collegato da un’e-mail inviata agli abbonati a un servizio per consentire loro di annullare l’iscrizione a questo servizio.
* **[!UICONTROL Blacklist]**: questo modello deve essere utilizzato quando un profilo non vuole più essere contattato da Campaign. Per ulteriori informazioni sull'inserimento in blacklist, consultate [Informazioni sull'opt-in e l'opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Questi modelli sono proposti per impostazione predefinita quando si crea una nuova pagina di destinazione.

![](assets/lp_creation_1.png)

Per accedere ai modelli della pagina di destinazione, fai clic sul logo Adobe Campaign in alto a sinistra e seleziona **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe consiglia di creare modelli personalizzati duplicando un modello incorporato. Alcuni parametri possono essere impostati solo nei modelli delle pagine di destinazione e non possono essere modificati direttamente nelle pagine di destinazione.

Durante la creazione di un modello, si consiglia di aggiungere un attributo **'type'** ai tag. Queste informazioni verranno elaborate dall'editor e aiuteranno l'utente a collegare un campo di database al campo del modulo durante la configurazione dell'applicazione Web.

Esempio di codice HTML nel modello:

```
<input id="email" type="email" name="email"/>
```

L'elenco ufficiale degli attributi 'type' è disponibile al seguente indirizzo: [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)