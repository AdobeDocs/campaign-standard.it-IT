---
title: Riconoscimento della gestione della quarantena
description: Scopri come ottimizzare la tua recapito con la gestione della quarantena.
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7e361d10d039718c421a3684c518347af2be951

---


# Riconoscimento della gestione della quarantena{#understanding-quarantine-management}

## Informazioni sulle quarantena {#about-quarantines}

È possibile mettere in quarantena un indirizzo e-mail o un numero di telefono, ad esempio, quando la cassetta postale è piena o se l&#39;indirizzo non esiste.

In ogni caso, la procedura di quarantena è conforme alle norme specifiche descritte nella presente [sezione](#conditions-for-sending-an-address-to-quarantine).

### Ottimizzazione della distribuzione tramite quarantena {#optimizing-your-delivery-through-quarantines}

I profili i cui indirizzi e-mail o numero di telefono si trovano in quarantena vengono automaticamente esclusi durante la preparazione dei messaggi (vedere [Identificazione degli indirizzi in quarantena per una consegna](#identifying-quarantined-addresses-for-a-delivery)). Ciò velocizzerà le consegne, poiché il tasso di errore ha un effetto significativo sulla velocità di consegna.

Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. Quarantine consente quindi di evitare la blacklist da parte di questi fornitori.

Inoltre, le quarantena contribuiscono a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

Per ulteriori informazioni sulle best practice per proteggere e ottimizzare le consegne, consulta [questa pagina](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantena e blacklist {#quarantine-vs-blacklisting}

**La quarantena** si applica solo a un indirizzo, non al profilo stesso. Ciò significa che, se due profili hanno lo stesso indirizzo e-mail, saranno entrambi interessati se l&#39;indirizzo viene messo in quarantena.

Allo stesso modo, un profilo il cui indirizzo e-mail è stato messo in quarantena potrebbe aggiornare il profilo e immettere un nuovo indirizzo, e potrebbe quindi essere nuovamente indirizzato mediante azioni di consegna.

**L&#39;inserimento in blacklist**, invece, impedisce al profilo di essere più mirato da una consegna, ad esempio dopo l&#39;annullamento dell&#39;iscrizione (opzione di rifiuto). Per ulteriori informazioni sul processo di creazione della blacklist, consulta [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Quando un utente risponde a un messaggio SMS con una parola chiave come &quot;STOP&quot; al fine di rifiutare le consegne degli SMS, il suo profilo non viene inserito in blacklist come nel processo di rifiuto delle e-mail. Il numero di telefono del profilo viene inviato alla quarantena con lo **[!UICONTROL Blacklisted]** stato. Questo stato si riferisce solo al numero di telefono, il profilo non viene inserito in blacklist in modo che l&#39;utente continui a ricevere i messaggi e-mail. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identificazione degli indirizzi in quarantena {#identifying-quarantined-addresses}

Gli indirizzi in quarantena possono essere elencati per una consegna specifica o per l&#39;intera piattaforma.

>[!NOTE]
>
>Per rimuovere un indirizzo dalla quarantena, contattare l’amministratore tecnico.

### Identificazione di indirizzi in quarantena per una consegna {#identifying-quarantined-addresses-for-a-delivery}

Gli indirizzi in quarantena per una consegna specifica sono elencati durante la fase di preparazione della consegna, nella **[!UICONTROL Exclusion logs]** scheda del dashboard di consegna (vedere [questa sezione](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificazione degli indirizzi in quarantena per l’intera piattaforma {#identifying-quarantined-addresses-for-the-entire-platform}

Gli amministratori possono elencare gli indirizzi in quarantena per l&#39;intera piattaforma dal **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>Questo menu elenca gli elementi in quarantena per i canali di **e-mail**, **SMS** e notifiche **** push.

![](assets/quarantines1.png)

>[!NOTE]
>
>L&#39;aumento delle quarantena è un effetto normale, legato all&#39;usura del database. Ad esempio, se la durata di un indirizzo e-mail è considerata di tre anni e la tabella del destinatario aumenta del 50% ogni anno, l’aumento delle quarantena può essere calcolato come segue: Fine anno 1: (1*0.33)/(1+0.5)=22%. Fine anno 2: ((1.22*0.33)+0.33)/(1.5+0.75)=32,5%.

## Condizioni per l&#39;invio di un indirizzo alla quarantena {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign gestisce la quarantena in base al tipo di consegna non riuscita e al motivo assegnato durante la qualifica dei messaggi di errore (consultate Tipi di [consegna non riuscita e motivi](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) e qualificazione [della posta](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)rimbalzata).

* **Errore** ignorato: gli errori ignorati non inviano un indirizzo alla quarantena.
* **Errore** rigido: l&#39;indirizzo e-mail corrispondente viene inviato immediatamente alla quarantena.
* **Errore** temporaneo: gli errori software non inviano immediatamente un indirizzo alla quarantena, ma incrementano un contatore di errori. Quando il contatore di errori raggiunge la soglia limite, l&#39;indirizzo viene messo in quarantena. Nella configurazione predefinita, la soglia è impostata su cinque errori, dove due errori sono significativi se si verificano almeno 24 ore di differenza. L&#39;indirizzo viene messo in quarantena al quinto errore. È possibile modificare la soglia del contatore di errori. Per ulteriori informazioni, consultare questa [pagina](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Quando una consegna ha esito positivo dopo un nuovo tentativo, viene reinizializzato il contatore di errori dell&#39;indirizzo precedente a quello messo in quarantena. Lo stato dell’indirizzo cambia in **[!UICONTROL Valid]** e viene eliminato dall’elenco delle quarantena dopo due giorni dal **[!UICONTROL Database cleanup]** flusso di lavoro.

Se un utente qualifica un&#39;e-mail come spam (**Feedback loop**), il messaggio viene automaticamente reindirizzato verso una cassetta postale tecnica gestita da Campaign. L&#39;indirizzo e-mail dell&#39;utente viene quindi inviato automaticamente in quarantena con lo **[!UICONTROL Blacklisted]** stato . Questo stato si riferisce solo all&#39;indirizzo, il profilo non viene inserito in blacklist, in modo che l&#39;utente continui a ricevere messaggi SMS e notifiche push.

>[!NOTE]
In Adobe Campaign la quarantena fa distinzione tra maiuscole e minuscole. Accertatevi di importare gli indirizzi e-mail in lettere maiuscole, in modo che non vengano ritirati in un secondo momento.

Nell&#39;elenco degli indirizzi in quarantena (vedere [Identificazione degli indirizzi in quarantena per l&#39;intera piattaforma](#identifying-quarantined-addresses-for-the-entire-platform)), il **[!UICONTROL Error reason]** campo indica il motivo per cui l&#39;indirizzo selezionato è stato messo in quarantena.

![](assets/quarantines2.png)

