---
title: Ricezione degli avvisi in caso di errori
description: Scopri come utilizzare il sistema di gestione degli avvisi.
page-status-flag: never-activated
uuid: a3ab733a-e3db-4adc-b930-cd4064b6dc1c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 0766bd57-c5f1-4f56-ac84-e5a04d3819ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '2031'
ht-degree: 2%

---


# Ricezione degli avvisi in caso di errori{#receiving-alerts-when-failures-happen}

## Informazioni sugli avvisi relativi alla consegna {#about-delivery-alerting}

The **Delivery alerting** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

Le notifiche inviate contengono un rapporto basato per impostazione predefinita sui seguenti criteri:

* Consegne non riuscite
* Consegne con preparazione non riuscita
* Consegne con un basso rapporto di errore soft bounce
* Consegne con un rapporto di errore difficile rimbalzo
* Consegne con stato in sospeso più lungo del solito
* Consegne con un throughput basso
* Consegne in corso

I destinatari degli avvisi possono monitorare le consegne elaborate da  Adobe Campaign e intraprendere le azioni appropriate in caso di problemi nella loro esecuzione.

Queste notifiche di avviso possono essere personalizzate in base a criteri di avviso specifici definiti tramite un dashboard nell&#39;interfaccia  di Adobe Campaign.

>[!NOTE]
>
>Le notifiche di avviso vengono inviate solo per e-mail.

Le notifiche inviate contengono:

* Indica **[!UICONTROL Summary]** il numero di consegne che soddisfano i criteri definiti e l&#39;etichetta/colore scelta per ciascun criterio.
* Una **[!UICONTROL Details]** sezione che elenca tutti i criteri di consegna definiti per il dashboard corrispondente e tutte le consegne per ciascun criterio.

![](assets/delivery-alerting_notification.png)

## Dashboard avvisi sulla distribuzione {#delivery-alerting-dashboards}

### Informazioni sulle dashboard di avvisi sulla distribuzione {#about-delivery-alerting-dashboards}

Per gestire i destinatari delle notifiche, definire i criteri di avviso e accedere alla cronologia degli avvisi, è necessario utilizzare le dashboard.

>[!NOTE]
>
>Per accedere e configurare le dashboard e i criteri di avviso, è necessario disporre dei diritti di amministrazione o essere visualizzati nel gruppo di sicurezza **Supervisori** consegna. Gli utenti standard non possono accedere alle dashboard nell&#39;interfaccia  Adobe Campaign. Possono ricevere solo le notifiche di avviso. Per ulteriori informazioni sugli utenti e sulla protezione in  Adobe Campaign, consulta [Tipi di utenti](../../administration/using/users-management.md) e [Informazioni sui gruppi](../../administration/using/managing-groups-and-users.md#about-security-groups)di protezione.

Dall&#39;interfaccia  Adobe Campaign, potete:

