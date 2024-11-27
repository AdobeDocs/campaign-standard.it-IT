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
source-git-commit: 058c59136c28e7fce2a79686919f900f410e324a
workflow-type: tm+mt
source-wordcount: '982'
ht-degree: 16%

---

# Conferma dell’invio{#confirming-the-send}

Dopo che hai completato la preparazione dei messaggi e hai eseguito i passaggi di approvazione, puoi inviarli. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

Solo gli utenti con il ruolo **[!UICONTROL Start deliveries]** possono confermare l&#39;invio. Per ulteriori informazioni, consulta la sezione [Elenco di ruoli](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Invio del messaggio {#sending-message}

Una volta completata la preparazione, segui i passaggi indicati di seguito per inviare il messaggio.

1. Fare clic sul pulsante **[!UICONTROL Confirm send]** presente nella barra delle azioni del messaggio.

   ![](assets/confirm_delivery.png)

1. Completare l&#39;invio facendo clic sul pulsante **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Attendere. Invio del messaggio in corso. Il blocco **[!UICONTROL Deployment]** mostra l’avanzamento dell’invio.

>[!NOTE]
>
>Se il messaggio è pianificato, viene inviato quando viene raggiunto l’orario di invio. Per ulteriori informazioni sulla pianificazione dei messaggi, consulta [questa sezione](../../sending/using/about-scheduling-messages.md).

Se utilizzi una consegna ricorrente senza periodo di aggregazione, puoi richiedere conferma prima di inviarla. Durante la configurazione del messaggio, apri il blocco **[!UICONTROL Schedule]** del dashboard di consegna e attiva l&#39;opzione dedicata.

![](assets/confirmation_recurring_deliveries.png)

## Informazioni sugli indicatori dei messaggi {#message-indicators}

>[!NOTE]
>
> Il **dashboard di distribuzione** fornisce dati per riferimento rapido, che potrebbe non corrispondere ai numeri nei report dinamici. Per informazioni accurate e affidabili, consigliamo di utilizzare il reporting dinamico come fonte di verità. [Ulteriori informazioni](../../reporting/using/get-started-reporting.md)

Dopo l&#39;invio del messaggio ai contatti, nell&#39;area **[!UICONTROL Deployment]** vengono visualizzati i dati KPI (Key Performance Indicator), inclusi:

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

Se l&#39;aggiornamento dei KPI richiede troppo tempo o non riflette i risultati dei log di invio, fare clic sul pulsante **[!UICONTROL Compute stats]** nella finestra **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

Il messaggio può essere visualizzato nella cronologia di uno dei profili target. Consulta [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md).

Dopo l’invio del messaggio, puoi tenere traccia del comportamento dei destinatari e monitorarlo per misurarne l’impatto. Per ulteriori informazioni, consulta queste sezioni:

* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)

### Reporting sul successo della consegna {#delivered-status-report}

>[!NOTE]
>
>Questa sezione si applica solo al canale e-mail.

Nella visualizzazione **[!UICONTROL Summary]** di ogni e-mail, la percentuale di **[!UICONTROL Delivered]** inizia al 100% e poi si abbassa progressivamente durante il [periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters) della consegna, man mano che vengono segnalati i mancati recapiti non permanenti e permanenti<!--from the Enhanced MTA to Campaign-->.

