---
title: Utilizzare l’integrazione con Microsoft Dynamics 365
description: Scopri come utilizzare Microsoft Dynamics 365 con integrazione Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cd1cbf907eb160b6bbc1a2a2d3dd1c601ac13635
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 0%

---


# Utilizzare l’integrazione con Microsoft Dynamics 365

Questa integrazione può eseguire diversi processi:

* **Ingresso**:

   * Inserire **i contatti** da Dynamics 365 in Campaign

   * **Entità** personalizzate: Inserisci tabelle personalizzate da Dynamics 365 a Campaign. Ulteriori informazioni [in questa sezione](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Avanzamento**: Consegnare eventi di marketing via e-mail da ACS a D365 (invio e-mail, apertura, clic, rimbalzo)

* **Rifiuto**: Sincronizzazione bidirezionale dello stato di rifiuto (ad esempio,  inserii nell&#39;elenco Bloccati)

Ulteriori dettagli sui flussi di dati sono disponibili [in questa sezione](#data-flows).

##  esperienza utente Adobe Campaign Standard

Quando un contatto viene creato, modificato (o eliminato, se attivato) in Dynamics 365, verrà inviato a Campaign.  Questi contatti saranno visibili nella schermata Profili di Campaign e possono essere indirizzati alle campagne di marketing.  Vedere la schermata Profili di seguito.

![](assets/MSdynamicsACS-usage1.png)

Quando un attributo di rinuncia viene modificato in Campaign, verrà riflesso in Dynamics 365 se hai selezionato la configurazione Campaign-to-Dynamics 365 o di opt-out bidirezionale e se hai mappato correttamente tale attributo specifico.

## Esperienza utente di Microsoft Dynamics 365

Per iniziare, i seguenti eventi di marketing e-mail vengono inviati da Campaign a Dynamics 365 e visualizzati nella visualizzazione Timeline di Dynamics 365 come attività personalizzate:

*  e-mail Adobe Campaign

*  Adobe Campaign Email Open

*  URL e-mail Adobe Campaign

*  messaggio di posta elettronica Adobe Campaign

Per visualizzare la timeline di un contatto, accedi all&#39;elenco dei contatti facendo clic su Sales Hub dal menu a discesa Dynamics 365.  Fate clic su Contatti nella barra del menu a sinistra e selezionate un contatto.

>[!NOTE]
>
>Per visualizzare questi eventi, è necessario installare l&#39;app  Adobe Campaign per Dynamics 365 in AppSource nell&#39;istanza Dynamics 365.

Di seguito è riportata un&#39;istantanea della schermata Contatti per &quot;Dynamics User&quot;.  Nella visualizzazione Timeline, noterete che all&#39;utente di Dynamics è stato inviato un messaggio e-mail associato con Nome campagna &quot;2019LoyaltyCamp&quot; e Nome consegna &quot;DM190&quot;.  Dynamics User ha aperto l&#39;e-mail e ha fatto clic su un URL nell&#39;e-mail; entrambe queste azioni hanno creato eventi che vengono visualizzati anche di seguito.  Se si guarda all&#39;angolo destro, viene visualizzata la scheda RA (Relationship Assistant); al momento, contiene un&#39;attività da seguire sull&#39;URL su cui è stato fatto clic.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Vedere di seguito per una panoramica della visualizzazione Timeline per l&#39;utente di Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Di seguito è riportato un primo piano della scheda Relationship Assistant (RA).  L&#39;app AppSource contiene un flusso di lavoro che controlla un evento Click per l&#39;URL e-mail  Adobe.  Quando si verifica questo evento, crea un&#39;attività e imposta una data di scadenza.  Questo consente all&#39;attività di essere visualizzata nella scheda RA, conferendogli un&#39;ulteriore visibilità.  Esiste un flusso di lavoro simile per  eventi di rimbalzo e-mail di Adobe, con l&#39;aggiunta di un&#39;attività per riconciliare l&#39;indirizzo e-mail non valido.  Questi flussi di lavoro possono essere disattivati nella soluzione.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se si fa clic sull&#39;oggetto dell&#39;evento di invio, verrà visualizzato un modulo simile a quello riportato di seguito.  I moduli per gli eventi open e bounce sono simili.

![](assets/do-not-localize/mirror_page_url_send.png)

Il modulo per gli eventi click URL e-mail aggiunge un attributo aggiuntivo per l&#39;URL su cui è stato fatto clic:

![](assets/do-not-localize/mirror_page_url_click.png)

Segue un elenco degli attributi e una descrizione:

* Oggetto: Oggetto dell&#39;evento; composto dall&#39;ID campagna e dall&#39;ID di consegna dell&#39;e-mail di consegna

* Proprietario: Utente dell&#39;applicazione creato nei passaggi successivi al provisioning

* Per quanto riguarda: Nome del contatto

* Nome campagna: ID campagna in Campaign Standard

* Nome consegna: L&#39;ID di consegna in Campaign Standard

* Data Di Invio/Apertura/Clic/Bloccato: Data/ora in cui è stato creato l’evento

* URL tracciamento: URL su cui è stato fatto clic

* URL pagina mirror: URL della pagina mirror dell’e-mail che è stata inviata/aperta/su cui è stato fatto clic/che è stata rimbalzata

>[!NOTE]
>
>Il periodo di scadenza della pagina mirror dell&#39;e-mail può essere modificato nella schermata di configurazione dell&#39;attività del canale e-mail della campagna corrispondente (vedete Parametri [del periodo di](../../administration/using/configuring-email-channel.md#validity-period-parameters)validità).

>[!NOTE]
>
>Per l&#39;opzione di rifiuto, quando un attributo di rinuncia viene modificato in Dynamics 365, questo si rifletterà in Campaign se hai selezionato la configurazione Dynamics 365-to-Campaign o l&#39;opzione di rifiuto bidirezionale e se hai mappato correttamente quel particolare attributo.

## Flussi di dati {#data-flows}

### Ingressi entità contatto e personalizzati

I record nuovi e aggiornati (e eliminati, se abilitati) vengono inviati dalla tabella di contatto di Dynamics 365 alla tabella di profilo della campagna.

Le mappature delle tabelle possono essere configurate per mappare gli attributi della tabella Dynamics 365 agli attributi della tabella Campaign. Le mappature delle tabelle possono essere modificate per aggiungere o rimuovere attributi, in base alle esigenze.

L&#39;esecuzione iniziale del flusso di dati è progettata per trasferire tutti i record mappati, compresi quelli contrassegnati come &quot;inattivi&quot;; in seguito, l&#39;integrazione elaborerà solo gli aggiornamenti incrementali. L&#39;eccezione è rappresentata dalla configurazione di un filtro; regole di filtraggio di base basate sugli attributi possono essere configurate per determinare quali record sincronizzare in Campaign.

Le regole di sostituzione di base possono essere configurate per sostituire un valore attributo con un valore diverso (ad esempio, &quot;green&quot; per &quot;#00FF00&quot;, &quot;F&quot; per 1, ecc.).

A seconda del volume di record, potrebbe essere necessario utilizzare l&#39;archivio SFTP della campagna per il trasferimento iniziale dei dati.  Vedere la sezione &quot;Trasferimento dati iniziale&quot;.

L&#39;attributo externalId della tabella del profilo della campagna deve essere popolato con l&#39;attributo contatto contactId di Dynamics 365 per consentire il funzionamento dell&#39;ingresso del contatto. Le entità personalizzate della campagna devono essere popolate anche con un attributo ID univoco di Dynamics 365; tuttavia, questo attributo può essere memorizzato in qualsiasi attributo di entità personalizzata di Campaign (vale a dire, non deve essere externalId).

>[!NOTE]
>
>Per l&#39;ingresso di entità personalizzata, il tracciamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.

### Flusso evento marketing e-mail

Gli eventi di marketing e-mail vengono inviati da Campaign a Dynamics 365 per essere visualizzati nella visualizzazione Timeline.

Tipi di eventi di marketing supportati:
* Invia - E-mail inviata al destinatario
* Apri - E-mail aperta dal destinatario
* Click - URL all&#39;interno dell&#39;e-mail cliccato dal destinatario
* Rimbalzo - E-mail al destinatario ha subito un duro rimbalzo

I seguenti attributi evento sono visualizzati in D365:
* Nome campagna di marketing
* Nome consegna e-mail
* Timestamp
* URL pagina mirror e-mail
* URL su cui è stato fatto clic (solo eventi clic)

Gli eventi di marketing e-mail possono essere attivati/disattivati per tipo (invio, apertura, clic, rimbalzo) in modo che solo i tipi di evento selezionati vengano passati a Dynamics 365.

### Flusso di rinuncia

I valori di rifiuto (ad esempio,  inserii nell&#39;elenco Bloccati) sono sincronizzati tra i sistemi; al momento della registrazione, potete scegliere tra le seguenti opzioni:
* Dynamics 365 è l&#39;origine della verità per i opt-out: gli attributi di rifiuto verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard
* Il Campaign Standard è la fonte di verità per i opt-out: gli attributi di rifiuto verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* Dynamics 365 AND Campaign Standard sono entrambe fonti di verità: gli attributi di rifiuto verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

In alternativa, se si dispone di un processo separato per gestire la sincronizzazione di rinuncia tra i sistemi, il flusso di dati di rinuncia dell&#39;integrazione può essere disattivato.

La mappatura del flusso di rifiuto deve essere specificata dal cliente, in quanto i requisiti aziendali possono essere diversi tra le società.  Dal lato Campagna, per la mappatura di rifiuto è possibile utilizzare solo gli attributi di rinuncia OOTB:
* inserire nell&#39;elenco Bloccati 
* blockListEmail
* blockListFax
* blockListMobile
* blockListPhone
* blockListPostalMail
* blockListPushnotification
* ccpaOptOut

In Dynamics 365, la maggior parte dei campi di rinuncia ha il prefisso &quot;donot&quot;; tuttavia, se i tipi di dati sono compatibili, è anche possibile utilizzare altri attributi a scopo di rifiuto.

### Trasferimento dati iniziale

Le tabelle di Dynamics 365 con più di 500 KB di record dovranno essere esportate nello storage SFTP della campagna per essere importate tramite il flusso di lavoro Campaign.

Il trasferimento iniziale dei dati è un unico trasferimento di dati basato su file. Dopo il trasferimento dei dati, l&#39;integrazione utilizzerà le API per gli aggiornamenti incrementali.
