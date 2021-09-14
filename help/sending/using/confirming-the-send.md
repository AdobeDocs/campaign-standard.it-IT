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
ht-degree: 17%

---

# Conferma dell’invio{#confirming-the-send}

Dopo che hai completato la preparazione dei messaggi e hai eseguito i passaggi di approvazione, puoi inviarli. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

Solo gli utenti con il ruolo **[!UICONTROL Start deliveries]** possono confermare l’invio. Per ulteriori informazioni, consulta la sezione [Elenco di ruoli](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Invio del messaggio {#sending-message}

Al termine della preparazione, segui i passaggi seguenti per inviare il messaggio.

1. Fai clic sul pulsante **[!UICONTROL Confirm send]** che si trova nella barra delle azioni del messaggio.

   ![](assets/confirm_delivery.png)

1. Per completare l’invio, fai clic sul pulsante **[!UICONTROL OK]** .

   ![](assets/confirm_delivery1.png)

1. Attendi l&#39;invio del messaggio. Il blocco **[!UICONTROL Deployment]** mostra l’avanzamento dell’invio.

>[!NOTE]
>
>Se il messaggio è pianificato, viene inviato al raggiungimento dell’orario di invio. Per ulteriori informazioni sulla pianificazione dei messaggi, consulta [questa sezione](../../sending/using/about-scheduling-messages.md).

Se utilizzi una consegna ricorrente senza periodo di aggregazione, puoi richiedere conferma prima di inviarla. Durante la configurazione del messaggio, apri il blocco **[!UICONTROL Schedule]** del dashboard di consegna e attiva l’opzione dedicata.

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

Se l’aggiornamento dei KPI richiede troppo tempo o non riflette i risultati dei log di invio, fai clic sul pulsante **[!UICONTROL Compute stats]** nella finestra **[!UICONTROL Deployment]** .

![](assets/sending_delivery7.png)

Il messaggio può essere visualizzato nella cronologia di uno dei profili di destinazione. Consulta [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md).

Una volta inviato un messaggio, puoi tenere traccia del comportamento dei destinatari e monitorarlo per misurarne l’impatto. Per ulteriori informazioni, consulta queste sezioni:

* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)

### Generazione rapporti di successo {#delivered-status-report}

>[!NOTE]
>
>Questa sezione si applica solo al canale e-mail.

Nella visualizzazione **[!UICONTROL Summary]** di ogni e-mail, la percentuale **[!UICONTROL Delivered]** inizia al 100% e poi scende progressivamente per tutto il periodo di validità della consegna [](../../administration/using/configuring-email-channel.md#validity-period-parameters), in quanto i rimbalzi morbidi e rigidi vengono segnalati nuovamente<!--from the Enhanced MTA to Campaign-->.

Infatti, tutti i messaggi vengono visualizzati come **[!UICONTROL Sent]** nel [log di invio](../../sending/using/monitoring-a-delivery.md#sending-logs) non appena vengono correttamente inviati da Campaign all’MTA avanzato (Agente di trasferimento messaggi). Rimangono in tale stato a meno che o fino a quando un [rimbalzo](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) per quel messaggio non viene comunicato nuovamente dall’MTA avanzato a Campaign.

Quando i messaggi di rimbalzo rigido vengono riportati dall’MTA avanzato, il loro stato cambia da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Delivered]** viene ridotta di conseguenza.

Quando i messaggi di rimbalzo soft vengono segnalati dall’MTA avanzato, vengono comunque visualizzati come **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** non è ancora aggiornata. I messaggi di rimbalzo temporaneo vengono quindi [ritentati](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) per tutto il periodo di validità della consegna:

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio rimane **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** rimane invariata.

* In caso contrario, lo stato cambia in **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Delivered]** viene ridotta di conseguenza.

Pertanto, è necessario attendere fino alla fine del periodo di validità per visualizzare la percentuale finale **[!UICONTROL Delivered]** e il numero finale dei messaggi **[!UICONTROL Sent]** e **[!UICONTROL Failed]**.

### Servizio di feedback e-mail (versione beta) {#email-feedback-service}

Grazie alla funzionalità EFS (Email Feedback Service), lo stato di ogni e-mail viene riportato con precisione, in quanto il feedback viene acquisito direttamente dall’MTA avanzato (Message Transfer Agent).

>[!IMPORTANT]
>
>Il servizio e-mail e-mail e’ attualmente disponibile come funzionalità beta.

Una volta avviata la consegna, la percentuale **[!UICONTROL Delivered]** non subirà alcuna modifica quando il messaggio viene inoltrato correttamente da Campaign all’MTA avanzato.

![](assets/efs-sending.png)

I registri di consegna mostrano lo stato **[!UICONTROL Pending]** per ogni indirizzo di destinazione.

![](assets/efs-pending.png)

Quando la consegna dei messaggi ai profili di destinazione viene segnalata nuovamente in tempo reale dall’MTA avanzato, i registri di consegna mostrano lo stato **[!UICONTROL Sent]** per ogni indirizzo che ha ricevuto correttamente il messaggio. La percentuale **[!UICONTROL Delivered]** viene aumentata di conseguenza con ogni consegna riuscita.

Quando i messaggi di rimbalzo rigido vengono riportati dall’MTA avanzato, lo stato del registro cambia da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza.

Quando i messaggi di rimbalzo soft vengono segnalati dall’MTA avanzato, lo stato del registro cambia anche da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza. La percentuale **[!UICONTROL Delivered]** rimane invariata. I messaggi di rimbalzo morbido vengono quindi ritentati durante il periodo di validità della consegna [](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio cambia in **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** viene aumentata di conseguenza.

* In caso contrario, lo stato rimane **[!UICONTROL Failed]**. Le percentuali **[!UICONTROL Delivered]** e **[!UICONTROL Bounces + errors]** rimangono invariate.

>[!NOTE]
>
>Per ulteriori informazioni sui rimbalzi rigidi e morbidi, consulta [questa sezione](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Per ulteriori informazioni sui nuovi tentativi dopo un errore temporaneo di consegna, consulta [questa sezione](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Modifiche introdotte dall&#39;EFS {#changes-introduced-by-efs}

Le tabelle riportate di seguito mostrano le modifiche apportate ai KPI e agli stati dei registri di invio introdotte dalla funzionalità EFS.

**Con il servizio di feedback via e-mail**

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio viene inviato correttamente da Campaign all’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** percentuale inizia a 0%</li><li>**[!UICONTROL Bounces + errors]** percentuale inizia a 0%</li></ul> | In sospeso |
| I messaggi di rimbalzo rigido vengono segnalati nuovamente dall’MTA avanzato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
| I messaggi di rimbalzo morbido vengono segnalati nuovamente dall’MTA avanzato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
| I nuovi tentativi dei messaggi di rimbalzo non sono riusciti | <ul><li>**[!UICONTROL Delivered]** la percentuale viene aumentata di conseguenza</li><li>**[!UICONTROL Bounces + errors]** la percentuale diminuisce di conseguenza</li></ul> | Inviato |
| Messaggi di rimbalzo morbido non riusciti | <ul><li> Nessuna modifica nella percentuale **[!UICONTROL Delivered]** </li><li> Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]** </li></ul> | Non riuscito |

**Servizio senza feedback e-mail**

| Passaggio nel processo di invio | Riepilogo KPI | Stato dei registri di invio |
|--- |--- |--- |
| Il messaggio viene inviato correttamente da Campaign all’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** percentuale inizia al 100%</li><li>**[!UICONTROL Bounces + errors]** percentuale inizia a 0%</li></ul> | Inviato |
| I messaggi di rimbalzo rigido vengono segnalati nuovamente dall’MTA avanzato | <ul><li>**[!UICONTROL Delivered]** la percentuale diminuisce di conseguenza</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
| I messaggi di rimbalzo morbido vengono segnalati nuovamente dall’MTA avanzato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]**</li></ul> | Inviato |
| I nuovi tentativi dei messaggi di rimbalzo non sono riusciti | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]**</li></ul> | Inviato |
| Messaggi di rimbalzo morbido non riusciti | <ul><li>**[!UICONTROL Delivered]** la percentuale diminuisce di conseguenza</li><li>**[!UICONTROL Bounces + errors]** la percentuale viene aumentata di conseguenza</li></ul> | Non riuscito |
