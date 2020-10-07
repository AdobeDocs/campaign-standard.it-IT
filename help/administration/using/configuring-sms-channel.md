---
title: Configurazione del canale SMS
description: '"Scopri i passaggi di configurazione per SMS: indirizzamento, codifica, formati e proprietà avanzate. "'
page-status-flag: never-activated
uuid: 5f13dbd5-9522-4199-8d9a-44c397cb2458
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 356d4d4f-3d5a-468c-bff8-96767cd8fff6
context-tags: extAccountMobile,overview;extAccount,main;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1625'
ht-degree: 99%

---


# Configurazione del canale SMS{#configuring-sms-channel}

Per inviare messaggi SMS, un amministratore deve configurare uno o più account esterni dal menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL SMS]** > **[!UICONTROL SMS accounts]**.

I passaggi per creare e modificare un account esterno sono descritti in dettaglio nella sezione [Account esterni](../../administration/using/external-accounts.md). Di seguito trovi i parametri specifici per account esterni per l’invio di messaggi SMS.

## Definizione di un indirizzamento SMS {#defining-an-sms-routing}

L’account esterno **[!UICONTROL SMS routing via SMPP]** viene fornito per impostazione predefinita, ma può essere utile aggiungere altri account.

Se desideri utilizzare il protocollo SMPP, puoi anche creare un nuovo account esterno. Per ulteriori informazioni sul protocollo e sulle impostazioni di SMS, consulta questa [nota tecnica](https://helpx.adobe.com/it/campaign/kb/sms-connector-protocol-and-settings.html).

1. Crea un nuovo account esterno da **[!UICONTROL Administration > Application settings > External accounts]**.
1. Definisci il tipo di account come **[!UICONTROL Routing]**, il canale come **[!UICONTROL Mobile (SMS)]** e la modalità di consegna come **[!UICONTROL Bulk delivery]**.

   ![](assets/sms_routing.png)

1. Definisci le impostazioni di connessione.

   Per immettere le impostazioni di connessione specifiche per l’invio di messaggi SMS, contatta il provider di servizi SMS che ti spiegherà come completare i diversi campi dell’account esterno.

   ![](assets/sms_connection.png)

   L’opzione **[!UICONTROL Enable TLS over SMPP]** ti consente di crittografare il traffico SMPP.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** ti consente di scaricare tutto il traffico SMPP nei file di log. Devi abilitare questa opzione per risolvere i problemi del connettore e per confrontare il traffico rilevato dal provider.

1. Contatta Adobe per ricevere il valore da immettere nel campo **[!UICONTROL SMS-C implementation name]**, a seconda del provider scelto.
1. Definisci le impostazioni del canale SMPP. Per ulteriori informazioni, consulta la sezione [Codifica e formati di SMS](#sms-encoding-and-formats).

   Abilita l’opzione **[!UICONTROL Store incoming MO in the database]** se desideri che tutti gli SMS in entrata siano archiviati nella tabella inSMS. Per ulteriori informazioni su come recuperare gli SMS in entrata, consulta questa [sezione](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   L’opzione **[!UICONTROL Enable Real-time KPI updates during SR processing]** ti consente di aggiornare i KPI (Key Performance Indicator) **[!UICONTROL Delivered]** o **[!UICONTROL Bounces + Errors]** in tempo reale dopo l’invio. Questi KPI si trovano nella finestra **[!UICONTROL Deployment]** e vengono ricalcolati direttamente dall’SR (Status Report) ricevuto dal provider.

   ![](assets/sms_connection_1.png)

1. Definisci i parametri **[!UICONTROL Throughput and timeouts]**.

   Puoi specificare il throughput massimo dei messaggi in uscita (&quot;MT&quot;, Mobile Terminated) in MT al secondo. Se inserisci &quot;0&quot; nel campo corrispondente, il throughput effettivo sarà illimitato.

   È necessario completare in secondi i valori di tutti i campi corrispondenti alle durate.

1. Definisci i parametri specifici di SMS-C nel caso sia necessario definire una mappatura di codifica specifica. Per ulteriori informazioni, consulta la sezione [Specifiche di SMSC](#smsc-specifics).

   Abilita l’opzione **[!UICONTROL Send full phone number (send characters other than digits)]** se non desideri rispettare il protocollo SMPP e trasferire il prefisso **[!UICONTROL +]** al server del provider SMS (SMS-C).

   Tuttavia, dato che alcuni provider richiedono l’uso del prefisso **[!UICONTROL +]**, ti consigliamo di verificare con il provider se è necessario abilitare questa opzione.

1. Se necessario, definisci le risposte automatiche per attivare le azioni in base al contenuto di una risposta. Per ulteriori informazioni, consulta [questa sezione](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Salva la configurazione dell’account esterno di indirizzamento SMS.

Ora puoi utilizzare il nuovo indirizzamento per inviare messaggi SMS con Adobe Campaign.

## Codifica e formati di SMS {#sms-encoding-and-formats}

### Codifica, lunghezza e traslitterazione di SMS {#sms-encoding--length-and-transliteration}

Per impostazione predefinita, il numero di caratteri in un SMS soddisfa gli standard GSM (Global System for Mobile Communications).

I messaggi SMS che utilizzano la codifica GSM sono limitati a 160 caratteri o 153 caratteri per SMS per messaggi inviati in più parti.

>[!NOTE]
>
>Alcuni caratteri contano come due (parentesi graffe e quadre, il simbolo dell’euro, ecc.). L’elenco dei caratteri GSM disponibili è presentato nella sezione [Tabella di caratteri - GSM Standard](#table-of-characters---gsm-standard).

Se lo desideri, puoi autorizzare la traslitterazione di caratteri selezionando la casella corrispondente.

![](assets/sms_transliteration.png)

La traslitterazione consiste nel sostituire un carattere di un SMS con un altro quando quel carattere non è preso in considerazione dallo standard GSM.

* Se la traslitterazione è **autorizzata**, ogni carattere non preso in considerazione viene sostituito da un carattere GSM al momento dell’invio del messaggio. Ad esempio, la lettera &quot;ë&quot; è sostituita da &quot;e&quot;. Il messaggio viene quindi leggermente modificato, ma il limite di caratteri rimane lo stesso.
* Quando la traslitterazione **non è autorizzata**, ogni messaggio che contiene caratteri non presi in considerazione viene inviato in formato binario (Unicode): tutti i caratteri vengono pertanto inviati così come sono. Tuttavia, i messaggi SMS che utilizzano Unicode sono limitati a 70 caratteri (o 67 caratteri per SMS per messaggi inviati in più parti). Se viene superato il numero massimo di caratteri, vengono inviati diversi messaggi, il che potrebbe comportare costi aggiuntivi.

>[!IMPORTANT]
>
>L’inserimento di campi di personalizzazione nel contenuto del messaggio SMS può introdurre caratteri che non vengono presi in considerazione dalla codifica GSM. Un esempio di contenuti simili è disponibile nella sezione [Personalizzazione di messaggi SMS](../../channels/using/personalizing-sms-messages.md).

Per impostazione predefinita, la traslitterazione di caratteri è disabilitata. Se desideri che tutti i caratteri nei messaggi SMS rimangano invariati, per non modificare ad esempio i nomi propri, ti consigliamo di non abilitare questa opzione.

Tuttavia, se i messaggi SMS contengono molti caratteri che generano messaggi Unicode, puoi abilitare questa opzione per limitare i costi di invio dei messaggi.

### Tabella di caratteri - GSM Standard {#table-of-characters---gsm-standard}

Questa sezione presenta i caratteri presi in considerazione dallo standard GSM. Tutti i caratteri inseriti nel corpo del messaggio, diversi da quelli indicati di seguito, convertono l’intero messaggio in formato binario (Unicode) e quindi lo limitano a 70 caratteri. Per ulteriori informazioni, consulta la sezione [Codifica, lunghezza e traslitterazione di SMS](#sms-encoding--length-and-transliteration).

**Caratteri base**

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

SP: Space

ESC: Escape

LF: Line Feed (avanzamento di riga)

CR: Carriage Return (ritorno a capo)

**Caratteri avanzati (contati due volte)**

^ { } [ ~ ] | €

### Specifiche di SMSC {#smsc-specifics}

>[!NOTE]
>
>Queste opzioni ti consentono di adattare il connettore in modo che funzioni con SMSC non standard (ovvero non esattamente conforme alla specifica di SMPP 3.4) o con requisiti di codifica specifici e solo gli utenti esperti dovrebbero configurarle.

Al momento di inviare un messaggio SMS, Adobe Campaign può utilizzare una o più codifiche di testo. Ogni codifica ha un set di caratteri specifico e determina il numero di caratteri da includere in un messaggio SMS.

Il campo **[!UICONTROL DATA_CODING]** consente ad Adobe Campaign di comunicare all’SMS-C quale codifica viene utilizzata.

>[!NOTE]
>
>La mappatura tra il valore **data_coding** e la codifica effettivamente utilizzata è standardizzata. Tuttavia, alcuni SMS-C hanno una mappatura specifica: in questo caso, l’amministratore di **Adobe Campaign** deve dichiarare questa mappatura. Consulta il provider per saperne di più.

La funzionalità **[!UICONTROL Define a specific mapping of encodings]** ti consente di dichiarare **data_codings** e di forzare la codifica, se necessario: a questo scopo, specifica una singola codifica nella tabella.

**Configurazione**

* Quando la funzionalità **[!UICONTROL Define a specific mapping of encodings]** non è selezionata, il connettore assume un comportamento generico:

   * Prova a utilizzare la codifica GSM a cui assegna il valore **data_coding = 0**.
   * Se non è possibile usare la codifica GSM, utilizza la codifica **UCS2** assegnandole il valore **data_coding = 8**.

   ![](assets/sms_data_coding.png)

* Quando la funzionalità **[!UICONTROL Define a specific mapping of encodings]** è selezionata, puoi definire sia le codifiche desiderate che i valori dei campi **[!UICONTROL data_coding]** collegati. Adobe Campaign cerca di utilizzare la prima codifica nell’elenco, quindi la seguente, se la prima codifica risulta impossibile.

   L’ordine di dichiarazione è importante: ti consigliamo di inserire l’elenco in ordine crescente **di costo** per favorire le codifiche che ti consentono di contenere il maggior numero possibile di caratteri in ogni messaggio SMS.

   Dichiara solo le codifiche che desideri utilizzare. Se alcune delle codifiche fornite dall’SMS-C non dovessero corrispondere allo scopo di utilizzo, non dichiararle nell’elenco.

   ![](assets/sms_data_coding1.png)

### Risposta automatica inviata al MO {#automatic-reply-sent-to-the-mo}

Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, puoi configurare messaggi da inviargli automaticamente e l’azione da eseguire.

Per ulteriori informazioni, consulta [questa sezione](../../channels/using/managing-incoming-sms.md).

## Configurazione delle proprietà di SMS {#configuring-sms-properties}

Questa sezione descrive l’elenco di parametri unici dell’SMS nella schermata delle proprietà di una consegna SMS o di un modello SMS.

I parametri specifici per l’invio di messaggi SMS sono raggruppati nelle sezioni **[!UICONTROL Send]** e **[!UICONTROL Advanced parameters]**.

![](assets/sms_options.png)

From the **[!UICONTROL Advanced parameters]** section:

* L’opzione **[!UICONTROL From]** ti consente di personalizzare il nome del mittente del messaggio SMS utilizzando una stringa di caratteri. Questo è il nome visualizzato come mittente del messaggio SMS sul telefono cellulare del destinatario.

   Se questo campo è vuoto, viene quindi utilizzato il numero di origine fornito nell’account esterno. Se non viene fornito alcun numero di origine, viene utilizzato il codice breve. L’account esterno specifico per la consegna SMS è presentato nella sezione [Definizione di un indirizzamento SMS](#defining-an-sms-routing).

   ![](assets/sms_smpp_2.png)

   >[!IMPORTANT]
   >
   >Controlla le leggi vigenti nel tuo paese riguardo alla modifica dell’indirizzo del mittente. Dovresti anche verificare con il provider di servizi SMS se offre questa funzionalità.

Dalla **[!UICONTROL Send]** sezione di un modello SMS:

* L’opzione **[!UICONTROL Maximum number of SMS per message]** ti consente di definire il numero di messaggi SMS da utilizzare per inviare un messaggio. Se questo numero viene superato, il messaggio non viene inviato.

   >[!IMPORTANT]
   >
   >Se hai inserito campi di personalizzazione o testo condizionale nel contenuto del tuo messaggio SMS, la lunghezza del messaggio e, di conseguenza, il numero di messaggi SMS da inviare possono variare da un destinatario all’altro. Per ulteriori informazioni, consulta la sezione [Personalizzazione di messaggi SMS](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_smpp_3.png)

* Il campo **[!UICONTROL Transmission mode]** ti consente di determinare il metodo di consegna di messaggi SMS:

   * **[!UICONTROL Saved on SIM card]**: il messaggio viene archiviato sulla scheda SIM del destinatario.
   * **[!UICONTROL Saved on mobile]**: il messaggio viene archiviato nella memoria interna del telefono.
   * **[!UICONTROL Flash]**: il messaggio viene visualizzato sul telefono cellulare del destinatario come notifica, quindi scompare e non viene salvato.
