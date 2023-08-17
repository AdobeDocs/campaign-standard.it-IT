---
title: Conferma dell’invio
description: Scopri come finalizzare la preparazione dei messaggi.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 0a0fe969-cdfd-4b0c-a746-081038424d86
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '942'
ht-degree: 18%

---

# Conferma dell’invio{#confirming-the-send}

Dopo che hai completato la preparazione dei messaggi e hai eseguito i passaggi di approvazione, puoi inviarli. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

Solo gli utenti con **[!UICONTROL Start deliveries]** Il ruolo può confermare l’invio. Per ulteriori informazioni, consulta la sezione [Elenco di ruoli](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Invio del messaggio {#sending-message}

Una volta completata la preparazione, segui i passaggi indicati di seguito per inviare il messaggio.

1. Fai clic su **[!UICONTROL Confirm send]** nella barra delle azioni del messaggio.

   ![](assets/confirm_delivery.png)

1. Completa l’invio facendo clic su **[!UICONTROL OK]** pulsante.

   ![](assets/confirm_delivery1.png)

1. Attendere. Invio del messaggio in corso. Il blocco **[!UICONTROL Deployment]** mostra l’avanzamento dell’invio.

>[!NOTE]
>
>Se il messaggio è pianificato, viene inviato quando viene raggiunto l’orario di invio. Per ulteriori informazioni sulla pianificazione dei messaggi, consulta [questa sezione](../../sending/using/about-scheduling-messages.md).

Se utilizzi una consegna ricorrente senza periodo di aggregazione, puoi richiedere conferma prima di inviarla. Durante la configurazione del messaggio, apri la **[!UICONTROL Schedule]** blocco del dashboard di consegna e attivazione dell’opzione dedicata.

![](assets/confirmation_recurring_deliveries.png)

## Informazioni sugli indicatori dei messaggi {#message-indicators}

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

Se l’aggiornamento dei KPI richiede troppo tempo o non riflette i risultati dei registri di invio, fai clic sul pulsante **[!UICONTROL Compute stats]** pulsante in **[!UICONTROL Deployment]** finestra.

![](assets/sending_delivery7.png)

Il messaggio può essere visualizzato nella cronologia di uno dei profili target. Consulta [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md).

Dopo l’invio del messaggio, puoi tenere traccia del comportamento dei destinatari e monitorarlo per misurarne l’impatto. Per ulteriori informazioni, consulta queste sezioni:

* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)

### Reporting sul successo della consegna {#delivered-status-report}

>[!NOTE]
>
>Questa sezione si applica solo al canale e-mail.

In **[!UICONTROL Summary]** visualizzazione di ogni e-mail, il **[!UICONTROL Delivered]** la percentuale inizia al 100% e poi diminuisce progressivamente durante la consegna [periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters), quando vengono segnalati i mancati recapiti morbidi e permanenti<!--from the Enhanced MTA to Campaign-->.

In effetti, tutti i messaggi vengono visualizzati come **[!UICONTROL Sent]** nel [log di invio](../../sending/using/monitoring-a-delivery.md#sending-logs) non appena sono stati inoltrati correttamente da Campaign all’MTA avanzato (Message Transfer Agent). Rimangono in tale stato a meno che o fino a quando un [rimbalzo](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) per tale messaggio viene ritrasmesso dall’MTA avanzato a Campaign.

Quando i messaggi non recapitabili vengono segnalati dall’MTA avanzato, il loro stato cambia da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** e **[!UICONTROL Delivered]** la percentuale è diminuita di conseguenza.

Quando i messaggi con mancati recapiti non permanenti vengono segnalati dall’MTA avanzato, vengono comunque visualizzati come **[!UICONTROL Sent]** e **[!UICONTROL Delivered]** percentuale non ancora aggiornata. I messaggi di mancato recapito sono quindi [nuovo tentativo](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) durante il periodo di validità della consegna:

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio rimane invariato **[!UICONTROL Sent]** e **[!UICONTROL Delivered]** La percentuale rimane invariata.

* In caso contrario, lo stato cambia in **[!UICONTROL Failed]** e **[!UICONTROL Delivered]** la percentuale è diminuita di conseguenza.

Pertanto, devi attendere fino alla fine del periodo di validità per visualizzare il **[!UICONTROL Delivered]** percentuale e il numero finale di **[!UICONTROL Sent]** e **[!UICONTROL Failed]** messaggi.

### Servizio di feedback delle e-mail (beta) {#email-feedback-service}

Con la funzionalità Email Feedback Service (EFS), lo stato di ogni e-mail viene segnalato con precisione, perché il feedback viene acquisito direttamente dall’MTA (Message Transfer Agent) avanzato.

>[!IMPORTANT]
>
>Il servizio di feedback delle e-mail è attualmente disponibile come funzionalità beta.

Una volta iniziata la consegna, non vi è alcuna modifica nel **[!UICONTROL Delivered]** percentuale di inoltro del messaggio da Campaign all’MTA avanzato.

![](assets/efs-sending.png)

I registri di consegna mostrano **[!UICONTROL Pending]** stato per ogni indirizzo di destinazione.

![](assets/efs-pending.png)

Quando la consegna dei messaggi ai profili di destinazione viene segnalata in tempo reale dall’MTA avanzato, i registri di consegna mostrano **[!UICONTROL Sent]** stato di ogni indirizzo che ha ricevuto correttamente il messaggio. Il **[!UICONTROL Delivered]** la percentuale viene aumentata di conseguenza con ogni consegna riuscita.

Quando i messaggi non recapitabili vengono segnalati dall’MTA avanzato, lo stato del registro cambia da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e **[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza.

Quando i messaggi con mancati recapiti non permanenti vengono segnalati dall’MTA avanzato, anche lo stato del registro cambia da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e **[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza. Il **[!UICONTROL Delivered]** La percentuale rimane invariata. I messaggi in mancati recapiti non permanenti vengono quindi ritentati durante la consegna [periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio cambia in **[!UICONTROL Sent]** e **[!UICONTROL Delivered]** la percentuale viene aumentata di conseguenza.

* In caso contrario, lo stato rimane invariato **[!UICONTROL Failed]**. Il **[!UICONTROL Delivered]** e **[!UICONTROL Bounces + errors]** Le percentuali rimangono invariate.

>[!NOTE]
>
>Per ulteriori informazioni sui mancati recapiti non permanenti, consulta [questa sezione](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Per ulteriori informazioni sui nuovi tentativi dopo un errore temporaneo di consegna, consulta [questa sezione](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Modifiche introdotte da EFS {#changes-introduced-by-efs}

Le tabelle seguenti mostrano le modifiche nei KPI e negli stati dei registri di invio introdotte dalla funzionalità EFS.

**Con servizio di feedback delle e-mail**

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio è stato inoltrato correttamente da Campaign all’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** la percentuale inizia allo 0%</li><li>**[!UICONTROL Bounces + errors]** la percentuale inizia allo 0%</li></ul> | In sospeso |
| I messaggi non recapitabili vengono segnalati dall’MTA avanzato | <ul><li>Nessuna modifica in **[!UICONTROL Delivered]** percentuale</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
| I messaggi in soft-bouncing vengono segnalati dall’MTA avanzato | <ul><li>Nessuna modifica in **[!UICONTROL Delivered]** percentuale</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
| Nuovi tentativi di messaggi con mancati recapiti non permanenti riusciti | <ul><li>**[!UICONTROL Delivered]** la percentuale viene aumentata di conseguenza</li><li>**[!UICONTROL Bounces + errors]** la percentuale è diminuita di conseguenza</li></ul> | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non riusciti | <ul><li> Nessuna modifica in **[!UICONTROL Delivered]** percentuale </li><li> Nessuna modifica in **[!UICONTROL Bounces + errors]** percentuale </li></ul> | Non riuscito |

**Senza servizio di feedback delle e-mail**

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio è stato inoltrato correttamente da Campaign all’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** la percentuale inizia al 100%</li><li>**[!UICONTROL Bounces + errors]** la percentuale inizia allo 0%</li></ul> | Inviato |
| I messaggi non recapitabili vengono segnalati dall’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** la percentuale è diminuita di conseguenza</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
| I messaggi in soft-bouncing vengono segnalati dall’MTA avanzato | <ul><li>Nessuna modifica in **[!UICONTROL Delivered]** percentuale</li><li>Nessuna modifica in **[!UICONTROL Bounces + errors]** percentuale</li></ul> | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non permanenti riusciti | <ul><li>Nessuna modifica in **[!UICONTROL Delivered]** percentuale</li><li>Nessuna modifica in **[!UICONTROL Bounces + errors]** percentuale</li></ul> | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non riusciti | <ul><li>**[!UICONTROL Delivered]** la percentuale è diminuita di conseguenza</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
