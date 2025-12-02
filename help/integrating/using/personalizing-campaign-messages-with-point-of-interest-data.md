---
title: Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse
description: Scopri come creare un messaggio personalizzato in base alla posizione degli abbonati con l’integrazione dei dati del punto di interesse.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 9%

---

# Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse{#personalizing-campaign-messages-with-point-of-interest-data}

In Adobe Campaign, puoi utilizzare i dati dei punti di interesse raccolti dagli abbonati all’app mobile per inviare loro messaggi di marketing personalizzati, ad esempio un’e-mail.

Puoi reagire solo ai dati dei punti di interesse con le consegne standard. [I messaggi transazionali](../../channels/using/getting-started-with-transactional-msg.md) non possono utilizzare i dati relativi alla posizione.

La prima reazione che puoi fare è di circa 10 minuti.

In questo caso, decidi di inviare un’e-mail a tutti gli abbonati che hanno visitato il tuo store di Boston nelle ultime due settimane.

1. Creare un’attività di e-mail marketing.
1. Durante la definizione del pubblico della consegna, trascina e rilascia l&#39;elemento **[!UICONTROL Subscriptions to an application]** nell&#39;area di lavoro.

   ![](assets/poi_subscriptions_app.png)

   La gestione dei tipi di pubblico è descritta nella sezione [Definizione dei tipi di pubblico](../../audiences/using/creating-audiences.md).

1. Nella finestra **[!UICONTROL Add a rule - Profile/Subscriptions to an application]**, trascinare e rilasciare l&#39;elemento **[!UICONTROL POI Location Subscription]** nell&#39;area di lavoro.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Nella finestra **[!UICONTROL Add a rule - POI Location Subscription]** immettere l&#39;etichetta del punto di interesse che si desidera utilizzare.

   ![](assets/poi_location_subscription.png)

1. Nel campo **[!UICONTROL Filter type]** seleziona **[!UICONTROL Relative]**.
1. Selezionare l&#39;opzione **[!UICONTROL Preceding days]** e immettere **[!UICONTROL 15]** nel campo corrispondente.
1. Definisci il numero di volte in cui l’utente deve aver visitato il punto di interesse.
1. Fai clic su **[!UICONTROL Confirm]** per salvare il pubblico.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Aggiungi contenuto all’e-mail.

   ![](assets/poi_email_content.png)

1. Conferma la creazione dell’attività per visualizzare la dashboard dell’e-mail.
1. Invia il messaggio.

L’e-mail con l’offerta di sconto del 10% verrà inviata agli abbonati che:

* Ho visitato il tuo negozio di Boston almeno una volta nelle ultime due settimane.
* L’app mobile era in primo piano almeno una volta durante la visita.

**Argomenti correlati:**

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization)
* [Invio di messaggi](../../sending/using/confirming-the-send.md)
