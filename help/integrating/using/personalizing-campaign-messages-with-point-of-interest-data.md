---
title: Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse
description: Scopri come creare un messaggio personalizzato basato sulla posizione degli abbonati con l'integrazione dei dati del punto di interesse.
page-status-flag: never-activated
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse{#personalizing-campaign-messages-with-point-of-interest-data}

In  Adobe Campaign, puoi utilizzare i dati dei punti di interesse raccolti dagli abbonati dell&#39;applicazione mobile per inviare loro messaggi di marketing personalizzati, ad esempio un&#39;e-mail.

Puoi reagire solo sui dati dei punti di interesse con consegne standard. [I messaggi](../../channels/using/getting-started-with-transactional-msg.md) transazionali non possono utilizzare i dati sulla posizione.

La prima reazione è di circa 10 minuti.

In questo caso, si decide di inviare un&#39;e-mail a tutti gli abbonati che hanno visitato il vostro Boston Store nelle ultime due settimane.

1. Creare un&#39;attività di e-mail marketing.
1. Quando definite l&#39;audience della distribuzione, trascinate l&#39; **[!UICONTROL Subscriptions to an application]** elemento nell&#39;area di lavoro.

   ![](assets/poi_subscriptions_app.png)

   La gestione delle audience è dettagliata nella sezione [Definizione delle audience](../../audiences/using/creating-audiences.md) .

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Nella **[!UICONTROL Add a rule - POI Location Subscription]** finestra, immettere l&#39;etichetta del punto di interesse che si desidera utilizzare.

   ![](assets/poi_location_subscription.png)

1. Nel campo **[!UICONTROL Filter type]** seleziona **[!UICONTROL Relative]**.
1. Selezionare l&#39; **[!UICONTROL Preceding days]** opzione e immettere **[!UICONTROL 15]** nel campo corrispondente.
1. Definisci quante volte l&#39;utente deve aver visitato il punto di interesse.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Aggiungete contenuto all’e-mail.

   ![](assets/poi_email_content.png)

1. Confermate la creazione dell&#39;attività per visualizzare il dashboard dell&#39;e-mail.
1. Invia il tuo messaggio.

L&#39;e-mail con l&#39;offerta di sconto del 10% verrà inviata agli abbonati che:

* Ho visitato il tuo Boston Store almeno una volta nelle ultime due settimane.
* L&#39;applicazione mobile è stata messa in primo piano almeno una volta durante la visita.

**Argomenti correlati:**

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization)
* [Invio di messaggi](../../sending/using/confirming-the-send.md)

