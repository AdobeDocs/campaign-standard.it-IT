---
solution: Campaign Standard
product: campaign
title: Ricezione degli avvisi in caso di errori
description: Scopri come utilizzare il sistema di gestione degli avvisi.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Proofs
role: Business Practitioner
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 2%

---


# Ricezione degli avvisi in caso di errori{#receiving-alerts-when-failures-happen}

## Informazioni sugli avvisi sulla consegna {#about-delivery-alerting}

La funzione **Avvisi di consegna** è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche contenenti informazioni sull’esecuzione delle consegne.

Le notifiche inviate contengono un rapporto basato per impostazione predefinita sui seguenti criteri:

* Consegne non riuscite
* Consegne con preparazione non riuscita
* Consegne con un rapporto di errore non recapitato non valido
* Consegne con un rapporto di errore non recapitato difficile
* Consegne con uno stato in sospeso più lungo del solito
* Consegne a bassa velocità
* Consegne in corso

I destinatari degli avvisi possono monitorare le consegne elaborate da Adobe Campaign e intraprendere azioni appropriate in caso di problemi di esecuzione.

Queste notifiche di avviso possono essere personalizzate in base a criteri di avviso specifici definiti tramite un dashboard nell’interfaccia di Adobe Campaign.

>[!NOTE]
>
>Le notifiche di avviso vengono inviate solo per e-mail.

Le notifiche inviate contengono:

* Un **[!UICONTROL Summary]** che mostra il numero di consegne che soddisfano i criteri definiti e l’etichetta/colore scelto per ciascun criterio.
* Una sezione **[!UICONTROL Details]** in cui sono elencati tutti i criteri di consegna definiti per il dashboard corrispondente e tutte le consegne per ciascun criterio.

![](assets/delivery-alerting_notification.png)

## Dashboard degli avvisi di consegna {#delivery-alerting-dashboards}

### Informazioni sulle dashboard degli avvisi di consegna {#about-delivery-alerting-dashboards}

Per gestire i destinatari delle notifiche, definire i criteri di avviso e accedere alla cronologia degli avvisi, devi utilizzare le dashboard.

