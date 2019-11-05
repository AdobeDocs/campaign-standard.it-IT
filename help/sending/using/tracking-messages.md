---
title: Tracciamento dei messaggi
description: Scopri come tenere traccia del comportamento dei destinatari della distribuzione.
page-status-flag: mai attivato
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: invio e tracciamento di messaggi
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Tracciamento dei messaggi{#tracking-messages}

## Informazioni sul tracciamento {#about-tracking}

Grazie alle sue funzionalità di tracciamento, Adobe Campaign consente di monitorare il comportamento dei destinatari della distribuzione. A tal fine, Adobe Campaign utilizza i cookie di sessione e i cookie permanenti.

Potete informare gli utenti che i vostri siti sono dotati di strumenti di monitoraggio Web tramite una richiesta di autorizzazione (che viene visualizzata sopra la pagina, ad esempio) con una casella di controllo per autorizzare l’uso dei cookie, o aggiungere un banner nella parte superiore della prima pagina in cui accedono, ecc. Le finestre a comparsa dovrebbero essere evitate in quanto spesso bloccate dai browser.

Adobe Campaign utilizza due tipi di cookie:

* Un cookie di sessione (nlid). Contiene l’identificatore dell’e-mail inviata al contatto (BroadlogId) e l’identificatore del modello di messaggio (deliveryId). Viene aggiunto quando il contatto fa clic su un URL incluso in un'e-mail inviata da Adobe Campaign e consente di tracciarne il comportamento sul Web. Questo cookie di sessione viene cancellato automaticamente alla chiusura del browser. Il contatto può configurare il browser per rifiutare i cookie.
* Cookie condiviso tra le soluzioni Adobe Experience Cloud. Questo consente di identificare gli utenti che interagiscono con le soluzioni Experience Cloud quando visitano un sito Web. La descrizione di questo cookie è disponibile qui: [https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_mc.html).

Sono disponibili informazioni di tracciamento per ogni contatto del database in **[!UICONTROL integrated customer profiles]**. For more on this, refer to [this section](../../audiences/using/integrated-customer-profile.md).

## Tracciamento dei registri {#tracking-logs}

La **[!UICONTROL Tracking logs]** scheda elenca la cronologia di tracciamento per la consegna. In questa scheda vengono visualizzate le informazioni di tracciamento dei messaggi inviati, ad esempio tutti gli URL tracciati da Adobe Campaign. Le informazioni di tracciamento in questa scheda vengono aggiornate ogni 10 minuti.

>[!NOTE]
>
>Se il tracciamento non è abilitato per una consegna, questa scheda non viene visualizzata. I registri di tracciamento sono disponibili solo per i canali di **e-mail** e di notifica **** push.

![](assets/tracking_logs.png)

Nell'esempio precedente, il destinatario:

* Apertura del messaggio.
* Fate clic sul collegamento personalizzato "LEARN MORE".
* Fare clic sul collegamento della pagina mirror e dell'annullamento dell'iscrizione.

Nella **[!UICONTROL Type]** colonna, i valori possibili sono:

* **[!UICONTROL Email click]**: i destinatari hanno fatto clic su un collegamento personalizzato.
* **[!UICONTROL Mirror page]**: il destinatario ha fatto clic su un collegamento alla pagina mirror.
* **[!UICONTROL Open]**: il destinatario ha aperto il messaggio e-mail.
* **[!UICONTROL Opt-out]**: il destinatario ha fatto clic su un collegamento di annullamento dell'iscrizione.

>[!NOTE]
>
>Per il canale di notifica **** push, vengono tracciati solo i clic sulle notifiche per dispositivi mobili. In tal caso, il valore sarà **[!UICONTROL Click on mobile notification]**.

Per ulteriori informazioni su come inserire i collegamenti di tracciamento, consulta [questa pagina](../../designing/using/links.md#inserting-a-link).

## URL tracciati {#tracked-urls}

La **[!UICONTROL Tracked URLs]** scheda raggruppa gli URL contenuti nel messaggio inviato, incluso il tipo di URL e l'URL di origine.

![](assets/sending_delivery6.png)

For more on tracking links, refer to [this section](../../designing/using/links.md#about-tracked-urls).
