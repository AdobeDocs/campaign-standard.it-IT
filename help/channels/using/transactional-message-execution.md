---
solution: Campaign Standard
product: campaign
title: Esecuzione e monitoraggio di messaggi transazionali
description: Scopri ulteriori informazioni sull'esecuzione dei messaggi transazionali e come monitorare i messaggi transazionali.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 62%

---


# Esecuzione e monitoraggio di messaggi transazionali {#transactional-messaging-execution}

## Invio di messaggi transazionali {#transactional-message-execution-delivery}

Dopo che il messaggio è stato pubblicato e l&#39;integrazione del sito è stata completata, quando un evento viene attivato, viene assegnato a un&#39;esecuzione finale.

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

La **consegna dell&#39;esecuzione** è un messaggio tecnico non utilizzabile e non funzionale creato una volta al mese per ciascun messaggio transazionale, e ogni volta che un messaggio transazionale viene modificato e pubblicato di nuovo.

**Argomenti correlati**:
* [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)
* [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)

## Processo dei tentativi di messaggistica transazionali {#transactional-message-retry-process}

Un messaggio sulle transazioni temporaneamente non consegnato è soggetto all’esecuzione di tentativi automatici fino alla scadenza della consegna. Per ulteriori informazioni sulla durata della consegna, consulta [Parametri del periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando un messaggio sulle transazioni non viene inviato, vi sono due sistemi di esecuzione di un nuovo tentativo:

* A livello di messaggistica sulle transazioni, un messaggio di questo tipo può avere esito negativo prima che l’evento venga assegnato a una consegna di esecuzione, che si trova tra la ricezione dell’evento e la preparazione della consegna. Consulta [Procedura per l’esecuzione di un nuovo tentativo di elaborazione degli eventi](#event-processing-retry-process).
* A livello del processo di invio, una volta che l’evento è stato assegnato a una consegna di esecuzione, il messaggio sulle transazioni potrebbe avere esito negativo a causa di un errore temporaneo. Consulta [Procedura per l’esecuzione di un nuovo tentativo invio del messaggio](#message-sending-retry-process).

### Procedura per l’esecuzione di un nuovo tentativo di elaborazione degli eventi {#event-processing-retry-process}

Quando un evento viene attivato, viene assegnato a un&#39;esecuzione consegna. Se l’evento non può essere assegnato a una consegna di esecuzione, l’elaborazione dell’evento viene posticipata. I tentativi vengono quindi eseguiti fino a quando l’evento non viene assegnato a una nuova consegna di esecuzione.

>[!NOTE]
>
>Un evento posticipato non viene visualizzato nei registi di invio del messaggio sulle transazioni, poiché non è ancora stato assegnato a una consegna di esecuzione.

Ad esempio, non è stato possibile assegnare l’evento a una consegna di esecuzione perché il relativo contenuto non era corretto, si è verificato un problema con i diritti di accesso o con il marchio, è stato rilevato un errore durante l’applicazione delle regole di tipologia e così via. In questo caso, puoi sospendere il messaggio, modificarlo per risolvere il problema e infine pubblicarlo nuovamente. Il sistema di esecuzione di un nuovo tentativo lo assegnerà a una nuova consegna di esecuzione.

### Procedura per l’esecuzione di un nuovo tentativo di invio del messaggio {#message-sending-retry-process}

Una volta che l’evento è stato assegnato a una consegna di esecuzione, il messaggio sulle transazioni può non riuscire a causa di un errore temporaneo, ad esempio se la cassetta postale del destinatario è piena. Per ulteriori informazioni, consulta [Tentativi dopo un errore temporaneo di consegna](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando un evento viene assegnato a un’esecuzione di consegna, viene visualizzato nei registri di invio dell’esecuzione di consegna e solo in questa fase. Le consegne non riuscite vengono visualizzate nella scheda **[!UICONTROL Execution list]** dei registri di invio dei messaggi transazionali.

### Limitazioni del processo di ripetizione {#limitations}

**Invio dell’aggiornamento dei registri**

Nel processo di esecuzione dei nuovi tentativi, i registri di invio della nuova consegna esecuzione non vengono aggiornati immediatamente, poiché tale procedura avviene tramite un flusso di lavoro pianificato. Ciò significa che il messaggio potrebbe trovarsi nello stato **[!UICONTROL Pending]** anche se l’evento sulle transazioni è stato elaborato dalla nuova consegna di esecuzione.

**Consegna di esecuzione non riuscita**

Non è possibile interrompere la consegna dell’esecuzione. Tuttavia, se la consegna dell’esecuzione corrente ha esito negativo, ne viene creata una nuova non appena viene ricevuto un nuovo evento, e tutti i nuovi eventi vengono elaborati dalla nuova consegna dell’esecuzione. Nessun nuovo evento viene elaborato dalla consegna dell’esecuzione non riuscita.

Se alcuni eventi già assegnati a un recapito dell&#39;esecuzione sono stati posticipati come parte del processo dei tentativi e se il recapito dell&#39;esecuzione non riesce, il sistema dei tentativi non assegna gli eventi posticipati al nuovo recapito dell&#39;esecuzione, il che significa che questi eventi sono persi. Controllare i [log di consegna](#monitoring-transactional-message-delivery) per vedere i destinatari che potrebbero essere stati interessati.

## Monitoraggio dei messaggi transazionali {#monitoring-transactional-message-delivery}

Per monitorare un messaggio transazionale, è necessario accedere alle [consegne di esecuzione ](#transactional-message-execution-delivery) corrispondenti.

1. Fai clic sull’icona in basso a destra del blocco **[!UICONTROL Deployment]** per visualizzare il registro di consegna del messaggio.

   ![](assets/message-center_access_logs.png)

1. Fare clic sulla scheda **[!UICONTROL Execution list]**.

   ![](assets/message-center_execution_tab.png)

1. Seleziona la consegna di esecuzione di tua scelta.

   ![](assets/message-center_execution_delivery.png)

1. Fare di nuovo clic sull&#39;icona in basso a destra del blocco **[!UICONTROL Deployment]**.

   ![](assets/message-center_execution_access_logs.png)

   Per ogni consegna di esecuzione, potete consultare i registri di consegna come fareste per una consegna standard. Per ulteriori informazioni sull&#39;accesso e l&#39;utilizzo dei registri, vedere [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md).

### Specificità dei messaggi transazionali basati su profilo {#profile-transactional-message-monitoring}

Per i messaggi transazionali basati su profilo, puoi monitorare le seguenti informazioni di profilo.

Seleziona la scheda **[!UICONTROL Sending logs]**. Nella colonna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica che un profilo ha acconsentito.

![](assets/message-center_marketing_sending_logs.png)

Selezionate la scheda **[!UICONTROL Exclusions logs]** per visualizzare i destinatari che sono stati esclusi dalla destinazione del messaggio, ad esempio gli indirizzi sul elenco Bloccati.

![](assets/message-center_marketing_exclusion_logs.png)

Per ogni profilo che ha rinunciato, la regola di tipologia **[!UICONTROL Address on denylist]** ha escluso il destinatario corrispondente.

Questa regola fa parte di una tipologia specifica che si applica a tutti i messaggi transazionali basati sulla tabella **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Argomenti correlati**:

* [Informazioni su tipologie e regole di tipologia](../../sending/using/about-typology-rules.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)
