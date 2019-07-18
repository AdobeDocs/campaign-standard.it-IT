---
title: Ricezione degli avvisi in caso di errori
seo-title: Ricezione degli avvisi in caso di errori
description: Ricezione degli avvisi in caso di errori
seo-description: Scopri come utilizzare il sistema di gestione avvisi.
page-status-flag: never-activated
uuid: a 3 ab 733 a-e 3 db -4 adc-b 930-cd 4064 b 6 dc 1 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: monitoring-messages
discoiquuid: 0766 bd 57-c 5 f 1-4 f 56-ac 84-e 5 a 04 d 3819 ec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Receiving alerts when failures happen{#receiving-alerts-when-failures-happen}

## About delivery alerting {#about-delivery-alerting}

The **Delivery alerting** feature is an alert management system that enables a group of users to automatically receive notifications containing information on the execution of their deliveries.

Le notifiche inviate contengono un report basato per impostazione predefinita sui seguenti criteri:

* Consegne non riuscite
* Consegne con preparazione non riuscita
* Consegne con un rapporto di errore rimbalzo leggero
* Consegne con un rapporto di errore rimbalzo grave
* Consegne con stato in sospeso più lungo del solito
* Consegne con bassa velocità
* Distribuzione in corso

I destinatari degli avvisi possono monitorare le consegne elaborate da Adobe Campaign e intraprendere azioni appropriate in caso di problemi durante l'esecuzione.

Queste notifiche di avvisi possono essere personalizzate in base a criteri di avviso specifici definiti tramite un dashboard nell'interfaccia di Adobe Campaign.

>[!NOTE]
>
>Le notifiche di avviso vengono inviate solo tramite e-mail.

Le notifiche inviate contengono:

* A **[!UICONTROL Summary]** displaying the number of deliveries meeting the criteria that you defined and the label/color that you chose for each criterion.
* **[!UICONTROL Details]** Una sezione che elenca tutti i criteri di consegna definiti per il dashboard corrispondente e tutte le consegne per ogni criterio.

![](assets/delivery-alerting_notification.png)

## Delivery alerting dashboards {#delivery-alerting-dashboards}

### About delivery alerting dashboards {#about-delivery-alerting-dashboards}

Per gestire i destinatari delle notifiche, definire i criteri di avviso e accedere alla cronologia degli avvisi, devi utilizzare dashboard.

>[!NOTE]
>
>To access and configure the dashboards and the alerting criteria, you must have administration rights or appear in the **Delivery supervisors** security group. Gli utenti standard non possono accedere ai dashboard nell'interfaccia di Adobe Campaign. Possono ricevere solo le notifiche di avviso. For more on users and security in Adobe Campaign, see [Types of users](../../administration/using/types-of-users.md) and [About security groups](../../administration/using/managing-groups-and-users.md#about-security-groups).

Nell'interfaccia di Adobe Campaign puoi:

* Creazione e gestione di dashboard di avvisi. See [Creating a delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard).
* Definire e gestire i criteri di avviso relativi alla distribuzione per ogni dashboard. Ad esempio, è possibile creare avvisi basati su consegne con errori di preparazione o consegne con un solo calo. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
* Modificate i parametri dei criteri per ogni dashboard. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
* Definite un gruppo di destinatari per ogni dashboard.

   Ad esempio, desiderate informare gli utenti con diritti di amministrazione solo per le consegne non riuscite. Tuttavia, gli utenti di marketing dovranno ricevere informazioni sulle consegne con un rapporto di errore non corretto. Pertanto, è necessario creare due dashboard differenti e definire i criteri desiderati per ciascun gruppo di destinatari.

* Accedere alla cronologia di tutti gli avvisi inviati per ogni dashboard.

   Quando si seleziona una dashboard, per impostazione predefinita viene visualizzato l'ultimo avviso inviato per il dashboard. Tutti gli avvisi inviati sono elencati a sinistra della schermata. Click an item in the **[!UICONTROL History]** list to access the corresponding alerts.

![](assets/delivery-alerting_dashboard.png)

### Creating a delivery alerting dashboard {#creating-a-delivery-alerting-dashboard}

Se desiderate inviare notifiche in base a criteri specifici a diversi gruppi di utenti, dovete utilizzare più dashboard. Per creare una nuova dashboard:

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**.
1. Select **[!UICONTROL Delivery alerting dashboards]** and click **[!UICONTROL Create]**.
1. Check the **[!UICONTROL Enabled]** box to activate the current dashboard.

   Se questa opzione è disattivata, le notifiche collegate a questo dashboard non vengono più inviate. Per impostazione predefinita questa opzione è disattivata.

   ![](assets/delivery-alerting_dashboard_general.png)

1. Select the group of recipients that you want to notify from the **[!UICONTROL Alert group]** drop-down list. To modify or create a group, see [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users).
1. From the **[!UICONTROL Delivery alerting criteria]** section, click **[!UICONTROL Create element]** to add criteria. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).
1. Select the **[!UICONTROL Edit properties]** button. In the **[!UICONTROL Criteria parameters]** tab, define how the criteria will be applied. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).
1. Click **[!UICONTROL Create]** to save the dashboard.

