---
solution: Campaign Standard
product: campaign
title: Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse
description: Scopri come creare un messaggio personalizzato basato sulla posizione degli abbonati con l'integrazione dei dati del punto di interesse.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse{#personalizing-campaign-messages-with-point-of-interest-data}

In  Adobe Campaign, puoi utilizzare i dati dei punti di interesse raccolti dagli abbonati dell&#39;applicazione mobile per inviare loro messaggi di marketing personalizzati, ad esempio un&#39;e-mail.

Puoi reagire solo sui dati dei punti di interesse con consegne standard. [I ](../../channels/using/getting-started-with-transactional-msg.md) messaggi transazionali non possono utilizzare i dati sulla posizione.

La prima reazione è di circa 10 minuti.

In questo caso, si decide di inviare un&#39;e-mail a tutti gli abbonati che hanno visitato il vostro Boston Store nelle ultime due settimane.

1. Creare un&#39;attività di e-mail marketing.
1. Quando definite l&#39;audience della distribuzione, trascinate e rilasciate l&#39;elemento **[!UICONTROL Subscriptions to an application]** nell&#39;area di lavoro.

   ![](assets/poi_subscriptions_app.png)

   La gestione delle audience è dettagliata nella sezione [Definizione delle audience](../../audiences/using/creating-audiences.md).

1. Nella finestra **[!UICONTROL Add a rule - Profile/Subscriptions to an application]**, trascinare l&#39;elemento **[!UICONTROL POI Location Subscription]** nell&#39;area di lavoro.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Nella finestra **[!UICONTROL Add a rule - POI Location Subscription]**, immettere l&#39;etichetta del punto di interesse che si desidera utilizzare.

   ![](assets/poi_location_subscription.png)

1. Nel campo **[!UICONTROL Filter type]** seleziona **[!UICONTROL Relative]**.
1. Selezionare l&#39;opzione **[!UICONTROL Preceding days]** e immettere **[!UICONTROL 15]** nel campo corrispondente.
1. Definisci quante volte l&#39;utente deve aver visitato il punto di interesse.
1. Fate clic su **[!UICONTROL Confirm]** per salvare il pubblico.

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

