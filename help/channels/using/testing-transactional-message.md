---
solution: Campaign Standard
product: campaign
title: Verifica di un messaggio transazionale
description: Scopri come verificare un messaggio transazionale in  Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 39%

---


# Verifica di un messaggio sulle transazioni {#testing-a-transactional-message}

Prima di pubblicare il messaggio transazionale, potete creare un profilo di test specifico che vi consenta di controllare correttamente il messaggio.

## Definizione di un profilo di test specifico {#defining-specific-test-profile}

Definite un profilo di test che sarà collegato all&#39;evento, per consentirvi di visualizzare l&#39;anteprima del messaggio e inviare una prova pertinente.

1. Dal [dashboard messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), fare clic sul pulsante **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Specifica le informazioni da inviare in formato JSON nella sezione **[!UICONTROL Event data used for personalization]**. Tale contenuto verrà utilizzato al momento della visualizzazione dell’anteprima del messaggio e quando il profilo di test riceve la bozza.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Se hai arricchito il messaggio, puoi anche immettere informazioni relative a un&#39;altra tabella, ad esempio **[!UICONTROL Profile]**. Vedere [Arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) e [Personalizzazione di un messaggio transazionale](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Una volta creato, il profilo di test verrà prespecificato nel messaggio di transazione. Per controllare la destinazione della bozza, fai clic sul blocco **[!UICONTROL Test profiles]** del messaggio.

   ![](assets/message-center_5.png)

Puoi anche creare un nuovo profilo di test o usarne uno già esistente nel menu **[!UICONTROL Test profiles]**. Per eseguire questa operazione:

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Nella sezione **[!UICONTROL Event]**, selezionate l&#39;evento appena creato. In questo esempio, seleziona &quot;Abbandono carrello (EVTcartAbandonment)&quot;.
1. Nella casella di testo **[!UICONTROL Event data]**, specifica le informazioni da inviare in formato JSON.

   ![](assets/message-center_3.png)

1. Salva le modifiche.
1. [Accedete al ](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) messaggio creato e selezionate il profilo di test aggiornato.

**Argomenti correlati:**

* [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)
* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)

## Invio della prova {#sending-proof}

Dopo aver creato uno o più profili di test specifici e aver salvato il messaggio transazionale, potete inviare una prova per verificarlo.

![](assets/message-center_10.png)

I passaggi per l&#39;invio di una prova sono descritti nella sezione [Invio di prove di validità](../../sending/using/sending-proofs.md).
