---
title: Configurazione del canale e-mail
seo-title: Configurazione del canale e-mail
description: Configurazione del canale e-mail
seo-description: Scopri come configurare il canale e-mail.
page-status-flag: never-activated
uuid: 9 fddb 655-b 445-41 f 3-9 b 02-5 d 356 fc 88 aa 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: configuring-channels
discoiquuid: 3752 d 41 f -8 c 59-4 fad-b 30 f-e 98 e 09 cd 74 a 8
context-tags: Extaccountemail, overview; Emailconfig, main; Ruleset, overview; distribuzione, proprietà, apri
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring email channel{#configuring-email-channel}

## Email channel parameters {#email-channel-parameters}

La schermata di configurazione e-mail consente di definire i parametri del canale e-mail.

![](assets/channels_1.png)

* **Parametri dell'intestazione delle e-mail inviate**

   In this section, you can specify the **[!UICONTROL masks]** authorized for the sender address and the error address. Se necessario, queste maschere possono essere separate mediante virgole. Questa configurazione è facoltativa. Quando questi campi vengono immessi, durante l'operazione di preparazione dei messaggi Adobe Campaign verifica che gli indirizzi immessi siano validi. Questa modalità operativo assicura che non vengano utilizzati indirizzi che potrebbero attivare problemi di prestazioni. Gli indirizzi di consegna devono essere configurati sul server di consegna.

* **Deliverability**

   Questo ID è fornito dal supporto. È necessario che i rapporti sul rendering funzionino correttamente.

* **Parametri di consegna**

   Adobe Campaign invia i messaggi a partire dalla data iniziale. **[!UICONTROL Message delivery duration]** Il campo consente di specificare la durata in cui i messaggi possono essere inviati.

   **[!UICONTROL Online resources validity duration]** Il campo viene usato per le risorse caricate, principalmente per la pagina speculare e le immagini. Le risorse presenti in questa pagina sono valide per un periodo limitato (per risparmiare spazio su disco).

* **Tentativi**

   I messaggi temporaneamente non consegnati sono soggetti a un ritry automatico. This section indicates how many retries should be performed the day after the send is started (**Number of retries**) and the minimum delay between retries (**Retry period**).

   Per impostazione predefinita, cinque tentativi sono pianificati per il primo giorno con un intervallo minimo di un'ora, con estensione valida per 24 ore. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Delivery parameters]** section.

* **Parametri di quarantena e-mail**

   In the **[!UICONTROL Time between two significant errors]** field, enter a value to define the time the application waits before incrementing the error counter in case of failure. Defaut value: **"1d"**, for 1 day.

   When the **[!UICONTROL Maximum number of errors before quarantine]** value is reached, the email address is then quarantined. Default value: **"5"**: the address will be quarantined on the sixth error. Ciò significa che il contatto verrà escluso automaticamente dalle consegne successive.

**Argomento** correlato:

[Gestione della gestione della quarantena](../../sending/using/understanding-quarantine-management.md)

## Email routing accounts {#email-routing-accounts}

The **[!UICONTROL Integrated email routing]** external account is provided by default. Contiene i parametri tecnici che consentono all'applicazione di inviare e-mail.

![](assets/channels_2.png)

The account type must always be set to **[!UICONTROL Routing]**, the channel to **[!UICONTROL Email]** and the delivery mode set to **[!UICONTROL Bulk delivery]**.

**Argomento** correlato:

[Account esterni](../../administration/using/external-accounts.md)

## Email processing rules {#email-processing-rules}

These rules contain the list of character strings which can be returned by remote servers and which let you qualify the error (**Hard**, **Soft** or **Ignored**).

Le regole predefinite sono le seguenti:

**Messaggi rimbalzi**

Quando un'e-mail non riesce, il server dei messaggi remoto restituisce un messaggio di errore di rimbalzo all'indirizzo specificato nelle impostazioni dell'applicazione. Adobe Campaign confronta il contenuto di ciascun messaggio di rimbalzo alle stringhe nell'elenco delle regole, quindi assegna uno dei tre tipi di errore.

L'utente può creare le proprie regole.

>[!CAUTION]
>
>When importing a package and when updating data via the **Update for deliverability** workflow, the user-created rules are overwritten.

**Gestione dei domini e-mail**

Le regole di gestione del dominio vengono utilizzate per regolare il flusso delle e-mail in uscita per un dominio specifico. Essi possono campionare i messaggi rimbalzati e bloccare l'invio laddove appropriato. Il server di messaggistica Adobe Campaign applica regole specifiche per i domini e le regole per il caso generale rappresentate da un asterisco nell'elenco delle regole. Le regole per i domini Hotmail e MSN sono disponibili per impostazione predefinita in Adobe Campaign.

Per configurare le regole di gestione del dominio, impostate semplicemente una soglia e determinati parametri SMTP. A **threshold** is a limit calculated as an error percentage beyond which all messages towards a specific domain are blocked.

Ad esempio, in generale, per un minimo di 300 messaggi, l'invio di e-mail viene bloccato per tre ore se il tasso di errore raggiunge il 90%.

The **SMTP parameters** act as filters applied for a blocking rule.

* You can choose whether or not to activate certain identification standards and encryption keys to check the domain name, such as **Sender ID**, **DomainKeys**, **DKIM**, and **S/MIME**.
* **Reltp relay**: consente di configurare l'indirizzo IP e la porta di un server relay per un determinato dominio.

**MX Management**

Ogni regola definisce una maschera indirizzo per MX. È quindi idoneo qualsiasi MX il cui nome corrisponda a questa maschera. La maschera può contenere " *" e "?" caratteri generici.

Ad esempio, i seguenti indirizzi:

* a.mx.ya hoo.com
* b.mx.ya hoo.com
* c.mx.ya hoo.com

sono compatibili con le maschere seguenti:

* *.yahoo.com
* ? .mx.yahoo.com

Queste regole vengono applicate in sequenza: la prima regola la cui maschera MX è compatibile con MX targeting viene applicata.

Per ciascuna regola sono disponibili i seguenti parametri:

* **[!UICONTROL Range of IDs]**: Questa opzione consente di indicare gli intervalli di identificatori (publicid) per i quali si applica la regola. Potete specificare:

   * Un numero: the rule will only apply to this publicid.
   * Un intervallo di numeri (numero 1-numero 2): la regola si applica a tutti gli edicids tra questi due numeri.
   Se il campo è vuoto, la regola viene applicata a tutti gli ID.

* **[!UICONTROL Shared]**: questa opzione indica che il numero più elevato di messaggi all'ora e delle connessioni è applicabile a tutti gli MXS collegati a questa regola.
* **[!UICONTROL Maximum number of connections]**: numero massimo di connessioni simultanee a un MX da un indirizzo specificato.
* **Numero massimo di messaggi**: Numero massimo di messaggi che possono essere inviati da una connessione. Dopo questo valore, la connessione viene chiusa e ne viene riaperta una nuova.
* **[!UICONTROL Messages per hour]**: numero massimo di messaggi che possono essere inviati entro un'ora per un MX tramite un indirizzo specificato.

>[!CAUTION]
>
>* Il server di consegna (MTA) deve essere riavviato se i parametri sono stati modificati.
>* La modifica o la creazione delle regole di gestione è solo per gli utenti esperti.
>



## List of email properties {#list-of-email-properties}

This section details the list of parameters available in the properties screen of an email or [email template](../../start/using/about-templates.md).

>[!NOTE]
>
>Alcuni parametri sono disponibili solo nei modelli. Parameters you can access [depend on your permissions](../../administration/using/types-of-users.md).

To edit the properties of an email or an email template, use the **[!UICONTROL Edit properties]** button.

![](assets/delivery_options_1.png)

### General parameters {#general-parameters}

On the top of the email parameter screen, identify the email using the **[!UICONTROL Label]** and **[!UICONTROL ID]** fields. Queste informazioni vengono visualizzate nell'interfaccia ma non sono visibili ai destinatari del messaggio.

![](assets/delivery_options_2.png)

>[!CAUTION]
>
>L'ID deve essere univoco.

The **[!UICONTROL Brand]** field allows you to select the brand linked to the delivery. For more information on using and configuring brands, refer to the [Branding](../../administration/using/branding.md) section.

**[!UICONTROL Campaign]** Il campo consente di inserire la campagna collegata all'e-mail.

You can also add a **[!UICONTROL Description]** in the corresponding field and edit the image displayed on the email thumbnail in the lists.

### Sending parameters {#sending-parameters}

The **[!UICONTROL Send]** section is only available for email templates. Contiene i seguenti parametri:

#### Retries parameters {#retries-parameters}

I messaggi temporaneamente non consegnati sono soggetti a un ritry automatico. This section indicates how many retries should be performed the day after the send is started ( **[!UICONTROL Max. number of retries]** ) and the minimum delay between retries ( **[!UICONTROL Retry period]** ).

Per impostazione predefinita, cinque tentativi sono pianificati per il primo giorno con un intervallo minimo di un'ora, con estensione valida per 24 ore. One retry per day is programmed after that and until the delivery deadline, which is defined in the [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters) section.

Il numero di tentativi può essere modificato a livello globale (contattate l'amministratore tecnico di Adobe) oppure per ogni modello di consegna o consegna

The **[!UICONTROL Test SMTP delivery]** option allows you to test sending messages via SMTP. I messaggi vengono elaborati fino alla connessione con il server SMTP, ma non vengono inviati. For more information on configuring SMTP, refer to the [List of email SMTP parameters](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters) section.

#### Email format parameters {#email-format-parameters}

Potete configurare il formato delle e-mail da inviare. Sono disponibili tre opzioni:

* **Utilizzate le preferenze dei destinatari** (modalità predefinita): il formato del messaggio è definito in base ai dati memorizzati nel profilo destinatario e memorizzati per impostazione predefinita nel **campo del formato** e-mail (@ emailformat). Se un destinatario desidera ricevere i messaggi in un determinato formato, questo è il formato inviato. Se il campo non è stato completato, viene inviato un messaggio multiparte (vedi di seguito).
* **Consenti al client di posta elettronica di scegliere il formato più appropriato (multiparte)**: il messaggio contiene entrambi i formati: testo e HTML. Il formato visualizzato al ricevimento dipende dalla configurazione del software di posta (multiparte) del destinatario.

   >[!CAUTION]
   >
   >Questa opzione include entrambe le versioni del messaggio. Pertanto, influisce sulla distribuzione, in quanto la dimensione del messaggio è maggiore.

* **Invia tutti i messaggi in formato testo**: il messaggio viene inviato in formato testo. Il formato HTML non verrà inviato, ma utilizzato per la pagina speculare solo quando il destinatario fa clic sul collegamento nel messaggio.

### Validity period parameters {#validity-period-parameters}

**[!UICONTROL Validity]** La sezione contiene i seguenti parametri:

* **[!UICONTROL Explicitly set validity dates]**: quando questa casella non è selezionata, è necessario immettere una durata nei campi **[!UICONTROL Delivery duration]** e **[!UICONTROL Resource validity limit]** . Selezionate questa casella per definire orari e date specifici.
* **[!UICONTROL Delivery duration]**: Adobe Campaign invia i messaggi a partire dalla data iniziale. Questo campo consente di specificare la durata in cui i messaggi possono essere inviati.
* **[!UICONTROL Resource validity duration]**: questo campo viene usato per le risorse caricate, principalmente per la pagina speculare e le immagini. Le risorse presenti in questa pagina sono valide per un periodo limitato (per risparmiare spazio su disco).
* **[!UICONTROL Mirror page management]**: La pagina speculare è una pagina HTML accessibile online tramite un browser Web. Il suo contenuto è identico al contenuto dell'e-mail. Per impostazione predefinita, la pagina speculare viene generata se il collegamento viene inserito nel contenuto della posta. Questo campo consente di modificare il modo in cui viene generata la pagina:

   >[!CAUTION]
   >
   >Per la pagina speculare, è necessario definire un contenuto HTML per l'e-mail.

   * **[!UICONTROL Generate the mirror page if a mirror link appears in the email content]** (modalità predefinita): La pagina speculare viene generata se il collegamento viene inserito nel contenuto della posta.
   * **Forza la generazione della pagina speculare**: anche se nei messaggi non viene inserito alcun collegamento alla pagina speculare, viene creata la pagina speculare.
   * **Non generate la pagina speculare**: non viene generata alcuna pagina speculare, anche se il collegamento è presente nei messaggi.
   * **Genera una pagina speculare con accesso facilitato utilizzando solo l'ID messaggio**: questa opzione consente di accedere al contenuto della pagina speculare, con informazioni di personalizzazione, nella finestra del registro di consegna.

>[!NOTE]
>
>The **[!UICONTROL Explicitly set validity dates]** and **[!UICONTROL Delivery duration]** parameters do not apply to transactional messages. For more on transactional messaging, see [this section](../../channels/using/about-transactional-messaging.md).

### Tracking parameters {#tracking-parameters}

**[!UICONTROL Tracking]** La sezione contiene i seguenti parametri:

* **[!UICONTROL Activate tracking]**: consente di attivare/disattivare il tracciamento dell'URL dei messaggi. To manage tracking for each message URL, use the **[!UICONTROL Links]** icon in the Email Designer action bar. See [About tracked URLs](../../designing/using/about-tracked-urls.md).
* **[!UICONTROL Tracking validity limit]**: consente di definire la durata per la quale verrà attivato il tracciamento negli URL.
* **[!UICONTROL Substitution URL for expired URLs]**: potete inserire un URL per una pagina Web che verrà visualizzata una volta scaduto il tracciamento.

### Advanced parameters {#advanced-parameters}

**[!UICONTROL Advanced parameters]** La sezione contiene più parametri.

I primi due campi consentono di inserire le informazioni necessarie per le intestazioni del messaggio e-mail elaborate (indirizzo di risposta e testo dell'indirizzo di risposta). Queste informazioni possono essere personalizzate. A tal fine, fate clic sul pulsante a destra del campo che verrà modificato, quindi aggiungete i campi di personalizzazione. Inserting and using the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

#### Target context {#target-context}

Il contesto di targeting consente di definire un set di tabelle da utilizzare per il targeting delle e-mail (nella schermata di definizione del pubblico) e la personalizzazione (definizione dei campi di personalizzazione nell'editor di contenuto HTML).

#### Routing {#routing}

Questo campo indica la modalità di routing utilizzata. Fa riferimento a un account esterno. Ad esempio, questo può essere utilizzato per utilizzare un account esterno contenente configurazioni di branding specifiche.

>[!NOTE]
>
>External accounts are accessible via the **Administration** &gt; **Application settings** &gt; **External accounts** menu.

#### Preparation {#preparation}

Preparing messages is detailed in the [Approving messages](../../sending/using/preparing-the-send.md) section.

* **[!UICONTROL Typology]**: prima di qualsiasi invio, i messaggi devono essere preparati per convalidare il contenuto e la configurazione. The verification rules applied during the preparation phase are defined in a **typology**. Ad esempio, per le e-mail, la preparazione prevede il controllo dell'oggetto, degli URL e delle immagini, ecc. Selezionate la tipologia da applicare in questo campo.

   >[!NOTE]
   >
   >Typologies, which can be accessed via the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu, are presented in the [Typologies](../../administration/using/about-typology-rules.md) section.

* **[!UICONTROL Compute the label during delivery analysis]**: consente di calcolare il valore etichetta dell'e-mail durante la fase di preparazione del messaggio.
* **[!UICONTROL Save SQL queries in the log]**: questa opzione consente di aggiungere registri di query SQL nel diario durante la fase di preparazione.

### List of email SMTP parameters {#list-of-email-smtp-parameters}

**[!UICONTROL SMTP]** La sezione contiene i seguenti parametri:

* **[!UICONTROL Character encoding]**: Selezionate la **[!UICONTROL Force encoding]** casella per forzare la codifica dei messaggi, quindi selezionate la codifica da utilizzare.
* **[!UICONTROL Bounce mails]**: per impostazione predefinita, i messaggi di rimbalzo vengono ricevuti nella inbox di errore della piattaforma (definito nella schermata **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]****[!UICONTROL Email]** &gt; &gt; **[!UICONTROL Configuration]** ). To define a specific error address for an email, enter the address in the **[!UICONTROL Error address]** field.
* **[!UICONTROL Additional SMTP headers]**: questa opzione consente l'aggiunta di intestazioni SMTP aggiuntive ai messaggi. The script entered in the **[!UICONTROL Headers]** field must reference one header per line, in the form of **name:value**. Se necessario, i valori vengono codificati automaticamente.

   >[!CAUTION]
   >
   >L'aggiunta di uno script per l'inserimento di intestazioni SMTP aggiuntive è riservata agli utenti avanzati. La sintassi di questo script deve essere conforme ai requisiti di questo tipo di contenuto: nessuno spazio inutilizzato, nessuna riga vuota, ecc.

### List of access authorization parameters {#list-of-access-authorization-parameters}

**[!UICONTROL Access authorization]** La sezione contiene i seguenti parametri:

* **[!UICONTROL Organizational unit]** Il campo consente di limitare l'accesso a questa e-mail a determinati utenti. Gli utenti associati all'unità o alle unità padre specificate avranno accesso in lettura e scrittura a questa e-mail. Gli utenti associati a unità figlie avranno accesso solo in lettura a questa e-mail.

   >[!NOTE]
   >
   >You can configure organizational units via the **Administration** &gt; **Users &amp; Security** menu.

* The **[!UICONTROL Created by]**, **[!UICONTROL Created]**, **[!UICONTROL Modified by]** and **[!UICONTROL Last modified]** fields are automatically completed.

## Archiving emails {#archiving-emails}

Puoi configurare Adobe Campaign per conservare una copia delle e-mail inviate dalla tua piattaforma.

Tuttavia, Adobe Campaign non gestisce i file archiviati. Consente di inviare i messaggi scelti a un indirizzo dedicato, da dove possono essere elaborati e archiviati mediante un sistema esterno.

Quando viene attivato nel modello di consegna, questa funzione consente di inviare una copia esatta dei messaggi inviati corrispondenti a un indirizzo e-mail Ccn (invisibile ai destinatari della distribuzione) che devi specificare.

### Recommendations and limitations {#recommendations-and-limitations}

* Questa funzione è facoltativa. Controllate il contratto di licenza e contattate il vostro account executive per attivarlo.
* Potete utilizzare solo un indirizzo e-mail Ccn.
* Solo i messaggi e-mail inviati correttamente vengono presi in considerazione. Non sono disponibili.
* Per motivi di privacy, i messaggi e-mail CCN devono essere elaborati da un sistema di archiviazione in grado di memorizzare informazioni personali identificabili (PII).
* Quando create un nuovo modello di consegna, per impostazione predefinita CCN e-mail non è abilitato, anche se l'opzione è stata acquistata. Devi attivarlo manualmente in ogni modello di consegna in cui desideri utilizzarlo.

### Activating email archiving {#activating-email-archiving}

Email BCC is activated in the [email template](../../start/using/about-templates.md), through a dedicated option:

1. Go to **Resources** &gt; **Templates** &gt; **Delivery templates**.
1. Duplicate the out-of-the-box **[!UICONTROL Send via email]** template.
1. Selezionare il modello duplicato.
1. Click the **[!UICONTROL Edit properties]** button to edit the template's properties.
1. Expand the **[!UICONTROL Send]** section.
1. Check the **[!UICONTROL Archive emails]** box to keep a copy of all sent messages for each delivery based on this template.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.

