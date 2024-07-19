---
title: Utilizzare l’integrazione con Microsoft Dynamics 365
description: Scopri come utilizzare Microsoft Dynamics 365 con l’integrazione di Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1652'
ht-degree: 1%

---

# Utilizzo dell’integrazione con Microsoft Dynamics 365

L’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 esegue diversi flussi di dati. Questi flussi sono descritti in [questa pagina](../../integrating/using/d365-acs-self-service-app-workflows.md).

Ulteriori dettagli sui flussi di dati sono disponibili più in basso in questo documento nella sezione [Flussi di dati](#data-flows).

## Esperienza utente di Adobe Campaign Standard

Quando un contatto viene creato, modificato o eliminato (se l’eliminazione è abilitata) in Microsoft Dynamics 365, viene inviato a Campaign Standard. Questi contatti saranno visibili nella schermata Profili in Campaign e possono essere indirizzati nelle campagne di marketing. Consulta la schermata Profili di seguito.

![](assets/MSdynamicsACS-usage1.png)

Quando un attributo di rinuncia viene modificato in Campaign, questo si rifletterà in Dynamics 365 se hai selezionato la configurazione di rinuncia **Unidirezionale (Campaign to Microsoft Dynamics 365)** o **Bidirezionale** e se tale attributo è stato mappato correttamente.

## Esperienza utente di Microsoft Dynamics 365

Per l’uscita, i seguenti eventi di e-mail marketing vengono inviati da Campaign a Dynamics 365 e visualizzati nella visualizzazione Timeline di Microsoft Dynamics 365 come attività personalizzate:

* Invio e-mail Adobe Campaign

* Apertura e-mail Adobe Campaign

* Clic sull’URL dell’e-mail di Adobe Campaign

* E-mail non recapitate in Adobe Campaign

Per visualizzare la sequenza temporale di un contatto, passa all’elenco dei contatti facendo clic su Sales Hub dal menu a discesa Dynamics 365. Fare quindi clic su Contatti sulla barra dei menu a sinistra e selezionare un contatto.

>[!NOTE]
>
>Per visualizzare questi eventi, è necessario installare l&#39;app **Adobe Campaign per Microsoft Dynamics 365** in AppSource nell&#39;istanza di Microsoft Dynamics 365. [Ulteriori informazioni](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Di seguito è riportata un&#39;istantanea della schermata Contatto per &quot;Dynamics User&quot;. Nella vista Timeline, noterai che all’utente di Dynamics è stata inviata un’e-mail associata al nome della campagna &quot;2019LoyaltyCamp&quot; e al nome della consegna &quot;DM190&quot;. Dynamics User ha aperto l’e-mail e ha fatto clic su un URL nell’e-mail; entrambe queste azioni hanno creato eventi che vengono visualizzati anche di seguito. Nell’angolo a destra viene visualizzata la scheda Relationship Assistant (RA), che attualmente contiene un’attività per il follow-up dell’URL su cui è stato fatto clic.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Di seguito è riportata una descrizione della vista Timeline per l’utente di Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Di seguito è riportata una breve descrizione della scheda Relationship Assistant (RA). L’app AppSource contiene un flusso di lavoro che verifica la presenza di un evento Clic su URL e-mail di Adobe. Quando si verifica questo evento, viene creata un&#39;attività e viene impostata una data di scadenza. Questo consente all’attività di essere visualizzata nella scheda RA, dandogli ulteriore visibilità. Esiste un flusso di lavoro simile, ad Adobe per gli eventi di mancato recapito e-mail, con l’aggiunta di un’attività per riconciliare l’indirizzo e-mail non valido. Questi flussi di lavoro possono essere disattivati nella soluzione.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Se fai clic sull’oggetto dell’evento di invio, visualizzerai un modulo simile a quello riportato di seguito. I moduli per gli eventi di apertura e mancato recapito sono simili.

![](assets/do-not-localize/mirror_page_url_send.png)

Il modulo per gli eventi di clic sugli URL e-mail aggiunge un attributo aggiuntivo per l’URL su cui è stato fatto clic:

![](assets/do-not-localize/mirror_page_url_click.png)

Di seguito è riportato un elenco degli attributi e una descrizione:

* **Oggetto**: oggetto dell&#39;evento; composto dall&#39;ID campagna e dall&#39;ID consegna della consegna e-mail

* **Proprietario**: l&#39;utente dell&#39;applicazione creato nei passaggi successivi al provisioning

* **Riguardo**: il nome del contatto

* **Nome campagna**: l&#39;ID campagna in Campaign Standard

* **Nome consegna**: l&#39;ID consegna in Campaign Standard

* **Data di invio/apertura/clic/mancato recapito**: data/ora di creazione dell&#39;evento

* **URL di tracciamento**: URL su cui è stato fatto clic

* **URL pagina mirror**: URL della pagina mirror dell&#39;e-mail inviata/aperta/su cui è stato fatto clic/non recapitata. Il periodo di scadenza della pagina mirror e-mail può essere modificato nella schermata di configurazione dell’attività del canale e-mail di Campaign corrispondente. [Ulteriori informazioni](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Per la rinuncia, quando un attributo di rinuncia viene modificato in Microsoft Dynamics 365, questo si rifletterà in Campaign se hai selezionato la configurazione di rinuncia **Unidirezionale (Campaign to Microsoft Dynamics 365)** o **Bidirezionale** e se tale attributo è stato mappato correttamente.

## Flussi di dati {#data-flows}

### Ingresso di contatti ed entità personalizzate

I record nuovi, aggiornati ed eliminati (Nota: i record eliminati devono essere abilitati) vengono inviati dalla tabella dei contatti di Microsoft Dynamics 365 alla tabella dei profili di Campaign.

Nell’interfaccia utente dell’applicazione di integrazione è possibile configurare le mappature delle tabelle per mappare gli attributi delle tabelle Microsoft Dynamics 365 agli attributi delle tabelle Campaign. Le mappature delle tabelle possono essere modificate per aggiungere/rimuovere attributi, in base alle esigenze.

L’esecuzione iniziale del flusso di dati è progettata per trasferire tutti i record mappati, inclusi quelli contrassegnati come &quot;inattivi&quot;; in seguito, l’integrazione elaborerà solo aggiornamenti incrementali. L’eccezione a questo problema si verifica se i dati vengono ripetuti o se viene configurato un filtro; è possibile configurare regole di filtro di base basate su attributi per determinare quali record sincronizzare con Campaign.

Le regole di sostituzione di base possono essere configurate nell’interfaccia utente dell’applicazione di integrazione per sostituire un valore di attributo con un valore diverso (ad esempio, &quot;verde&quot; per &quot;#00FF00&quot;, &quot;F&quot; per 1, ecc.).

A seconda del volume di record, potrebbe essere necessario utilizzare l’archiviazione SFTP di Campaign per il trasferimento iniziale dei dati. [Ulteriori informazioni](#initial-data-transfer).

L’attributo externalId della tabella di profilo di Campaign deve essere compilato con l’attributo contactId di Dynamics 365 affinché l’ingresso del contatto funzioni. Le entità personalizzate di Campaign devono anche essere compilate con un attributo ID univoco di Dynamics 365; tuttavia, questo attributo può essere memorizzato in qualsiasi attributo di entità personalizzato di Campaign (ovvero, non deve essere externalId).

>[!NOTE]
>
>Per l’ingresso di entità personalizzate, il rilevamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.

#### Entità personalizzate

L&#39;integrazione [Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) supporta entità personalizzate, consentendo la sincronizzazione delle entità personalizzate in Dynamics 365 con le risorse personalizzate corrispondenti in Campaign.

I nuovi dati nelle risorse personalizzate possono essere utilizzati per diversi scopi, tra cui segmentazione e personalizzazione.

L’integrazione supporta sia tabelle collegate che non collegate. Il collegamento è supportato fino a tre livelli (ovvero, livello1->livello2->livello3).

>[!IMPORTANT]
>
>Se un record di risorse personalizzato di Campaign contiene informazioni personali, vengono applicate raccomandazioni specifiche. Per ulteriori informazioni, consulta [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).
>

Durante la configurazione dei flussi di dati di entità personalizzate, è importante tenere presente quanto segue:

* La creazione e la modifica di risorse personalizzate di Campaign sono operazioni sensibili che devono essere eseguite solo da utenti esperti.
* Per i flussi di dati di entità personalizzate, il rilevamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.
* Se un record padre e un record figlio collegato vengono creati quasi contemporaneamente in Dynamics 365, a causa dell’elaborazione parallela dell’integrazione, esiste una leggera possibilità che un nuovo record figlio possa essere scritto in Campaign prima del relativo record padre.

* Se l&#39;elemento padre e l&#39;elemento figlio sono collegati sul lato Campaign utilizzando l&#39;opzione **1 cardinality simple link**, il record figlio rimarrà nascosto e inaccessibile (tramite interfaccia utente o API) fino a quando non arriva in Campaign.

* (Presupponendo il collegamento semplice con cardinalità **1** in Campaign) Se il record figlio viene aggiornato o eliminato in Dynamics 365 e la modifica viene scritta in Campaign prima che il record padre venga visualizzato in Campaign (probabilmente, ma è una possibilità remota), tale aggiornamento o eliminazione non verrà elaborato in Campaign e verrà generato un errore. In caso di aggiornamento, il record in questione dovrà essere aggiornato nuovamente in Dynamics 365 per sincronizzare il record aggiornato. In caso di eliminazione, il record in questione dovrà essere gestito separatamente dal lato Campaign, in quanto non esiste più un record in Dynamics 365 da eliminare o aggiornare.

* Se ci si imbatte in una situazione in cui si ritiene di disporre di record secondari nascosti e non è possibile accedervi, è possibile modificare temporaneamente il tipo di collegamento di cardinalità in **0 o 1 collegamento semplice di cardinalità** per accedere a tali record.

Una panoramica più completa delle risorse personalizzate di Campaign è disponibile [in questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

### Flusso degli eventi di e-mail marketing{#email-marketing-event-flow}

Gli eventi di marketing e-mail vengono inviati da Campaign a Microsoft Dynamics 365 per essere visualizzati nella visualizzazione Timeline.

Tipi di eventi di marketing supportati:
* Invia: e-mail inviata al destinatario
* Apri: e-mail aperta dal destinatario
* Clic: URL nell’e-mail su cui il destinatario ha fatto clic
* Mancato recapito: l’e-mail al destinatario ha subito un problema grave

In Dynamics 365 vengono visualizzati i seguenti attributi di evento:
* Nome della campagna di marketing
* Nome consegna e-mail
* Timestamp
* URL pagina mirror e-mail
* URL su cui è stato fatto clic (solo eventi clic)

È possibile abilitare/disabilitare gli eventi di e-mail marketing per tipo (invia, apri, fai clic, rimuovi) in modo che solo i tipi di evento selezionati vengano passati a Dynamics 365.

### Flusso di rinuncia {#opt-out-flow}

I valori di rinuncia (ad esempio, inserisce nell&#39;elenco Bloccati di) sono sincronizzati tra i sistemi; puoi scegliere tra le seguenti opzioni durante l’onboarding:

* **Unidirezionale (da Microsoft Dynamics 365 a Campaign)**: Dynamics 365 è la fonte di verità per le rinunce. Gli attributi di rinuncia verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard&quot;
* **Unidirezionale (campagna a Microsoft Dynamics 365)**: Campaign Standard è l&#39;origine di verità per le rinunce. Gli attributi di rinuncia verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* **Bidirezionale**: Dynamics 365 AND Campaign Standard sono entrambe origini di verità. Gli attributi di rinuncia verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

In alternativa, se disponi di un processo separato per gestire la sincronizzazione delle rinunce tra i sistemi, il flusso di dati di rinuncia dell’integrazione può essere disabilitato.

>[!NOTE]
>
>Nell&#39;interfaccia utente dell&#39;applicazione di integrazione, i casi d&#39;uso **Unidirezionale (da Microsoft Dynamics 365 a Campaign)** e **Bidirezionale** di rinuncia sono configurati in un flusso di lavoro di rinuncia separato. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>Il caso di utilizzo della rinuncia **unidirezionale (da Campaign a Microsoft Dynamics 365)** è un&#39;eccezione ed è configurato nel flusso di lavoro Invio (Contatto al profilo).
>

La mappatura del flusso di rinuncia deve essere specificata dal cliente, in quanto i requisiti di business possono variare tra le aziende. Sul lato Campaign, per la mappatura della rinuncia è possibile utilizzare solo gli attributi di rinuncia inclusi:

* INSERISCO NELL&#39;ELENCO BLOCCATI DI
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

In Dynamics 365, la maggior parte dei campi di rinuncia hanno il prefisso &quot;donot&quot;; tuttavia, puoi anche utilizzare altri attributi a scopo di rinuncia se i tipi di dati sono compatibili.

### Trasferimento iniziale dei dati {#initial-data-transfer}

Il trasferimento iniziale dei dati potrebbe richiedere un po’ di tempo a seconda del numero di record che si stanno acquisendo da Microsoft Dynamics 365. Dopo il trasferimento iniziale dei dati, l’integrazione utilizzerà gli aggiornamenti incrementali.
