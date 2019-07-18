---
title: Messaggi di tracciamento
seo-title: Messaggi di tracciamento
description: Messaggi di tracciamento
seo-description: Scopri come tenere traccia del comportamento dei destinatari della distribuzione.
page-status-flag: never-activated
uuid: c 3721647-0663-4614-a 9 c 9-3 b 3 a 40 af 328 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: invio-and-tracking-messages
discoiquuid: 6 fa 50 f 0 d -3 dcf -4 a 9 e-bccc -1 ecda 2 bfb 449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Tracking messages{#tracking-messages}

## About tracking {#about-tracking}

Grazie alle funzionalità di tracciamento, Adobe Campaign consente di tenere traccia del comportamento dei destinatari della distribuzione. A questo scopo, Adobe Campaign utilizza i cookie di sessione e i cookie permanenti.

È possibile informare gli utenti che i siti sono dotati di strumenti di tracciamento Web tramite una richiesta di autorizzazione (ad esempio) con una casella di controllo per autorizzare l'utilizzo dei cookie, oppure aggiungere un banner nella parte superiore della prima pagina su cui si trovano, ecc. Le finestre a comparsa devono essere evitate perché spesso bloccate dai browser.

Adobe Campaign utilizza due tipi di cookie:

* Cookie sessione (nlid). Contiene l'identificatore dell'e-mail inviata al contatto (broadlogid) e l'identificatore del modello di messaggio (deliveryid). Viene aggiunta quando il contatto fa clic su un URL incluso in un'e-mail inviata da Adobe Campaign e vi consente di monitorarne il funzionamento sul Web. Il cookie di sessione viene cancellato automaticamente quando il browser viene chiuso. Il contatto può configurare il browser per rifiutare i cookie.
* Un cookie condiviso tra le soluzioni Adobe Experience Cloud. Questo consente di identificare gli utenti che interagiscono con le soluzioni Experience Cloud quando visitano un sito Web. The description of this cookie is available here: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracking logs {#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. Questa scheda visualizza le informazioni di tracciamento per i messaggi inviati, ad esempio tutti gli URL tracciati da Adobe Campaign. Le informazioni di tracciamento riportate in questa scheda vengono aggiornate ogni 10 minuti.

>[!NOTE]
>
>Se il tracciamento non è abilitato per una consegna, questa scheda non viene visualizzata. Tracking logs are available for the **email** and **push notification** channels only.

![](assets/tracking_logs.png)

Nell'esempio precedente, il destinatario:

* È stato aperto il messaggio.
* Clic sul collegamento personalizzato «LEARN MORE».
* Clic sull'iscrizione e sul collegamento della pagina speculare.

In the **[!UICONTROL Type]** column, the possible values are:

* **[!UICONTROL Email click]**: i destinatari hanno fatto clic su un collegamento personalizzato.
* **[!UICONTROL Mirror page]**: il destinatario ha fatto clic su un collegamento alla pagina speculare.
* **[!UICONTROL Open]**: il destinatario ha aperto il messaggio e-mail.
* **[!UICONTROL Opt-out]**: il destinatario ha fatto clic su un collegamento di annullamento dell'iscrizione.

>[!NOTE]
>
>For the **push notification** channel, only clicks on mobile notifications are tracked. In that case, the value will be **[!UICONTROL Click on mobile notification]**.

For more on how to insert tracking links, refer to [this page](../../designing/using/inserting-a-link.md).

## Tracked URLs {#tracked-urls}

**[!UICONTROL Tracked URLs]** La scheda raggruppa gli URL contenuti nel messaggio inviato, incluso il tipo di URL e il relativo URL di origine.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/about-tracked-urls.md).
