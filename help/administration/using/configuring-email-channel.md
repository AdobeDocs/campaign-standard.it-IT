---
title: Configurazione del canale e-mail in Adobe Campaign Standard
description: Scopri come configurare il canale e-mail in Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 9fddb655-b445-41f3-9b02-5d356fc88aa1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3752d41f-8c59-4fad-b30f-e98e09cd74a8
context-tags: extAccountEmail,overview;emailConfig,main;ruleSet,overview;delivery,properties,open
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e2303055b3370efab204adbdb1b9f567a555a23f
workflow-type: tm+mt
source-wordcount: '2331'
ht-degree: 0%

---


# Configurazione del canale e-mail{#configuring-email-channel}

In qualità di [amministratore](../../administration/using/users-management.md#functional-administrators)di Campaign, puoi configurare le impostazioni dei canali e-mail. Queste impostazioni avanzate includono parametri generali del canale e-mail, account di routing e-mail, regole di elaborazione e-mail e proprietà e-mail. In questa pagina verrà illustrato come modificare i valori predefiniti per l&#39;e-mail generale e i parametri di invio.

Tenete presente che alcune impostazioni e-mail ora sono gestite dall&#39;MTA avanzato di Adobe Campaign. Pertanto:
* Alcune configurazioni nell&#39;interfaccia utente di Campaign non sono più applicate:
   * Le **[!UICONTROL Retries]** impostazioni nel menu [](#email-channel-parameters) Configurazione e nei parametri [](#retries-parameters) Invio delle proprietà e-mail.
   * Le regole **[!UICONTROL MX management]** e **[!UICONTROL Domain management]** le regole nel menu [Regole di elaborazione e-](#email-processing-rules)mail.

* Altri parametri sono ora gestiti parzialmente da Enhanced MTA, mentre alcune configurazioni possono ancora essere eseguite all&#39;interno di Campaign. Le impostazioni interessate sono le seguenti:
   * Il **[!UICONTROL Message delivery duration]** parametro nel **[!UICONTROL Configuration]** menu. Per ulteriori informazioni, consulta [questa sezione](#email-channel-parameters).
   * Il parametro **[!UICONTROL Delivery duration]** o **[!UICONTROL Validity limit for sending messages]** nella **[!UICONTROL Validity period]** sezione. Per ulteriori informazioni, consulta [questa sezione](#validity-period-parameters).
   * Le **[!UICONTROL Bounce mails]** regole nel **[!UICONTROL Email processing rules]**. Per ulteriori informazioni, consulta [questa sezione](#email-processing-rules).

## Parametri canale e-mail {#email-channel-parameters}

La schermata di configurazione e-mail consente di definire i parametri per il canale e-mail. Gli amministratori possono accedere a queste configurazioni nel **[!UICONTROL Administration]>[!UICONTROL Channels]>[!UICONTROL Email]>[!UICONTROL Configuration]**menu.

![](assets/channels_1.png)

* **Campi maschere autorizzati**

   La **[!UICONTROL Header parameters of sent emails]** sezione elenca gli indirizzi e-mail autorizzati che potete utilizzare per inviare e-mail ai destinatari (indirizzo del mittente) e per consentire loro di inviare risposte automatizzate come rimbalzi asincroni, risposte non in ufficio, ecc. (indirizzo di errore).  Adobe Campaign verifica che gli indirizzi immessi siano validi durante la fase di preparazione dei messaggi. Questa modalità operativa assicura che non vengano utilizzati indirizzi che possano causare problemi di recapito.
   * Sia il mittente che l&#39;indirizzo di errore sono impostati da Adobe. Questi campi non possono essere vuoti.
   * Non è possibile modificare tali campi. Per aggiornare un indirizzo, contatta il team di assistenza clienti Adobe.
   * Per aggiungere un altro indirizzo, potete utilizzare il Pannello [di](https://docs.adobe.com/content/help/en/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html) controllo per impostare un nuovo sottodominio o contattare il team di assistenza clienti di Adobe. Tenete presente che se vengono utilizzate più maschere, queste saranno separate da virgole.
   * È buona norma impostare gli indirizzi utilizzando una stella come *@yourdomain.com: consente di utilizzare qualsiasi indirizzo che termina con il nome del sottodominio.

* **Realizzazione**

   L&#39; **[!UICONTROL Delivery reports ID]** assistenza è fornita dal team di assistenza clienti Adobe. Identifica ogni istanza con un ID di recapito che viene utilizzato nei rapporti tecnici di recapito.
   <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Parametri di consegna**

   Adobe Campaign invia i messaggi a partire dalla data di inizio. Il **[!UICONTROL Message delivery duration]** campo consente di specificare l&#39;intervallo di tempo entro il quale verrà ritentato qualsiasi messaggio nel recapito che rilevi un errore temporaneo o un rimbalzo morbido.

   >[!IMPORTANT]
   >
   >**Questo parametro in Campaign ora viene utilizzato solo se impostato su 3,5 giorni o meno.** Se definisci un valore superiore a 3,5 giorni, non verrà preso in considerazione in quanto ora è gestito dall&#39;MTA avanzata di Adobe Campaign.

   Il **[!UICONTROL Online resources validity duration]** campo viene utilizzato per le risorse caricate, principalmente per la pagina mirror e le immagini. Le risorse presenti in questa pagina sono valide per un periodo di tempo limitato (per risparmiare spazio su disco).

* **Tentativi**

   I messaggi temporaneamente non consegnati sono soggetti a un nuovo tentativo automatico. Per ulteriori informazioni, vedere [Tentativi dopo un errore](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)temporaneo di consegna.

   >[!NOTE]
   >
   >Il numero massimo di tentativi da eseguire e il ritardo minimo tra i tentativi sono ora gestiti dall&#39;MTA avanzata di Adobe Campaign, in base alle prestazioni di un IP sia storicamente che attualmente in un determinato dominio. Le impostazioni **Riprova** in Campaign verranno ignorate.

   <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parametri di quarantena e-mail**

   Nel **[!UICONTROL Time between two significant errors]** campo, immettere un valore per definire l&#39;ora in cui l&#39;applicazione attende prima di incrementare il contatore di errori in caso di errore con rimbalzo non corretto. Il valore predefinito è **&quot;1d&quot;**, per 1 giorno.

   Una volta raggiunto il **[!UICONTROL Maximum number of errors before quarantine]** valore, l&#39;indirizzo e-mail viene quindi messo in quarantena. Il valore predefinito è **&quot;5&quot;**: l&#39;indirizzo verrà messo in quarantena al quinto errore. Ciò significa che il contatto sarà automaticamente escluso dalle consegne successive.
   <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

   Per ulteriori informazioni sulle quarantena, vedere [Informazioni sulla gestione](../../sending/using/understanding-quarantine-management.md)della quarantena.

## Account di routing e-mail {#email-routing-accounts}

L&#39;account **[!UICONTROL Integrated email routing]** esterno è fornito per impostazione predefinita. Contiene i parametri tecnici che consentono all&#39;applicazione di inviare e-mail.

![](assets/channels_2.png)

Il tipo di account deve essere sempre impostato su **[!UICONTROL Routing]**, il canale su **[!UICONTROL Email]** e la modalità di consegna impostata su **[!UICONTROL Bulk delivery]**.

**Argomento** correlato:

[Account esterni](../../administration/using/external-accounts.md)

## Regole di elaborazione e-mail {#email-processing-rules}

Gli amministratori **[!UICONTROL Email processing rules]** possono accedervi tramite il **[!UICONTROL Administration > Channels > Email]** menu.

I domini e-mail e le regole MX ora sono gestiti dall&#39;MTA avanzata di Adobe Campaign:
* **La firma dell&#39;autenticazione dell&#39;e-mail DKIM (DomainKeys Identified Mail)** viene fatta dall&#39;MTA avanzata per tutti i messaggi con tutti i domini. Non firma con **Sender ID**, **DomainKeys** o **S/MIME** , a meno che non venga specificato diversamente a livello Enhanced MTA.
* L&#39;MTA avanzata utilizza le proprie regole MX che le consentono di personalizzare il throughput in base al dominio in base alla reputazione storica dell&#39;e-mail e al feedback in tempo reale proveniente dai domini in cui si inviano le e-mail.

### Messaggi di rimbalzo {#bounce-mails}

I messaggi di rimbalzo asincroni sono ancora qualificati dal processo Campaign inMail attraverso le **[!UICONTROL Bounce mails]** regole.

Queste regole contengono l&#39;elenco di stringhe di caratteri che possono essere restituite dai server remoti e che consentono di qualificare l&#39;errore (**Hard**, **Soft** o **Ignored**).

>[!NOTE]
>
>Per i messaggi di errore di consegna sincrona, l&#39;MTA avanzata di Adobe Campaign determina il tipo di rimbalzo e la qualifica e invia nuovamente tali informazioni a Campaign.

Per ulteriori informazioni sulla qualifica della posta indesiderata, consulta questa [sezione](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Elenco delle proprietà delle e-mail {#list-of-email-properties}

In questa sezione viene illustrato l&#39;elenco dei parametri disponibili nella schermata delle proprietà di un modello e-mail o e-mail.

>[!NOTE]
>
>Alcuni parametri sono disponibili solo nei modelli. I parametri a cui potete accedere [dipendono dalle vostre autorizzazioni](../../administration/using/users-management.md).

Per modificare le proprietà di un modello e-mail o e-mail, utilizzate il **[!UICONTROL Edit properties]** pulsante .

![](assets/delivery_options_1.png)

### Parametri generali {#general-parameters}

Nella parte superiore della schermata dei parametri e-mail, identificate il messaggio e-mail utilizzando i **[!UICONTROL Label]** campi e **[!UICONTROL ID]** . Queste informazioni vengono visualizzate nell&#39;interfaccia ma non sono visibili ai destinatari del messaggio.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>L&#39;ID deve essere univoco.

Il **[!UICONTROL Brand]** campo consente di selezionare il marchio collegato alla consegna. Per ulteriori informazioni sull’utilizzo e la configurazione dei marchi, consulta la sezione [Branding](../../administration/using/branding.md) .

Il **[!UICONTROL Campaign]** campo consente di inserire la campagna collegata al messaggio e-mail.

Potete anche aggiungere un **[!UICONTROL Description]** nel campo corrispondente e modificare l’immagine visualizzata nella miniatura dell’e-mail negli elenchi.

### Invio di parametri {#sending-parameters}

La **[!UICONTROL Send]** sezione è disponibile solo per i modelli e-mail. Contiene i seguenti parametri:

#### Parametri dei tentativi {#retries-parameters}

I messaggi temporaneamente non consegnati sono soggetti a un nuovo tentativo automatico. Per ulteriori informazioni, vedere [Tentativi dopo un errore](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)temporaneo di consegna.

>[!NOTE]
>
>Il ritardo minimo tra i tentativi e il numero massimo di tentativi da eseguire è ora gestito dall&#39;MTA avanzato di Adobe Campaign, in base alle prestazioni di un IP sia storicamente che attualmente in un determinato dominio. Le impostazioni **Tentativi** campagna verranno ignorate.

<!--This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](#validity-period-parameters) section.

The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template.-->

L&#39;impostazione **della durata di** consegna (definita nella sezione dei parametri [del periodo di](#validity-period-parameters) validità) **impostata in Campaign continuerà a essere rispettata, ma solo fino a 3,5 giorni**. A questo punto, tutti i messaggi nella coda dei tentativi verranno rimossi dalla coda e inviati nuovamente come rimbalzo. Per ulteriori informazioni sugli errori di consegna, consulta questa [sezione](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Parametri del formato e-mail {#email-format-parameters}

Potete configurare il formato delle e-mail da inviare. Sono disponibili tre opzioni:

* **Usa preferenze** del destinatario (modalità predefinita): il formato del messaggio viene definito in base ai dati memorizzati nel profilo del destinatario e memorizzato per impostazione predefinita nel campo Formato **** e-mail (@emailFormat). Se un destinatario desidera ricevere i messaggi in un determinato formato, si tratta del formato inviato. Se il campo non è completato, viene inviato un messaggio alternativo multiparte (vedi sotto).
* **Consenti al client di posta elettronica destinatario di scegliere il formato più appropriato (alternativa multiparte)**: il messaggio contiene entrambi i formati: text e HTML. Il formato visualizzato in base alla ricezione dipende dalla configurazione del software di posta del destinatario (multipart-alternative).

   >[!IMPORTANT]
   >
   >Questa opzione include entrambe le versioni del messaggio. Di conseguenza, influisce sulla velocità di consegna, poiché la dimensione del messaggio è maggiore.

* **Invia tutti i messaggi in formato** testo: il messaggio viene inviato in formato testo. Il formato HTML non verrà inviato, ma utilizzato per la pagina mirror solo quando il destinatario fa clic sul collegamento nel messaggio.

#### Modalità di prova SMTP {#smtp-test-mode}

L&#39; **[!UICONTROL Enable SMTP test mode]** opzione consente di verificare l&#39;invio di e-mail tramite una connessione SMTP senza inviare effettivamente i messaggi.
I messaggi vengono elaborati fino al raggiungimento della connessione con il server SMTP, ma non vengono inviati.

![](assets/smtp-test-mode.png)

Questa opzione è disponibile per i modelli e-mail e e-mail.

Se abilitate l&#39;opzione della modalità di prova SMTP per un modello e-mail, questa opzione sarà attivata per tutti i messaggi e-mail creati da questo modello.

>[!IMPORTANT]
>
>Quando questa opzione è abilitata per un messaggio e-mail, nessun messaggio verrà inviato finché non viene deselezionato.
>Nel dashboard del modello e-mail o del modello e-mail verrà visualizzato un avviso.

Per ulteriori informazioni sulla configurazione di SMTP, vedere la sezione [Elenco dei parametri](#list-of-email-smtp-parameters) SMTP dell&#39;e-mail.

### Parametri periodo di validità {#validity-period-parameters}

La **[!UICONTROL Validity period]** sezione contiene i seguenti parametri:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: quando questa casella è deselezionata, è necessario immettere una durata nei campi **[!UICONTROL Delivery duration]** e **[!UICONTROL Resource validity limit]** .

   Selezionare questa casella se si desidera definire date e ore specifiche.

   ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]** / **[!UICONTROL Validity limit for sending messages]**: Adobe Campaign invia i messaggi a partire dalla data di inizio. Questo campo consente di specificare la durata durante la quale i messaggi possono essere inviati.

   >[!IMPORTANT]
   >
   >Questo parametro ora è gestito dall&#39;MTA avanzato di Adobe Campaign. **È necessario definire un valore fino a 3,5 giorni.** Se si definisce un valore superiore a 3,5 giorni, non verrà preso in considerazione.

* **[!UICONTROL Resource validity duration]** / **[!UICONTROL Validity limit date for resources]**: questo campo viene utilizzato per le risorse caricate, principalmente per la pagina mirror e le immagini. Le risorse presenti in questa pagina sono valide per un periodo di tempo limitato (per risparmiare spazio su disco).
* **[!UICONTROL Mirror page management]**: la pagina mirror è una pagina HTML accessibile online tramite un browser Web. Il contenuto è identico al contenuto dell’e-mail. Per impostazione predefinita, la pagina mirror viene generata se il collegamento viene inserito nel contenuto della posta elettronica. Questo campo consente di modificare il modo in cui viene generata la pagina:

   >[!IMPORTANT]
   >
   >Il contenuto HTML deve essere stato definito per l&#39;e-mail per la pagina mirror da creare.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modalità predefinita): la pagina mirror viene generata se il collegamento viene inserito nel contenuto della posta.
   * **Forza la generazione della pagina** mirror: anche se nei messaggi non viene inserito alcun collegamento alla pagina mirror, verrà creata la pagina mirror.
   * **Non generate la pagina** mirror: non viene generata alcuna pagina mirror, anche se il collegamento è presente nei messaggi.
   * **Genera una pagina mirror accessibile solo utilizzando l&#39;ID** messaggio: questa opzione consente di accedere al contenuto della pagina mirror, con informazioni sulla personalizzazione, nella finestra del registro di distribuzione.

>[!NOTE]
>
>Il **[!UICONTROL Delivery duration]** parametro non si applica ai messaggi transazionali. Per ulteriori informazioni sui messaggi transazionali, consulta [questa sezione](../../channels/using/about-transactional-messaging.md).

### Parametri di tracciamento {#tracking-parameters}

La **[!UICONTROL Tracking]** sezione contiene i seguenti parametri:

* **[!UICONTROL Activate tracking]**: consente di attivare/disattivare il tracciamento URL del messaggio. Per gestire il tracciamento di ciascun URL del messaggio, utilizza l&#39; **[!UICONTROL Links]** icona nella barra delle azioni di Designer e-mail. Consultate [Gli URL](../../designing/using/links.md#about-tracked-urls)tracciati.
* **[!UICONTROL Tracking validity limit]**: consente di definire la durata per la quale verrà attivato il tracciamento sugli URL.
* **[!UICONTROL Substitution URL for expired URLs]**: potete immettere un URL per una pagina Web che verrà visualizzata una volta scaduto il tracciamento.

### Parametri avanzati {#advanced-parameters}

La **[!UICONTROL Advanced parameters]** sezione contiene più parametri.

I primi campi consentono di inserire le informazioni necessarie per elaborare le intestazioni dei messaggi e-mail. È possibile gestire qui l&#39;indirizzo e il testo della risposta, nonché l&#39;indirizzo del mittente (che riempie il campo &quot;Da:&quot;). Queste informazioni possono essere personalizzate.

Fate clic sul pulsante a destra del campo da modificare, quindi aggiungete il campo di personalizzazione, il blocco di contenuto o il testo dinamico.

![](assets/advancedparameters.png)

L&#39;inserimento e l&#39;utilizzo del contenuto di personalizzazione sono descritti dettagliatamente nella documentazione [Personalizzazione del contenuto](../../designing/using/personalization.md) dell&#39;e-mail.

#### Contesto di destinazione {#target-context}

Il contesto di targeting consente di definire un set di tabelle da utilizzare per il targeting delle e-mail (nella schermata di definizione dell&#39;audience) e la personalizzazione (definizione dei campi di personalizzazione nell&#39;editor di contenuti HTML).

#### Routing {#routing}

Questo campo indica la modalità di routing utilizzata. Fa riferimento a un account esterno. Ad esempio, questo può essere utilizzato se desiderate utilizzare un account esterno contenente specifiche configurazioni di branding.

>[!NOTE]
>
>Gli account esterni sono accessibili tramite il menu **Amministrazione** > Impostazioni **** applicazione > Account **** esterni.

#### Preparazione {#preparation}

La preparazione dei messaggi è dettagliata nella sezione [Approvare i messaggi](../../sending/using/preparing-the-send.md) .

* **[!UICONTROL Typology]**: prima di qualsiasi invio, i messaggi devono essere preparati per convalidare il contenuto e la configurazione. Le regole di verifica applicate durante la fase di preparazione sono definite in una **tipologia**. Ad esempio, per le e-mail, la preparazione prevede il controllo dell’oggetto, degli URL e delle immagini, ecc. Selezionare la tipologia da applicare in questo campo.

   >[!NOTE]
   >
   >Le tipologie, accessibili tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** , sono presentate in [questa sezione](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: consente di calcolare il valore dell’etichetta dell’e-mail durante la fase di preparazione dei messaggi utilizzando campi di personalizzazione, blocchi di contenuto e testo dinamico.

   È inoltre possibile personalizzare l&#39;etichetta di consegna con le variabili di evento dichiarate nell&#39;attività del segnale esterno del flusso di lavoro. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: questa opzione consente di aggiungere i registri query SQL nel giornale di registrazione durante la fase di preparazione.

#### Impostazioni prova {#proof-settings}

Questa sezione consente di configurare il prefisso predefinito da utilizzare nella riga dell&#39;oggetto della prova. For more in this, refer to [this section](../../sending/using/sending-proofs.md).

### Elenco dei parametri SMTP dell&#39;e-mail {#list-of-email-smtp-parameters}

La **[!UICONTROL SMTP]** sezione contiene i seguenti parametri:

* **[!UICONTROL Character encoding]**: seleziona la **[!UICONTROL Force encoding]** casella se desideri forzare la codifica dei messaggi, quindi seleziona la codifica da utilizzare.
* **[!UICONTROL Bounce mails]**: per impostazione predefinita, i messaggi di rimbalzo vengono ricevuti nella inbox degli errori della piattaforma (definita in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]** schermata). Per definire un indirizzo di errore specifico per un&#39;e-mail, immettete l&#39;indirizzo nel **[!UICONTROL Error address]** campo.
* **[!UICONTROL Additional SMTP headers]**: questa opzione consente di aggiungere intestazioni SMTP aggiuntive ai messaggi. Lo script immesso nel **[!UICONTROL Headers]** campo deve fare riferimento a un&#39;intestazione per riga, sotto forma di **nome:valore**. Se necessario, i valori vengono codificati automaticamente.

   >[!IMPORTANT]
   >
   >L&#39;aggiunta di uno script per l&#39;inserimento di intestazioni SMTP aggiuntive è riservata agli utenti avanzati. La sintassi di questo script deve essere conforme ai requisiti di questo tipo di contenuto: nessuno spazio inutilizzato, nessuna linea vuota, ecc.

### Elenco dei parametri di autorizzazione di accesso {#list-of-access-authorization-parameters}

La **[!UICONTROL Access authorization]** sezione contiene i seguenti parametri:

* Il **[!UICONTROL Organizational unit]** campo consente di limitare l’accesso a questo messaggio e-mail a determinati utenti. Gli utenti associati all&#39;unità o alle unità padre specificate avranno accesso in lettura e scrittura a questa e-mail. Gli utenti associati alle unità figlie avranno accesso in sola lettura a questo messaggio e-mail.

   >[!NOTE]
   >
   >Potete configurare le unità organizzative dal menu **Amministrazione** > **Utenti e sicurezza** .

* I **[!UICONTROL Created by]**, **[!UICONTROL Created]****[!UICONTROL Modified by]** e **[!UICONTROL Last modified]** i campi vengono completati automaticamente.
