---
solution: Campaign Standard
product: campaign
title: Preparazione dell’invio
description: Scopri come definire la preparazione prima dell’invio.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Preparazione dell’invio{#preparing-the-send}

La preparazione corrisponde alla fase di calcolo della popolazione target e generazione del contenuto del messaggio per ciascun profilo incluso nel target. Una volta terminata la preparazione, i messaggi sono pronti per essere inviati, immediatamente o in [data e ora previste](../../sending/using/about-scheduling-messages.md).

1. Per iniziare a preparare l&#39;invio, fare clic sul pulsante **Prepara** nella barra delle azioni.

   ![](assets/preparing_delivery_2.png)

1. Il blocco **[!UICONTROL Deployment]** mostra lo stato di preparazione, quindi le statistiche di preparazione: numero di messaggi con targeting, numero di messaggi da inviare, ecc.

   A seconda delle dimensioni della popolazione interessata, questa operazione potrebbe richiedere del tempo.

   ![](assets/preparing_delivery.png)

1. Arrestate la preparazione in qualsiasi momento utilizzando il pulsante **Stop**, situato nella barra delle azioni.

   Durante la fase di preparazione, non vengono inviati messaggi. È quindi possibile iniziare o interrompere questo processo senza rischiare di avere un impatto su di esso.

   ![](assets/preparing_delivery_6.png)

1. Il messaggio viene salvato automaticamente durante la preparazione alla consegna. Se devi apportare delle modifiche alla pianificazione del messaggio dopo il passaggio di preparazione, dovrai fare di nuovo clic sul pulsante **[!UICONTROL Prepare]** per tenere conto di tali modifiche. Per ulteriori informazioni sulla pianificazione di un messaggio, fare riferimento a [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Per visualizzare i registri di preparazione, fare clic sul pulsante situato in basso a destra del blocco.

   ![](assets/preparing_delivery_4.png)

1. Si apre la finestra **[!UICONTROL Deployment]**, correggete eventuali errori e riavviate la preparazione.

   Nell&#39;ultimo messaggio di registro sono visualizzati tutti i messaggi di errore e il numero di errori. Un&#39;icona specifica mostra il tipo di errore rilevato: l’icona gialla indica un errore di elaborazione non critico; l’icona rossa indica un errore critico che impedisce l’avvio della consegna.

   ![](assets/preparing_delivery_3.png)

1. Controllare le statistiche di preparazione prima di confermare l&#39;invio dei messaggi. Se il numero di messaggi da inviare non corrisponde alla configurazione, modificare la popolazione di destinazione (vedere [Selezione di un&#39;audience in un messaggio](../../audiences/using/selecting-an-audience-in-a-message.md)) e riavviare la preparazione.

Una volta completata la preparazione, il messaggio è pronto per essere inviato. Per ulteriori informazioni, vedere [Conferma di invio](../../sending/using/confirming-the-send.md).

**Regole di tipologia**

 Adobe Campaign viene fornito con una serie di regole di tipologia integrate applicate durante la preparazione dei messaggi. Vengono utilizzati per verificare se un messaggio è valido e soddisfa i criteri di qualità. Vedere [Tipologie](../../sending/using/about-typology-rules.md). Potete definire regole di tipologia personalizzate, ad esempio impostare regole di affaticamento tra canali globali che escludano automaticamente i profili con eccesso di sollecitazione dalle campagne. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

**Controllo messaggi SMS**

Se hai inserito campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, questi fattori possono introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Durante l&#39;esecuzione della preparazione, viene monitorata la lunghezza del messaggio e, se supera il limite, viene visualizzato un messaggio di avviso.

Per ulteriori informazioni, consultare le sezioni [Codifica SMS, lunghezza e traslitterazione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) e [Personalizzazione dei messaggi SMS](../../channels/using/personalizing-sms-messages.md).
