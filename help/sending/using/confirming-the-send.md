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
source-git-commit: b48e246ee515d2f250d866ed72d5765bf1ccb326
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 20%

---


# Conferma dell’invio{#confirming-the-send}

Dopo che hai completato la preparazione dei messaggi e hai eseguito i passaggi di approvazione, puoi inviarli. Per ulteriori informazioni sulla preparazione dei messaggi, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).

Solo gli utenti con il ruolo **[!UICONTROL Start deliveries]** possono confermare l’invio. Per ulteriori informazioni, consulta la sezione [Elenco di ruoli](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Invio del messaggio {#sending-message}

Una volta completata la preparazione, segui i passaggi indicati di seguito per inviare il tuo messaggio.

1. Fare clic sul pulsante **[!UICONTROL Confirm send]** presente nella barra delle azioni del messaggio.

   ![](assets/confirm_delivery.png)

1. Per completare l&#39;invio, fare clic sul pulsante **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Attendi che il messaggio venga inviato. Il blocco **[!UICONTROL Deployment]** mostra l’avanzamento dell’invio.

>[!NOTE]
>
>Se il messaggio è pianificato, viene inviato all’orario stabilito di invio. Per ulteriori informazioni sulla pianificazione dei messaggi, consulta [questa sezione](../../sending/using/about-scheduling-messages.md).

Se utilizzi una consegna ricorrente senza periodo di aggregazione, puoi richiedere conferma prima di inviarla. A questo scopo, durante la configurazione del messaggio, aprite il blocco **[!UICONTROL Schedule]** del dashboard di distribuzione e attivate l&#39;opzione dedicata.

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

Se l&#39;aggiornamento dei KPI richiede troppo tempo o non tiene conto dei risultati dei registri di invio, fare clic sul pulsante **[!UICONTROL Compute stats]** nella finestra **[!UICONTROL Deployment]**.

![](assets/sending_delivery7.png)

Il messaggio può essere visualizzato nella cronologia di uno dei profili di destinazione. Consulta [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md).

Una volta inviato il messaggio, puoi tenere traccia del comportamento dei destinatari e monitorarlo per misurare il suo impatto. Per ulteriori informazioni, consulta queste sezioni:

* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)

### Generazione di rapporti di riuscita {#delivered-status-report}

>[!NOTE]
>
>Questa sezione si applica solo al canale e-mail.

Nella **[!UICONTROL Summary]** visualizzazione di ogni e-mail, la percentuale **[!UICONTROL Delivered]** inizia al 100% e poi scende progressivamente durante il periodo di [validità](../../administration/using/configuring-email-channel.md#validity-period-parameters), quando i rimbalzi morbidi e rigidi vengono riportati<!--from the Enhanced MTA to Campaign-->.

In effetti, tutti i messaggi vengono visualizzati come **[!UICONTROL Sent]** nel [log di invio](../../sending/using/monitoring-a-delivery.md#sending-logs) non appena vengono correttamente inviati da Campaign all&#39;agente di trasferimento messaggi avanzato (MTA). Rimangono nello stato a meno che o fino a quando un [bounce](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) per quel messaggio non venga comunicato nuovamente dall&#39;MTA avanzato alla campagna.

Quando i messaggi di rimbalzo rigido vengono segnalati dall&#39;MTA avanzata, il loro stato cambia da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Delivered]** viene ridotta di conseguenza.

Quando i messaggi di rimbalzo soft vengono segnalati dall&#39;MTA avanzata, vengono comunque visualizzati come **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** non è ancora aggiornata. I messaggi di rimbalzo temporaneo vengono quindi [riprovati](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) durante il periodo di validità della consegna:

* Se un tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio rimane **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** rimane invariata.

* In caso contrario, lo stato cambia in **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Delivered]** viene diminuita di conseguenza.

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, their status changes to **[!UICONTROL Failed]**.-->

<!--For more on retries after a delivery temporary failure, see [this section](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).-->

Di conseguenza, è necessario attendere fino alla fine del periodo di validità per visualizzare la percentuale finale **[!UICONTROL Delivered]** e il numero finale di messaggi effettivi **[!UICONTROL Sent]** e **[!UICONTROL Failed]**.

### Servizio di feedback e-mail (beta) {#email-feedback-service}

>[!NOTE]
>
>Questa sezione si applica solo al canale e-mail.

Grazie alla funzionalità EFS (Email Feedback Service), lo stato di ogni e-mail viene riportato con precisione, perché il feedback viene acquisito direttamente dall&#39;Enhanced MTA (Message Transfer Agent).

>[!IMPORTANT]
>
>Il servizio e-mail di feedback è attualmente disponibile come funzionalità beta.

Una volta avviata la consegna, non si verifica alcuna modifica nella percentuale **[!UICONTROL Delivered]** quando il messaggio viene inviato correttamente da Campaign all&#39;MTA avanzata.

![](assets/efs-sending.png)

I registri di consegna mostrano lo stato **[!UICONTROL Pending]** per ciascun indirizzo di destinazione.

![](assets/efs-pending.png)

Quando il messaggio viene effettivamente recapitato ai profili di destinazione e una volta che tali informazioni vengono riportate in tempo reale dall&#39;MTA avanzata, i registri di consegna mostrano lo stato **[!UICONTROL Sent]** per ogni indirizzo che ha ricevuto correttamente il messaggio. La percentuale **[!UICONTROL Delivered]** viene aumentata di conseguenza con ogni consegna completata correttamente.

Quando i messaggi di rimbalzo rigido vengono segnalati dall&#39;MTA avanzata, lo stato del registro cambia da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza.

Quando i messaggi di rimbalzo soft vengono segnalati dall&#39;MTA avanzata, lo stato del registro cambia anche da **[!UICONTROL Pending]** a **[!UICONTROL Failed]** e la percentuale **[!UICONTROL Bounces + errors]** viene aumentata di conseguenza. La percentuale **[!UICONTROL Delivered]** rimane invariata. I messaggi di rimbalzo temporaneo vengono quindi ritentati durante il periodo di consegna [validità](../../administration/using/configuring-email-channel.md#validity-period-parameters):

* Se un nuovo tentativo ha esito positivo prima della fine del periodo di validità, lo stato del messaggio cambia in **[!UICONTROL Sent]** e la percentuale **[!UICONTROL Delivered]** viene aumentata di conseguenza.

* In caso contrario, lo stato rimane **[!UICONTROL Failed]**. Le percentuali **[!UICONTROL Delivered]** e **[!UICONTROL Bounces + errors]** rimangono invariate.

>[!NOTE]
>
>Per ulteriori informazioni sui rimbalzi rigidi e morbidi, vedere [questa sezione](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Per ulteriori informazioni sui tentativi dopo un errore temporaneo di consegna, vedere [questa sezione](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Modifiche introdotte da EFS {#changes-introduced-by-efs}

La tabella seguente mostra le modifiche apportate ai KPI e agli stati di invio dei log introdotte dalla funzionalità EFS.

| Procedura di invio<br> | Riepilogo KPI<br>SENZA EFS | Invio dello stato dei registri<br>SENZA EFS | Riepilogo KPI<br>CON EFS | Invio dello stato dei registri<br>CON EFS |
|--- |--- |--- | --- | --- |
| Il messaggio viene inviato correttamente da Campaign all&#39;MTA avanzata | <ul><li>**[!UICONTROL Delivered]** percentuale inizia al 100%</li><li>**[!UICONTROL Bounces + errors]** percentuale inizia a 0%</li></ul> | Inviato | <ul><li>**[!UICONTROL Delivered]** percentuale inizia a 0%</li><li>**[!UICONTROL Bounces + errors]** percentuale inizia a 0%</li></ul> | In sospeso |
| I messaggi di rimbalzo duro vengono segnalati nuovamente dall&#39;MTA avanzata | <ul><li>**[!UICONTROL Delivered]** percentuale diminuisce di conseguenza</li><li>**[!UICONTROL Bounces + errors]** percentuale aumentata di conseguenza</li></ul> | Operazione non riuscita | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** percentuale aumentata di conseguenza</li></ul> | Operazione non riuscita |
| I messaggi di rimbalzo temporaneo vengono segnalati nuovamente dall&#39;MTA avanzata | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]**</li></ul> | Inviato | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>**[!UICONTROL Bounces + errors]** percentuale aumentata di conseguenza</li></ul> | Operazione non riuscita |
| I tentativi di messaggi soft-bouncing hanno avuto esito positivo | <ul><li>Nessuna modifica nella percentuale **[!UICONTROL Delivered]**</li><li>Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]**</li></ul> | Inviato | <ul><li>**[!UICONTROL Delivered]** percentuale aumentata di conseguenza</li><li>**[!UICONTROL Bounces + errors]** percentuale diminuisce di conseguenza</li></ul> | Inviato |
| Messaggi di rimbalzo temporaneo non riusciti | <ul><li>**[!UICONTROL Delivered]** percentuale diminuisce di conseguenza</li><li>**[!UICONTROL Bounces + errors]** percentuale aumentata di conseguenza</li></ul> | Operazione non riuscita | <ul><li> Nessuna modifica nella percentuale **[!UICONTROL Delivered]** </li><li> Nessuna modifica nella percentuale **[!UICONTROL Bounces + errors]** </li></ul> | Operazione non riuscita |
