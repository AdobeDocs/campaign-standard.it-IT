---
title: Configurazione del canale e-mail in Adobe Campaign Standard
description: Scopri come configurare il canale e-mail in Adobe Campaign Standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 76d70fd1-dd93-4a6d-b18c-96ebe5a27a7d
source-git-commit: 26a1c36003645446fb8b827d76afba749d64e9f2
workflow-type: tm+mt
source-wordcount: '2729'
ht-degree: 58%

---

# Configurazione del canale e-mail{#configuring-email-channel}

In qualità di [amministratore](../../administration/using/users-management.md#functional-administrators) di Campaign, puoi effettuare la configurazione delle impostazioni del canale e-mail. Tali impostazioni avanzate includono i parametri generali del canale e-mail, account di indirizzamento e-mail, regole di elaborazione e-mail e proprietà e-mail. In questa pagina, scopri come modificare i valori predefiniti per l’e-mail generale e i parametri di invio.

## Parametri del canale e-mail {#email-channel-parameters}

La schermata di configurazione e-mail consente di definire i parametri per il canale e-mail. Gli amministratori possono accedere a queste configurazioni nel menu **[!UICONTROL Administration]> [!UICONTROL Channels] > [!UICONTROL Email] >[!UICONTROL Configuration]**.

![](assets/channels_1.png)

* **Campi delle maschere autorizzate**

  La sezione **[!UICONTROL Header parameters of sent emails]** elenca gli indirizzi e-mail autorizzati che puoi utilizzare per spedire e-mail ai destinatari (indirizzo del mittente) e per consentir loro di inviare risposte automatizzate, quali messaggi non recapitati asincroni, risposte fuori sede e così via (indirizzo di errore).

  Durante la fase di preparazione dei messaggi, Adobe Campaign verifica che gli indirizzi immessi siano validi. Questa modalità operativa assicura che non vengano utilizzati indirizzi che possono causare problemi di consegna.

   * Sia l’indirizzo del mittente che l’indirizzo di errore sono impostati da Adobe. Questi campi non possono essere vuoti.
   * Non è possibile modificarli. Per aggiornare un indirizzo, contatta il team di Assistenza cliente Adobe.
   * Per aggiungere un altro indirizzo, puoi utilizzare [Pannello di controllo Campaign della campagna](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/setting-up-new-subdomain.html?lang=it) per impostare un nuovo sottodominio o contatta il team di assistenza clienti Adobe. Se vengono utilizzate più maschere, vengono separate da virgole.
   * È buona norma impostare gli indirizzi utilizzando una stella come **@yourdomain.com**: ti consente di utilizzare qualsiasi indirizzo che termina con il nome del sottodominio.

* **Consegna**

  L’**[!UICONTROL Delivery reports ID]** è fornito dal team di Assistenza cliente Adobe. Identifica ogni istanza con un ID di consegna che viene utilizzato nei report tecnici di consegna.
  <!--The Technical Deliverability report is not accessible through the UI in ACS. It will be replaced with 250ok in the future (project starting).-->

* **Parametri di consegna**

  Adobe Campaign invia i messaggi a partire dalla data di inizio.

  Quando un messaggio in una consegna viene rifiutato a causa di un errore temporaneo o di un mancato recapito non permanente, Campaign tenta di inviare questo messaggio ogni giorno. Utilizza il **[!UICONTROL Message delivery duration]** per specificare l’intervallo di tempo durante i nuovi tentativi.

  >[!IMPORTANT]
  >
  >**Questo parametro adesso viene utilizzato in Campaign solo se è impostato su 3,5 giorni o meno.** Se definisci un valore superiore a 3,5 giorni, questo non verrà preso in considerazione.

  Il campo **[!UICONTROL Online resources validity duration]** viene utilizzato per le risorse caricate, principalmente per la pagina mirror e per le immagini. Le risorse presenti in questa pagina sono valide per un periodo di tempo limitato (per risparmiare spazio su disco).

* **Nuovi tentativi**

  I messaggi temporaneamente non consegnati sono soggetti a un nuovo tentativo automatico. Per ulteriori informazioni, consulta [Tentativi dopo un errore temporaneo di consegna](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

  >[!IMPORTANT]
  >
  >Il numero massimo di nuovi tentativi da eseguire e il ritardo minimo tra di essi si basano ora sulle prestazioni di un IP sia storicamente che attualmente in un determinato dominio. Il **[!UICONTROL Retry period]** e **[!UICONTROL Number of retries]** le impostazioni in Campaign verranno ignorate.

  <!--This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**). By default, five retries are scheduled for the first day with a minimum interval of one hour, spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.-->

* **Parametri di quarantena e-mail**

  Nel campo **[!UICONTROL Time between two significant errors]**, immetti un valore per definire il tempo che l’applicazione attende prima di incrementare il contatore degli errori in caso di errore di messaggio non recapitato. Il valore predefinito è **&quot;1d&quot;**, che corrisponde a 1 giorno.

  Una volta raggiunto il valore **[!UICONTROL Maximum number of errors before quarantine]**, l’indirizzo e-mail viene quindi messo in quarantena. Il valore predefinito è **5&quot;**: l’indirizzo viene messo in quarantena al quinto errore. Ciò significa che il contatto sarà automaticamente escluso dalle consegne successive.
  <!--Actually the way ACS works is that the address is already on the quarantine list on the first bounce, but with a different status meaning that the error count has started.-->

  Per ulteriori informazioni sulle quarantena, consulta [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md).

## Account di indirizzamento e-mail {#email-routing-accounts}

L’account esterno **[!UICONTROL Integrated email routing]** è fornito per impostazione predefinita. Contiene i parametri tecnici che consentono all’applicazione di effettuare l’invio di e-mail.

![](assets/channels_2.png)

Il tipo di account deve essere sempre impostato su **[!UICONTROL Routing]**, il canale su **[!UICONTROL Email]** e la modalità di consegna su **[!UICONTROL Bulk delivery]**.

**Argomento correlato**:

[Account esterni](../../administration/using/external-accounts.md)

## Regole di elaborazione e-mail {#email-processing-rules}

È possibile accedere alle **[!UICONTROL Email processing rules]** tramite il menu **[!UICONTROL Administration > Channels > Email]**.

>[!IMPORTANT]
>
>I domini e-mail e le regole MX ora vengono gestiti automaticamente<!--by the Adobe Campaign Enhanced MTA (Message Transfer Agent)--> e non possono essere modificati.

* **DKIM (DomainKeys Identified Mail)** la firma di autenticazione e-mail viene eseguita per tutti i messaggi di tutti i domini. Non firma con **ID mittente**, **DomainKeys**, o **S/MIME**.
* Le regole MX personalizzano automaticamente la velocità effettiva per dominio in base alla reputazione cronologica dell’e-mail e al feedback in tempo reale proveniente dai domini in cui invii le e-mail.

<!--Note that the email domains and the MX rules are now managed by the Adobe Campaign Enhanced MTA:
* **DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.
* The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

### Messaggi non recapitati {#bounce-mails}

I messaggi non recapitati asincroni sono ancora qualificati dal processo Campaign inMail attraverso le regole **[!UICONTROL Bounce mails]**.

Tali regole contengono l’elenco di stringhe di caratteri che possono essere restituite dai server remoti e che ti consentono di qualificare l’errore (**Rigido**, **Morbido** o **Ignorato**).

>[!IMPORTANT]
>
>I messaggi di errore di consegna sincrona sono ora qualificati dall’MTA avanzato di Adobe Campaign, che determina il tipo di e la qualifica di mancato recapito e invia nuovamente tali informazioni a Campaign.

Per ulteriori informazioni sulla qualifica della posta non recapitata, consulta questa [sezione](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

<!--Because they are now managed by the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used. For more on bounce mail qualification, see this [section](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

### Management of email domains {#managing-email-domains}

The email domains are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL Domain management]** rules are no longer used.

**DKIM (DomainKeys Identified Mail)** email authentication signing is done by the Enhanced MTA for all messages with all domains. It does not sign with **Sender ID**, **DomainKeys**, or **S/MIME** unless otherwise specified at the Enhanced MTA level.

### MX management {#mx-management}

The MX rules are now managed by the Adobe Campaign Enhanced MTA. The Adobe Campaign **[!UICONTROL MX management]** delivery throughput rules are no longer used.

The Enhanced MTA uses its own MX rules that allow it to customize your throughput by domain based on your own historical email reputation, and on the real-time feedback coming from the domains where you are sending emails.-->

## Elenco delle proprietà e-mail {#list-of-email-properties}

In questa sezione viene illustrato l’elenco dei parametri disponibili nella schermata delle proprietà di un e-mail o di un modello e-mail.

>[!NOTE]
>
>Alcuni parametri sono disponibili solo nei modelli. I parametri a cui puoi accedere [dipendono dalle tue autorizzazioni](../../administration/using/users-management.md).

Per modificare le proprietà di un e-mail o di un modello e-mail, utilizza il pulsante **[!UICONTROL Edit properties]**.

![](assets/delivery_options_1.png)

### Parametri generali {#general-parameters}

Nella parte superiore della schermata dei parametri e-mail, identifica il messaggio e-mail utilizzando i campi **[!UICONTROL Label]** e **[!UICONTROL ID]**. Queste informazioni vengono visualizzate nell’interfaccia ma non sono visibili ai destinatari del messaggio.

![](assets/delivery_options_2.png)

>[!IMPORTANT]
>
>L’ID deve essere univoco.

Utilizza il **[!UICONTROL Brand]** per selezionare il brand collegato alla consegna. Per ulteriori informazioni sull’utilizzo e sulla configurazione dei brand, consulta la sezione [Branding](../../administration/using/branding.md).

In **[!UICONTROL Campaign]** , immetti la campagna associata all’e-mail.

Puoi anche aggiungere una **[!UICONTROL Description]** nel campo corrispondente e modificare l’immagine visualizzata nella miniatura dell’e-mail negli elenchi.

### Parametri di invio {#sending-parameters}

La sezione **[!UICONTROL Send]** è disponibile solo per i modelli e-mail. Contiene i seguenti parametri:

#### Parametri dei nuovi tentativi {#retries-parameters}

I messaggi temporaneamente non consegnati sono soggetti a un nuovo tentativo automatico. Per ulteriori informazioni, consulta [Tentativi dopo un errore temporaneo di consegna](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!IMPORTANT]
>
>Il ritardo minimo tra i nuovi tentativi e il numero massimo di nuovi tentativi da eseguire ora si basano sulle prestazioni di un IP sia storicamente che attualmente in un determinato dominio. Il **[!UICONTROL Retry period]** e **[!UICONTROL Max. number of retries]** le impostazioni in Campaign verranno ignorate.

L’**impostazione della durata di consegna** (definita nella sezione [Parametri del periodo di validità](#validity-period-parameters)) **configurata in Campaign continuerà a essere rispettata, ma solo fino a 3,5 giorni**. A questo punto, tutti i messaggi nella coda dei nuovi tentativi verranno rimossi e reinviati come messaggi non recapitati. Per ulteriori informazioni sugli errori di consegna, consulta questa [sezione](../../sending/using/understanding-delivery-failures.md#about-delivery-failures).

#### Parametri del formato e-mail {#email-format-parameters}

Puoi configurare il formato delle e-mail da inviare. Sono disponibili tre opzioni:

* **Use recipient preferences** (modalità predefinita): il formato del messaggio viene definito in base ai dati memorizzati nel profilo del destinatario e poi memorizzato per impostazione predefinita nel campo **Email format** (@emailFormat). Se un destinatario desidera ricevere i messaggi in un determinato formato, questo sarà il formato inviato. Se il campo non è completato, viene inviato un messaggio multipart-alternative (vedi sotto).
* **Let recipient mail client choose the most appropriate format (multipart-alternative)**: il messaggio contiene entrambi i formati: testo e HTML. Il formato visualizzato in base alla ricezione dipende dalla configurazione del software di posta del destinatario (multipart-alternative).

  >[!IMPORTANT]
  >
  >Questa opzione include entrambe le versioni del messaggio. Di conseguenza, influisce sulla velocità effettiva di consegna, poiché la dimensione del messaggio è maggiore.

* **Send all messages in text format**: il messaggio viene inviato in formato testo. Il formato HTML non verrà inviato, ma sarà utilizzato per la pagina mirror solo quando il destinatario farà clic sul collegamento nel messaggio.

#### Modalità di prova SMTP {#smtp-test-mode}

Utilizza il **[!UICONTROL Enable SMTP test mode]** opzione per verificare l’invio di e-mail tramite una connessione SMTP senza inviare effettivamente i messaggi. La consegna viene elaborata fino alla connessione al server SMTP, ma non viene inviata: per ogni destinatario della consegna, Campaign si connette al server del provider SMTP, esegue il comando SMTP RCPT TO e chiude la connessione prima del comando SMTP DATA.

![](assets/smtp-test-mode.png)

Questa opzione è disponibile per le e-mail e per i modelli e-mail.

Se abiliti l’opzione della modalità di prova SMTP per un modello e-mail, questa opzione sarà attivata per tutti i messaggi e-mail creati da questo modello.

>[!IMPORTANT]
>
>Quando questa opzione è abilitata per un’e-mail, nessun messaggio verrà inviato finché non viene deselezionato.
>Nell’e-mail o nel dashboard del modello e-mail verrà visualizzato un avviso.

Per ulteriori informazioni sulla configurazione di SMTP, consulta la sezione [Elenco dei parametri SMTP dell’e-mail](#list-of-email-smtp-parameters).

### Parametri del periodo di validità {#validity-period-parameters}

La sezione **[!UICONTROL Validity period]** contiene i seguenti parametri:

![](assets/delivery-validity-period.png)

* **[!UICONTROL Explicitly set validity dates]**: quando questa casella è deselezionata, è necessario inserire una durata nei campi **[!UICONTROL Delivery duration]** e **[!UICONTROL Resource validity limit]**.

  Se desideri date e ore specifiche, seleziona questa casella.

  ![](assets/delivery-set-explicit-dates.png)

* **[!UICONTROL Delivery duration]**/**[!UICONTROL Validity limit for sending messages]**: Adobe Campaign invia i messaggi a partire dalla data di inizio. Utilizzare questo campo per specificare il periodo durante il quale è possibile inviare i messaggi.

  >[!IMPORTANT]
  >
  >**È necessario definire un valore fino a 3,5 giorni.** Se imposti un valore superiore a 3,5 giorni, questo non verrà preso in considerazione.
  >
  >Il parametro **[!UICONTROL Delivery duration]** non si applica ai messaggi sulle transazioni. Per ulteriori informazioni sulla messaggistica transazionale, consulta [questa sezione](../../channels/using/getting-started-with-transactional-msg.md).

* **[!UICONTROL Resource validity duration]**/**[!UICONTROL Validity limit date for resources]**: questo campo viene utilizzato per le risorse caricate, principalmente per la pagina mirror e per le immagini. Le risorse presenti in questa pagina sono valide per un periodo di tempo limitato (per risparmiare spazio su disco).
* **[!UICONTROL Mirror page management]**: la pagina mirror è una pagina HTML accessibile online tramite un browser web. Il contenuto è identico a quello dell’e-mail. Per impostazione predefinita, la pagina mirror viene generata se il collegamento viene inserito nel contenuto dell’e-mail. Utilizza questo campo per modificare la modalità di generazione della pagina:

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modalità predefinita): la pagina mirror viene generata se il collegamento viene inserito nel contenuto dell’e-mail.
   * **Forza la generazione della pagina mirror**: anche se nei messaggi non viene inserito alcun collegamento alla pagina mirror, la pagina verrà creata ugualmente.
   * **Non generare la pagina mirror**: non viene creata alcuna pagina mirror, anche se il collegamento è presente nei messaggi.
   * **Genera una pagina mirror accessibile utilizzando solo l’identificatore del messaggio**: questa opzione consente di accedere al contenuto della pagina mirror, con i dati di personalizzazione, nella finestra del registro di consegna.

  >[!IMPORTANT]
  >
  >La pagina speculare viene generata solo se per l’e-mail è stato definito un contenuto HTML.
  >


### Parametri di tracciamento {#tracking-parameters}

La sezione **[!UICONTROL Tracking]** contiene i seguenti parametri:

* **[!UICONTROL Activate tracking]**: utilizza questa opzione per attivare/disattivare il tracciamento URL del messaggio. Per gestire il tracciamento di ciascun URL del messaggio, utilizza l’icona **[!UICONTROL Links]** nella barra delle azioni di E-mail Designer. Consulta la sezione [Informazioni sugli URL tracciati](../../designing/using/links.md#about-tracked-urls).
* **[!UICONTROL Tracking validity limit]**: utilizza questa opzione per definire la durata per la quale verrà attivato il tracciamento sugli URL.
* **[!UICONTROL Substitution URL for expired URLs]**: utilizza questa opzione per immettere un URL per una pagina web di fallback: viene visualizzata una volta scaduto il tracciamento.
* **[!UICONTROL Use tracking pixel at the top of email]**: utilizza questa opzione per spostare il pixel di tracciamento nella parte superiore dell’e-mail invece che nella parte inferiore. Per impostazione predefinita, questo pixel si trova nella parte inferiore delle e-mail. Se invii messaggi di grandi dimensioni, considera di spostare questo pixel nella parte superiore delle e-mail invece che nella parte inferiore per migliorare il tracciamento aperto, altrimenti il pixel di tracciamento potrebbe essere tagliato da alcuni provider e-mail.

### Parametri avanzati {#advanced-parameters}

La sezione **[!UICONTROL Advanced parameters]** contiene più parametri.

I primi campi consentono di inserire le informazioni necessarie per l’elaborazione delle intestazioni dei messaggi e-mail. Qui puoi gestire l’indirizzo e il testo della risposta, nonché l’indirizzo del mittente, che riempie il campo &quot;Da:&quot;. Queste informazioni possono essere personalizzate.

Fai clic sul pulsante a destra del campo da modificare, quindi aggiungi il campo di personalizzazione, il blocco di contenuto o il testo dinamico.

![](assets/advancedparameters.png)

L’inserimento e l’utilizzo del contenuto di personalizzazione sono descritti in modo dettagliato nella documentazione [Personalizzazione del contenuto dell’e-mail](../../designing/using/personalization.md).

#### Contesto del target {#target-context}

Utilizza il contesto di targeting per definire un set di tabelle da utilizzare per il targeting delle e-mail (nella schermata di definizione del pubblico) e la personalizzazione (definizione dei campi di personalizzazione nell’editor di contenuti di HTML).

#### Indirizzamento {#routing}

Questo campo indica la modalità di indirizzamento utilizzata. Fa riferimento a un account esterno. Ad esempio, può essere utilizzato se desideri ricorrere a un account esterno contenente configurazioni di branding specifiche.

>[!NOTE]
>
>Gli account esterni sono accessibili tramite il menu **Administration** > **Application settings** > **External accounts**.

#### Preparazione {#preparation}

La preparazione dei messaggi è spiegata nel dettaglio nella sezione [Approvazione dei messaggi](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Typology]**: prima di qualsiasi invio, i messaggi devono essere preparati al fine di convalidarne il contenuto e la configurazione. Le regole di verifica applicate durante la fase di preparazione sono definite in una **tipologia**. Ad esempio, per le e-mail, la preparazione prevede il controllo dell’oggetto, degli URL e delle immagini e così via. Seleziona la tipologia da applicare in questo campo.

  >[!NOTE]
  >
  >Le tipologie, accessibili tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]**, sono presentate in [questa sezione](../../sending/using/about-typology-rules.md).

* **[!UICONTROL Compute the label during delivery preparation]**: utilizza questa opzione per calcolare il valore dell’etichetta dell’e-mail durante la fase di preparazione dei messaggi tramite campi di personalizzazione, blocchi di contenuto e testo dinamico.

  È inoltre possibile personalizzare l’etichetta di consegna con le variabili evento dichiarate nell’attività del segnale esterno del flusso di lavoro. Per ulteriori informazioni, consulta [questa sezione](../../automating/using/calling-a-workflow-with-external-parameters.md).

* **[!UICONTROL Save SQL queries in the log]**: utilizza questa opzione per aggiungere i registri di query SQL nel giornale di registrazione durante la fase di preparazione.

#### Impostazioni di bozza {#proof-settings}

In questa sezione puoi configurare il prefisso predefinito da utilizzare nella riga dell’oggetto dei messaggi della bozza. Ulteriori informazioni sulle bozze in [questa sezione](../../sending/using/sending-proofs.md).

### Elenco parametri SMTP e-mail {#list-of-email-smtp-parameters}

La sezione **[!UICONTROL SMTP]** contiene i seguenti parametri:

* **[!UICONTROL Character encoding]**: seleziona la casella **[!UICONTROL Force encoding]** per forzare la codifica dei messaggi, quindi scegli la codifica da utilizzare.
* **[!UICONTROL Bounce mails]**: per impostazione predefinita, i messaggi non recapitati vengono ricevuti nella casella in entrata degli errori della piattaforma (definita nella schermata **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Configuration]**). Per impostare un indirizzo di errore specifico per un’e-mail, inseriscilo nel campo **[!UICONTROL Error address]**.
* **[!UICONTROL Additional SMTP headers]**: questa opzione ti consente di aggiungere ai messaggi le intestazioni SMTP aggiuntive. Lo script immesso nel campo **[!UICONTROL Headers]** deve fare riferimento a un’intestazione per riga, nella forma di **nome:valore**. Se necessario, i valori vengono codificati automaticamente.

  >[!IMPORTANT]
  >
  >L’aggiunta di uno script per l’inserimento di intestazioni SMTP aggiuntive è un’operazione riservata agli utenti avanzati. La sintassi di questo script deve essere conforme ai requisiti di questo tipo di contenuto: nessuno spazio inutilizzato, nessuna linea vuota e così via.

  A partire dal 1° giugno 2024, Google e Yahoo! richiederà ai mittenti di conformarsi **Annulla iscrizione mailing list con un solo clic**. Campaign supporta questa funzionalità come funzione standard.

  >[!CAUTION]
  >
  >Se modifichi il valore dell’intestazione in **[!UICONTROL Additional SMTP headers]** dei modelli e-mail, potrebbe compromettere la conformità con il **Annulla iscrizione mailing list con un solo clic** requisiti di Google e Yahoo!.

### Elenco dei parametri di autorizzazione di accesso {#list-of-access-authorization-parameters}

La sezione **[!UICONTROL Access authorization]** contiene i seguenti parametri:

* Il **[!UICONTROL Organizational unit]** Questo campo viene utilizzato per limitare l’accesso a questo messaggio e-mail a determinati utenti. Gli utenti associati all’unità o alle unità principali specificate avranno accesso in lettura e scrittura a questa e-mail. Gli utenti associati alle unità secondarie avranno accesso in sola lettura a questa e-mail.

  >[!NOTE]
  >
  >Puoi configurare le unità organizzative dal menu **Administration** > **Users &amp; Security**.

* I campi **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** e **[!UICONTROL Last modified]** vengono completati automaticamente.

## Impostazioni legacy {#legacy-settings}

Se sei **NOT** Se utilizzi la versione più recente di Campaign, i parametri e le sezioni dell’interfaccia utente descritti di seguito sono ancora applicabili.

### Nuovi tentativi {#legacy-retries}

Il **[!UICONTROL Retries]** impostazioni in [Menu Configurazione](#email-channel-parameters) e nella [Parametri di invio](#retries-parameters) delle proprietà e-mail indica quanti tentativi devono essere eseguiti il giorno successivo all’avvio dell’invio (**[!UICONTROL Number of retries]** / **[!UICONTROL Max. number of retries]**) e il ritardo minimo tra un nuovo tentativo e l&#39;altro (**[!UICONTROL Retry period]**).

Il numero di tentativi può essere modificato a livello globale (contatta l’amministratore tecnico Adobe) o per ogni modello di consegna o consegna.

Per impostazione predefinita, per il primo giorno sono pianificati cinque nuovi tentativi con un intervallo minimo di un’ora, suddivisi nelle 24 ore del giorno. Un nuovo tentativo al giorno viene programmato dopo tale e fino alla scadenza della consegna, definita globalmente in **[!UICONTROL Delivery parameters]** sezione del **[!UICONTROL Configuration]** o nel menu **[!UICONTROL Validity period]** a livello di consegna (consulta la sezione [Durata consegna](#legacy-delivery-duration) sezione successiva).

### Durata consegna {#legacy-delivery-duration}

Utilizza il **[!UICONTROL Message delivery duration]** parametro in [Menu Configurazione](#email-channel-parameters) per specificare l’intervallo di tempo entro il quale verrà ritentato qualsiasi messaggio nella consegna che riscontri un errore temporaneo o un messaggio non recapitato.

Utilizza il **[!UICONTROL Delivery duration]** o **[!UICONTROL Validity limit for sending messages]** parametro in [Parametri del periodo di validità](#validity-period-parameters) per specificare la durata durante la quale i messaggi possono essere inviati.

### Regole di elaborazione e-mail {#legacy-email-processing-rules}

Il **[!UICONTROL MX management]**, **[!UICONTROL Bounce mails]** e **[!UICONTROL Domain management]** le regole possono essere accessibili e modificate dagli amministratori tramite **[!UICONTROL Administration > Channels > Email > Email processing rules]** menu. [Ulteriori informazioni](#email-processing-rules).

### Qualificazione di mail non recapitate {#legacy-bounce-mail-qualification}

Per elencare i vari mancati recapiti e i tipi di errore e i motivi associati, fai clic sul pulsante **Adobe** in alto a sinistra, quindi seleziona **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

I mancati recapiti possono avere i seguenti stati di qualifica:

* **[!UICONTROL To qualify]**: la posta non recapitata deve essere qualificata. La qualifica deve essere eseguita dal team Deliverability per garantire il corretto funzionamento della piattaforma. Se non è qualificata, la posta non recapitata non viene utilizzata per arricchire l’elenco delle regole di elaborazione e-mail.
* **[!UICONTROL Keep]**: la mail non recapitata è stata qualificata e verrà utilizzata da **Aggiornamento per il recapito messaggi** il flusso di lavoro da confrontare con le regole di elaborazione e-mail esistenti e arricchire l’elenco.
* **[!UICONTROL Ignore]**: la mail non recapitata è stata qualificata ma non verrà utilizzata da **Aggiornamento per il recapito messaggi** flusso di lavoro. Pertanto, non verranno inviate alle istanze client.

>[!NOTE]
>
>In caso di interruzione di un ISP, le e-mail inviate tramite Campaign verranno contrassegnate erroneamente come messaggi non recapitati. Per risolvere questo problema, devi aggiornare la qualifica di mancato recapito. [Ulteriori informazioni](../../administration/using/update-bounce-qualification.md).

<!--Bounces are qualified through the **[!UICONTROL Bounce mails]** processing rule. For more on accessing this rule, refer to this [section](#legacy-bounce-mail-qualification).-->

### Generazione di rapporti sugli indicatori di consegna {#legacy-delivered-status-report}

In **[!UICONTROL Summary]** visualizzazione di ogni messaggio, **[!UICONTROL Delivered]** la percentuale aumenta progressivamente durante il periodo di validità della consegna, quando vengono segnalati i mancati recapiti non permanenti e permanenti.

I messaggi in mancati recapiti non permanenti vengono visualizzati come **[!UICONTROL Failed]** il primo giorno successivo alla consegna. Questi messaggi vengono ritentati ogni giorno, fino alla fine del periodo di validità della consegna.