>[!NOTE]
>
>Per accedere e configurare le dashboard e i criteri di avviso, è necessario disporre dei diritti di amministrazione o essere visualizzati nel gruppo di sicurezza **Supervisori consegna** . Gli utenti standard non possono accedere alle dashboard nell’interfaccia di Adobe Campaign. Possono ricevere solo le notifiche di avviso. Per ulteriori informazioni sugli utenti e sulla sicurezza in Adobe Campaign, consulta [Tipi di utenti](../../administration/using/users-management.md) e [Informazioni sui gruppi di sicurezza](../../administration/using/managing-groups-and-users.md#about-security-groups).

Dall’interfaccia di Adobe Campaign, puoi:

* Crea e gestisci dashboard di avvisi sulla consegna. Consulta [Creazione di un dashboard di avvisi sulla consegna](#creating-a-delivery-alerting-dashboard).
* Definisci e gestisci i criteri di avviso sulla consegna per ciascun dashboard. Ad esempio, puoi creare avvisi basati su consegne con preparazione non riuscita o consegne con throughput limitato. Consulta [Informazioni sui criteri di avviso](#about-alerting-criteria).
* Modificate i parametri dei criteri per ogni dashboard. Vedere [Parametri dei criteri](#criteria-parameters).
* Definisci un gruppo di destinatari per ogni dashboard.

   Ad esempio, desideri informare gli utenti con diritti di amministrazione solo delle consegne non riuscite. Tuttavia, desideri che gli utenti di marketing ricevano informazioni sulle consegne con un indice di errore non recapitato morbido. Pertanto, devi creare due diverse dashboard e definire i criteri desiderati per ogni gruppo di destinatari.

* Accedi alla cronologia di tutti gli avvisi inviati per ogni dashboard.

   Quando si seleziona un dashboard, per impostazione predefinita viene visualizzato l’ultimo avviso inviato per il dashboard. Tutti gli avvisi inviati sono elencati a sinistra dello schermo. Fai clic su una voce nell&#39;elenco **[!UICONTROL History]** per accedere agli avvisi corrispondenti.

![](assets/delivery-alerting_dashboard.png)

### Creazione di un dashboard di avvisi sulla consegna {#creating-a-delivery-alerting-dashboard}

Per inviare notifiche basate su criteri specifici a diversi gruppi di utenti, è necessario utilizzare diverse dashboard. Per creare un nuovo dashboard:

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Seleziona **[!UICONTROL Delivery alerting dashboards]** e fai clic su **[!UICONTROL Create]**.
1. Seleziona la casella **[!UICONTROL Enabled]** per attivare il dashboard corrente.

   Se questa opzione è disabilitata, le notifiche collegate a questo dashboard non vengono più inviate. Questa opzione è disabilitata per impostazione predefinita.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Seleziona il gruppo di destinatari a cui inviare la notifica dall’elenco a discesa **[!UICONTROL Alert group]** . Per modificare o creare un gruppo, vedere [Creazione di un gruppo di sicurezza e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Nella sezione **[!UICONTROL Delivery alerting criteria]** , fai clic su **[!UICONTROL Create element]** per aggiungere criteri. Consulta [Informazioni sui criteri di avviso](#about-alerting-criteria).
1. Fai clic sul pulsante **[!UICONTROL Edit properties]**. Nella scheda **[!UICONTROL Criteria parameters]** , definisci come verranno applicati i criteri. Vedere [Parametri dei criteri](#criteria-parameters).
1. Fai clic su **[!UICONTROL Create]** per salvare il dashboard.

Ogni volta che una consegna soddisfa i criteri definiti in questo dashboard, viene inviata una notifica di avviso al gruppo di utenti specificato.

## Criteri di avviso sulla consegna {#delivery-alerting-criteria}

### Informazioni sui criteri di avviso {#about-alerting-criteria}

Per accedere ai criteri di avviso sulla consegna, vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** e seleziona **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

Nei dashboard degli avvisi di consegna possono essere utilizzati i seguenti criteri:

* **[!UICONTROL Deliveries failed]**: Qualsiasi consegna pianificata all’interno di un intervallo definito, con stato errato.
* **[!UICONTROL Deliveries with preparation failed]**: Qualsiasi consegna modificata all’interno di un intervallo definito per il quale la fase di preparazione (calcolo del target e generazione di contenuto) non è riuscita. Per ulteriori informazioni, consulta [Preparazione dell&#39;invio](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualsiasi consegna pianificata all’interno di un intervallo definito, con uno stato almeno  **[!UICONTROL In progress]**, con un rapporto di errore non recapitato morbido maggiore di una percentuale definita.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualsiasi consegna pianificata all’interno di un intervallo definito, con almeno uno stato  **[!UICONTROL In progress]**, con un rapporto di errore non recapitato difficile maggiore di una percentuale definita.
* **[!UICONTROL Deliveries with long start pending]**: Qualsiasi consegna pianificata all’interno di un intervallo definito, con uno  **[!UICONTROL Start pending]** stato per più di una durata definita,  **[!UICONTROL Start pending]** stato che significa che i messaggi non sono ancora stati presi in considerazione dal sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualsiasi consegna iniziata per più tempo di una durata definita, con meno di una percentuale definita di messaggi elaborati, con un throughput inferiore a un valore definito.
* **[!UICONTROL Deliveries in progress]**: Qualsiasi consegna pianificata all’interno di un intervallo definito, con lo  **[!UICONTROL In progress]** stato .

>[!NOTE]
>
>Tutti i parametri applicati ai criteri di cui sopra hanno valori predefiniti. Questi valori possono essere modificati nella scheda **[!UICONTROL Criteria parameters]** dei dashboard degli avvisi di consegna. Vedere [Parametri dei criteri](#criteria-parameters).

È possibile selezionare qualsiasi elemento dall&#39;elenco **[!UICONTROL Delivery alerting criteria]** per accedere ai relativi dettagli.

![](assets/delivery-alerting_criteria_definition.png)

Per ogni criterio, puoi definire le seguenti impostazioni:

* **[!UICONTROL Indicators to add in alerts]**, ovvero le colonne che verranno visualizzate nella  **[!UICONTROL Details]** sezione della notifica per le consegne corrispondenti al criterio selezionato.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, ovvero l’etichetta e il colore che verranno visualizzati accanto al criterio di consegna nel riepilogo della notifica.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Se un criterio viene soddisfatto per una consegna, viene ripetuto in ogni notifica inviata entro il periodo di monitoraggio. In caso contrario, per una singola consegna verrà inviato un solo avviso al giorno (alla prima occorrenza) in base al criterio di avviso.

   Per impostazione predefinita, questa opzione è impostata una volta al giorno per tutti i criteri.

**Argomenti correlati:**

* [Registri di invio](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequenza degli avvisi](#alerting-frequency)
* [Icone e stati dell’attività di marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creazione di un criterio di avviso sulla consegna {#creating-a-delivery-alerting-criterion}

Puoi creare nuovi criteri di avviso sulla consegna per soddisfare le tue esigenze.

Ad esempio, puoi creare un nuovo criterio che consenta di inviare una notifica in cui sono elencate tutte le consegne con uno stato **[!UICONTROL Finished]** .

A questo scopo, devi innanzitutto estendere la risorsa **Consegna** e aggiungere un nuovo filtro che ti consenta di selezionare solo le consegne con uno stato **[!UICONTROL Finished]** .

1. Vai a **Adobe Campaign** > **Amministrazione** > **Sviluppo** > **Risorse personalizzate** e fai clic su **[!UICONTROL Create]**.
1. Seleziona **[!UICONTROL Extend an existing resource]**, seleziona la risorsa **[!UICONTROL Delivery]** dall’elenco a discesa e fai clic su **[!UICONTROL Create]** per modificarla.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Per ulteriori informazioni sull’estensione di una risorsa esistente, consulta [Definire la risorsa](../../developing/using/creating-or-extending-the-resource.md).

1. Nella risorsa **[!UICONTROL Delivery]** , vai alla scheda **[!UICONTROL Filter definition]** e fai clic su **[!UICONTROL Add an element]** per creare un filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Modifica la nuova definizione del filtro: nella finestra **[!UICONTROL Filter definition]** , trascina e rilascia l’elemento **[!UICONTROL Status]** nell’area di lavoro e seleziona **[!UICONTROL Finished]** come condizione del filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Per ulteriori informazioni sulla creazione e la modifica di filtri personalizzati, consulta [Definire i filtri](../../developing/using/configuring-filter-definition.md).

1. Salva le modifiche e pubblica le risorse. Per ulteriori informazioni, consulta [Pubblicazione di una risorsa personalizzata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Il filtro viene creato e può ora essere selezionato in un nuovo criterio di avviso sulla consegna.

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, seleziona **[!UICONTROL Delivery alerting criteria]** e fai clic su **[!UICONTROL Create]**.
1. Nell’elenco a discesa **[!UICONTROL Delivery filter applied by this criterion]** , seleziona il filtro appena creato.

   ![](assets/delivery-alerting_cus-filter.png)

   È possibile definire le impostazioni del criterio nello stesso modo in cui sono state definite per i criteri predefiniti. Consulta [Informazioni sui criteri di avviso](#about-alerting-criteria).

Una volta creati, questi criteri possono essere aggiunti a un dashboard di avvisi sulla consegna e ad altri criteri. Consulta [Informazioni sulle dashboard degli avvisi sulla consegna](#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Argomento correlato:**

[Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)

## Parametri di avviso sulla consegna {#delivery-alerting-parameters}

### Parametri dei criteri {#criteria-parameters}

Nella scheda **[!UICONTROL Criteria parameters]** di un [dashboard di avviso sulla consegna](#creating-a-delivery-alerting-dashboard), puoi definire le impostazioni applicabili ai criteri selezionati in questo dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Ad esempio, se immetti 100 in questo campo, una notifica viene inviata solo per le consegne con un target pari o superiore a 100 destinatari. Questo parametro si applica a tutti i criteri.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Numero di ore prima e dopo l&#39;ora corrente. Vengono prese in considerazione solo le consegne che hanno una data di contatto in questo intervallo di tempo. Questo parametro si applica a tutti i criteri. Per impostazione predefinita, il valore di questo campo è impostato su 24 ore.

   Per ulteriori informazioni sulla data di contatto, vedere [Informazioni sulla pianificazione](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Viene inviata una notifica per tutte le consegne con un rapporto di errore non recapitato morbido maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è impostato su 0,05 (5%).

   Per ulteriori informazioni sugli errori di mancato recapito, consulta [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Elenco dei tipi di errori di consegna](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Viene inviata una notifica per tutte le consegne con un rapporto di errore mancato recapito maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è impostato su 0,05 (5%).

   Per ulteriori informazioni sugli errori di mancato recapito, consulta [Qualificazione di mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Elenco dei tipi di errori di consegna](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Viene inviata una notifica per tutte le consegne con uno  **[!UICONTROL Start pending]** stato per un periodo superiore alla durata specificata in questo campo,  **[!UICONTROL Start pending]** stato che significa che i messaggi non sono ancora stati presi in considerazione dal sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Per il  **[!UICONTROL In progress]** criterio vengono prese in considerazione solo le consegne avviate (con  **[!UICONTROL Deliveries with low throughput]** stato ) per più della durata specificata.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Per il  **[!UICONTROL Deliveries with low throughput]** criterio vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati inferiore alla percentuale specificata.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Per il  **[!UICONTROL Deliveries with low throughput]** criterio vengono prese in considerazione solo le consegne con una velocità effettiva inferiore al valore specificato.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati superiore alla percentuale specificata.

### Frequenza degli avvisi {#alerting-frequency}

L’opzione **[!UICONTROL Frequency of delivery alerting]** consente di definire il ritardo tra due invii di avvisi. Per impostazione predefinita, è impostato su 10 minuti.

Puoi modificare questa impostazione tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

>[!NOTE]
>
>Questa opzione si applica a tutte le dashboard definite in Adobe Campaign. Non è possibile impostare una frequenza specifica per ogni dashboard.

## Motivi degli avvisi sulla consegna {#delivery-alerting-reasons}

La funzione **Avvisi di consegna** mantiene tutti gli utenti Adobe Campaign coinvolti automaticamente informati sullo stato di esecuzione della consegna, tramite e-mail e dashboard.

Ora quando ricevi una notifica di avviso sulla consegna, ecco alcuni suggerimenti su cosa puoi fare.

Innanzitutto, controlla la scheda **Log** della consegna per visualizzare tutte le informazioni relative alla consegna e alle bozze. Le icone rosso e giallo consentono di identificare errori o avvisi. L’icona rossa indica un errore critico che impedisce l’avvio della consegna.

Per visualizzare la cronologia di ogni occorrenza di una consegna, seleziona la scheda **[!UICONTROL Sending logs]** . Contiene l’elenco dei messaggi inviati e i relativi stati. Qui puoi controllare lo stato di consegna per ciascun destinatario ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, ecc.). Per ulteriori informazioni, consulta [Invio di registri](../../sending/using/monitoring-a-delivery.md#sending-logs).

Di seguito sono riportati alcuni possibili motivi per ricevere notifiche di avviso in base ai criteri soddisfatti per una consegna.

* **[!UICONTROL Deliveries failed]**: Questo criterio ti informa di tutte le consegne con uno stato errato. Può essere dovuto a:

   * Problema con il server di consegna (MTA, Agente di trasferimento messaggi)
   * Timeout di connessione tra il server di consegna Adobe Campaign e il server ricevente
   * Un problema di recapito messaggi
   * Un flusso di lavoro errato

   Se la consegna viene attivata con un flusso di lavoro, controlla se tale flusso di lavoro è stato avviato correttamente. Per ulteriori informazioni, consulta [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md). In caso contrario, contatta il tuo amministratore Adobe Campaign per risolvere il problema.

* **[!UICONTROL Deliveries with preparation failed]**: Un errore può verificarsi durante la preparazione della consegna nei seguenti casi:

   * Nella consegna manca un soggetto.
   * La sintassi nei campi di personalizzazione è errata.
   * Il target è mancante.
   * La consegna supera il limite di dimensioni.

   Per ulteriori informazioni, consulta [Preparazione dell&#39;invio](../../sending/using/preparing-the-send.md). Tuttavia, questi errori vengono generalmente rilevati durante l’analisi dei messaggi. Vedere [Regole di controllo](../../sending/using/control-rules.md).

* Le possibili cause di un avviso **[!UICONTROL Delivery with bad error ratio for soft bounces]** possono essere:

   * Il server del destinatario non è attivo.
   * La cassetta postale del destinatario è piena.

   Per ulteriori informazioni, controlla le schede **[!UICONTROL Exclusion logs]** e **[!UICONTROL Exclusion causes]** dei registri di consegna. Consulta [Log di esclusione](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   Le possibili cause di un avviso **[!UICONTROL Delivery with bad error ratio for hard bounces]** possono essere:

   * Il destinatario viene aggiunto al elenco Bloccati, il che significa che non desidera più essere contattato.
   * L&#39;indirizzo e-mail del destinatario non esiste.
   * Il dominio del destinatario non esiste.
   * Il server del destinatario sta bloccando la consegna.

   Per evitare errori di rimbalzo morbido e rigido, segui le best practice riportate di seguito:

   * Crea regole di tipologia di filtro per escludere una parte del target del messaggio durante l’analisi della consegna, ad esempio i destinatari in quarantena. Consulta [Creazione di una regola di filtro](../../sending/using/filtering-rules.md).
   * Aggiorna regolarmente il database dei clienti per mantenere buoni processi di gestione della quarantena. Consulta [Informazioni sulla quarantena](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * In generale, migliorare il recapito messaggi nel miglior modo possibile. Consulta la documentazione dettagliata Adobe Campaign [Recapito messaggi](../../sending/using/about-deliverability.md) e contatta il tuo amministratore Adobe Campaign per assistenza.



* **[!UICONTROL Deliveries with long start pending]**: Di solito questo significa che c&#39;è un problema a livello di MTA (Message Transfer Agent). Il processo di esecuzione è in attesa della disponibilità di alcune risorse. L&#39;MTA potrebbe non essere stato avviato.

   **[!UICONTROL Deliveries with low throughput]**: Anche in questo caso, si tratta di un problema di recapito messaggi che significa che l’MTA è troppo lento.

   Per ulteriori informazioni su questi problemi, contatta il tuo amministratore Adobe Campaign.

**Argomenti correlati:**

* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Informazioni sul consenso e diniego in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

