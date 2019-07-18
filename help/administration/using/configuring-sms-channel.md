---
title: Configurazione del canale SMS
seo-title: Configurazione del canale SMS
description: Configurazione del canale SMS
seo-description: '" Consulta i passaggi di configurazione SMS: operazioni di instradamento, codifica, formati e proprietà avanzate. "'
page-status-flag: never-activated
uuid: 5 f 13 dbd 5-9522-4199-8 d 9 a -44 c 397 cb 2458
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: configuring-channels
discoiquuid: 356 d 4 d 4 f -3 d 5 a -468 c-bff 8-96767 cd 8 fff 6
context-tags: Extaccountmobile, panoramica; Extaccount, main; delivery, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Configuring SMS channel{#configuring-sms-channel}

To send SMS messages, one or several external accounts must be configured by an administrator under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL SMS]** &gt; **[!UICONTROL SMS accounts]** menu.

The steps for creating and modifying an external account are detailed in the [External accounts](../../administration/using/external-accounts.md) section. Sotto i parametri specifici di account esterni per l'invio di messaggi SMS.

## Defining an SMS Routing {#defining-an-sms-routing}

The external account **[!UICONTROL SMS routing via SMPP]** is provided by default, but it can be useful to add other accounts.

Se desiderate utilizzare il protocollo SMPP, potete anche creare un nuovo account esterno. For more information on SMS protocol and settings, refer to this [technical note](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Create a new external account from **[!UICONTROL Administration > Application settings > External accounts]**.
1. Define the account type as **[!UICONTROL Routing]**, the channel as **[!UICONTROL Mobile (SMS)]** and the delivery mode as **[!UICONTROL Bulk delivery]**.

   Once these routing parameters have been defined, the SMS connector ( **[!UICONTROL Generic SMPP]** ) is selected automatically. Questo connettore consente ad Adobe Campaign di inviare messaggi SMS direttamente ai profili di destinazione connettendosi a un breve centro di servizi di messaggio (SMS-C) tramite il protocollo SMPP.

   ![](assets/sms_routing.png)

1. Definire le impostazioni di connessione.

   Per immettere le impostazioni di connessione specifiche per l'invio dei messaggi SMS, contattate il provider di servizi SMS che fornirà spiegazioni su come completare i diversi campi account esterni.

   ![](assets/sms_connection.png)

   The **[!UICONTROL Enable TLS over SMPP]** option allows you to encrypt SMPP traffic.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** consente di scaricare tutto il traffico SMPP nei file di registro. Questa opzione deve essere attivata per risolvere eventuali problemi del connettore e per confrontare il traffico visualizzato dal fornitore.

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. Definite le impostazioni del canale SMPP. You can learn more in the [SMS encoding and formats](../../administration/using/configuring-sms-channel.md#sms-encoding-and-formats) section.

   Enable the **[!UICONTROL Store incoming MO in the database]** if you want all incoming SMS to be stored in the inSMS table. For more information on how to retrieve your incoming SMS, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   The **[!UICONTROL Enable Real-time KPI updates during SR processing]** option allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. These KPIs can be found in the **[!UICONTROL Deployment]** window and are directly recalculated from the SR (Status Report) received from the provider.

   ![](assets/sms_connection_1.png)

1. Define the **[!UICONTROL Throughput and timeouts]** parameters.

   Puoi specificare la velocità massima di messaggi in uscita ("MT", Mobile Terminated) in MT al secondo. Se immettete "0" nel campo corrispondente, la velocità sarà illimitata.

   I valori di tutti i campi corrispondenti alle durate devono essere completati in secondi.

1. Definite i parametri specifici di SMS-C nel caso in cui sia necessario definire una specifica mappatura di codifica. For more information, refer to the [SMSC specifics](../../administration/using/configuring-sms-channel.md#smsc-specifics) section.

   Enable the **[!UICONTROL Send full phone number (send characters other than digits)]** option if you don't want to respect the SMPP protocol and transfer the **[!UICONTROL +]** prefix to the server of the SMS provider (SMS-C).

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. Se necessario, definire risposte automatiche per attivare azioni in base al contenuto di una risposta. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Salvate la configurazione dell'account esterno di instradamento SMS.

Ora puoi utilizzare il nuovo indirizzamento per inviare messaggi SMS con Adobe Campaign.

## SMS encoding and formats {#sms-encoding-and-formats}

### SMS encoding, length and transliteration {#sms-encoding--length-and-transliteration}

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications).

I messaggi SMS con codifica GSM sono limitati a 160 caratteri, oppure 153 caratteri per SMS per messaggi inviati in più parti.

>[!NOTE]
>
>Alcuni caratteri contano come due (parentesi quadre, quadre quadre, simbolo euro ecc.). The list of available GSM characters is presented in the [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard) section.

Se lo si desidera, è possibile autorizzare la trasformazione dei caratteri controllando la casella corrispondente.

![](assets/sms_transliteration.png)

La traslittura consiste nella sostituzione di un carattere di SMS per un altro quando tale carattere non viene considerato dallo standard GSM.

* If transliteration is **authorized**, each character that is not taken into account is replaced by a GSM character when the message is sent. Ad esempio, la lettera "ë" viene sostituita da "e". Il messaggio viene quindi leggermente modificato, ma il limite di caratteri rimarrà invariato.
* When transliteration is **not authorized**, each message that contains characters that are not taken into account is sent in binary format (Unicode): all of the characters are therefore sent as they are. Tuttavia, i messaggi SMS con Unicode sono limitati a 70 caratteri (o 67 caratteri per SMS per messaggi inviati in più parti). Se viene superato il numero massimo di caratteri, vengono inviati diversi messaggi, che possono quindi creare costi aggiuntivi.

>[!CAUTION]
>
>L'inserimento di campi personalizzati nel contenuto del messaggio SMS può introdurre caratteri che non vengono considerati in base alla codifica GSM. A content example is offered in the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

Per impostazione predefinita, la trasformazione dei caratteri è disattivata. Se desiderate mantenere invariati tutti i caratteri nei messaggi SMS, per non modificare i nomi corretti ad esempio, è consigliabile non abilitare questa opzione.

Tuttavia, se i messaggi SMS contengono molti caratteri che generano messaggi Unicode, potete scegliere di abilitare questa opzione per limitare i costi di invio dei messaggi.

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

In questa sezione sono presentati i caratteri presi in considerazione dallo standard GSM. Tutti i caratteri inseriti nel corpo del messaggio, diversi da quelli indicati di seguito, convertono l'intero messaggio in formato binario (Unicode) e quindi limitarlo a 70 caratteri. For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

**Caratteri di base**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP: Spazio

ESC: Esc

LF: Feed linea

CR: Ritorno a capo

**Caratteri avanzati (contati due volte)**

^ { } [ ~ ] | €

### SMSC specifics {#smsc-specifics}

>[!NOTE]
>
>Queste opzioni consentono di adattare il connettore per lavorare con SMSC non standard (ovvero non con esattamente le specifiche SMPP 3.4) oppure con requisiti di codifica specifici e devono essere configurati solo dagli utenti avanzati.

Quando si invia un messaggio SMS, Adobe Campaign può utilizzare una o più codifiche di testo. Ogni codifica ha un proprio set di caratteri specifico e determina il numero di caratteri che rientrano in un messaggio SMS.

**[!UICONTROL DATA_CODING]** Il campo consente ad Adobe Campaign di comunicare con SMS-C quale codifica viene utilizzata.

>[!NOTE]
>
>The mapping between the **data_coding** value and the encoding actually used is standardized. Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. Per ulteriori informazioni, consultate il vostro fornitore.

**[!UICONTROL Define a specific mapping of encodings]** La funzionalità consente di dichiarare **i dati data_ codings** e di forzare la codifica, se necessario: A tal fine, specificare una codifica singola nella tabella.

**Configurazione**

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is not checked, the connector takes on a generic behavior:

   * It will try to use GSM encoding to which it assigns the value **data_coding = 0**.
   * If GSM encoding fails, it will use **UCS2** encoding to which it assigns the value **data_coding = 8**.
   ![](assets/sms_data_coding.png)

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is checked, you can define the encodings that you would like to use as well as the linked **[!UICONTROL data_coding]** field values. Adobe Campaign proverà a utilizzare la prima codifica nell'elenco, quindi le seguenti, se la prima codifica risulta impossibile.

   The order of declaration is important: it is recommended that you put the list in ascending order **of cost** in order to favor the encodings allowing you to fit as many characters as possible in each SMS message.

   Dichiarare solo le codifiche che si desidera utilizzare. Se alcune codifiche fornite da SMS-C non devono corrispondere a quelle dell'uso, non dichiararle nell'elenco.

   ![](assets/sms_data_coding1.png)

### Automatic reply sent to the MO {#automatic-reply-sent-to-the-mo}

Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, è possibile configurare messaggi che vengono inviati automaticamente e l'azione da eseguire.

For more information, refer to [this section](../../channels/using/managing-incoming-sms.md).

## Configuring SMS properties {#configuring-sms-properties}

Questa sezione descrive l'elenco di parametri univoci di SMS nella schermata Proprietà di una consegna SMS o di un modello SMS.

The specific parameters for sending SMS messages are regrouped in the **[!UICONTROL Send]** and in the **[!UICONTROL Advanced parameters]** sections.

![](assets/sms_options.png)

* The **[!UICONTROL From]** option allows you to personalize the name of the SMS message sender using a string of characters. Si tratta del nome che verrà visualizzato come nome mittente del messaggio SMS sul telefono cellulare del destinatario.

   Se questo campo è vuoto, sarà il numero di origine fornito nell'account esterno che verrà utilizzato. Se non viene fornito alcun numero di origine, sarà il codice breve che verrà utilizzato. The external account specific to SMS delivery is presented in the [External SMS account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >Controllate la normativa del vostro paese in merito alla modifica dell'indirizzo del mittente. È inoltre necessario rivolgersi al provider di servizi SMS per verificare se offrire questa funzionalità.

* The **[!UICONTROL Maximum number of SMS per message]** option allows you to define the number of SMS messages to use to send a message. Se questo numero viene superato, il messaggio non verrà inviato.

   >[!CAUTION]
   >
   >Se sono stati inseriti campi di personalizzazione o testo condizionale nel contenuto del messaggio SMS, la lunghezza del messaggio e, come risultato, il numero di messaggi SMS da inviare possono variare da un destinatario all'altro. For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

* **[!UICONTROL Transmission mode]** Il campo consente di determinare il metodo di consegna per i messaggi SMS:

   * **[!UICONTROL Saved on SIM card]**: il messaggio viene memorizzato nella scheda SIM del destinatario.
   * **[!UICONTROL Saved on mobile]**: il messaggio viene memorizzato nella memoria interna del telefono.
   * **[!UICONTROL Flash]**: il messaggio viene visualizzato sul telefono mobile del destinatario come notifica, quindi scompare senza essere salvato.

