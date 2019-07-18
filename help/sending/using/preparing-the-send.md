---
title: Preparazione dell'invio
seo-title: Preparazione dell'invio
description: Preparazione dell'invio
seo-description: Scopri come definire la preparazione prima dell'invio.
page-status-flag: never-activated
uuid: 1038 dae 2-164 c -4579-9294-bdf 2 a 4 eb 12 d 6
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: preparazione-and-testing-messages
discoiquuid: 003 abc 83-7 f 07-471 f-ab 2 f -1 d 352 d 22 c 26 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Preparing the send{#preparing-the-send}

La preparazione corrisponde al passaggio del calcolo della popolazione di destinazione e alla generazione del contenuto del messaggio per ogni profilo incluso nella destinazione. Once preparation is finished, the messages are ready to be sent, either immediately or at [the scheduled date and time](../../sending/using/about-scheduling-messages.md).

1. To start preparing the send, click the **Prepare** button located in the action bar.

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** Il blocco mostra l'avanzamento della preparazione, quindi le statistiche di preparazione: numero di messaggi mirati, numero di messaggi da inviare, ecc.

   A seconda delle dimensioni della popolazione di destinazione, l'operazione potrebbe richiedere del tempo.

   ![](assets/preparing_delivery.png)

1. Stop the preparation at any time using the **Stop** button, located in the action bar.

   Durante la fase di preparazione, non viene inviato alcun messaggio. Potete quindi avviarlo o interromperlo senza rischio di compromettere nulla.

   ![](assets/preparing_delivery_6.png)

1. Il messaggio viene salvato automaticamente durante la preparazione all'area di visualizzazione. If you need to make any changes to your message's schedule after the preparation step, you will need to make sure that you click the **[!UICONTROL Prepare]** button again for those changes to be taken into account. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Per visualizzare i registri di preparazione, fate clic sul pulsante situato in basso a destra nel blocco.

   ![](assets/preparing_delivery_4.png)

1. The **[!UICONTROL Deployment]** window opens, correct any errors then restart the preparation.

   L'ultimo messaggio di registro visualizza tutti i messaggi di errore e il numero di errori. Un'icona specifica mostra il tipo di errore rilevato: L'icona gialla indica un errore di elaborazione non critico, l'icona rossa indica un errore critico che impedisce l'avvio della distribuzione.

   ![](assets/preparing_delivery_3.png)

1. Controllate le statistiche di preparazione prima di confermare l'invio dei messaggi. If the number of messages to send does not correspond to your configuration, edit the targeted population (see [Selecting an audience in a message](../../audiences/using/selecting-an-audience-in-a-message.md)) and restart the preparation.

Una volta completata la preparazione, il messaggio è pronto per l'invio. For more on this, see [Confirming send](../../sending/using/confirming-the-send.md).

**Regole per i tipi di telefono**

Adobe Campaign viene fornito con una serie di regole di tipo "build-in" applicate durante la preparazione del messaggio. Vengono utilizzati per verificare se un messaggio è valido e soddisfa i criteri di qualità. See [Typologies](../../administration/using/about-typology-rules.md). Potete definire le vostre regole di tipologie personalizzate, ad esempio, potete impostare regole globali di affaticamento cross-channel che escluderanno automaticamente i profili superflui dalle campagne. See [Fatigue rules](../../administration/using/fatigue-rules.md).

**Controllo SMS del messaggio**

Se sono stati inseriti campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, questi fattori potrebbero introdurre caratteri non considerati in base alla codifica GSM. Quando la preparazione viene eseguita, la lunghezza del messaggio viene monitorata e viene visualizzato un messaggio di avviso se superato il limite.

For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) and [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) sections.
