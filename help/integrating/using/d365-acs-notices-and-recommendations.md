---
title: Gestione dei dati di Campaign e Microsoft Dynamics 365
description: Scopri come Campaign Standard e Microsoft Dynamics 365 gestiscono i dati comuni
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# Best practice e limitazioni {#acs-msdyn-best-practices}

## Gestire i dati {#acs-msdyn-manage-data}

Per la sincronizzazione di contatti e entità personalizzate, questa integrazione tratta **Microsoft Dynamics 365 come fonte di verità**.  Eventuali modifiche agli attributi sincronizzati devono essere eseguite in Dynamics 365 e non in Adobe Campaign Standard).  Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte in Campaign durante la sincronizzazione, in quanto la sincronizzazione avviene in una direzione.

Facoltativamente, è possibile configurare l’integrazione per emettere chiamate di eliminazione profilo a Campaign quando un contatto viene eliminato in Dynamics 365 per mantenere l’integrità dei dati. Tuttavia, l’eliminazione di un profilo è diversa dall’eliminazione di una privacy. Una cancellazione della privacy in Campaign rimuoverà il record del profilo Campaign e le voci di registro associate; mentre, una cancellazione regolare del profilo eliminerà solo il record del profilo Campaign, lasciando i resti indietro nei registri di Campaign. Se la funzione di eliminazione del profilo è abilitata nell’integrazione, per elaborare correttamente le richieste di privacy degli interessati dovranno essere seguiti ulteriori passaggi. Fai riferimento ai passaggi descritti nella sezione [Sezione sulla privacy qui sotto](#manage-privacy-requests).

## Privacy{#acs-msdyn-manage-privacy}

Questa integrazione è progettata per trasferire i dati degli utenti finali tra Microsoft Dynamics 365 e Adobe Campaign Standard. Questi dati includono informazioni personali se sono contenuti nei dati dell&#39;utente finale.  In qualità di titolare del trattamento dei dati, l’azienda è responsabile del rispetto di tutte le leggi e i regolamenti sulla privacy applicabili alla raccolta e all’utilizzo dei dati personali.

Questa integrazione è progettata per trasferire i dati degli utenti finali (compresi, tra l’altro, quelli personali, se contenuti nei dati degli utenti finali) tra Microsoft Dynamics 365 e Adobe Campaign Standard. In qualità di titolare del trattamento dei dati, l’azienda è responsabile del rispetto di tutte le leggi e i regolamenti sulla privacy applicabili alla raccolta e all’utilizzo dei dati personali.

L’integrazione non emette alcun problema di privacy della persona interessata (ad esempio, RGPD) e elimina o gestisce altre richieste di privacy (ad eccezione della rinuncia). Quando esegui le richieste di privacy, devi farlo sia in Microsoft Dynamics 365 che in Campaign (tramite Adobe Experience Platform Privacy Service), in modo indipendente.

Se hai configurato l’integrazione per emettere chiamate regolari di eliminazione dei profili in Campaign quando un contatto viene eliminato in Dynamics 365, segui i passaggi seguenti. Assicurati che non vengano apportati aggiornamenti al record in questione durante questo processo.

1. Emetti la richiesta di cancellazione della privacy a [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Monitora la richiesta fino al completamento

1. Verifica che il record non sia più nell’istanza Campaign

1. (Presto disponibile) Rilascia privacy in Dynamics 365

1. Verifica che il record sia stato rimosso da entrambi i sistemi

Di seguito sono riportati i collegamenti che ti aiutano ad implementare le richieste relative alla privacy di accesso e/o eliminazione in ogni sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Se un record di risorse personalizzato di Campaign contiene informazioni personali applicabili all’utilizzo di Campaign da parte di un cliente, tale record deve essere collegato a un record di profilo di Campaign corrispondente (direttamente o tramite un’altra risorsa personalizzata) in modo che un’eliminazione correlata alla privacy nel record di profilo possa anche eliminare il record di risorse personalizzate collegato contenente informazioni personali; le opzioni di collegamento ed eliminazione tra le entità devono essere configurate per consentire la rimozione in cascata dei record collegati. Le informazioni personali non devono essere inserite in una risorsa personalizzata non collegata al profilo.

## Rinuncia {#opt-out}

A causa delle differenze negli attributi di rinuncia tra Microsoft Dynamics 365 e Campaign e delle differenze nei requisiti aziendali di ciascun cliente, la mappatura della rinuncia è stata lasciata come esercizio da completare per il cliente.  È importante garantire che le rinunce siano mappate correttamente tra i sistemi in modo che le preferenze di rinuncia dell&#39;utente finale vengano mantenute e che non ricevano una comunicazione tramite un canale da cui hanno rinunciato.

Tieni presente che solo i seguenti elementi possono essere utilizzati nelle mappature di rinuncia:

* Attributi della campagna con il prefisso &quot;Non più contatto per&quot; (ad esempio, Non più contatto per e-mail), o

* l’attributo specifico per il CCPA

Puoi trovare ulteriori informazioni sui campi dell’entità profilo [qui](../../developing/using/datamodel-profile.md).

In Dynamics 365, la maggior parte dei campi di rinuncia ha il prefisso &quot;donot&quot;, tuttavia, puoi utilizzare anche altri attributi a scopo di rinuncia se i tipi di dati sono compatibili.

Quando effettui il provisioning dell’integrazione, avrai la possibilità di specificare la configurazione di rinuncia necessaria per la tua azienda:

* **Unidirezionale (da Microsoft Dynamics 365 a Campaign)**: Dynamics 365 è una fonte di verità per le rinunce. Gli attributi di rinuncia verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard
* **Unidirezionale (da Campaign a Microsoft Dynamics 365)**: Campaign Standard è la fonte di verità per le rinunce. Gli attributi di rinuncia verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* **Bidirezionale**: Dynamics 365 E Campaign Standard sono entrambe fonti di verità. Gli attributi di rinuncia verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

In alternativa, se disponi di un processo separato per gestire la sincronizzazione di rinuncia tra i sistemi, il flusso di dati di rinuncia dell’integrazione può essere disabilitato.

La configurazione di rinuncia bidirezionale utilizza la logica per determinare quale valore scrivere in entrambi i sistemi. La logica confronta le marche temporali tra i due sistemi (modifica a livello di record in Dynamics 365, modifica a livello di attributo in Campaign) per determinare quale sistema prevale. Se Campaign contiene la marca temporale più recente, prevale il valore Campaign. Se Dynamics 365 contiene la marca temporale più recente o se è uguale, optedout=TRUE verrà vinto (supponendo che uno dei valori sia TRUE).

Scopri come selezionare le opzioni di consenso/rinuncia in [questa sezione](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Rivedi e, se appropriato, aggiorna le regole di tipologia predefinite e specifiche in Adobe Campaign prima di apportare modifiche qui, per assicurarti che tali modifiche siano applicate correttamente a tutte le comunicazioni in uscita. Ad esempio, assicurati che tutte le mappature delle preferenze di rinuncia riflettano accuratamente le scelte di intento/comunicazione del destinatario e non interrompano inavvertitamente la consegna di relazioni o messaggi transazionali come le conferme degli ordini dei clienti.

Se hai selezionato la **Bidirezionale** o **Unidirezionale (da Campaign a Microsoft Dynamics 365)** configurazione di rinuncia, i dati di rinuncia di Campaign verranno esportati periodicamente tramite flusso di lavoro nell’area di archiviazione SFTP di Campaign (vedi &quot;Utilizzo SFTP di Campaign di seguito&quot;). Nel caso in cui i flussi di lavoro di rinuncia di Campaign smettano di essere in esecuzione, dovrai riavviare manualmente il prima possibile per ridurre la possibilità di mancate sincronizzazioni.

>[!IMPORTANT]
>
>Se hai bisogno di **Bidirezionale** o **Unidirezionale (da Campaign a Microsoft Dynamics 365)** configurazione di rinuncia, dovrai effettuare la richiesta al contatto tecnico Adobe per la configurazione dei flussi di lavoro di rinuncia sull’istanza Campaign

## Utilizzo di Campaign SFTP

L’archiviazione SFTP di Campaign deve essere utilizzata dall’integrazione nei casi d’uso seguenti.  Devi accertarti che il tuo account SFTP abbia una capacità di archiviazione adeguata per gestire questi casi d’uso. Il superamento della capacità di archiviazione SFTP con licenza può gravemente compromettere l’utilizzo funzionale di Campaign, l’integrazione e/o l’account SFTP.

| Caso d’uso | Descrizione |
|---|---|
| Bidirezionale e unidirezionale (da Campaign a Microsoft Dynamics 365) | I flussi di dati di rinuncia bidirezionale e unidirezionale (da Campaign a Microsoft Dynamics 365) utilizzeranno l’archiviazione SFTP di Campaign. Un flusso di lavoro Campaign esporta le modifiche incrementali nella cartella SFTP. Da lì, l&#39;integrazione raccoglierà i record e il processo. |
| Log di rinuncia | I registri di output dal connettore saranno utili per la risoluzione dei problemi di integrazione. I registri di output possono essere attivati/disattivati. |


>[!IMPORTANT]
>
>Sei responsabile delle informazioni che accedi e scarica dalle cartelle SFTP. Se le informazioni contengono dati personali, l&#39;utente è responsabile del rispetto di tutte le leggi e i regolamenti sulla privacy applicabili. [Ulteriori informazioni](#acs-msdyn-manage-privacy).

## Gestione dati

### Dati di Campaign esistenti

Questa integrazione sincronizza i contatti e le entità personalizzate da Microsoft Dynamics 365 a Campaign. I record di campagna creati al di fuori dell’integrazione (ovvero non creati dal processo di sincronizzazione) non verranno modificati dall’integrazione, inclusi i record di Campaign esistenti al momento della configurazione dell’integrazione.

Poiché questa integrazione utilizza **[!UICONTROL externalId]** in Campaign per sincronizzare i record del profilo Campaign con i record di contatto di Dynamics 365, questo campo Campaign (**[!UICONTROL externalId]** ) deve essere compilata con Microsoft Dynamics 365 **[!UICONTROL contactId]** per i record che desideri sincronizzare da Microsoft Dynamics 365.  Le entità personalizzate vengono anche sincronizzate utilizzando un ID univoco di Microsoft Dynamics 365. L’entità personalizzata Campaign deve includere questo attributo ID come colonna di tabella. La colonna externalId può essere utilizzata per memorizzare questo valore di attributo, ma non è necessaria per le entità personalizzate di Campaign.

Tieni presente che Microsoft Dynamics 365 è ancora la fonte della verità e che i dati del profilo Campaign possono essere sovrascritti quando l’integrazione rileva gli aggiornamenti sul lato Dynamics 365.  Possono essere necessari anche altri passaggi per abilitare l’integrazione, a seconda della distribuzione esistente; pertanto, si consiglia di lavorare a stretto contatto con il contatto tecnico Adobe.

>[!NOTE]
>
>A causa della complessità delle implementazioni dei clienti esistenti, è consigliabile utilizzare il contatto tecnico Adobe per pianificare e configurare l’integrazione.

### Frequenza di sincronizzazione dati

L’integrazione utilizza un’architettura che consente di rilevare e aggiungere gli aggiornamenti alla &quot;coda&quot; di elaborazione poco dopo l’esecuzione in Microsoft Dynamics 365 (ad esempio, streaming, non elaborazione batch). Per questo motivo, non è necessario specificare le frequenze o i programmi di esecuzione del flusso di dati.

L’eccezione è rappresentata dai flussi di dati di rinuncia bidirezionale e Campaign a Dynamics 365. Per queste configurazioni di rinuncia, i record Campaign aggiornati vengono esportati su SFTP tramite un flusso di lavoro Campaign una volta al giorno, dopodiché lo strumento di integrazione legge il file ed elabora il record.

### Contratto di utilizzo dei dati

Se ti trovi nelle aree EMEA o APAC, alcuni dei tuoi dati verranno elaborati negli Stati Uniti nell’ambito di questa integrazione. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Guardrail e limitazioni

>[!IMPORTANT]
>
>Alcune azioni da parte tua (ad esempio, acquisizione iniziale di record, riproduzione di dati di record, ecc.) potrebbe comportare l’acquisizione di un gran numero di record da Microsoft Dynamics 365 all’istanza Adobe Campaign. Per ridurre il rischio di problemi di prestazioni, ti consigliamo di interrompere tutti i processi di Campaign (ad esempio, nessuna attività di marketing, nessuna esecuzione di flussi di lavoro, ecc.) fino a dopo l’acquisizione di un gran numero di record in Campaign.

### Entità personalizzate

La [Integrazione Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) supporta le entità personalizzate, consentendo la sincronizzazione delle entità personalizzate in Dynamics 365 con le risorse personalizzate corrispondenti in Campaign.

L’integrazione supporta sia tabelle collegate che non collegate.

Durante la configurazione dei flussi di dati di entità personalizzati, è importante tenere presente quanto segue:

* La creazione e la modifica di risorse personalizzate di Campaign sono operazioni sensibili che devono essere eseguite solo da utenti esperti.
* Per i flussi di dati di entità personalizzati, il tracciamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.
* Se in Dynamics 365 viene creato un record figlio padre e collegato in modo simile, a causa dell’elaborazione parallela dell’integrazione, è possibile scrivere un nuovo record figlio in Campaign prima del record padre.

* Se l’elemento padre e l’elemento figlio sono collegati sul lato Campaign utilizzando **1 cardinalità semplice collegamento** il record figlio rimarrà nascosto e inaccessibile (tramite interfaccia utente o API) fino all’arrivo del record principale in Campaign.

* (Supponendo **1 cardinalità semplice collegamento** in Campaign) Se il record figlio viene aggiornato o eliminato in Dynamics 365 e tale modifica viene scritta in Campaign prima che il record padre venga visualizzato in Campaign (non probabile, ma possibilità remota), tale aggiornamento o eliminazione non verrà elaborato in Campaign e verrà generato un errore. In caso di aggiornamento, il record in questione dovrà essere nuovamente aggiornato in Dynamics 365 per sincronizzare il record aggiornato. In caso di cancellazione, è necessario provvedere separatamente al record in questione sul lato Campaign, in quanto non esiste più un record in Dynamics 365 da eliminare o aggiornare.

* Se ti trovi in una situazione in cui ritieni di avere dei record figlio nascosti e non hai modo di accedervi, puoi cambiare temporaneamente il tipo di collegamento della cardinalità in **0 o 1 collegamento semplice cardinalità** per accedere a tali documenti.

Puoi trovare una panoramica più completa delle risorse personalizzate di Campaign [in questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

### Guardrail di integrazione

Quando si intende utilizzare questa integrazione, è necessario tenere conto delle seguenti protezioni. Rivolgiti al tuo rappresentante tecnico Adobe se ritieni di superare queste protezioni.

* Per supportare il volume di chiamate del motore generato dall’integrazione, dovrai ottenere la licenza del pacchetto Campaign appropriato. Il superamento del volume di chiamata del motore concesso in licenza potrebbe causare un deterioramento delle prestazioni di Campaign.

   Utilizza quanto segue per stimare il volume di chiamata del motore dall&#39;integrazione:

   * Inserti di record (ovvero, nuovo record): 1 chiamata al motore
   * Il record elimina: 1 chiamata al motore
   * Aggiornamenti record: 2 chiamate al motore (solo 1 chiamata se il record di destinazione è identico al record di origine, ovvero se non viene apportata alcuna modifica al record Campaign)

   Quando si calcola il volume complessivo delle chiamate al motore Campaign, è importante tenere conto di altre fonti di chiamate al motore, tra cui pagine di destinazione, WebApps, JSSP, API, registrazioni di app mobili, ecc.

   Visualizza le informazioni sul pacchetto Adobe Campaign Standard qui: [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html)

* L’integrazione supporta un massimo di 15 milioni di record totali per la sincronizzazione iniziale con le risorse in Campaign. La sincronizzazione incrementale è limitata dal pacchetto Adobe Campaign Standard.

* L’offerta di integrazione standard include il supporto di fino a venti entità personalizzate, ciascuna con un massimo di 50 colonne di dimensioni.

* Prima di implementare l’integrazione, dovrai creare e pubblicare le risorse personalizzate.

* La profondità massima della tabella quando si collegano le tabelle è due (ovvero, tabella1->tabella2->tabella3)

* L’integrazione supporta fino a 5 colonne collegate per ogni risorsa personalizzata. Il collegamento di più colonne tra risorse personalizzate può avere un impatto notevole sulle prestazioni. **0 o 1 collegamento semplice cardinalità** è da preferirsi a **1 cardinalità semplice collegamento**.

* L’integrazione supporta la trasformazione tra i tipi di dati di Microsoft Dynamics 365 primitivi (booleani, interi, decimali, doppi, stringhe, date, time, date) e i tipi di dati di Adobe Campaign Standard (integer, booleano, float, double, date, datetime, string). I tipi di dati più avanzati vengono interpretati come stringhe e sincronizzati così come sono.

* Potrebbe essere necessario stabilire finestre di manutenzione di onboarding tra l&#39;Adobe e il cliente.

* Tieni presente che aumenti significativi o &quot;picchi&quot; nell’utilizzo dell’integrazione (ad esempio, un forte aumento dei record nuovi o aggiornati) possono causare rallentamenti nella sincronizzazione dei dati.

* Come parte dell’integrazione, è necessario completare i passaggi di configurazione pre-integrazione in Microsoft Azure e Dynamics 365. Vedi i passaggi di configurazione [in questa pagina](../../integrating/using/d365-acs-configure-d365.md)

* È previsto che porterai i modelli di dati Dynamics 365 e Campaign all’integrazione e li manterrai.

### Limiti di integrazione

L’integrazione è stata progettata per risolvere il caso d’uso generale dello spostamento di dati tra Microsoft Dynamics 365 e Campaign, ma non per risolvere ogni caso d’uso specifico per ciascun cliente:

* L’integrazione non rilascia alcuna eliminazione relativa alla privacy (ad esempio, RGPD). La responsabilità di soddisfare le richieste sulla privacy degli utenti finali incombe al cliente; tali richieste devono essere effettuate in modo indipendente sia in Campaign (tramite Adobe Experience Platform Privacy Service) che in Dynamics 365. Se necessario, l’integrazione può eseguire eliminazioni regolari per facilitare la sincronizzazione dei dati.   Revisione [la sezione Privacy](#manage-privacy-requests) per ulteriori informazioni.

* Nessun dato di profilo o di entità personalizzata verrà sincronizzato da Campaign a Dynamics 365, ad eccezione delle informazioni di rinuncia (se configurate dal cliente).

* La gestione degli abbonamenti alle campagne (ad esempio, abbonamenti/annullamenti di abbonamenti) non è supportata in modo nativo.

* La composizione e l’attivazione di campagne e-mail Campaign da Dynamics 365 non è supportata.

* L&#39;integrazione **not** supporta la rimozione remota dei dati tra i modelli di dati di Dynamics 365 e Campaign Standard. È previsto che l’integrazione sincronizzi una tabella di Dynamics 365 con una tabella di Campaign.
