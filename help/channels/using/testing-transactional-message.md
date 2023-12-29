---
title: Verifica di un messaggio transazionale
description: Scopri come verificare un messaggio transazionale in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 5138826d-ae08-403b-91ef-91027ef6e78e
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 30%

---

# Verifica di un messaggio transazionale {#testing-a-transactional-message}

Prima di pubblicare il messaggio sulle transazioni, puoi creare un profilo di test specifico che ti consenta di controllarlo correttamente.

## Definizione di un profilo di test specifico {#defining-specific-test-profile}

Definisci un profilo di test da collegare all’evento, che ti consentirà di visualizzare l’anteprima del messaggio e di inviare una bozza rilevante.

1. Dalla sezione [dashboard dei messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), fare clic su **[!UICONTROL Create test profile]** pulsante.

   ![](assets/message-center_test-profile.png)

1. Specifica le informazioni da inviare in formato JSON nella sezione **[!UICONTROL Event data used for personalization]**. Tale contenuto verrà utilizzato al momento della visualizzazione dell’anteprima del messaggio e quando il profilo di test riceve la bozza.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Se hai arricchito il messaggio, puoi anche inserire informazioni relative a un’altra tabella, ad esempio **[!UICONTROL Profile]**. Consulta [Arricchimento dell’evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) e [Personalizzazione di un messaggio sulle transazioni](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Una volta creato, il profilo di test verrà prespecificato nel messaggio sulle transazioni. Per controllare la destinazione della bozza, fai clic sul blocco **[!UICONTROL Test profiles]** del messaggio.

   ![](assets/message-center_5.png)

Puoi anche creare un nuovo profilo di test o usarne uno già esistente in **[!UICONTROL Test profiles]** menu. Per eseguire questa operazione:

1. Fai clic su **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. In **[!UICONTROL Event]** , seleziona l’evento appena creato. In questo esempio, seleziona &quot;Abbandono carrello (EVTcartAbandonment)&quot;.
1. Nella casella di testo **[!UICONTROL Event data]**, specifica le informazioni da inviare in formato JSON.

   ![](assets/message-center_3.png)

1. Salva le modifiche.
1. [Accedere al messaggio](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) che hai creato e seleziona il profilo di test aggiornato.

**Argomenti correlati:**

* [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)
* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)

## Invio della bozza {#sending-proof}

Dopo aver creato uno o più profili di test specifici e salvato il messaggio sulle transazioni, puoi inviare una bozza per verificarlo.

![](assets/message-center_10.png)

La procedura per l’invio di una bozza è illustrata nella [Invio di bozze](../../sending/using/sending-proofs.md) sezione.
