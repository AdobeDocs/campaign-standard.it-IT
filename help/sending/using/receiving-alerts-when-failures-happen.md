---
title: Ricezione degli avvisi in caso di errori
description: Scopri come utilizzare il sistema di gestione degli avvisi.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: User
level: Beginner
exl-id: dc8bd1d3-e199-4901-9b1f-7b485879897d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2038'
ht-degree: 2%

---

# Ricezione degli avvisi in caso di errori{#receiving-alerts-when-failures-happen}

## Informazioni sugli avvisi sulla consegna {#about-delivery-alerting}

Il **Avvisi sulla consegna** Questa funzione è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche contenenti informazioni sull’esecuzione delle consegne.

Le notifiche inviate contengono un rapporto basato per impostazione predefinita sui seguenti criteri:

* Consegne non riuscite
* Consegne con preparazione non riuscita
* Consegne con una proporzione di errori di mancati recapiti non permanenti non valida
* Consegne con un rapporto di errore non recapitabile non valido
* Consegne con stato in sospeso più lungo del solito
* Consegne a bassa velocità
* Consegne in corso

I destinatari degli avvisi possono monitorare le consegne in fase di elaborazione da parte di Adobe Campaign e intraprendere azioni appropriate in caso di problemi nell’esecuzione.

Queste notifiche di avviso possono essere personalizzate in base a criteri di avviso specifici definiti tramite una dashboard nell’interfaccia di Adobe Campaign.

>[!NOTE]
>
>Le notifiche di avviso vengono inviate solo tramite e-mail.

Le notifiche inviate contengono:

* A **[!UICONTROL Summary]** visualizzazione del numero di consegne che soddisfano i criteri definiti e dell’etichetta/colore scelto per ciascun criterio.
* A **[!UICONTROL Details]** sezione in cui sono elencati tutti i criteri di consegna definiti per il dashboard corrispondente e tutte le consegne per ciascun criterio.

![](assets/delivery-alerting_notification.png)

## Dashboard di avvisi sulla consegna {#delivery-alerting-dashboards}

### Informazioni sulle dashboard degli avvisi di consegna {#about-delivery-alerting-dashboards}

Per gestire i destinatari delle notifiche, definire i criteri di avviso e accedere alla cronologia degli avvisi, è necessario utilizzare le dashboard.