Ogni volta che una consegna soddisfa i criteri definiti in questo dashboard, viene inviata una notifica di avviso al gruppo di utenti specificato.

## Delivery alerting criteria {#delivery-alerting-criteria}

### About alerting criteria {#about-alerting-criteria}

To access the delivery alerting criteria, go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]** and select **[!UICONTROL Delivery alerting criteria]**.

![](assets/delivery-alerting_criteria.png)

I criteri seguenti possono essere utilizzati nelle dashboard di avvisi di distribuzione:

* **[!UICONTROL Deliveries failed]**: Qualsiasi consegna pianificata entro un intervallo definito, con stato errato.
* **[!UICONTROL Deliveries with preparation failed]**: Qualsiasi distribuzione modificata entro un intervallo definito, per cui il passaggio della preparazione (calcolo target e generazione contenuto) non è riuscito. For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md).
* **[!UICONTROL Delivery with bad error ratio for soft bounces]**: Qualsiasi consegna pianificata entro un intervallo definito, con uno stato, con **[!UICONTROL In progress]** un rapporto di errore rimbalzo leggero maggiore di una percentuale definita.
* **[!UICONTROL Delivery with bad error ratio for hard bounces]**: Qualsiasi consegna pianificata entro un intervallo definito, con uno stato, con **[!UICONTROL In progress]** un rapporto di errore rimbalzo netto maggiore di una percentuale definita.
* **[!UICONTROL Deliveries with long start pending]**: Qualsiasi consegna pianificata entro un intervallo definito, con **[!UICONTROL Start pending]** uno stato per più di una durata definita, **[!UICONTROL Start pending]** con lo stato che i messaggi non sono stati ancora considerati dal sistema.
* **[!UICONTROL Deliveries with low throughput]**: Qualsiasi distribuzione avviata per più di una durata definita, con minore di una percentuale definita di messaggi elaborati, con una velocità inferiore a un valore definito.
* **[!UICONTROL Deliveries in progress]**: Qualsiasi consegna pianificata entro un intervallo definito, con **[!UICONTROL In progress]** lo stato.

