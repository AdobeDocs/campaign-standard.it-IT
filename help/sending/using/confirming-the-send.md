---
solution: Campaign Standard
product: campaign
title: Conferma dell’invio
description: Scopri come finalizzare la preparazione dei messaggi.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 100%

---


# Conferma dell’invio{#confirming-the-send}

Dopo che hai completato la preparazione dei messaggi e hai eseguito i passaggi di approvazione, puoi inviarli. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

Solo gli utenti con il ruolo **[!UICONTROL Start deliveries]** possono confermare l’invio. Per ulteriori informazioni, consulta la sezione [Elenco di ruoli](../../administration/using/list-of-roles.md).

Gli utenti senza questo ruolo visualizzano il seguente messaggio:

![](assets/confirm_delivery_2.png)

Per inviare la consegna, fai clic sul pulsante **[!UICONTROL Confirm send]** che si trova nella barra delle azioni del messaggio.

![](assets/confirm_delivery.png)

Ti viene chiesto di finalizzare l’invio definitivamente facendo clic sul pulsante **[!UICONTROL OK]**.

![](assets/confirm_delivery1.png)

Il messaggio viene inviato.

>[!NOTE]
>
>Se il messaggio è pianificato, viene inviato all’orario stabilito di invio. Per ulteriori informazioni sulla pianificazione dei messaggi, consulta [questa sezione](../../sending/using/about-scheduling-messages.md).

Se utilizzi una consegna ricorrente senza periodo di aggregazione, puoi richiedere conferma prima di inviarla. A questo scopo, apri il blocco **[!UICONTROL Schedule]** del dashboard di consegna, quindi attiva l’opzione dedicata.

![](assets/confirmation_recurring_deliveries.png)

Il blocco **[!UICONTROL Deployment]** mostra l’avanzamento dell’invio.

Dopo l’invio del messaggio ai contatti, l’area **[!UICONTROL Deployment]** mostra i dati KPI (Key Performance Indicator), inclusi:

* Il numero dei messaggi da inviare
* Il numero dei messaggi inviati
* La percentuale dei messaggi inviati
* La percentuale dei messaggi non recapitati e degli errori
* La percentuale dei messaggi aperti
* La percentuale di clic nei messaggi (per e-mail)

   >[!NOTE]
   >
   >L’**[!UICONTROL Open rate]** e il **[!UICONTROL Click-through rate]** vengono aggiornati ogni ora.

![](assets/sending_delivery.png)

Se l’aggiornamento dei KPI richiede troppo tempo o non tiene conto dei risultati dei log di invio, fai clic sul pulsante **[!UICONTROL Compute stats]** nella finestra **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

Puoi visualizzare il messaggio nella cronologia di uno dei profili cliente che costituisce parte del pubblico. Consulta [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md).

Dopo l’invio del messaggio, puoi tenere traccia del comportamento dei destinatari e monitorarlo per misurarne l’impatto. Per ulteriori informazioni, consulta queste sezioni:

* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)