>[!NOTE]
>
>Per accedere e configurare le dashboard e i criteri di avviso, è necessario disporre dei diritti di amministrazione o essere visualizzati nella **Supervisori della consegna** gruppo di sicurezza. Gli utenti standard non possono accedere alle dashboard nell’interfaccia di Adobe Campaign. Possono solo ricevere le notifiche di avviso. Per ulteriori informazioni sugli utenti e sulla sicurezza in Adobe Campaign, consulta [Tipi di utenti](../../administration/using/users-management.md) e [Informazioni sui gruppi di sicurezza](../../administration/using/managing-groups-and-users.md#about-security-groups).

Dall’interfaccia di Adobe Campaign, puoi:

* Crea e gestisci dashboard di avviso sulla consegna. Consulta [Creazione di un dashboard di avvisi sulla consegna](#creating-a-delivery-alerting-dashboard).
* Definisci e gestisci i criteri di avviso di consegna per ogni dashboard. Ad esempio, puoi creare avvisi basati su consegne con preparazione non riuscita o consegne con una sola velocità effettiva ridotta. Consulta [Informazioni sui criteri di avviso](#about-alerting-criteria).
* Modificate i parametri dei criteri per ciascun quadro comandi. Consulta [Parametri dei criteri](#criteria-parameters).
* Definisci un gruppo di destinatari per ogni dashboard.

  Ad esempio, desideri informare solo gli utenti con diritti di amministrazione delle consegne non riuscite. Tuttavia, desideri che gli utenti marketing ricevano informazioni sulle consegne con una percentuale di errori non validi di soft bounce. Pertanto, devi creare due dashboard diversi e definire i criteri desiderati per ciascun gruppo di destinatari.

* Accedi alla cronologia di tutti gli avvisi inviati per ogni dashboard.

  Quando si seleziona un dashboard, per impostazione predefinita viene visualizzato l’ultimo avviso inviato per il dashboard. Tutti gli avvisi inviati sono elencati a sinistra dello schermo. Fai clic su un elemento in **[!UICONTROL History]** per accedere agli avvisi corrispondenti.

![](assets/delivery-alerting_dashboard.png)

### Creazione di un dashboard di avvisi sulla consegna {#creating-a-delivery-alerting-dashboard}

Se desideri inviare notifiche in base a criteri specifici a diversi gruppi di utenti, devi utilizzare diversi dashboard. Per creare un nuovo dashboard:

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Seleziona **[!UICONTROL Delivery alerting dashboards]** e fai clic su **[!UICONTROL Create]**.
1. Controlla la **[!UICONTROL Enabled]** per attivare il dashboard corrente.

   Se questa opzione è disabilitata, le notifiche collegate a questo dashboard non vengono più inviate. Questa opzione è disabilitata per impostazione predefinita.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Seleziona il gruppo di destinatari a cui desideri inviare la notifica da **[!UICONTROL Alert group]** elenco a discesa. Per modificare o creare un gruppo, vedere [Creazione di un gruppo di sicurezza e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Dalla sezione **[!UICONTROL Delivery alerting criteria]** , fare clic su **[!UICONTROL Create element]** per aggiungere criteri. Consulta [Informazioni sui criteri di avviso](#about-alerting-criteria).
1. Seleziona la **[!UICONTROL Edit properties]** pulsante. In **[!UICONTROL Criteria parameters]** , definisci come verranno applicati i criteri. Consulta [Parametri dei criteri](#criteria-parameters).
1. Clic **[!UICONTROL Create]** per salvare la dashboard.

Ora, ogni volta che una consegna soddisfa i criteri definiti in questa dashboard, viene inviata una notifica di avviso al gruppo di utenti specificato.

## Criteri per gli avvisi di consegna {#delivery-alerting-criteria}

### Informazioni sui criteri di avviso {#about-alerting-criteria}

Per accedere ai criteri di avviso sulla consegna, vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** e seleziona **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

I seguenti criteri possono essere utilizzati nelle dashboard degli avvisi di consegna:

* **[!UICONTROL Deliveries failed]**: qualsiasi consegna pianificata all’interno di un intervallo definito, con uno stato errato.
* **[!UICONTROL Deliveries with preparation failed]**: qualsiasi consegna modificata all’interno di un intervallo definito, per la quale la fase di preparazione (calcolo del target e generazione del contenuto) non è riuscita. Per ulteriori informazioni, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: qualsiasi consegna programmata entro un intervallo definito, con uno stato di almeno **[!UICONTROL In progress]**, con un rapporto di errore di mancato recapito non permanente maggiore di una percentuale definita.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: qualsiasi consegna programmata entro un intervallo definito, con uno stato di almeno **[!UICONTROL In progress]**, con un rapporto di errore di mancato recapito permanente maggiore di una percentuale definita.
* **[!UICONTROL Deliveries with long start pending]**: qualsiasi consegna programmata entro un intervallo definito, con un **[!UICONTROL Start pending]** status per un periodo di tempo superiore a una durata definita, **[!UICONTROL Start pending]** stato, ovvero che i messaggi non sono ancora stati presi in considerazione dal sistema.
* **[!UICONTROL Deliveries with low throughput]**: qualsiasi consegna avviata per una durata superiore a una determinata, con meno di una percentuale definita di messaggi elaborati, con una velocità effettiva inferiore a un valore definito.
* **[!UICONTROL Deliveries in progress]**: qualsiasi consegna programmata entro un intervallo definito, con **[!UICONTROL In progress]** stato.

>[!NOTE]
>
>Tutti i parametri che si applicano ai criteri di cui sopra hanno valori di default. Questi valori possono essere modificati nella **[!UICONTROL Criteria parameters]** delle dashboard di avviso sulla consegna. Consulta [Parametri dei criteri](#criteria-parameters).

È possibile selezionare qualsiasi elemento dal **[!UICONTROL Delivery alerting criteria]** per accedere ai relativi dettagli.

![](assets/delivery-alerting_criteria_definition.png)

Per ciascun criterio, puoi definire le seguenti impostazioni:

* **[!UICONTROL Indicators to add in alerts]**, ovvero le colonne che verranno visualizzate nel **[!UICONTROL Details]** sezione per le consegne corrispondenti al criterio selezionato.

  ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, ovvero l’etichetta e il colore che verranno visualizzati accanto al criterio di consegna nel riepilogo della notifica.

  ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: se un criterio è soddisfatto per una consegna, viene ripetuto in ogni notifica inviata entro il periodo di monitoraggio. In caso contrario, verrà inviato un solo avviso al giorno (alla prima occorrenza) in base al criterio di avviso per una consegna.

  Per impostazione predefinita, questa opzione è impostata su una volta al giorno per tutti i criteri.

**Argomenti correlati:**

* [Registri di invio](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequenza degli avvisi](#alerting-frequency)
* [Icone e stati dell’attività di marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creazione di un criterio di avviso sulla consegna {#creating-a-delivery-alerting-criterion}

Puoi creare nuovi criteri di avviso sulla consegna per soddisfare meglio le tue esigenze.

Ad esempio, puoi creare un nuovo criterio che consenta di inviare una notifica in cui sono elencate tutte le consegne con una **[!UICONTROL Finished]** stato.

A questo scopo, devi innanzitutto estendere il **Consegna** e aggiungi un nuovo filtro che consente di selezionare solo le consegne con un **[!UICONTROL Finished]** stato.

1. Vai a **Adobe Campaign** > **Amministrazione** > **Sviluppo** > **Risorse personalizzate** e fai clic su **[!UICONTROL Create]**.
1. Seleziona **[!UICONTROL Extend an existing resource]**, seleziona la **[!UICONTROL Delivery]** risorsa dall’elenco a discesa e fai clic su **[!UICONTROL Create]** per modificarlo.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Per ulteriori informazioni sull’estensione di una risorsa esistente, consulta [Definire la risorsa](../../developing/using/creating-or-extending-the-resource.md).

1. In **[!UICONTROL Delivery]** risorsa, vai al **[!UICONTROL Filter definition]** e fai clic su **[!UICONTROL Add an element]** per creare un filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Modifica la nuova definizione del filtro: in **[!UICONTROL Filter definition]** , trascina e rilascia la **[!UICONTROL Status]** nell&#39;area di lavoro e selezionare **[!UICONTROL Finished]** come condizione del filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Per ulteriori informazioni sulla creazione e la modifica di filtri personalizzati, consulta [Definire i filtri](../../developing/using/configuring-filter-definition.md).

1. Salva le modifiche e pubblica le risorse. Per ulteriori informazioni, consulta [Pubblicazione di una risorsa personalizzata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Il filtro viene creato e ora può essere selezionato in un nuovo criterio di avviso sulla consegna.

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, seleziona **[!UICONTROL Delivery alerting criteria]** e fai clic su **[!UICONTROL Create]**.
1. In **[!UICONTROL Delivery filter applied by this criterion]** , selezionare il filtro appena creato.

   ![](assets/delivery-alerting_cus-filter.png)

   È possibile definire le impostazioni del criterio allo stesso modo dei criteri predefiniti. Consulta [Informazioni sui criteri di avviso](#about-alerting-criteria).

Una volta creati, questi criteri possono essere aggiunti a una dashboard di avvisi di consegna e ad altri criteri. Consulta [Informazioni sulle dashboard degli avvisi di consegna](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Argomento correlato:**

[Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)

## Parametri di avviso sulla consegna {#delivery-alerting-parameters}

### Parametri dei criteri {#criteria-parameters}

In **[!UICONTROL Criteria parameters]** scheda di una [dashboard degli avvisi di consegna](#creating-a-delivery-alerting-dashboard), è possibile definire le impostazioni che si applicano ai criteri selezionati in questo dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: ad esempio, se immetti 100 in questo campo, una notifica viene inviata solo per le consegne con una destinazione uguale o superiore a 100 destinatari. Questo parametro si applica a tutti i criteri.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: numero di ore prima e dopo l’ora corrente. Vengono prese in considerazione solo le consegne con una data di contatto in questo intervallo di tempo. Questo parametro si applica a tutti i criteri. Per impostazione predefinita, il valore di questo campo è impostato su 24 ore.

  Per ulteriori informazioni sulla data di contatto, consulta [Informazioni sulla pianificazione](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: viene inviata una notifica per tutte le consegne con un rapporto di errore di mancato recapito non permanente maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è 0,05 (5%).

  Per ulteriori informazioni sugli errori di mancato recapito non permanente, consulta [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Elenco dei tipi di errori di consegna](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: viene inviata una notifica per tutte le consegne con un rapporto di errore per mancati recapiti permanenti maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è 0,05 (5%).

  Per ulteriori informazioni sugli errori permanenti di mancato recapito, consulta [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Elenco dei tipi di errori di consegna](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: viene inviata una notifica per tutte le consegne con una **[!UICONTROL Start pending]** stato per un periodo superiore alla durata specificata in questo campo, **[!UICONTROL Start pending]** stato, ovvero che i messaggi non sono ancora stati presi in considerazione dal sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: solo consegne avviate (con **[!UICONTROL In progress]** oltre la durata specificata vengono presi in considerazione per il **[!UICONTROL Deliveries with low throughput]** criterio.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: per le consegne con una percentuale di messaggi elaborati inferiore alla percentuale specificata, vengono prese in considerazione solo le consegne **[!UICONTROL Deliveries with low throughput]** criterio.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: per la consegna vengono considerate solo le consegne con una velocità effettiva inferiore al valore specificato **[!UICONTROL Deliveries with low throughput]** criterio.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati superiore alla percentuale specificata.

### Frequenza degli avvisi {#alerting-frequency}

Il **[!UICONTROL Frequency of delivery alerting]** consente di definire il ritardo tra due invii di avvisi. Per impostazione predefinita è impostato su 10 minuti.

È possibile modificare questa impostazione tramite **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

>[!NOTE]
>
>Questa opzione è applicabile a tutte le dashboard definite in Adobe Campaign. Non è possibile impostare una frequenza specifica per ogni dashboard.

## Motivi degli avvisi sulla consegna {#delivery-alerting-reasons}

Il **Avvisi sulla consegna** tramite e-mail e dashboard, tutti gli utenti di Adobe Campaign interessati vengono automaticamente informati sullo stato di esecuzione della consegna.

Ora, quando ricevi una notifica di avviso sulla consegna, ecco alcuni suggerimenti su cosa puoi fare.

Prima di tutto, controlla il **Log** per visualizzare tutte le informazioni relative alla consegna e alle bozze. Le icone rosse e gialle consentono di identificare errori o avvisi. L’icona rossa indica un errore critico che impedisce l’avvio della consegna.

Per visualizzare la cronologia di ogni occorrenza di una consegna, seleziona la **[!UICONTROL Sending logs]** scheda. Contiene l’elenco dei messaggi inviati e i relativi stati. Qui puoi controllare lo stato di consegna per ogni destinatario ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, ecc.). Per ulteriori informazioni, consulta [Registri di invio](../../sending/using/monitoring-a-delivery.md#sending-logs).

Di seguito sono riportati alcuni possibili motivi per ricevere notifiche di avviso in base ai criteri soddisfatti per una consegna.

* **[!UICONTROL Deliveries failed]**: questo criterio ti informa su tutte le consegne con uno stato errato. Può essere dovuto a:

   * Un problema con il server di consegna (MTA, agente di trasferimento messaggi)
   * Timeout di connessione tra il server di consegna Adobe Campaign e il server ricevente
   * Un problema di recapito messaggi
   * Un flusso di lavoro errato

  Se la consegna viene attivata con un flusso di lavoro, verifica che il flusso di lavoro sia stato avviato correttamente. Per ulteriori informazioni, consulta [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md). In caso contrario, contatta il tuo amministratore Adobe Campaign per risolvere il problema.

* **[!UICONTROL Deliveries with preparation failed]**: si può verificare un errore durante la preparazione della consegna nei seguenti casi:

   * Oggetto mancante nella consegna.
   * Nei campi di personalizzazione è presente una sintassi errata.
   * Destinazione mancante.
   * La consegna supera il limite di dimensioni.

  Per ulteriori informazioni, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md). Tuttavia, questi errori vengono generalmente individuati durante l’analisi dei messaggi. Consulta [Regole di controllo](../../sending/using/control-rules.md).

* Le possibili cause di un **[!UICONTROL Delivery with bad error ratio for soft bounces]** l&#39;avviso può essere:

   * Il server del destinatario non è attivo.
   * La cassetta postale del destinatario è piena.

  Per ulteriori informazioni, consulta **[!UICONTROL Exclusion logs]** e **[!UICONTROL Exclusion causes]** schede dei registri di consegna. Consulta [Exclusion logs](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

  Le possibili cause di un **[!UICONTROL Delivery with bad error ratio for hard bounces]** l&#39;avviso può essere:

   * Il destinatario viene aggiunto al inserisco nell&#39;elenco Bloccati di, ovvero non desidera più essere contattato.
   * L’indirizzo e-mail del destinatario non esiste.
   * Il dominio del destinatario non esiste.
   * Il server del destinatario sta bloccando la consegna.

  Per evitare errori di mancato recapito non permanenti e permanenti, segui le best practice riportate di seguito:

   * Genera regole di tipologia di filtro per escludere una parte del target del messaggio durante l’analisi della consegna, ad esempio i destinatari in quarantena. Consulta [Creazione di una regola di filtro](../../sending/using/filtering-rules.md).
   * Aggiorna regolarmente il database dei clienti per mantenere processi di gestione della quarantena ottimali. Consulta [Informazioni sulla quarantena](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * In generale, migliora il più possibile il recapito messaggi. Consulta Adobe Campaign [Recapito messaggi](../../sending/using/about-deliverability.md) documentazione dettagliata e contatta l’amministratore di Adobe Campaign per assistenza.

* **[!UICONTROL Deliveries with long start pending]**: di solito questo significa che si è verificato un problema a livello dell’MTA (Message Transfer Agent). Il processo di esecuzione è in attesa della disponibilità di alcune risorse. L’MTA potrebbe non essere stato avviato.

  **[!UICONTROL Deliveries with low throughput]**: anche in questo caso, si tratta di un problema di recapito messaggi che significa che l’MTA è troppo lento.

  Per ulteriori informazioni su questi problemi, contatta il tuo amministratore Adobe Campaign.

**Argomenti correlati:**

* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Informazioni su consenso e rinuncia in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
