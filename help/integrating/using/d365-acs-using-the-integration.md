---
title: Utilizzo dell'integrazione con Microsoft Dynamics 365
description: Scopri come utilizzare Microsoft Dynamics 365 con integrazione Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 0%

---


# Utilizzo dell&#39;integrazione di Microsoft Dynamics 365

Esistono diversi flussi di dati che l&#39;integrazione di Adobe Campaign Standard  con Microsoft Dynamics 365 esegue. Questi flussi sono descritti in [questa pagina](../../integrating/using/d365-acs-self-service-app-workflows.md).

Ulteriori dettagli sui flussi di dati sono disponibili in questo documento nella sezione [Flussi di dati](#data-flows).

##  esperienza utente Adobe Campaign Standard

Quando un contatto viene creato, modificato o eliminato (se eliminato è abilitato) in Microsoft Dynamics 365, verrà inviato al Campaign Standard. Questi contatti saranno visibili nella schermata Profili di Campaign e possono essere indirizzati alle campagne di marketing. Vedere la schermata Profili di seguito.

![](assets/MSdynamicsACS-usage1.png)

Quando un attributo di rinuncia viene modificato in Campaign, verrà riflesso in Dynamics 365 se hai selezionato la configurazione di rifiuto **Unidirezionale (Campaign to Microsoft Dynamics 365)** o **Bidirezionale** e se hai mappato correttamente tale attributo specifico.

## Esperienza utente di Microsoft Dynamics 365

Per iniziare, i seguenti eventi di marketing e-mail vengono inviati da Campaign a Dynamics 365 e visualizzati nella visualizzazione Timeline di Microsoft Dynamics 365 come attività personalizzate:

*  e-mail Adobe Campaign

*  Adobe Campaign Email Open

*  URL e-mail Adobe Campaign

*  messaggio di posta elettronica Adobe Campaign

Per visualizzare la timeline di un contatto, accedi all&#39;elenco dei contatti facendo clic su Sales Hub dal menu a discesa Dynamics 365. Fate clic su Contatti nella barra del menu a sinistra e selezionate un contatto.

>[!NOTE]
>
>Per visualizzare questi eventi, è necessario installare l&#39;app **Adobe Campaign per Microsoft Dynamics 365** in AppSource nell&#39;istanza di Microsoft Dynamics 365. [Ulteriori informazioni](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Di seguito è riportata un&#39;istantanea della schermata Contatti per &quot;Dynamics User&quot;. Nella visualizzazione Timeline, noterete che all&#39;utente di Dynamics è stato inviato un messaggio e-mail associato con Nome campagna &quot;2019LoyaltyCamp&quot; e Nome consegna &quot;DM190&quot;. Dynamics User ha aperto l&#39;e-mail e ha fatto clic su un URL nell&#39;e-mail; entrambe queste azioni hanno creato eventi che vengono visualizzati anche di seguito. Se si guarda all&#39;angolo destro, viene visualizzata la scheda RA (Relationship Assistant); al momento, contiene un&#39;attività da seguire sull&#39;URL su cui è stato fatto clic.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Vedere di seguito per una panoramica della visualizzazione Timeline per l&#39;utente di Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Di seguito è riportato un primo piano della scheda Relationship Assistant (RA). L&#39;app AppSource contiene un flusso di lavoro che controlla un evento Click per l&#39;URL e-mail  Adobe. Quando si verifica questo evento, crea un&#39;attività e imposta una data di scadenza. Questo consente all&#39;attività di essere visualizzata nella scheda RA, conferendogli un&#39;ulteriore visibilità. Esiste un flusso di lavoro simile per  eventi di rimbalzo e-mail di Adobe, con l&#39;aggiunta di un&#39;attività per riconciliare l&#39;indirizzo e-mail non valido. Questi flussi di lavoro possono essere disattivati nella soluzione.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se si fa clic sull&#39;oggetto dell&#39;evento di invio, verrà visualizzato un modulo simile a quello riportato di seguito. I moduli per gli eventi open e bounce sono simili.

![](assets/do-not-localize/mirror_page_url_send.png)

Il modulo per gli eventi click URL e-mail aggiunge un attributo aggiuntivo per l&#39;URL su cui è stato fatto clic:

![](assets/do-not-localize/mirror_page_url_click.png)

Segue un elenco degli attributi e una descrizione:

* **Oggetto**: Oggetto dell&#39;evento; composto dall&#39;ID campagna e dall&#39;ID di consegna dell&#39;e-mail di consegna

* **Proprietario**: Utente dell&#39;applicazione creato nei passaggi successivi al provisioning

* **Per** quanto riguarda: Nome del contatto

* **Nome** campagna: ID campagna in Campaign Standard

* **Nome** consegna: L&#39;ID di consegna in Campaign Standard

* **Data Di Invio/Apertura/Clic/Bloccato**: Data/ora in cui è stato creato l’evento

* **URL** tracciamento: URL su cui è stato fatto clic

* **URL** pagina mirror: URL della pagina mirror dell’e-mail che è stata inviata/aperta/su cui è stato fatto clic/che è stata rimbalzata. Il periodo di scadenza della pagina mirror dell&#39;e-mail può essere modificato nella schermata di configurazione dell&#39;attività del canale e-mail della campagna corrispondente. [Ulteriori informazioni](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Per l&#39;opzione di rifiuto, quando un attributo di rinuncia viene modificato in Microsoft Dynamics 365, verrà visualizzato in Campaign se avete selezionato la configurazione di rifiuto **Unidirezionale (Campaign to Microsoft Dynamics 365)** o **Bidirezionale** e se tale attributo è stato mappato correttamente.

## Flussi di dati {#data-flows}

### Contatto e ingresso entità personalizzato

Record nuovi, aggiornati ed eliminati (Nota: eliminato deve essere attivato) viene inviato dalla tabella dei contatti di Microsoft Dynamics 365 alla tabella dei profili di Campaign.

Le mappature delle tabelle possono essere configurate nell&#39;interfaccia utente dell&#39;applicazione di integrazione per mappare gli attributi della tabella di Microsoft Dynamics 365 agli attributi della tabella di Campaign. Le mappature delle tabelle possono essere modificate per aggiungere o rimuovere attributi, in base alle esigenze.

L&#39;esecuzione iniziale del flusso di dati è progettata per trasferire tutti i record mappati, compresi quelli contrassegnati come &quot;inattivi&quot;; in seguito, l&#39;integrazione elaborerà solo gli aggiornamenti incrementali. Fa eccezione la riproduzione dei dati o la configurazione di un filtro; regole di filtraggio di base basate sugli attributi possono essere configurate per determinare quali record sincronizzare in Campaign.

Le regole di sostituzione di base possono essere configurate nell&#39;interfaccia utente dell&#39;applicazione di integrazione per sostituire un valore attributo con un valore diverso (ad esempio, &quot;verde&quot; per &quot;#00FF00&quot;, &quot;F&quot; per 1, ecc.).

A seconda del volume di record, potrebbe essere necessario utilizzare l&#39;archivio SFTP della campagna per il trasferimento iniziale dei dati. [Ulteriori informazioni](#initial-data-transfer).

L&#39;attributo externalId della tabella del profilo della campagna deve essere popolato con l&#39;attributo contatto contactId di Dynamics 365 per consentire il funzionamento dell&#39;ingresso del contatto. Le entità personalizzate della campagna devono essere popolate anche con un attributo ID univoco di Dynamics 365; tuttavia, questo attributo può essere memorizzato in qualsiasi attributo di entità personalizzata di Campaign (vale a dire, non deve essere externalId).

>[!NOTE]
>
>Per l&#39;ingresso di entità personalizzata, il tracciamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.

#### Entità personalizzate

L&#39;integrazione di [Microsoft Dynamics 365- Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) supporta entità personalizzate, consentendo la sincronizzazione delle entità personalizzate in Dynamics 365 con le risorse personalizzate corrispondenti in Campaign.

I nuovi dati contenuti nelle risorse personalizzate possono essere utilizzati per diversi scopi, tra cui segmentazione e personalizzazione.

L&#39;integrazione supporta tabelle collegate e non collegate. Il collegamento è supportato fino a tre livelli (livello1->livello2->livello3).

>[!IMPORTANT]
>
>Se un qualsiasi record di risorse personalizzato della campagna contiene informazioni personali, si applicano raccomandazioni specifiche. Ulteriori informazioni [in questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).


Quando si configurano flussi di dati di entità personalizzati, è importante tenere presente quanto segue:

* La creazione e la modifica di risorse personalizzate per Campaign sono operazioni sensibili che devono essere eseguite solo da utenti esperti.
* Per i flussi di dati di entità personalizzati, il tracciamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.
* Se in Dynamics 365 viene creato un record padre e un record figlio collegato vicino alla stessa ora, a causa dell&#39;elaborazione parallela dell&#39;integrazione, è possibile che un nuovo record figlio venga scritto in Campaign prima del record padre.

* Se il padre e il figlio sono collegati sul lato della campagna utilizzando l&#39;opzione **1 collegamento semplice della cardinalità**, il record figlio rimarrà nascosto e inaccessibile (tramite interfaccia utente o API) fino all&#39;arrivo del record padre in Campaign.

* (Presupponendo che **1 collegamento semplice per cardinalità** nella campagna) Se il record figlio viene aggiornato o eliminato in Dynamics 365, e che tale modifica viene scritta in Campaign prima che il record padre venga visualizzato in Campaign (non probabile, ma una possibilità remota), tale aggiornamento o eliminazione non verrà elaborato in Campaign e verrà generato un errore. In caso di aggiornamento, il record in questione dovrà essere aggiornato di nuovo in Dynamics 365 per sincronizzare il record aggiornato. In caso di eliminazione, il record in questione dovrà essere gestito separatamente sul lato Campaign, poiché non esiste più un record in Dynamics 365 da eliminare o aggiornare.

* Se ti trovi in una situazione in cui credi di avere dei record figlio nascosti e non hai modo di accedervi, puoi cambiare temporaneamente il tipo di collegamento cardinalità su **0 o 1 cardinalità link semplice** per accedere a tali record.

Una panoramica più completa delle risorse personalizzate per Campaign si trova [in questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

### Flusso eventi di marketing e-mail{#email-marketing-event-flow}

Gli eventi di marketing e-mail vengono inviati da Campaign a Microsoft Dynamics 365 per essere visualizzati nella visualizzazione Timeline.

Tipi di eventi di marketing supportati:
* Invia - E-mail inviata al destinatario
* Apri - E-mail aperta dal destinatario
* Click - URL all&#39;interno dell&#39;e-mail cliccato dal destinatario
* Rimbalzo - E-mail al destinatario ha subito un duro rimbalzo

In Dynamics 365 vengono visualizzati i seguenti attributi evento:
* Nome campagna di marketing
* Nome consegna e-mail
* Timestamp
* URL pagina mirror e-mail
* URL su cui è stato fatto clic (solo eventi clic)

Gli eventi di marketing e-mail possono essere attivati/disattivati per tipo (invio, apertura, clic, rimbalzo) in modo che solo i tipi di evento selezionati vengano passati a Dynamics 365.

### Flusso di rifiuto {#opt-out-flow}

I valori di rifiuto (ad esempio, elenco Bloccati) sono sincronizzati tra i sistemi; al momento della registrazione, potete scegliere tra le seguenti opzioni:

* **Unidirezionale (da Microsoft Dynamics 365 a Campaign)**: Dynamics 365 è l&#39;origine della verità per i opt-out. Gli attributi di rifiuto verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard&quot;
* **Unidirezionale (da Campaign a Microsoft Dynamics 365)**: Il Campaign Standard è la fonte di verità per le opposizioni. Gli attributi di rifiuto verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* **Bidirezionale**: Dynamics 365 AND Campaign Standard sono entrambe fonti di verità. Gli attributi di rifiuto verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

In alternativa, se si dispone di un processo separato per gestire la sincronizzazione di rinuncia tra i sistemi, il flusso di dati di rinuncia dell&#39;integrazione può essere disattivato.

>[!NOTE]
>
>Nell&#39;interfaccia utente dell&#39;applicazione di integrazione, i **casi di utilizzo unidirezionali (da Microsoft Dynamics 365 a Campaign)** e **bidirezionale** sono configurati in un flusso di lavoro di rifiuto separato. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>Il caso di utilizzo di **Unidirezionale (Campaign to Microsoft Dynamics 365)** è un&#39;eccezione; è configurato all’interno del flusso di lavoro Ingresso (contatto con profilo).


La mappatura del flusso di rifiuto deve essere specificata dal cliente, in quanto i requisiti aziendali possono essere diversi tra le società. Dal lato della campagna, per la mappatura di rifiuto è possibile utilizzare solo gli attributi di rinuncia OOTB:

* elenco Bloccati
* DengListEmail
* DengListFax
* DengListMobile
* DengListPhone
* DengListPostalMail
* DengListPushnotification
* ccpaOptOut

In Dynamics 365, la maggior parte dei campi di rinuncia ha il prefisso &quot;donot&quot;; tuttavia, se i tipi di dati sono compatibili, è anche possibile utilizzare altri attributi a scopo di rifiuto.

### Trasferimento dati iniziale {#initial-data-transfer}

Il trasferimento iniziale dei dati potrebbe richiedere alcuni minuti a seconda del numero di record che si sta acquisendo da Microsoft Dynamics 365. Dopo il trasferimento iniziale dei dati, l&#39;integrazione riprenderà gli aggiornamenti incrementali.