* Creazione e gestione di dashboard di avvisi sulla distribuzione. Consultate [Creazione di un dashboard](#creating-a-delivery-alerting-dashboard)di avvisi sulla consegna.
* Definite e gestite i criteri di avviso per la consegna per ogni dashboard. Ad esempio, puoi creare avvisi basati su consegne con preparazione non riuscita o consegne con un throughput limitato. Consultate [Informazioni sui criteri](#about-alerting-criteria)di avviso.
* Modificate i parametri dei criteri per ogni dashboard. Vedere Parametri [](#criteria-parameters)dei criteri.
* Definite un gruppo di destinatari per ogni dashboard.

   Ad esempio, desiderate informare gli utenti con diritti di amministrazione solo delle consegne non riuscite. Tuttavia, vuoi che gli utenti di marketing ricevano informazioni sulle consegne con un debole rapporto errori rimbalzati. Pertanto, è necessario creare due diverse dashboard e definire i criteri desiderati per ciascun gruppo di destinatari.

* Consente di accedere alla cronologia di tutti gli avvisi inviati per ogni dashboard.

   Quando si seleziona un dashboard, per impostazione predefinita viene visualizzato l’ultimo avviso inviato per il dashboard. Tutti gli avvisi inviati sono elencati a sinistra dello schermo. Fare clic su una voce nell&#39; **[!UICONTROL History]** elenco per accedere ai relativi avvisi.

![](assets/delivery-alerting_dashboard.png)

### Creazione di un dashboard di avvisi per la consegna {#creating-a-delivery-alerting-dashboard}

Se desiderate inviare notifiche basate su criteri specifici a diversi gruppi di utenti, dovete utilizzare diverse dashboard. Per creare una nuova dashboard:

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**.
1. Seleziona **[!UICONTROL Delivery alerting dashboards]** e fai clic su **[!UICONTROL Create]**.
1. Selezionare la **[!UICONTROL Enabled]** casella per attivare il dashboard corrente.

   Se questa opzione è disabilitata, le notifiche collegate a questo dashboard non vengono più inviate. Questa opzione è disabilitata per impostazione predefinita.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Dall’elenco a **[!UICONTROL Alert group]** discesa, selezionate il gruppo di destinatari a cui desiderate inviare una notifica. Per modificare o creare un gruppo, consultate [Creazione di un gruppo di protezione e assegnazione di utenti](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. Dalla **[!UICONTROL Delivery alerting criteria]** sezione, fate clic **[!UICONTROL Create element]** per aggiungere criteri. Consultate [Informazioni sui criteri](#about-alerting-criteria)di avviso.
1. Fai clic sul pulsante **[!UICONTROL Edit properties]**. Nella **[!UICONTROL Criteria parameters]** scheda, definire le modalità di applicazione dei criteri. Vedere Parametri [](#criteria-parameters)dei criteri.
1. Click **[!UICONTROL Create]** to save the dashboard.

Ogni volta che una consegna soddisfa i criteri definiti in questo dashboard, viene inviata una notifica di avviso al gruppo specificato di utenti.

## Criteri di avviso sulla consegna {#delivery-alerting-criteria}

### Informazioni sui criteri di avviso {#about-alerting-criteria}

Per accedere ai criteri di avviso relativi alla consegna, andate a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]** e selezionate **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

I seguenti criteri possono essere utilizzati nelle dashboard di avvisi di consegna:

* **[!UICONTROL Deliveries failed]**: Qualsiasi consegna pianificata entro un intervallo definito, con stato errato.
* **[!UICONTROL Deliveries with preparation failed]**: Qualsiasi consegna modificata all&#39;interno di un intervallo definito per il quale la fase di preparazione (calcolo target e generazione di contenuto) non è riuscita. Per ulteriori informazioni, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualsiasi consegna programmata all&#39;interno di un intervallo definito, con uno stato almeno **[!UICONTROL In progress]**, con un rapporto di errore con rimbalzo morbido maggiore di una percentuale definita.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualsiasi consegna programmata all&#39;interno di un intervallo definito, con uno stato almeno **[!UICONTROL In progress]**, con un rapporto di errore duro superiore a una percentuale definita.
* **[!UICONTROL Deliveries with long start pending]**: Qualsiasi consegna programmata all&#39;interno di un intervallo definito, con uno **[!UICONTROL Start pending]** stato per più di una durata definita, **[!UICONTROL Start pending]** stato che significa che i messaggi non sono ancora stati presi in considerazione dal sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualsiasi consegna ha avuto inizio per più tempo di una durata definita, con meno di una percentuale definita di messaggi elaborati, con un throughput inferiore a un valore definito.
* **[!UICONTROL Deliveries in progress]**: Qualsiasi consegna pianificata entro un intervallo definito, con lo **[!UICONTROL In progress]** stato.

>[!NOTE]
>
>Tutti i parametri applicati ai criteri di cui sopra hanno valori predefiniti. Questi valori possono essere modificati nella **[!UICONTROL Criteria parameters]** scheda delle dashboard di avvisi di consegna. Vedere Parametri [](#criteria-parameters)dei criteri.

Potete selezionare qualsiasi elemento dall’ **[!UICONTROL Delivery alerting criteria]** elenco per accedere ai relativi dettagli.

![](assets/delivery-alerting_criteria_definition.png)

Per ciascun criterio, potete definire le seguenti impostazioni:

* **[!UICONTROL Indicators to add in alerts]**, ovvero le colonne che verranno visualizzate nella **[!UICONTROL Details]** sezione della notifica per le consegne corrispondenti al criterio selezionato.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, ossia l’etichetta e il colore che verranno visualizzati accanto al criterio di consegna nel riepilogo della notifica.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Se un criterio è soddisfatto per una consegna, viene ripetuto in ciascuna notifica inviata entro il periodo di monitoraggio. In caso contrario, per una singola consegna verrà inviato un solo avviso al giorno (alla prima occorrenza).

   Per impostazione predefinita, questa opzione è impostata una volta al giorno per tutti i criteri.

**Argomenti correlati:**

* [Registri di invio](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequenza avvisi](#alerting-frequency)
* [Icone e stati dell’attività di marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creazione di un criterio di avviso per la consegna {#creating-a-delivery-alerting-criterion}

Potete creare nuovi criteri di avviso per la consegna in base alle vostre esigenze.

Ad esempio, puoi creare un nuovo criterio che consente di inviare una notifica in cui sono elencate tutte le consegne con **[!UICONTROL Finished]** stato.

A questo scopo, è innanzitutto necessario estendere la risorsa **Consegna** e aggiungere un nuovo filtro che consenta di selezionare solo le consegne con **[!UICONTROL Finished]** stato.

1. Andate a **Adobe Campaign** > **Amministrazione** > **Sviluppo** > Risorse **** personalizzate e fate clic su **[!UICONTROL Create]**.
1. Selezionate **[!UICONTROL Extend an existing resource]**, selezionate la **[!UICONTROL Delivery]** risorsa dall’elenco a discesa e fate clic **[!UICONTROL Create]** per modificarla.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   Per ulteriori informazioni sull&#39;estensione di una risorsa esistente, consultate [Definire la risorsa](../../developing/using/creating-or-extending-the-resource.md).

1. Nella **[!UICONTROL Delivery]** risorsa, andate alla **[!UICONTROL Filter definition]** scheda e fate clic **[!UICONTROL Add an element]** per creare un filtro.

   ![](assets/delivery-alerting_new-filter.png)

1. Modificate la nuova definizione del filtro: nella **[!UICONTROL Filter definition]** finestra, trascinate l’ **[!UICONTROL Status]** elemento nell’area di lavoro e selezionatelo **[!UICONTROL Finished]** come condizione filtro.

   ![](assets/delivery-alerting_filter-status.png)

   Per ulteriori informazioni sulla creazione e la modifica di filtri personalizzati, consultate [Definire i filtri](../../developing/using/configuring-filter-definition.md).

1. Salvate le modifiche e pubblicate le risorse. For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Il filtro viene creato e ora può essere selezionato in un nuovo criterio di avviso relativo alla distribuzione.

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Delivery alerting]**, seleziona **[!UICONTROL Delivery alerting criteria]** e fai clic su **[!UICONTROL Create]**.
1. Nell’elenco a **[!UICONTROL Delivery filter applied by this criterion]** discesa, selezionate il filtro appena creato.

   ![](assets/delivery-alerting_cus-filter.png)

   Potete definire le impostazioni del criterio allo stesso modo dei criteri predefiniti. Consultate [Informazioni sui criteri](#about-alerting-criteria)di avviso.

Una volta creati, questi criteri possono essere aggiunti a una dashboard di avvisi per la consegna e ad altri criteri. Consultate [Informazioni sulle dashboard](#about-delivery-alerting-dashboards)di avvisi sulla distribuzione.

![](assets/delivery-alerting_new-criterion.png)

**Argomento correlato:**

[Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)

## Parametri di avviso sulla distribuzione {#delivery-alerting-parameters}

### Parametri dei criteri {#criteria-parameters}

Nella **[!UICONTROL Criteria parameters]** scheda di una dashboard [avvisi](#creating-a-delivery-alerting-dashboard)di distribuzione, potete definire le impostazioni applicabili ai criteri selezionati in questa dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Ad esempio, se immetti 100 in questo campo, una notifica viene inviata solo per le consegne con una destinazione pari o superiore a 100 destinatari. Questo parametro si applica a tutti i criteri.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Numero di ore prima e dopo l’ora corrente. Sono prese in considerazione solo le consegne che hanno una data di contatto in questo intervallo di tempo. Questo parametro si applica a tutti i criteri. Per impostazione predefinita, il valore di questo campo è impostato su 24 ore.

   Per ulteriori informazioni sulla data di contatto, vedere [Informazioni sulla pianificazione](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Viene inviata una notifica per tutte le consegne con un rapporto di errore soft bounce maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è impostato su 0,05 (5%).

   Per ulteriori informazioni sugli errori di rimbalzo soft, consulta Qualificazione [e](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) elenco dei tipi [](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)di consegna non riuscita.

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Viene inviata una notifica per tutte le consegne con un rapporto di errore rimbalzo rigido maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è impostato su 0,05 (5%).

   Per ulteriori informazioni sugli errori di rimbalzo rigido, consulta [Qualificazione](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) e [Elenco dei tipi](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)di consegna non riuscita.

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Viene inviata una notifica per tutte le consegne con uno **[!UICONTROL Start pending]** stato maggiore della durata specificata in questo campo, **[!UICONTROL Start pending]** stato che significa che i messaggi non sono ancora stati presi in considerazione dal sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Per il **[!UICONTROL In progress]** criterio vengono prese in considerazione solo le consegne iniziate (con **[!UICONTROL Deliveries with low throughput]** stato) per più della durata specificata.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Per il **[!UICONTROL Deliveries with low throughput]** criterio vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati inferiore alla percentuale specificata.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Per il **[!UICONTROL Deliveries with low throughput]** criterio vengono prese in considerazione solo le consegne con una velocità effettiva inferiore al valore specificato.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati superiore alla percentuale specificata.

### Frequenza avvisi {#alerting-frequency}

L&#39; **[!UICONTROL Frequency of delivery alerting]** opzione consente di definire il ritardo tra due invii di avvisi. Per impostazione predefinita, è impostata su 10 minuti.

Potete modificare questa impostazione tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

>[!NOTE]
>
>Questa opzione è valida per tutte le dashboard definite in  Adobe Campaign. Non è possibile impostare una frequenza specifica per ogni dashboard.

## Motivi di avviso sulla consegna {#delivery-alerting-reasons}

La funzione **di avviso** sulla distribuzione consente a tutti gli utenti Adobe Campaign interessati di ricevere automaticamente informazioni sullo stato di esecuzione della consegna tramite e-mail e dashboard.

Ora, quando ricevi una notifica di avviso sulla consegna, ecco alcuni suggerimenti su cosa puoi fare.

Prima di tutto, controllare la scheda **Log** della consegna per visualizzare tutte le informazioni relative alla consegna e alle prove. Le icone rosso e giallo consentono di identificare errori o avvisi. L&#39;icona rossa indica un errore critico che impedisce l&#39;avvio della consegna.

Per visualizzare la cronologia di ogni occorrenza di una consegna, selezionare la **[!UICONTROL Sending logs]** scheda. Contiene l&#39;elenco dei messaggi inviati e i relativi stati. Qui puoi controllare lo stato di consegna per ogni destinatario ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]** ecc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Di seguito sono riportati alcuni possibili motivi per ricevere le notifiche di avviso in base ai criteri soddisfatti per la consegna.

* **[!UICONTROL Deliveries failed]**: Questo criterio vi informa di tutte le consegne con stato errato. Può essere dovuto a:

   * Problema con il server di consegna (MTA, Agente di trasferimento messaggi)
   * Timeout della connessione tra il server di distribuzione Adobe Campaign  e il server di ricezione
   * Un problema di recapito
   * Flusso di lavoro errato

   Se la consegna viene attivata con un flusso di lavoro, verificate che il flusso di lavoro sia stato avviato correttamente. Per ulteriori informazioni, consultate [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md). In caso contrario, contattate il vostro amministratore  Adobe Campaign per risolvere il problema.

* **[!UICONTROL Deliveries with preparation failed]**: Un errore può verificarsi durante la preparazione della consegna nei seguenti casi:

   * Alla consegna manca un oggetto.
   * Nei campi di personalizzazione è presente una sintassi errata.
   * Destinazione mancante.
   * La consegna supera il limite di dimensioni.

   Per ulteriori informazioni, consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md). Tuttavia, questi errori vengono generalmente rilevati durante l&#39;analisi dei messaggi. Vedere [Regole](../../sending/using/control-rules.md)di controllo.

* Le possibili cause di un **[!UICONTROL Delivery with bad error ratio for soft bounces]** avviso possono essere:

   * Il server del destinatario non è attivo.
   * La cassetta postale del destinatario è piena.

   Per ulteriori informazioni, controllate le schede **[!UICONTROL Exclusion logs]** e **[!UICONTROL Exclusion causes]** i registri di consegna. Consultate [Registri](../../sending/using/monitoring-a-delivery.md#exclusion-logs)di esclusione.

   Le possibili cause di un **[!UICONTROL Delivery with bad error ratio for hard bounces]** avviso possono essere:

   * Il destinatario viene aggiunto al elenco Bloccati, il che significa che non desidera più essere contattato.
   * L&#39;indirizzo e-mail del destinatario non esiste.
   * Il dominio del destinatario non esiste.
   * Il server del destinatario sta bloccando la consegna.

   Per evitare errori di rimbalzo morbido e duro, seguite le best practice riportate di seguito:

   * Crea regole di tipologia di filtro per escludere una parte della destinazione del messaggio durante l&#39;analisi del recapito, ad esempio i destinatari in quarantena. Consultate [Creazione di una regola](../../sending/using/filtering-rules.md)di filtro.
   * Aggiornate regolarmente il database dei clienti per mantenere buoni i processi di gestione della quarantena. Consultate [Le quarantena](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * In generale, è possibile migliorare l&#39;offerta al meglio. Consultate la documentazione dettagliata sulla [distribuzione](../../sending/using/about-deliverability.md) di Adobe Campaign  e contattate il vostro amministratore Adobe Campaign  per assistenza.



* **[!UICONTROL Deliveries with long start pending]**: Solitamente ciò significa che esiste un problema a livello di agente di trasferimento messaggi (MTA). Il processo di esecuzione è in attesa della disponibilità di alcune risorse. L&#39;MTA potrebbe non essere stato avviato.

   **[!UICONTROL Deliveries with low throughput]**: Anche in questo caso si tratta di un problema di recapito, il che significa che l&#39;MTA è troppo lento.

   Per ulteriori informazioni su questi problemi, contattate il vostro amministratore  Adobe Campaign.

**Argomenti correlati:**

* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Informazioni sul consenso e diniego in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

