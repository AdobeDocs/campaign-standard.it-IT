---
solution: Campaign Standard
product: campaign
title: Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse
description: Scopri come creare un messaggio personalizzato in base alla posizione degli abbonati con l’integrazione dei dati del punto di interesse .
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Pubblici
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 10%

---


# Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse{#personalizing-campaign-messages-with-point-of-interest-data}

In Adobe Campaign puoi utilizzare i dati dei punti di interesse raccolti dagli abbonati all’app mobile per inviare loro messaggi di marketing personalizzati, ad esempio un’e-mail.

Puoi reagire solo ai dati dei punti di interesse con le consegne standard. [I ](../../channels/using/getting-started-with-transactional-msg.md) messaggi transazionali non possono utilizzare i dati sulla posizione.

Il più presto che si può reagire è di circa 10 minuti.

In questo caso, decidi di inviare un’e-mail a tutti gli abbonati che hanno visitato il tuo negozio di Boston nelle ultime due settimane.

1. Crea un’attività di marketing e-mail.
1. Quando definisci il pubblico della consegna, trascina e rilascia l’elemento **[!UICONTROL Subscriptions to an application]** nell’area di lavoro.

   ![](assets/poi_subscriptions_app.png)

   La gestione dei tipi di pubblico è descritta nella sezione [Definizione dei tipi di pubblico](../../audiences/using/creating-audiences.md) .

1. Nella finestra **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** , trascina e rilascia l’elemento **[!UICONTROL POI Location Subscription]** nell’area di lavoro.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Nella finestra **[!UICONTROL Add a rule - POI Location Subscription]**, immetti l’etichetta del punto di interesse che desideri utilizzare.

   ![](assets/poi_location_subscription.png)

1. Nel campo **[!UICONTROL Filter type]** seleziona **[!UICONTROL Relative]**.
1. Seleziona l’opzione **[!UICONTROL Preceding days]** e immetti **[!UICONTROL 15]** nel campo corrispondente.
1. Definisci il numero di volte in cui l’utente deve aver visitato il punto di interesse.
1. Fai clic su **[!UICONTROL Confirm]** per salvare il pubblico.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Aggiungi contenuti all’e-mail.

   ![](assets/poi_email_content.png)

1. Conferma la creazione dell’attività per visualizzare il dashboard e-mail.
1. Invia il tuo messaggio.

L’e-mail con l’offerta di sconto del 10% verrà inviata agli abbonati che:

* Ho visitato il tuo negozio di Boston almeno una volta nelle ultime due settimane.
* Hai avuto la tua app mobile in primo piano almeno una volta durante la visita.

**Argomenti correlati:**

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization)
* [Invio di messaggi](../../sending/using/confirming-the-send.md)

