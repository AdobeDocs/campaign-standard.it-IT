---
title: Modelli per pagine di destinazione
description: Ulteriori informazioni sui modelli delle pagine di destinazione.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Informazioni sui modelli di pagina di destinazione {#landing-page-templates}

Campaign viene fornito con un set di modelli di pagina di destinazione incorporati:

* **[!UICONTROL Acquisition]**: questo è il modello predefinito per le pagine di destinazione, che consente di acquisire e aggiornare i dati nel database Campaign.
* **[!UICONTROL Subscription]**: questo modello deve essere utilizzato per offrire iscrizioni a un servizio.
* **[!UICONTROL Unsubscription]**: questo modello può essere collegato da un’e-mail inviata agli abbonati a un servizio per consentire loro di annullare l’iscrizione a questo servizio.
* **[!UICONTROL Block list]**: questo modello deve essere utilizzato quando un profilo non vuole più essere contattato da Campaign. Per ulteriori informazioni sulla gestione degli elenchi di blocchi, consultate [Informazioni sull&#39;opt-in e l&#39;opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Questi modelli sono proposti per impostazione predefinita quando si crea una nuova pagina di destinazione.

![](assets/lp_creation_1.png)

Per accedere ai modelli della pagina di destinazione, fate clic sul logo del Adobe Campaign  nell’angolo in alto a sinistra e selezionate **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Landing page templates]**.

>[!NOTE]
>
>Adobe consiglia di creare modelli personalizzati duplicando un modello incorporato. Alcuni parametri possono essere impostati solo nei modelli delle pagine di destinazione e non possono essere modificati direttamente nelle pagine di destinazione.

Durante la creazione di un modello, si consiglia di aggiungere un attributo **&#39;type&#39;** ai tag. Queste informazioni verranno elaborate dall&#39;editor e aiuteranno l&#39;utente a collegare un campo di database al campo del modulo durante la configurazione dell&#39;applicazione Web.

Esempio di codice HTML nel modello:

```
<input id="email" type="email" name="email"/>
```

L&#39;elenco ufficiale degli attributi &#39;type&#39; è disponibile al seguente indirizzo: [https://www.w3schools.com/tags/att_input_type.asp](https://www.w3schools.com/tags/att_input_type.asp)