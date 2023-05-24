---
title: Informazioni sulla gestione della quarantena
description: Scopri come ottimizzare le consegne e-mail con la gestione della quarantena.
audience: sending
content-type: reference
topic-tags: monitoring-messages
feature: Deliverability
role: User
level: Intermediate
exl-id: ed269751-78ab-4189-89d9-116bf42c0c90
source-git-commit: eec8c66d4947e04cd0eb3dcf0f09d395d9db68b9
workflow-type: tm+mt
source-wordcount: '1429'
ht-degree: 24%

---

# Informazioni sulla gestione della quarantena{#understanding-quarantine-management}

## Informazioni sulla quarantena {#about-quarantines}

È possibile mettere in quarantena un indirizzo e-mail o un numero di telefono, ad esempio, quando la casella di posta è piena o se l’indirizzo non esiste.

In ogni caso, la procedura di quarantena è conforme alle regole specifiche descritte nella presente [sezione](#conditions-for-sending-an-address-to-quarantine).

### Ottimizzazione della consegna tramite quarantena {#optimizing-your-delivery-through-quarantines}

I profili con indirizzi e-mail o numeri di telefono in quarantena vengono automaticamente esclusi durante la preparazione dei messaggi (vedi [Identificazione degli indirizzi messi in quarantena per una consegna](#identifying-quarantined-addresses-for-a-delivery)). In questo modo le consegne sono più rapide, poiché il tasso di errore ha un effetto significativo sulla velocità di consegna.

Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. La quarantena consente quindi di evitare di essere aggiunti al elenco Bloccati da parte di questi provider.

Inoltre, le quarantene contribuiscono a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

Per ulteriori informazioni sulle best practice per proteggere e ottimizzare le consegne, consulta [questa pagina](../../sending/using/delivery-best-practices.md).

### Quarantena e Inserisco nell&#39;elenco Bloccati di {#quarantine-vs-denylist}

Elenco Bloccati La quarantena e il non si applicano allo stesso oggetto:

* **Quarantena** si applica solo a un **indirizzo** (o numero di telefono, ecc.), non al profilo stesso. Ad esempio, un profilo con un indirizzo e-mail messo in quarantena potrebbe aggiornare il profilo e immettere un nuovo indirizzo, per poi essere nuovamente indirizzato mediante azioni di consegna. Allo stesso modo, se due profili hanno lo stesso numero di telefono, saranno entrambi interessati se il numero viene messo in quarantena.

   Gli indirizzi o i numeri di telefono in quarantena vengono visualizzati nel [registri di esclusione](#identifying-quarantined-addresses-for-a-delivery) (per una consegna) o nella [elenco di quarantena](#identifying-quarantined-addresses-for-the-entire-platform) (per l’intera piattaforma).

* Essere sul **inserisco nell&#39;elenco Bloccati**, dall&#39;altro, darà luogo al **profilo** non sono più oggetto della consegna, ad esempio dopo l’annullamento dell’abbonamento (rinuncia) per un determinato canale. Ad esempio, se un profilo nella inserisce nell&#39;elenco Bloccati di invio del canale e-mail presenta due indirizzi e-mail, entrambi gli indirizzi verranno esclusi dalla consegna. Per ulteriori informazioni sulla procedura di inserisce nell&#39;elenco Bloccati del, consulta [Informazioni su consenso e rinuncia in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

   Puoi verificare se un profilo si trova nel inserisco nell&#39;elenco Bloccati di per uno o più canali nel **[!UICONTROL No longer contact (on denylist)]** sezione del profilo di **[!UICONTROL General]** scheda. Vedi [questa sezione](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

>[!NOTE]
>
>La quarantena include un **Elenco Bloccati Il** stato, che si applica quando i destinatari segnalano il messaggio come spam o rispondono a un messaggio SMS con una parola chiave come &quot;STOP&quot;. In tal caso, l’indirizzo o il numero di telefono del profilo viene messo in quarantena con il **[!UICONTROL On denylist]** stato. Per ulteriori informazioni sulla gestione dei messaggi STOP SMS, consulta [questa sezione](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

&lt;!: quando un utente risponde a un messaggio SMS con una parola chiave come STOP per rifiutare le consegne SMS, il suo profilo non viene aggiunto al elenco Bloccati di gestione delle e-mail come nel processo di rinuncia alle e-mail. Il numero di telefono del profilo viene messo in quarantena con **[!UICONTROL On denylist]** stato. Questo stato si riferisce solo al numero di telefono, il che significa che il profilo continuerà a ricevere messaggi e-mail.<!-- Also, if the profile has another phone number, he can still receive SMS messages on the other number. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).-->

## Identificazione degli indirizzi messi in quarantena {#identifying-quarantined-addresses}

Gli indirizzi in quarantena possono essere visualizzati per una consegna specifica o per l’intera piattaforma.

<!--
If you need to remove an address from quarantine, contact your technical administrator.
-->

### Identificazione di indirizzi messi in quarantena per una consegna {#identifying-quarantined-addresses-for-a-delivery}

Gli indirizzi in quarantena per una consegna specifica vengono elencati durante la fase di preparazione della consegna, nella scheda **[!UICONTROL Exclusion logs]** del dashboard di consegna (vedi [questa sezione](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Per ulteriori informazioni sulla preparazione della consegna, consulta [questa sezione](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificazione degli indirizzi messi in quarantena per l’intera piattaforma {#identifying-quarantined-addresses-for-the-entire-platform}

Gli amministratori possono accedere all’elenco dettagliato degli indirizzi e-mail messi in quarantena per l’intera piattaforma da **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

<!--
This menu lists quarantined elements for **Email**, **SMS** and **Push notification** channels.
-->

![](assets/quarantines1.png)

>[!NOTE]
>
>L’aumento del numero di quarantene è un effetto normale, legato all’&quot;usura&quot; del database. Ad esempio, se la durata di un indirizzo e-mail è considerata di tre anni e la tabella del destinatario aumenta del 50% ogni anno, l’aumento delle quarantene può essere calcolato come segue: fine anno 1: (1&#42;0,33)/(1+0,5)=22%. Fine anno 2: ((1,22&#42;0,33)+0,33)/(1,5+0,75)=32,5%.

Sono disponibili filtri per aiutarti a sfogliare l’elenco. Puoi filtrare in base all’indirizzo, allo stato e/o al canale.

![](assets/quarantines-filters.png)

Puoi modificare o [eliminare](#removing-a-quarantined-address) ogni voce, nonché crearne di nuove.

Per modificare una voce, fai clic sulla riga corrispondente e modifica i campi in base alle esigenze.

![](assets/quarantines-edit.png)

Per aggiungere manualmente una nuova voce, utilizzare **[!UICONTROL Create]** pulsante.

![](assets/quarantines-create-button.png)

Definisci l’indirizzo (o il numero di telefono, ecc.) e tipo di canale. È possibile impostare uno stato per l&#39;inserimento nell&#39;elenco di quarantena e un motivo di errore. È inoltre possibile indicare la data in cui si è verificato l&#39;errore, il numero di errori e immettere il testo dell&#39;errore. Se necessario, seleziona dall’elenco a discesa l’ultima consegna inviata all’indirizzo.

![](assets/quarantines-create-last-delivery.png)

## Rimozione di un indirizzo dalla quarantena {#removing-a-quarantined-address}

### Aggiornamenti automatici {#unquarantine-auto}

Gli indirizzi che corrispondono a condizioni specifiche vengono automaticamente eliminati dall’elenco di quarantena dal flusso di lavoro di pulizia del database. Per ulteriori informazioni sui flussi di lavoro tecnici, consulta [questa sezione](../../administration/using/technical-workflows.md#list-of-technical-workflows).

Gli indirizzi vengono rimossi automaticamente dall’elenco di quarantena nei seguenti casi:

* Indirizzi in una **[!UICONTROL Erroneous]** Lo stato verrà rimosso dall’elenco di quarantena dopo una consegna riuscita.
* Indirizzi in una **[!UICONTROL Erroneous]** Lo stato verrà rimosso dall’elenco di quarantena se l’ultimo messaggio non recapitato si è verificato più di 10 giorni fa. Per ulteriori informazioni sulla gestione degli errori soft, consulta [questa sezione](#soft-error-management).
* Indirizzi in una **[!UICONTROL Erroneous]** stato non restituito con **[!UICONTROL Mailbox full]** L’errore verrà rimosso dall’elenco di quarantena dopo 30 giorni.

Il loro stato diventa quindi **[!UICONTROL Valid]**.

Numero massimo di tentativi da eseguire in caso di **[!UICONTROL Erroneous]** Lo stato e il ritardo minimo tra i nuovi tentativi si basano ora sulle prestazioni di un IP sia storicamente che attualmente in un determinato dominio.


>[!IMPORTANT]
>
>Destinatari con un indirizzo in una **[!UICONTROL Quarantine]** o **[!UICONTROL Denylisted]** non vengono mai rimossi, anche se ricevono un’e-mail.


### Aggiornamenti manuali {#unquarantine-manual}

È inoltre possibile rimuovere manualmente la quarantena di un indirizzo.  Per rimuovere manualmente un indirizzo dall’elenco di quarantena, è possibile rimuoverlo dall’elenco o modificarne lo stato in **[!UICONTROL Valid]**.

* Seleziona l’indirizzo da **[!UICONTROL Administration > Channels > Quarantines > Addresses]** elenca e seleziona **[!UICONTROL Delete element]**.

   ![](assets/quarantine-delete-address.png)

* Seleziona un indirizzo e modificane le impostazioni **[!UICONTROL Status]** a **[!UICONTROL Valid]**.

   ![](assets/quarantine-valid-status.png)


### Aggiornamenti in blocco {#unquarantine-bulk}

Potrebbe essere necessario eseguire aggiornamenti in blocco sull’elenco di quarantena, ad esempio in caso di interruzione del servizio dell’ISP. In questo caso, le e-mail vengono erroneamente contrassegnate come mancate consegne perché non possono essere consegnate correttamente al destinatario. Questi indirizzi devono essere rimossi dall’elenco di quarantena.

Per eseguire questa operazione, crea un flusso di lavoro e aggiungi un **[!UICONTROL Query]** attività nella tabella di quarantena per filtrare tutti i destinatari interessati. Una volta identificate, possono essere rimosse dall’elenco di quarantena e incluse nelle consegne e-mail future di Campaign.

In base alla tempistica dell’incidente, di seguito sono riportate le linee guida consigliate per questa query.

* **Testo di errore (testo di quarantena)** contiene &quot;550-5.1.1&quot; E **Testo di errore (testo di quarantena)** contiene &quot;support.ISP.com&quot;

   dove &quot;support.ISP.com&quot; può essere: &quot;support.apple.com&quot; o &quot;support.google.com&quot;, ad esempio

* **Stato aggiornamento (@lastModified)** il o dopo il GG/MM/AAAA HH:MM:SS AM
* **Stato aggiornamento (@lastModified)** entro il GG/MM/AAAA HH:MM:SS PM

Dopo aver visualizzato l’elenco dei destinatari interessati, aggiungi un **[!UICONTROL Update data]** per impostare lo stato del loro indirizzo e-mail su **[!UICONTROL Valid]** in modo che vengano rimossi dall’elenco di quarantena dal **[!UICONTROL Database cleanup]** flusso di lavoro. Puoi anche semplicemente eliminarli dalla tabella di quarantena.

## Condizioni per la messa in quarantena di un indirizzo {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign gestisce la quarantena in base al tipo di consegna non riuscita e al motivo assegnato durante la qualifica dei messaggi di errore (consulta [Tipi di consegna non riuscita e motivi](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) e [Qualifica delle e-mail non recapitate](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Errore ignorato**: gli errori ignorati non mettono un indirizzo in quarantena.
* **Errore rigido**: l’indirizzo e-mail corrispondente viene messo immediatamente in quarantena.
* **Errore morbido**: gli errori morbidi non mettono immediatamente un indirizzo in quarantena, ma incrementano un contatore di errori. Per ulteriori informazioni, consulta [Gestione degli errori morbidi](#soft-error-management).

   <!--
  When the error counter reaches the limit threshold, the address goes into quarantine. In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error. The error counter threshold can be modified. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).
  When a delivery is successful after a retry, the error counter of the address which was prior to that quarantined is reinitialized. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.
  -->

Se un utente qualifica un’e-mail come spam ([ciclo di feedback](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#feedback-loops)), il messaggio viene automaticamente reindirizzato a una casella di posta tecnica gestita da Adobe. L’indirizzo e-mail dell’utente viene quindi messo automaticamente in quarantena con lo stato **[!UICONTROL On denylist]**. Questo stato si riferisce solo all’indirizzo, il profilo non è nel inserisco nell&#39;elenco Bloccati di, in modo che l’utente continui a ricevere messaggi SMS e notifiche push.

>[!NOTE]
>
>In Adobe Campaign la quarantena distingue tra maiuscole e minuscole. Accertati di importare gli indirizzi e-mail in lettere minuscole, in modo che non vengano reindirizzate in un secondo momento.

Nell’elenco degli indirizzi messi in quarantena (vedi [Identificazione degli indirizzi messi in quarantena per l’intera piattaforma](#identifying-quarantined-addresses-for-the-entire-platform)), il campo **[!UICONTROL Error reason]** indica per quale motivo l’indirizzo selezionato è stato messo in quarantena.

![](assets/quarantines2.png)

### Gestione degli errori morbidi {#soft-error-management}

Al contrario degli errori rigidi, gli errori morbidi non mettono immediatamente un indirizzo in quarantena, ma incrementano un contatore di errori.

I tentativi verranno eseguiti durante il [durata della consegna](../../administration/using/configuring-email-channel.md#validity-period-parameters). Quando il contatore di errori raggiunge la soglia limite, l’indirizzo viene messo in quarantena. Per ulteriori informazioni, consulta [Tentativi dopo un errore temporaneo di consegna](understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--In the default configuration, the threshold is set at five errors, where two errors are significant if they occur at least 24 hours apart. The address is placed in quarantine at the fifth error.
The error counter threshold can be modified.-->

Il contatore degli errori viene reinizializzato se l&#39;ultimo errore significativo si è verificato più di 10 giorni fa. Lo stato dell’indirizzo diventa quindi **Valido** e viene cancellato dall’elenco delle quarantene dal **Database cleanup** flusso di lavoro. (Per ulteriori informazioni sui flussi di lavoro tecnici, consulta [questa sezione](../../administration/using/technical-workflows.md#list-of-technical-workflows).)
