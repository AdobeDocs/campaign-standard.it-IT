---
solution: Campaign Standard
product: campaign
title: Preparazione dell’invio
description: Scopri come definire la preparazione prima dell’invio.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Ottimizzazione dei tempi di invio
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 2%

---


# Preparazione dell’invio{#preparing-the-send}

La preparazione corrisponde alla fase di calcolo della popolazione target e generazione del contenuto del messaggio per ciascun profilo incluso nel target. Al termine della preparazione, i messaggi sono pronti per essere inviati, immediatamente o in [data e ora pianificate](../../sending/using/about-scheduling-messages.md).

1. Per iniziare a preparare l’invio, fai clic sul pulsante **Prepare** presente nella barra delle azioni.

   ![](assets/preparing_delivery_2.png)

1. Il blocco **[!UICONTROL Deployment]** mostra l&#39;avanzamento della preparazione, quindi le statistiche di preparazione: numero di messaggi con targeting, numero di messaggi da inviare, ecc.

   A seconda della dimensione della popolazione target, questa operazione potrebbe richiedere del tempo.

   ![](assets/preparing_delivery.png)

1. Arresta la preparazione in qualsiasi momento utilizzando il pulsante **Stop**, situato nella barra delle azioni.

   Durante la fase di preparazione, non vengono inviati messaggi. È quindi possibile iniziare o interrompere questo processo senza rischi di influire su nulla.

   ![](assets/preparing_delivery_6.png)

1. Il messaggio viene salvato automaticamente durante la preparazione alla consegna. Per apportare modifiche alla pianificazione del messaggio dopo la fase di preparazione, è necessario assicurarsi di fare nuovamente clic sul pulsante **[!UICONTROL Prepare]** per tenere conto di tali modifiche. Per ulteriori informazioni sulla pianificazione di un messaggio, consulta questa [pagina](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Per visualizzare i registri di preparazione, fai clic sul pulsante in basso a destra del blocco .

   ![](assets/preparing_delivery_4.png)

1. Viene visualizzata la finestra **[!UICONTROL Deployment]**, correggi eventuali errori e riavvia la preparazione.

   Nell’ultimo messaggio di log vengono visualizzati tutti i messaggi di errore e il numero di errori. Un&#39;icona specifica mostra il tipo di errore rilevato: l’icona gialla indica un errore di elaborazione non critico; l’icona rossa indica un errore critico che impedisce l’avvio della consegna.

   ![](assets/preparing_delivery_3.png)

1. Controlla le statistiche di preparazione prima di confermare l’invio dei messaggi. Se il numero di messaggi da inviare non corrisponde alla configurazione, modifica la popolazione target (consulta [Selezione di un pubblico in un messaggio](../../audiences/using/selecting-an-audience-in-a-message.md)) e riavvia la preparazione.

Una volta completata la preparazione, il messaggio è pronto per essere inviato. Per ulteriori informazioni, consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

**Regole di tipologia**

Adobe Campaign viene fornito con un set di regole di tipologia integrate applicate durante la preparazione dei messaggi. Vengono utilizzati per verificare se un messaggio è valido e soddisfa i criteri di qualità. Vedere [Tipologie](../../sending/using/about-typology-rules.md). Puoi definire regole di tipologia personalizzate, ad esempio, per impostare regole di affaticamento globali cross-channel che escluderanno automaticamente i profili sollecitati eccessivamente dalle campagne. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

**Controllo messaggi SMS**

Se hai inserito campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, questi fattori possono introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Quando viene eseguita la preparazione, viene monitorata la lunghezza del messaggio e viene visualizzato un messaggio di avviso se supera il limite.

Per ulteriori informazioni, consulta le sezioni [Codifica, lunghezza e traslitterazione SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) e [Personalizzazione di messaggi SMS](../../channels/using/personalizing-sms-messages.md) .
