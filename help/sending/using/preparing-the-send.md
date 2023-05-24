---
title: Preparazione dell’invio
description: Scopri come definire la preparazione prima dell’invio.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 0140c41a-7255-4b77-a1b7-c6f7b1135e51
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 12%

---

# Preparazione dell’invio{#preparing-the-send}

La preparazione corrisponde alla fase di calcolo della popolazione target e di generazione del contenuto del messaggio per ciascun profilo incluso nel target. Una volta completata la preparazione, i messaggi sono pronti per essere inviati, immediatamente o al [la data e l’ora pianificate](../../sending/using/about-scheduling-messages.md).

1. Per iniziare a preparare l’invio, fai clic su **Prepara** nella barra delle azioni.

   ![](assets/preparing_delivery_2.png)

1. Il **[!UICONTROL Deployment]** il blocco mostra l’avanzamento della preparazione, quindi le statistiche di preparazione: numero di messaggi target, numero di messaggi da inviare, ecc.

   A seconda della dimensione della popolazione target, questa operazione potrebbe richiedere del tempo.

   ![](assets/preparing_delivery.png)

1. Interrompere la preparazione in qualsiasi momento utilizzando **Interrompi** nella barra delle azioni.

   Durante la fase di preparazione, non vengono inviati messaggi. È quindi possibile iniziare o interrompere questo processo senza alcun rischio.

   ![](assets/preparing_delivery_6.png)

1. Il messaggio viene salvato automaticamente durante la fase di preparazione per la consegna. Se devi apportare modifiche alla pianificazione del messaggio dopo il passaggio di preparazione, dovrai accertarti di fare clic su **[!UICONTROL Prepare]** affinché tali modifiche vengano prese in considerazione. Per ulteriori informazioni su come pianificare un messaggio, consulta questa [pagina](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Per visualizzare i registri di preparazione, fai clic sul pulsante che si trova in basso a destra del blocco.

   ![](assets/preparing_delivery_4.png)

1. Il **[!UICONTROL Deployment]** viene visualizzata la finestra, correggi eventuali errori e riavvia la preparazione.

   L’ultimo messaggio del registro presenta eventuali messaggi di errore e il numero di errori. Un’icona specifica mostra il tipo di errore riscontrato: l’icona gialla indica un errore di elaborazione non critico, l’icona rossa indica un errore critico che impedisce l’avvio della consegna.

   ![](assets/preparing_delivery_3.png)

1. Controlla le statistiche di preparazione prima di confermare l’invio dei messaggi. Se il numero di messaggi da inviare non corrisponde alla configurazione, modifica la popolazione target (vedi [Selezione di un pubblico in un messaggio](../../audiences/using/selecting-an-audience-in-a-message.md)) e riavviare la preparazione.

Una volta completata la preparazione, il messaggio è pronto per essere inviato. Per ulteriori informazioni, consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

**Regole di tipologia**

Adobe Campaign viene fornito con un set di regole di tipologia integrate che vengono applicate durante la preparazione dei messaggi. Vengono utilizzati per verificare se un messaggio è valido e soddisfa i criteri di qualità. Consulta [Tipologie](../../sending/using/about-typology-rules.md). Puoi definire regole di tipologia personalizzate, ad esempio può impostare regole di affaticamento globali cross-channel che escluderanno automaticamente dalle campagne i profili sollecitati eccessivamente. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

**Controllo dei messaggi SMS**

Se hai inserito campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, questi fattori possono introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Quando la preparazione viene eseguita, viene monitorata la lunghezza del messaggio e, se supera il limite, viene visualizzato un messaggio di avviso.

Per ulteriori informazioni, consulta [Codifica, lunghezza e traslitterazione di SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) e [Personalizzazione dei messaggi SMS](../../channels/using/personalizing-sms-messages.md) sezioni.
