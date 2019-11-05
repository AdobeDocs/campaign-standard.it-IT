---
title: Conferma dell’invio
description: Scopri come finalizzare la preparazione dei messaggi.
page-status-flag: mai attivato
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: invio e tracciamento di messaggi
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: consegna,distribuzione,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Conferma dell’invio{#confirming-the-send}

Una volta completata la preparazione dei messaggi e la fase di approvazione, puoi inviarli. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

Solo gli utenti con il **[!UICONTROL Start deliveries]** ruolo possono confermare l’invio. Per ulteriori informazioni, consultare la sezione [Elenco di ruoli](../../administration/using/list-of-roles.md) .

Gli utenti senza questo ruolo visualizzeranno il seguente messaggio:

![](assets/confirm_delivery_2.png)

Per inviare la consegna, fai clic sul **[!UICONTROL Confirm send]** pulsante nella barra delle azioni del messaggio.

![](assets/confirm_delivery.png)

Verrà chiesto di finalizzare l'invio definitivamente facendo clic sul **[!UICONTROL OK]** pulsante.

![](assets/confirm_delivery1.png)

Il messaggio viene inviato.

>[!NOTE]
>
>Se il messaggio è pianificato, verrà inviato al momento dell'invio. For more on scheduling messages, refer to [this section](../../sending/using/about-scheduling-messages.md).

Se si utilizza una consegna periodica senza periodo di aggregazione, è possibile richiedere conferma prima dell'invio della consegna. A questo scopo, aprite il **[!UICONTROL Schedule]** blocco del dashboard di consegna, quindi attivate l'opzione dedicata.

![](assets/confirmation_recurring_deliveries.png)

Il **[!UICONTROL Deployment]** blocco mostra l'avanzamento dell'invio.

Una volta inviato il messaggio ai contatti, la **[!UICONTROL Deployment]** zona mostra i dati KPI (Key Performance Indicator), inclusi:

* Numero di messaggi da inviare
* Numero di messaggi inviati
* Percentuale di messaggi inviati
* Percentuale di errori e rimbalzi
* Percentuale di messaggi aperti
* Percentuale di clic nei messaggi (per e-mail)

   >[!NOTE]
   >
   >Il **[!UICONTROL Open rate]** e **[!UICONTROL Click-through rate]** vengono aggiornati ogni ora.

![](assets/sending_delivery.png)

Se l'aggiornamento dei KPI richiede troppo tempo o non tiene conto dei risultati dei registri di invio, fare clic sul **[!UICONTROL Compute stats]** pulsante nella **[!UICONTROL Deployment]** finestra.

![](assets/sending_delivery7.png)

Il messaggio può essere visualizzato nella cronologia di uno dei profili cliente che costituisce parte del pubblico. See [Integrated customer profile](../../audiences/using/integrated-customer-profile.md).

Una volta inviato il messaggio, puoi tenere traccia del comportamento dei destinatari e monitorarlo per misurarne l’impatto. Per ulteriori informazioni, consulta le sezioni seguenti:

* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)