In effetti, tutti i messaggi vengono visualizzati come **[!UICONTROL Sent]** nei [registri di invio](../../sending/using/monitoring-a-delivery.md#sending-logs) non appena vengono inoltrati correttamente da Campaign all’MTA avanzato (agente di trasferimento messaggi). Rimangono in tale stato a meno che o fino a quando un [mancato recapito](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) per quel messaggio non viene comunicato dall&#39;MTA avanzato a Campaign.

Quando i messaggi non recapitabili vengono segnalati dall&#39;MTA avanzato, il loro stato cambia da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** e la percentuale di **[!UICONTROL Delivered]** viene diminuita di conseguenza.

Quando i messaggi con mancati recapiti non permanenti vengono segnalati dall’MTA avanzato, vengono comunque visualizzati come **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** non è ancora aggiornata. I messaggi con mancati recapiti non permanenti vengono quindi [ritentati](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) per tutto il periodo di validità della consegna:

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio rimane **[!UICONTROL Sent]** e la percentuale di **[!UICONTROL Delivered]** rimane invariata.

* In caso contrario, lo stato diventa **[!UICONTROL Failed]** e la percentuale di **[!UICONTROL Delivered]** viene diminuita di conseguenza.

Pertanto, è necessario attendere fino alla fine del periodo di validità per visualizzare la percentuale finale di **[!UICONTROL Delivered]** e il numero finale di **[!UICONTROL Sent]** e **[!UICONTROL Failed]** messaggi.

### Servizio di feedback delle e-mail (beta) {#email-feedback-service}

Con la funzionalità Email Feedback Service (EFS), lo stato di ogni e-mail viene segnalato con precisione, perché il feedback viene acquisito direttamente dall’MTA (Message Transfer Agent) avanzato.

>[!IMPORTANT]
>
>Il servizio di feedback delle e-mail è attualmente disponibile come funzionalità beta.

Una volta avviata la consegna, non vi è alcuna modifica nella percentuale di **[!UICONTROL Delivered]** quando il messaggio viene inoltrato correttamente da Campaign all’MTA avanzato.

![](assets/efs-sending.png)

I registri di consegna mostrano lo stato **[!UICONTROL Pending]** per ogni indirizzo di destinazione.

![](assets/efs-pending.png)

Quando la consegna dei messaggi ai profili di destinazione viene segnalata in tempo reale dall’MTA avanzato, i registri di consegna mostrano lo stato **[!UICONTROL Sent]** per ogni indirizzo che ha ricevuto correttamente il messaggio. La percentuale di **[!UICONTROL Delivered]** viene aumentata di conseguenza a ogni consegna riuscita.

Quando i messaggi non recapitabili vengono segnalati dall&#39;MTA avanzato, lo stato del registro cambia da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e la percentuale di **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza.

Quando vengono segnalati i messaggi in soft-bouncing dall&#39;MTA avanzato, anche lo stato del registro cambia da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e la percentuale di **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza. La percentuale **[!UICONTROL Delivered]** rimane invariata. I messaggi non recapitabili vengono quindi ritentati per tutto il [periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters) della consegna:

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio cambia in **[!UICONTROL Sent]** e la percentuale di **[!UICONTROL Delivered]** viene aumentata di conseguenza.

* In caso contrario, lo stato rimane **[!UICONTROL Failed]**. Le percentuali **[!UICONTROL Delivered]** e **[!UICONTROL Bounces + errors]** rimangono invariate.

>[!NOTE]
>
>Per ulteriori informazioni sui mancati recapiti permanenti e non permanenti, consulta [questa sezione](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Per ulteriori informazioni sui nuovi tentativi dopo un errore temporaneo di consegna, vedere [questa sezione](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Modifiche introdotte da EFS {#changes-introduced-by-efs}

Le tabelle seguenti mostrano le modifiche nei KPI e negli stati dei registri di invio introdotte dalla funzionalità EFS.

**Con Servizio Di Feedback E-Mail**

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio è stato inoltrato correttamente da Campaign all’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** percentuale inizia a 0%</li><li>**[!UICONTROL Bounces + errors]** percentuale inizia a 0%</li></ul> | In sospeso |
| I messaggi non recapitabili vengono segnalati dall’MTA avanzato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>La percentuale di **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza</li></ul> | Non riuscito |
| I messaggi in soft-bouncing vengono segnalati dall’MTA avanzato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>La percentuale di **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza</li></ul> | Non riuscito |
| Nuovi tentativi di messaggi con mancati recapiti non permanenti riusciti | <ul><li>La percentuale di **[!UICONTROL Delivered]** viene aumentata di conseguenza</li><li>**[!UICONTROL Bounces + errors]** percentuale diminuita di conseguenza</li></ul> | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non riusciti | <ul><li> Nessuna modifica nella percentuale **[!UICONTROL Delivered]** </li><li> Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]** </li></ul> | Non riuscito |

**Senza Servizio Di Feedback E-Mail**

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio è stato inoltrato correttamente da Campaign all’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** percentuale inizia al 100%</li><li>**[!UICONTROL Bounces + errors]** percentuale inizia a 0%</li></ul> | Inviato |
| I messaggi non recapitabili vengono segnalati dall’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** percentuale diminuita di conseguenza</li><li>La percentuale di **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza</li></ul> | Non riuscito |
| I messaggi in soft-bouncing vengono segnalati dall’MTA avanzato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]**</li></ul> | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non permanenti riusciti | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]**</li></ul> | Inviato |
| Nuovi tentativi di messaggi con mancati recapiti non riusciti | <ul><li>**[!UICONTROL Delivered]** percentuale diminuita di conseguenza</li><li>La percentuale di **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza</li></ul> | Non riuscito |