>[!NOTE]
>
>Tutti i parametri applicati ai criteri indicati sopra presentano valori predefiniti. These values can be changed in the **[!UICONTROL Criteria parameters]** tab of the delivery alerting dashboards. See [Criteria parameters](../../sending/using/receiving-alerts-when-failures-happen.md#criteria-parameters).

You can select any item from the **[!UICONTROL Delivery alerting criteria]** list to access its details.

![](assets/delivery-alerting_criteria_definition.png)

Per ogni criterio potete definire le seguenti impostazioni:

* **[!UICONTROL Indicators to add in alerts]**, ovvero le colonne che verranno visualizzate nella **[!UICONTROL Details]** sezione della notifica per le consegne corrispondenti al criterio selezionato.

   ![](assets/delivery-alerting_notification_colums.png)

* **[!UICONTROL Alert type]**, cioè l'etichetta e il colore che saranno visualizzati accanto al criterio di consegna nel riepilogo della notifica.

   ![](assets/delivery-alerting_notification_labels.png)

* **[!UICONTROL Criteria frequency]**: Se viene soddisfatto un criterio per una consegna, questo viene ripetuto in ogni notifica inviata entro il periodo di monitoraggio. In caso contrario, viene inviato un solo avviso al giorno (sulla prima occorrenza) tramite criterio di avviso.

   Per impostazione predefinita, questa opzione è impostata una volta al giorno per tutti i criteri.

**Argomenti correlati:**

* [Invio di registri](../../sending/using/monitoring-a-delivery.md#sending-logs)
* [Frequenza avvisi](../../sending/using/receiving-alerts-when-failures-happen.md#alerting-frequency)
* [Icone e stati di attività di marketing](../../start/using/marketing-activities.md#marketing-activity-icons-and-statuses)

### Creating a delivery alerting criterion {#creating-a-delivery-alerting-criterion}

È possibile creare nuovi criteri di avviso sulla distribuzione per soddisfare meglio le esigenze.

For example, you can create a new criterion enabling to send a notification listing all deliveries with a **[!UICONTROL Finished]** status.

To do this, you first need to extend the **Delivery** resource and add a new filter allowing you to select only the deliveries with a **[!UICONTROL Finished]** status.

1. Go to **Adobe Campaign** &gt; **Administration** &gt; **Development** &gt; **Custom resources** and click **[!UICONTROL Create]**.
1. Select **[!UICONTROL Extend an existing resource]**, select the **[!UICONTROL Delivery]** resource from the drop-down list and click **[!UICONTROL Create]** to edit it.

   ![](assets/delivery-alerting_extend-delivery-cus.png)

   For more on extending an existing resource, see [Define the resource](../../developing/using/creating-or-extending-the-resource.md).

1. In the **[!UICONTROL Delivery]** resource, go to the **[!UICONTROL Filter definition]** tab and click **[!UICONTROL Add an element]** to create a filter.

   ![](assets/delivery-alerting_new-filter.png)

1. Edit the new filter definition: in the **[!UICONTROL Filter definition]** window, drag and drop the **[!UICONTROL Status]** item into the workspace and select **[!UICONTROL Finished]** as the filter condition.

   ![](assets/delivery-alerting_filter-status.png)

   For more on creating and editing custom filters, see [Define filters](../../developing/using/configuring-filter-definition.md).

1. Salvate le modifiche e pubblicate le risorse. For more on this, see [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   Il filtro viene creato e ora può essere selezionato in un nuovo criterio di avviso sulla distribuzione.

1. Go to **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Delivery alerting]**, select **[!UICONTROL Delivery alerting criteria]** and click **[!UICONTROL Create]**.
1. In the **[!UICONTROL Delivery filter applied by this criterion]** drop-down list, select the filter that you just created.

   ![](assets/delivery-alerting_cus-filter.png)

   Potete definire le impostazioni del criterio come per i criteri predefiniti. See [About alerting criteria](../../sending/using/receiving-alerts-when-failures-happen.md#about-alerting-criteria).

Una volta creati, questi criteri possono essere aggiunti a un dashboard di avvisi sulla distribuzione e ad altri criteri. See [About delivery alerting dashboards](../../sending/using/receiving-alerts-when-failures-happen.md#about-delivery-alerting-dashboards).

![](assets/delivery-alerting_new-criterion.png)

**Argomento correlato:**

[Aggiunta o estensione di una risorsa](../../developing/using/key-steps-of-adding-a-resource.md)

## Delivery alerting parameters {#delivery-alerting-parameters}

### Criteria parameters {#criteria-parameters}

In the **[!UICONTROL Criteria parameters]** tab of a [delivery alerting dashboard](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-dashboard), you can define the settings that apply to the criteria selected in this dashboard.

![](assets/delivery-alerting_dashboard_criteria-parameters.png)

* **[!UICONTROL Delivery target minimum size]**: Ad esempio, se immetti 100 in questo campo, una notifica viene inviata solo per le consegne con una destinazione pari o superiore a 100 destinatari. Questo parametro si applica a tutti i criteri.
* **[!UICONTROL Monitoring period before and after the contact date (in hours)]**: Numero di ore prima e dopo l'ora corrente. Sono considerate solo le consegne con data di contatto in questo intervallo di tempo. Questo parametro si applica a tutti i criteri. Per impostazione predefinita, il valore di questo campo è impostato su 24 ore.

   For more information on the contact date, see [About the scheduling](../../sending/using/about-scheduling-messages.md).

* **[!UICONTROL Maximum ratio of soft bounce errors]**: Una notifica viene inviata per tutte le consegne con un rapporto di errore di rimbalzo leggero maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è impostato su 0.05 (5%).

   For more on soft bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Maximum ratio of hard bounce errors]**: Una notifica viene inviata per tutte le consegne con un rapporto di errore rimbalzo deciso maggiore del valore specificato. Per impostazione predefinita, il valore di questo campo è impostato su 0.05 (5%).

   For more on hard bounce errors, see [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification) and [List of delivery failure types](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

* **[!UICONTROL Minimum time threshold for delivery in 'Start pending' status (in minutes)]**: Una notifica viene inviata per tutte le consegne con **[!UICONTROL Start pending]** uno stato oltre la durata specificata in questo campo, **[!UICONTROL Start pending]** lo stato implica che i messaggi non sono stati ancora considerati dal sistema.
* **[!UICONTROL Minimum time required for the computation of the throughput (in minutes)]**: Per il criterio vengono prese in considerazione solo le consegne avviate (con **[!UICONTROL In progress]** stato) per più della durata **[!UICONTROL Deliveries with low throughput]** specificata.
* **[!UICONTROL Maximum percentage of processed messages for the computation of the throughput]**: Per il **[!UICONTROL Deliveries with low throughput]** criterio vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati inferiori alla percentuale specificata.
* **[!UICONTROL Minimum expected throughput (in sent messages per hour)]**: Per il **[!UICONTROL Deliveries with low throughput]** criterio vengono prese in considerazione solo le consegne con una velocità inferiore al valore specificato.
* **[!UICONTROL Minimum processed ratio required for 'Deliveries in progress' criterion]**: Vengono prese in considerazione solo le consegne con una percentuale di messaggi elaborati superiori alla percentuale specificata.

### Alerting frequency {#alerting-frequency}

The **[!UICONTROL Frequency of delivery alerting]** option allows to define the delay between two alert sendings. Per impostazione predefinita, è impostata su 10 minuti.

You can change this setting through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

>[!NOTE]
>
>Questa opzione si applica a tutte le dashboard definite in Adobe Campaign. Non potete impostare una frequenza specifica per ogni dashboard.

## Delivery alerting reasons {#delivery-alerting-reasons}

The **Delivery alerting** feature keeps all of your involved Adobe Campaign users automatically informed about the delivery execution status, via email and dashboard.

Ora che ricevi una notifica di avviso sulla distribuzione, ecco alcuni suggerimenti sulle operazioni che puoi eseguire.

First of all, check the delivery's **Log** tab to view all information relating to the delivery and proofs. Le icone rosso e giallo consentono di identificare errori o avvertenze. L'icona rossa indica un errore critico che impedisce l'avvio della distribuzione.

To view the history of every occurrence of a delivery, select the **[!UICONTROL Sending logs]** tab. Contiene l'elenco dei messaggi inviati e dei relativi stati. There you can check the delivery status for each recipient ( **[!UICONTROL Sent]**, **[!UICONTROL Pending]**, **[!UICONTROL Failed]**, etc.). For more on this, see [Sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Di seguito sono riportati alcuni motivi possibili per ricevere notifiche di avviso in base ai criteri soddisfatti per una consegna.

* **[!UICONTROL Deliveries failed]**: Questo criterio vi informerà di tutte le consegne con stato errato. Può essere dovuto a:

   * Un problema con il server di consegna (MTA, Message Transfer Agent)
   * Un orario di connessione tra il server di consegna Adobe Campaign e il server ricevente
   * Un problema di consegna
   * Un flusso di lavoro errato
   Se la consegna viene attivata con un flusso di lavoro, verificate che il flusso di lavoro sia stato avviato correttamente. For more on this, see [Executing a workflow](../../automating/using/executing-a-workflow.md). In caso contrario, contattate l'amministratore di Adobe Campaign per risolvere il problema.

* **[!UICONTROL Deliveries with preparation failed]**: Si può verificare un errore durante la preparazione della distribuzione nei casi seguenti:

   * Alla consegna manca un oggetto.
   * Nei campi di personalizzazione è presente una sintassi errata.
   * La destinazione è mancante.
   * La distribuzione eccede il limite di dimensione.
   For more on this, see [Preparing the send](../../sending/using/preparing-the-send.md). Tuttavia, questi errori sono generalmente rilevati durante l'analisi dei messaggi. See [Control rules](../../administration/using/control-rules.md).

* The possible causes for a **[!UICONTROL Delivery with bad error ratio for soft bounces]** alert can be:

   * Il server del destinatario è guasto.
   * La casella postale del destinatario è piena.
   For more information, check the **[!UICONTROL Exclusion logs]** and **[!UICONTROL Exclusion causes]** tabs of the delivery logs. See [Exclusion logs](../../sending/using/monitoring-a-delivery.md#exclusion-logs).

   The possible causes for a **[!UICONTROL Delivery with bad error ratio for hard bounces]** alert can be:

   * Il destinatario è in lista nera, ovvero non desidera più essere contattato.
   * L'indirizzo e-mail del destinatario non esiste.
   * Il dominio del destinatario non esiste.
   * Il server del destinatario sta bloccando la consegna.
   Per evitare errori di rimbalzo netti e netti, seguite le procedure ottimali di seguito:

   * Create regole di filtraggio per escludere una parte della destinazione del messaggio durante l'analisi della consegna, ad esempio i destinatari in quarantena. See [Creating a filtering rule](../../administration/using/filtering-rules.md).
   * Aggiornate regolarmente il database dei clienti per mantenere buoni processi di gestione delle quarantena. See [About quarantines](../../sending/using/understanding-quarantine-management.md#about-quarantines).
   * In generale, migliorate il rendimento in modo ottimale. See the Adobe Campaign v7 [Managing deliverability](http://docs.campaign.adobe.com/doc/AC/getting_started/EN/deliverability.html) detailed guide and contact your Adobe Campaign administrator for assistance.



* **[!UICONTROL Deliveries with long start pending]**: In genere si verifica un problema a livello di MTA (Message Transfer Agent). Il processo di esecuzione è in attesa della disponibilità di alcune risorse. L'MTA potrebbe non essere stato avviato.

   **[!UICONTROL Deliveries with low throughput]**: Anche se si tratta di un problema di consegna, l'MTA è troppo lento.

   Per ulteriori informazioni, contatta l'amministratore di Adobe Campaign.

**Argomenti correlati:**

* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Gestione della gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

