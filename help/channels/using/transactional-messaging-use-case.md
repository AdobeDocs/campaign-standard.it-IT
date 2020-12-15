---
solution: Campaign Standard
product: campaign
title: Caso di utilizzo di messaggi transazionali
description: Scopri un esempio completo della funzionalità di messaggistica transazionale  Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 2%

---


# Caso di utilizzo di messaggi transazionali {#transactional-messaging-use-case}

In questo esempio, si desidera utilizzare la funzionalità di messaggistica transazionale  Adobe Campaign per inviare un messaggio e-mail di conferma dopo ogni acquisto sul sito Web, identificando i clienti tramite il proprio ID CRM.

I prerequisiti sono i seguenti:

* Accertatevi che la risorsa **[!UICONTROL Profile]** sia stata estesa con un nuovo campo corrispondente all&#39;ID CRM.

* Create e pubblicate una risorsa personalizzata corrispondente agli acquisti e collegatela alla risorsa **[!UICONTROL Profile]**. In questo modo, potrai recuperare informazioni da questa risorsa per arricchire il contenuto del messaggio.

Per ulteriori informazioni sull&#39;estensione, la creazione e la pubblicazione di risorse, consultate [questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

Le fasi principali per l&#39;implementazione di questo caso di utilizzo sono illustrate di seguito.

>[!NOTE]
>
>Per una rappresentazione grafica del processo generale di messaggistica transazionale, vedere [questo schema](../../channels/using/getting-started-with-transactional-msg.md#key-steps).

## Passaggio 1 - Creare e pubblicare la configurazione dell&#39;evento {#create-event-configuration}

1. Create un nuovo evento utilizzando il canale **[!UICONTROL Email]**. Vedi [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Selezionate la dimensione di targeting **[!UICONTROL Profile]** per creare un messaggio transazionale basato su profilo [](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

1. Definite gli attributi che saranno disponibili per personalizzare il messaggio transazionale. In questo esempio, aggiungi i campi &quot;CRM ID&quot; e &quot;Product Identifier&quot;. Vedere [Definizione degli attributi evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes).

   ![](assets/message-center_usecase1.png)

1. Per arricchire il contenuto del messaggio con informazioni relative agli acquisti del cliente, create un arricchimento per la risorsa **[!UICONTROL Purchase]**. Vedere [Arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content).

   ![](assets/message-center_usecase2.png)

1. Create una condizione di partecipazione tra il campo &quot;Product Identifier&quot; precedentemente aggiunto all&#39;evento e il campo corrispondente dalla risorsa **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase3.png)

1. Poiché è obbligatorio per gli eventi basati sul profilo, è necessario creare anche un arricchimento per la risorsa **[!UICONTROL Profile]**.

1. Crea una condizione di partecipazione tra il campo &quot;ID CRM&quot; precedentemente aggiunto al messaggio e il campo corrispondente dalla risorsa **[!UICONTROL Profile]** estesa. <!--What's the purpose to have created a CRM ID for this event and to have the CRM ID as a join condition? could it be any other field provided you created it in the event?-->

   ![](assets/message-center_usecase4.png)

1. Nella sezione **[!UICONTROL Targeting enrichment]**, selezionare l&#39;arricchimento sulla risorsa **[!UICONTROL Profile]**, che verrà utilizzata come destinazione del messaggio durante l&#39;esecuzione del recapito.

   ![](assets/message-center_usecase5.png)

1. Visualizzate l’anteprima e pubblicate l’evento. Vedi [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Passaggio 2 - Modifica e pubblica il messaggio di transazione {#create-transactional-message}

1. Passate al messaggio transazionale creato automaticamente al momento della pubblicazione dell’evento. Vedere [Accesso ai messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Modifica e personalizza il messaggio. Vedere [Modifica di un messaggio di transazione profilo](../../channels/using/editing-transactional-message.md#editing-profile-transactional-message).

1. Attraverso la riconciliazione con il campo &quot;ID CRM&quot; aggiunto alla risorsa **[!UICONTROL Profile]**, l&#39;utente ha accesso diretto a tutte le informazioni di profilo per [personalizzare](../../designing/using/personalization.md#inserting-a-personalization-field) il messaggio.

   ![](assets/message-center_usecase6.png)

1. Attraverso la riconciliazione con il campo &quot;ID prodotto&quot;, puoi arricchire il contenuto del messaggio con informazioni relative agli acquisti del cliente aggiungendo qualsiasi campo dalla risorsa **[!UICONTROL Purchase]**.

   ![](assets/message-center_usecase7.png)

   A questo scopo, selezionare **[!UICONTROL Insert personalization field]** dalla barra degli strumenti contestuale. Dal nodo **[!UICONTROL Context]** > **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]**, aprire il nodo corrispondente alla risorsa **[!UICONTROL Purchase]** personalizzata e selezionare un campo qualsiasi.

1. Puoi testare il messaggio utilizzando un profilo di test specifico. Vedere [Verifica di un messaggio transazionale](../../channels/using/testing-transactional-message.md#testing-a-transactional-message).

1. Quando il contenuto è pronto, salvate le modifiche e pubblicate il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

## Passaggio 3 - Integrare l&#39;attivazione dell&#39;evento {#integrate-event-trigger}

Integrate l’evento nel vostro sito Web. Vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Passaggio 4 - Invio di messaggi {#message-delivery}

Una volta che tutti questi passaggi sono stati eseguiti, non appena un cliente acquista prodotti dal tuo sito web, riceve un&#39;e-mail di conferma personalizzata con informazioni sul suo acquisto.