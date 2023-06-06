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
source-git-commit: 17522f4df86c7fb46593472316d57b4ba4acee2b
workflow-type: tm+mt
source-wordcount: '2471'
ht-degree: 1%

---

# Best practice e limitazioni {#acs-msdyn-best-practices}

## Gestire i dati {#acs-msdyn-manage-data}

Per la sincronizzazione di contatti ed entità personalizzate, questa integrazione tratta **Microsoft Dynamics 365 come fonte di verità**.  Eventuali modifiche agli attributi sincronizzati devono essere eseguite in Dynamics 365 e non in Adobe Campaign Standard).  Se vengono apportate modifiche in Campaign, queste possono eventualmente essere sovrascritte in Campaign durante la sincronizzazione, in quanto la sincronizzazione si trova in una direzione.

L’integrazione può essere configurata facoltativamente per emettere chiamate di eliminazione profilo a Campaign quando un contatto viene eliminato in Dynamics 365 per mantenere l’integrità dei dati. Tuttavia, l’eliminazione di un profilo è diversa dall’eliminazione di una privacy. Se si elimina la privacy in Campaign, verranno rimossi il record del profilo Campaign e le voci di registro associate; se invece si elimina un profilo regolarmente, verrà eliminato solo il record del profilo Campaign, lasciando i residui nei registri di Campaign. Se la funzione di eliminazione del profilo è abilitata nell’integrazione, dovranno essere seguiti ulteriori passaggi per elaborare correttamente le richieste di privacy dell’interessato. Consulta i passaggi della sezione [Sezione Privacy di seguito](#manage-privacy-requests).

## Privacy{#acs-msdyn-manage-privacy}

Questa integrazione è progettata per trasferire i dati degli utenti finali tra Microsoft Dynamics 365 e Adobe Campaign Standard. Questi dati includono informazioni personali se contenute nei dati dell’utente finale.  In qualità di titolare del trattamento, la tua azienda è responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili alla raccolta e all’utilizzo dei dati personali.

Questa integrazione è progettata per trasferire i dati dell’utente finale (incluse, a titolo esemplificativo e non esaustivo, le informazioni personali, se contenute nei dati dell’utente finale) tra Microsoft Dynamics 365 e Adobe Campaign Standard. In qualità di titolare del trattamento, la tua azienda è responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili alla raccolta e all’utilizzo dei dati personali.

L’integrazione non genera alcun problema di privacy dell’interessato (ad es., RGPD) per quanto riguarda l’eliminazione o la gestione di altre richieste di privacy (ad eccezione della rinuncia). Quando si elaborano le richieste di accesso a dati personali, è necessario farlo in Microsoft Dynamics 365 e Campaign (tramite Adobe Experience Platform Privacy Service) in modo indipendente.

Se hai configurato l’integrazione in modo da emettere regolari chiamate di eliminazione profilo a Campaign quando un contatto viene eliminato in Dynamics 365, è necessario seguire i passaggi seguenti. Verificare che non vengano apportati aggiornamenti al record in questione durante questo processo.

1. Invia la richiesta di eliminazione della privacy a [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Monitora la richiesta fino al suo completamento

1. Verifica che il record non sia più presente nell’istanza Campaign

1. (Subito dopo) Problema di eliminazione della privacy in Dynamics 365

1. Verificare che il record sia stato rimosso da entrambi i sistemi


>[!IMPORTANT]
>
>Se un record di risorse personalizzate di Campaign contiene informazioni personali applicabili all’utilizzo di Campaign da parte di un cliente, tale record deve essere collegato a un record di profilo di Campaign corrispondente (direttamente o tramite un’altra risorsa personalizzata) in modo che un’eliminazione correlata alla privacy nel record di profilo possa eliminare anche il record di risorse personalizzate collegato contenente informazioni personali; le opzioni di collegamento e eliminazione tra le entità devono essere configurate per abilitare la rimozione in serie dei record collegati. Le informazioni personali non devono essere inserite in una risorsa personalizzata non collegata al profilo.

## Rinuncia {#opt-out}

A causa delle differenze negli attributi di rinuncia tra Microsoft Dynamics 365 e Campaign e delle differenze nei requisiti aziendali di ciascun cliente, la mappatura della rinuncia è stata lasciata come un esercizio da completare per il cliente.  È importante garantire che le rinunce siano correttamente mappate tra i sistemi in modo che le preferenze di rinuncia dell’utente finale siano mantenute e che non riceva una comunicazione tramite un canale da cui ha rinunciato.

Tieni presente che solo i seguenti elementi possono essere utilizzati nelle mappature di rinuncia:

* Attributi della campagna con il prefisso &quot;Non contattare più tramite&quot; (ad esempio, Non contattare più tramite e-mail), oppure

* l’attributo specifico per il CCPA

Ulteriori informazioni sui campi dell’entità profilo sono disponibili [qui](../../developing/using/datamodel-profile.md).

In Dynamics 365, la maggior parte dei campi di rinuncia hanno il prefisso &quot;donot&quot;, tuttavia, puoi utilizzare anche altri attributi a scopo di rinuncia se i tipi di dati sono compatibili.

Durante il provisioning dell’integrazione, potrai specificare la configurazione di rinuncia necessaria per la tua azienda:

* **Unidirezionale (da Microsoft Dynamics 365 a Campaign)**: Dynamics 365 è la fonte di verità per le rinunce. Gli attributi di rinuncia verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard
* **Unidirezionale (da Campaign a Microsoft Dynamics 365)**: Campaign Standard è la fonte di verità per le rinunce. Gli attributi di rinuncia verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* **Bidirezionale**: Dynamics 365 E Campaign Standard sono entrambe fonti di verità. Gli attributi di rinuncia verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

In alternativa, se disponi di un processo separato per gestire la sincronizzazione delle rinunce tra i sistemi, il flusso di dati di rinuncia dell’integrazione può essere disabilitato.

La configurazione della rinuncia bidirezionale utilizza la logica per determinare quale valore scrivere in entrambi i sistemi. La logica confronta le marche temporali tra i due sistemi (modifica a livello di record in Dynamics 365, modifica a livello di attributo in Campaign) per determinare quale sistema prevale. Se Campaign contiene la marca temporale più recente, prevale il valore Campaign. Se Dynamics 365 contiene la marca temporale più recente o se sono uguali, allora opt-out=TRUE avrà esito positivo (supponendo che uno dei valori sia TRUE).

Scopri come selezionare le opzioni di consenso/diniego in [questa sezione](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Rivedi e, se appropriato, aggiorna le regole di tipologia predefinite e specifiche in Adobe Campaign prima di apportare modifiche qui per garantire che tali modifiche siano applicate correttamente a tutte le comunicazioni in uscita. Ad esempio, assicurati che eventuali mappature alle preferenze di rinuncia riflettano accuratamente le scelte di intento/comunicazione del destinatario e non interrompano inavvertitamente la consegna di messaggi di relazione o transazionali come le conferme degli ordini dei clienti.

Se hai selezionato **Bidirezionale** o **Unidirezionale (da Campaign a Microsoft Dynamics 365)** configurazione di rinuncia, i dati di rinuncia di Campaign verranno esportati periodicamente tramite il flusso di lavoro nell’area di archiviazione SFTP di Campaign (consulta &quot;Utilizzo di Campaign SFTP di seguito&quot;). Nel caso in cui il flusso di lavoro di rinuncia di Campaign si interrompa, dovrai riavviare manualmente il prima possibile per ridurre la possibilità di sincronizzazioni di rinuncia perse.

>[!IMPORTANT]
>
>Se hai bisogno di **Bidirezionale** o **Unidirezionale (da Campaign a Microsoft Dynamics 365)** configurazione della rinuncia, dovrai effettuare la richiesta al contatto tecnico del tuo Adobe per la configurazione dei flussi di lavoro di rinuncia nell’istanza Campaign

## Utilizzo SFTP della campagna

L’archiviazione SFTP di Campaign dovrà essere utilizzata dall’integrazione nei casi d’uso seguenti.  È necessario assicurarsi che l’account SFTP disponga di una capacità di archiviazione adeguata per soddisfare questi casi d’uso. Il superamento della capacità di archiviazione SFTP concessa in licenza può compromettere gravemente l’utilizzo funzionale di Campaign, l’integrazione e/o l’account SFTP.

| Caso d’uso | Descrizione |
|---|---|
| Bidirezionale e unidirezionale (da Campaign a Microsoft Dynamics 365) | I flussi di dati di rinuncia bidirezionali e unidirezionali (da Campaign a Microsoft Dynamics 365) utilizzeranno l’archiviazione SFTP di Campaign. Un flusso di lavoro di Campaign esporta le modifiche incrementali nella cartella SFTP. Da lì, l’integrazione acquisirà i record e i processi. |
| Registri di rinuncia | I registri di output dal connettore sono utili per la risoluzione dei problemi di integrazione. È possibile attivare/disattivare i registri di output. |


>[!IMPORTANT]
>
>Sei responsabile delle informazioni a cui accedi e che scarichi dalle cartelle SFTP. Se le informazioni contengono dati personali, sei responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili. [Ulteriori informazioni](#acs-msdyn-manage-privacy).

## Gestione dei dati

### Dati campagna esistenti

Questa integrazione sincronizzerà i contatti e le entità personalizzate da Microsoft Dynamics 365 a Campaign. I record di Campaign creati al di fuori dell’integrazione (ovvero non creati dal processo di sincronizzazione) non verranno modificati dall’integrazione, compresi i record di Campaign esistenti al momento della configurazione dell’integrazione.

Poiché questa integrazione utilizza **[!UICONTROL externalId]** in Campaign per sincronizzare i record del profilo di Campaign con i record dei contatti di Dynamics 365, questo campo Campaign (**[!UICONTROL externalId]** ) deve essere compilato con Microsoft Dynamics 365 **[!UICONTROL contactId]** per i record da sincronizzare da Microsoft Dynamics 365.  Le entità personalizzate vengono sincronizzate anche utilizzando un ID univoco di Microsoft Dynamics 365. L’entità personalizzata Campaign dovrà includere questo attributo ID come colonna di tabella. La colonna externalId può essere utilizzata per memorizzare questo valore di attributo, ma non è necessaria per le entità personalizzate di Campaign.

Tieni presente che Microsoft Dynamics 365 è ancora la fonte di verità e che i dati del profilo Campaign possono essere sovrascritti man mano che l’integrazione rileva aggiornamenti sul lato Dynamics 365.  Potrebbero essere necessari altri passaggi per abilitare l’integrazione, a seconda della distribuzione esistente; pertanto, si consiglia di lavorare a stretto contatto con il contatto tecnico Adobe.

>[!NOTE]
>
>A causa della complessità delle implementazioni esistenti per i clienti, ti consigliamo di collaborare con il contatto tecnico Adobe durante la pianificazione e la configurazione dell’integrazione.

### Frequenza di sincronizzazione dati

L’integrazione utilizza un’architettura che consente di rilevare gli aggiornamenti e aggiungerli alla &quot;coda&quot; di elaborazione poco dopo che si verificano in Microsoft Dynamics 365 (ad esempio, streaming e non elaborazione batch). Per questo motivo, non è necessario specificare le frequenze di esecuzione o le pianificazioni del flusso di dati.

L’eccezione è rappresentata dai flussi di dati di rinuncia bidirezionali e di Campaign a Dynamics 365. Per queste configurazioni di rinuncia, i record di Campaign aggiornati vengono esportati in SFTP tramite un flusso di lavoro di Campaign una volta al giorno, dopo di che lo strumento di integrazione legge il file ed elabora il record.

### Contratto di utilizzo dati

Se ti trovi in aree EMEA o APAC, alcuni dei tuoi dati verranno elaborati negli Stati Uniti come parte di questa integrazione. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Guardrail e limitazioni

>[!IMPORTANT]
>
>Alcune azioni da parte tua (ad esempio, acquisizione iniziale dei record, riproduzione dei dati dei record, ecc.) potrebbe causare l’acquisizione di un carico elevato di record da Microsoft Dynamics 365 all’istanza Adobe Campaign. Per ridurre il rischio di problemi di prestazioni, si consiglia di arrestare tutti i processi di Campaign (ad esempio, nessuna attività di marketing, nessuna esecuzione di flussi di lavoro, ecc.) fino a dopo l’acquisizione del grande carico di record in Campaign.

### Entità personalizzate

Il [Integrazione con Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) supporta le entità personalizzate, consentendo la sincronizzazione di entità personalizzate in Dynamics 365 con le risorse personalizzate corrispondenti in Campaign.

L’integrazione supporta sia tabelle collegate che non collegate.

Durante la configurazione dei flussi di dati di entità personalizzate, è importante tenere presente quanto segue:

* La creazione e la modifica di risorse personalizzate di Campaign sono operazioni sensibili che devono essere eseguite solo da utenti esperti.
* Per i flussi di dati di entità personalizzate, il rilevamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.
* Se un record padre e un record figlio collegato vengono creati quasi contemporaneamente in Dynamics 365, a causa dell’elaborazione parallela dell’integrazione, esiste una leggera possibilità che un nuovo record figlio possa essere scritto in Campaign prima del relativo record padre.

* Se l&#39;elemento padre e l&#39;elemento figlio sono collegati sul lato campagna utilizzando **Collegamento semplice con cardinalità 1** , il record secondario rimarrà nascosto e inaccessibile (tramite l’interfaccia utente o l’API) fino a quando il record principale non arriva in Campaign.

* (supponendo che **Collegamento semplice con cardinalità 1** in Campaign) Se il record secondario viene aggiornato o eliminato in Dynamics 365 e tale modifica viene scritta in Campaign prima che il record principale venga visualizzato in Campaign (probabilmente, ma è una possibilità remota), tale aggiornamento o eliminazione non verrà elaborato in Campaign e verrà generato un errore. In caso di aggiornamento, il record in questione dovrà essere aggiornato nuovamente in Dynamics 365 per sincronizzare il record aggiornato. In caso di eliminazione, il record in questione dovrà essere gestito separatamente dal lato Campaign, in quanto non esiste più un record in Dynamics 365 da eliminare o aggiornare.

* Se ci si imbatte in una situazione in cui si ritiene di disporre di record secondari nascosti e non è possibile accedervi, è possibile modificare temporaneamente il tipo di collegamento cardinalità in **Collegamento semplice con cardinalità 0 o 1** per accedere a tali documenti.

È disponibile una panoramica più completa delle risorse personalizzate di Campaign [in questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

### Guardrail di integrazione

Quando si pianifica l’utilizzo di questa integrazione, è necessario tenere conto dei seguenti guardrail. Se ritieni di superare questi guardrail, rivolgiti al tuo rappresentante tecnico Adobe.

* Sarà necessario concedere in licenza il pacchetto Campaign appropriato per supportare il volume di chiamate al motore generato dall’integrazione. Il superamento del volume di chiamate al motore concesso in licenza potrebbe causare un deterioramento delle prestazioni di Campaign.

   Utilizza quanto segue per aiutare a stimare il volume di chiamate del motore dall’integrazione:

   * Inserimenti di record (ad esempio, nuovo record): 1 chiamata del motore
   * Eliminazioni record: 1 chiamata motore
   * Aggiornamenti dei record: 2 chiamate al motore (solo 1 chiamata se il record di destinazione è identico al record di origine, ovvero se non viene apportata alcuna modifica al record Campaign)

   Quando si calcola il volume complessivo delle chiamate al motore di Campaign, è importante tenere conto di altre origini di chiamate al motore, tra cui pagine di destinazione, WebApps, JSSP, API, registrazioni di app mobili e così via.

   Visualizza le informazioni sul pacchetto Adobe Campaign Standard qui: [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html)

* L’integrazione supporta un massimo di 15 milioni di record totali per la sincronizzazione iniziale con le risorse in Campaign. La sincronizzazione incrementale è limitata dal pacchetto Adobe Campaign Standard.

* L’offerta di integrazione standard include il supporto di un massimo di venti entità personalizzate, ciascuna con una dimensione massima di 50 colonne.

* Dovrai creare e pubblicare le risorse personalizzate prima di implementare l’integrazione.

* La profondità massima della tabella quando si collegano le tabelle è due (ad esempio, tabella1->tabella2->tabella3)

* L’integrazione supporta fino a 5 colonne collegate per risorsa personalizzata. Il collegamento di più colonne tra risorse personalizzate può avere un notevole impatto sulle prestazioni. **Collegamento semplice con cardinalità 0 o 1** è da preferirsi rispetto a **Collegamento semplice con cardinalità 1**.

* L’integrazione supporta la trasformazione tra tipi di dati primitivi di Microsoft Dynamics 365 (booleano, intero, decimale, doppio, stringa, data e ora, data) e tipi di dati di Adobe Campaign Standard (intero, booleano, float, doppio, data, datetime, stringa). I tipi di dati più avanzati vengono interpretati come stringhe e sincronizzati così come sono.

* Potrebbe essere necessario stabilire finestre di manutenzione per l’onboarding tra Adobe e il cliente.

* Tieni presente che aumenti significativi o &quot;picchi&quot; nell’utilizzo dell’integrazione (ad esempio, un forte aumento di record nuovi o aggiornati) possono causare rallentamenti nella sincronizzazione dei dati.

* Come parte dell’integrazione, è previsto il completamento dei passaggi di configurazione di pre-integrazione in Microsoft Azure e Dynamics 365. Consulta i passaggi di configurazione [in questa pagina](../../integrating/using/d365-acs-configure-d365.md)

* È previsto che inserirai i modelli dati di Dynamics 365 e Campaign nell’integrazione e che li manterrai.

### Limiti di integrazione

L’integrazione è stata progettata per risolvere il caso d’uso generale dello spostamento di dati comune tra Microsoft Dynamics 365 e Campaign, ma non è destinata a risolvere ogni caso d’uso specifico di ciascun cliente:

* L’integrazione non genera alcun problema di eliminazione di dati personali (ad es., GDPR). La responsabilità di soddisfare le richieste sulla privacy degli utenti finali spetta al cliente; tali richieste devono essere effettuate in Campaign (tramite Adobe Experience Platform Privacy Service) e Dynamics 365 in modo indipendente. Se necessario, l’integrazione può eseguire eliminazioni regolari per facilitare la sincronizzazione dei dati.   Revisione [la sezione Privacy](#manage-privacy-requests) per ulteriori informazioni.

* Da Campaign a Dynamics 365 non verranno sincronizzati dati di profilo o di entità personalizzate, ad eccezione delle informazioni di rinuncia (se configurate dal cliente).

* La gestione delle sottoscrizioni alle campagne (ad esempio, abbonamenti/annullamenti di abbonamenti) non è supportata in modalità nativa.

* La composizione e l’attivazione di campagne e-mail di Campaign da Dynamics 365 non sono supportate.

* L’integrazione **non** supporta il rimodellamento dei dati tra i modelli dati di Dynamics 365 e Campaign Standard. È previsto che l’integrazione sincronizzi una tabella Dynamics 365 in una tabella Campaign.
