---
solution: Campaign Standard
product: campaign
title: Gestione dei dati di Campaign e Microsoft Dynamics 365
description: Campaign Standard e Microsoft Dynamics 365 gestiscono i dati comuni
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '2467'
ht-degree: 1%

---


# Best practice e limitazioni {#acs-msdyn-best-practices}

## Gestisci dati {#acs-msdyn-manage-data}

Per la sincronizzazione delle entità di contatto e personalizzata, questa integrazione considera **Microsoft Dynamics 365 come l&#39;origine della verità**.  Eventuali modifiche agli attributi sincronizzati devono essere apportate in Dynamics 365 e non in  Adobe Campaign Standard).  Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte in Campaign durante la sincronizzazione, in quanto la sincronizzazione avviene in una sola direzione.

Facoltativamente, l&#39;integrazione può essere configurata per eseguire chiamate di eliminazione profilo a Campaign quando un contatto viene eliminato in Dynamics 365 per mantenere l&#39;integrità dei dati. Tuttavia, l’eliminazione di un profilo è diversa dall’eliminazione della privacy. Un&#39;eliminazione della privacy in Campaign rimuoverà il record del profilo della campagna e le relative voci di registro; mentre un&#39;eliminazione regolare del profilo eliminerà solo il record del profilo della campagna, lasciando i resti indietro nei registri delle campagne. Se la funzione di eliminazione del profilo è abilitata nell&#39;integrazione, per elaborare correttamente le richieste di privacy degli interessati dovranno essere seguiti passaggi aggiuntivi. Fare riferimento ai passaggi descritti nella sezione [Privacy di seguito](#manage-privacy-requests).

## Privacy{#acs-msdyn-manage-privacy}

Questa integrazione è progettata per trasferire i dati utente finale tra Microsoft Dynamics 365 e  Adobe Campaign Standard. Questi dati includono informazioni personali se sono contenuti nei dati dell&#39;utente finale.  In qualità di titolare del trattamento dei dati, la tua azienda è responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili alla raccolta e all&#39;uso dei dati personali.

Questa integrazione è progettata per trasferire i dati degli utenti finali (compresi, tra l&#39;altro, quelli personali, se contenuti nei dati degli utenti finali), tra Microsoft Dynamics 365 e  Adobe Campaign Standard. In qualità di titolare del trattamento dei dati, la tua azienda è responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili alla raccolta e all&#39;uso dei dati personali.

L&#39;integrazione non emette alcun soggetto di dati per la privacy (ad esempio, GDPR), elimina o gestisce qualsiasi altra richiesta di privacy (ad eccezione del rifiuto). Durante l&#39;elaborazione delle richieste di privacy, è necessario farlo sia in Microsoft Dynamics 365 che in Campaign (tramite l&#39;Adobe Experience Platform Privacy Service ), in modo indipendente.

Se hai configurato l&#39;integrazione per eseguire regolarmente chiamate di eliminazione dei profili a Campaign quando un contatto viene eliminato in Dynamics 365, devi seguire i passaggi indicati di seguito. Verificare che durante questo processo non siano apportati aggiornamenti al record in questione.

1. Emissione della richiesta di eliminazione della privacy su [ Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Monitorare la richiesta fino al completamento

1. Verifica che il record non sia più nell&#39;istanza Campaign

1. (Presto dopo) Problema di eliminazione della privacy in Dynamics 365

1. Verifica che il record sia stato rimosso da entrambi i sistemi

Di seguito sono riportati i collegamenti per aiutarvi a implementare le richieste di accesso e/o di eliminazione relative alla privacy in ogni sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Se un record di risorse personalizzate della campagna contiene informazioni personali applicabili all&#39;uso di Campaign da parte del cliente, tale record deve essere collegato a un record di profilo della campagna corrispondente (direttamente o tramite un&#39;altra risorsa personalizzata), in modo che un&#39;eliminazione correlata alla privacy nel record di profilo possa anche eliminare il record di risorse personalizzate collegato contenente informazioni personali; le opzioni di collegamento ed eliminazione tra le entità devono essere configurate per consentire la rimozione in cascata dei record collegati. Le informazioni personali non devono essere inserite in una risorsa personalizzata non collegata al profilo.

## Rifiuto {#opt-out}

A causa delle differenze negli attributi di rifiuto tra Microsoft Dynamics 365 e Campaign e delle differenze nei requisiti aziendali di ciascun cliente, la mappatura della rinuncia è stata lasciata come esercizio per il completamento del cliente.  È importante garantire che le opzioni di rifiuto siano mappate correttamente tra i sistemi in modo che le preferenze di rifiuto dell&#39;utente finale vengano mantenute e che non ricevano una comunicazione tramite un canale da cui hanno rinunciato.

Nelle mappature di rinuncia è possibile utilizzare solo i seguenti elementi:

* Attributi della campagna con il prefisso &quot;Non più contattare per&quot; (ad esempio, Non più contattare per e-mail), oppure

* l&#39;attributo specifico per CCPA

Ulteriori informazioni sui campi delle entità profilo sono disponibili [qui](../../developing/using/datamodel-profile.md).

In Dynamics 365, la maggior parte dei campi di rinuncia ha il prefisso &quot;donot&quot;, tuttavia, se i tipi di dati sono compatibili, è anche possibile utilizzare altri attributi a scopo di rifiuto.

Durante il provisioning dell&#39;integrazione, avrete la possibilità di specificare quale configurazione di rifiuto avete bisogno per la vostra azienda:

* **Unidirezionale (da Microsoft Dynamics 365 a Campaign)**: Dynamics 365 è l&#39;origine della verità per i opt-out. Gli attributi di rifiuto verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard
* **Unidirezionale (da Campaign a Microsoft Dynamics 365)**: Il Campaign Standard è la fonte di verità per le opposizioni. Gli attributi di rifiuto verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* **Bidirezionale**: Dynamics 365 AND Campaign Standard sono entrambe fonti di verità. Gli attributi di rifiuto verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

In alternativa, se si dispone di un processo separato per gestire la sincronizzazione di rinuncia tra i sistemi, il flusso di dati di rinuncia dell&#39;integrazione può essere disattivato.

La configurazione bidirezionale di rinuncia utilizza la logica per determinare quale valore scrivere in entrambi i sistemi. La logica confronta le marche temporali tra i due sistemi (modifica a livello di record in Dynamics 365, modifica a livello di attributo in Campaign) per determinare quale sistema prevale. Se Campaign contiene la marca temporale più recente, il valore Campaign prevale. Se Dynamics 365 contiene la marca temporale più recente o se è uguale, optout=TRUE vincerà (supponendo che uno dei valori sia TRUE).

Scoprite come selezionare le opzioni di opt-in/out in [questa sezione](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Rivedete e, se appropriato, aggiornate le regole di tipologia predefinite e specifiche in  Adobe Campaign prima di apportare le modifiche qui per garantire che tali modifiche siano correttamente applicate a tutte le comunicazioni in uscita. Ad esempio, accertatevi che le mappature delle preferenze di rifiuto riflettano accuratamente le scelte di intenti/comunicazione del destinatario e non interrompano inavvertitamente la consegna di relazioni o messaggi transazionali come le conferme dell&#39;ordine del cliente.

Se hai selezionato la configurazione **Bidirezionale** o **Unidirezionale (da Campaign a Microsoft Dynamics 365)** di rifiuto, i dati di rifiuto della campagna verranno esportati periodicamente tramite il flusso di lavoro nell&#39;area di archiviazione SFTP della campagna (vedi &quot;Utilizzo SFTP campagna di seguito&quot;). Nel caso in cui i flussi di lavoro di rifiuto della campagna si arrestino, sarà necessario riavviare manualmente il più presto possibile per ridurre la possibilità di mancata sincronizzazione.

>[!IMPORTANT]
>
>Se è necessaria la configurazione **Bidirezionale** o **Unidirezionale (da Campaign a Microsoft Dynamics 365)** opt-out, sarà necessario effettuare la richiesta al contatto tecnico  Adobe affinché i flussi di lavoro di rifiuto siano impostati nell&#39;istanza Campaign

## Utilizzo SFTP campagna

Lo storage SFTP della campagna dovrà essere utilizzato dall&#39;integrazione nei casi di utilizzo indicati di seguito.  Sarà necessario assicurarsi che il tuo account SFTP disponga di capacità di storage adeguate per poter gestire questi casi d&#39;uso. Superare la capacità di storage SFTP concessa in licenza potrebbe compromettere gravemente l&#39;utilizzo funzionale di Campaign, l&#39;integrazione e/o l&#39;account SFTP.

| Caso d’uso | Descrizione |
|---|---|
| Bidirezionale e unidirezionale (da Campaign a Microsoft Dynamics 365) | I flussi di dati bidirezionali e unidirezionali (da Campaign a Microsoft Dynamics 365) per la rinuncia utilizzeranno l&#39;archiviazione SFTP della campagna. Un flusso di lavoro Campaign esporta le modifiche incrementali nella cartella SFTP. Da qui, l&#39;integrazione recupererà i record e il processo. |
| Registri di rifiuto | I registri di uscita dal connettore saranno utili per risolvere eventuali problemi di integrazione. I registri di output possono essere attivati/disattivati. |


>[!IMPORTANT]
>
>Siete responsabili delle informazioni a cui avete accesso e che scaricate dalle cartelle SFTP. Se le informazioni contengono dati personali, l&#39;Utente è tenuto a rispettare tutte le leggi e le normative vigenti in materia di privacy. [Ulteriori informazioni](#acs-msdyn-manage-privacy).

## Gestione dati

### Dati campagna esistenti

Questa integrazione sincronizzerà i contatti e le entità personalizzate da Microsoft Dynamics 365 a Campaign. I record delle campagne creati al di fuori dell&#39;integrazione (ovvero, non creati dal processo di sincronizzazione) non verranno modificati dall&#39;integrazione, inclusi i record delle campagne esistenti al momento della configurazione dell&#39;integrazione.

Poiché questa integrazione utilizza il campo **[!UICONTROL externalId]** di Campaign per sincronizzare i record dei profili di Campaign con i record di contatto Dynamics 365, il campo Campaign (**[!UICONTROL externalId]** ) deve essere popolato con Microsoft Dynamics 365 **[!UICONTROL contactId]** per i record che si desidera sincronizzare da Microsoft Dynamics 365.  Le entità personalizzate vengono sincronizzate anche utilizzando un ID univoco di Microsoft Dynamics 365. L&#39;entità personalizzata Campaign dovrà includere questo attributo ID come colonna di tabella. La colonna externalId può essere utilizzata per memorizzare questo valore attributo, ma non è necessaria per le entità personalizzate di Campaign.

Ricorda che Microsoft Dynamics 365 è ancora l&#39;origine della verità e che i dati del profilo Campaign possono essere sovrascritti quando l&#39;integrazione rileva gli aggiornamenti sul lato Dynamics 365.  Possono essere necessari altri passaggi per abilitare l&#39;integrazione, a seconda della distribuzione esistente; si consiglia pertanto di collaborare strettamente con il contatto tecnico  Adobe.

>[!NOTE]
>
>A causa della complessità delle implementazioni dei clienti esistenti, è consigliabile utilizzare il contatto tecnico  Adobe al momento della pianificazione e della configurazione dell&#39;integrazione.

### Frequenza sincronizzazione dati

L&#39;integrazione utilizza un&#39;architettura che consente agli aggiornamenti di essere rilevati e aggiunti alla &quot;coda&quot; di elaborazione subito dopo che si verificano in Microsoft Dynamics 365 (ad es., streaming, non elaborazione batch). Per questo motivo, non è necessario specificare le frequenze di esecuzione del flusso di dati o i programmi.

L&#39;eccezione a questo è rappresentata dai flussi di dati bidirezionali e Campaign to Dynamics 365 opt-out. Per queste configurazioni di rifiuto, i record Campaign aggiornati vengono esportati su SFTP tramite un flusso di lavoro Campaign una volta al giorno, dopo di che lo strumento di integrazione legge il file ed elabora il record.

### Accordo sull&#39;utilizzo dei dati

Se ti trovi nelle aree EMEA o APAC, alcuni dei tuoi dati saranno elaborati negli Stati Uniti come parte di questa integrazione. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Gardrail e limitazioni

>[!IMPORTANT]
>
>Alcune azioni da parte dell&#39;utente (ad esempio, acquisizione iniziale di record, riproduzione di dati di record, ecc.) potrebbe causare l&#39;acquisizione di un grande carico di record da Microsoft Dynamics 365 all&#39;istanza Adobe Campaign . Per ridurre il rischio di problemi di prestazioni, si consiglia di arrestare tutti i processi di Campaign (ad esempio, nessuna attività di marketing, nessuna esecuzione di flussi di lavoro, ecc.) fino a quando l&#39;elevato carico di record non sarà stato trasferito in Campaign.

### Entità personalizzate

L&#39;integrazione di [Microsoft Dynamics 365- Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) supporta entità personalizzate, consentendo la sincronizzazione delle entità personalizzate in Dynamics 365 con le risorse personalizzate corrispondenti in Campaign.

L&#39;integrazione supporta tabelle collegate e non collegate.

Quando si configurano flussi di dati di entità personalizzati, è importante tenere presente quanto segue:

* La creazione e la modifica di risorse personalizzate per Campaign sono operazioni sensibili che devono essere eseguite solo da utenti esperti.
* Per i flussi di dati di entità personalizzati, il tracciamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.
* Se in Dynamics 365 viene creato un record padre e un record figlio collegato vicino alla stessa ora, a causa dell&#39;elaborazione parallela dell&#39;integrazione, è possibile che un nuovo record figlio venga scritto in Campaign prima del record padre.

* Se il padre e il figlio sono collegati sul lato della campagna utilizzando l&#39;opzione **1 collegamento semplice della cardinalità**, il record figlio rimarrà nascosto e inaccessibile (tramite interfaccia utente o API) fino all&#39;arrivo del record padre in Campaign.

* (Presupponendo che **1 collegamento semplice per cardinalità** nella campagna) Se il record figlio viene aggiornato o eliminato in Dynamics 365, e che tale modifica viene scritta in Campaign prima che il record padre venga visualizzato in Campaign (non probabile, ma una possibilità remota), tale aggiornamento o eliminazione non verrà elaborato in Campaign e verrà generato un errore. In caso di aggiornamento, il record in questione dovrà essere aggiornato di nuovo in Dynamics 365 per sincronizzare il record aggiornato. In caso di eliminazione, il record in questione dovrà essere gestito separatamente sul lato Campaign, poiché non esiste più un record in Dynamics 365 da eliminare o aggiornare.

* Se ti trovi in una situazione in cui credi di avere dei record figlio nascosti e non hai modo di accedervi, puoi cambiare temporaneamente il tipo di collegamento cardinalità su **0 o 1 cardinalità link semplice** per accedere a tali record.

Una panoramica più completa delle risorse personalizzate per Campaign si trova [in questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

### Guardrail di integrazione

Nel pianificare l&#39;utilizzo di questa integrazione è necessario tenere conto dei seguenti tuteli. Consultate il vostro rappresentante tecnico  Adobe se ritenete di superare questi corrimani.

* Dovrai ottenere la licenza per il pacchetto Campaign corretto per supportare il volume di chiamate al motore generato dall&#39;integrazione. Il superamento del volume di chiamate del motore concesso in licenza potrebbe causare un peggioramento delle prestazioni della campagna.

   Utilizzate quanto segue per stimare il volume delle chiamate del motore dall&#39;integrazione:

   * Inserti di record (ad es., nuovo record): 1 chiamata al motore
   * Eliminazioni di record: 1 chiamata al motore
   * Aggiornamenti dei record: 2 chiamate al motore (solo 1 chiamata se il record di destinazione è identico al record di origine - ovvero, se non viene apportata alcuna modifica al record della campagna)

   Quando si stima il volume complessivo delle chiamate al motore Campaign, è importante tenere conto di altre origini di chiamate al motore, tra cui pagine di destinazione, WebApps, JSSP, API, registrazioni di app mobili, ecc.

   Vedi le informazioni sul pacchetto Campaign: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* L&#39;integrazione supporta un massimo di 30 milioni di contatti.

* L&#39;offerta di integrazione standard include il supporto per fino a cinque entità personalizzate, ciascuna con un massimo di 50 colonne di dimensioni.

* Prima di implementare l&#39;integrazione, dovrete creare e pubblicare le risorse personalizzate.

* La profondità massima della tabella quando si collegano le tabelle è due (cioè, tabella1->tabella2->tabella3)

* Il supporto per i tipi di dati Microsoft Dynamic 365 è limitato. Se il modello dati contiene un tipo di dati diverso dai tipi di dati semplici (ad esempio, stringhe, interi, decimali, ecc.), potrebbe essere necessario aggiornare il modello dati prima di utilizzare l&#39;integrazione.

* Se hai scelto di conservare i dati esistenti nelle entità personalizzate di Campaign, dovrai preparare i dati per l&#39;integrazione.

* Le finestre di manutenzione di onboarding possono essere stabilite tra  Adobe e il cliente.

* Tenete presente che aumenti significativi o &quot;picchi&quot; nell&#39;utilizzo dell&#39;integrazione (ad esempio, un forte aumento dei record nuovi o aggiornati) possono causare rallentamenti nella sincronizzazione dei dati.

* Come parte dell&#39;integrazione, è previsto di completare i passaggi di configurazione pre-integrazione in Microsoft Azure e Dynamics 365. Vedere i passaggi di configurazione [in questa pagina](../../integrating/using/d365-acs-configure-d365.md)

* È previsto che i modelli di dati Dynamics 365 e Campaign vengano portati all&#39;integrazione e che vengano mantenuti.

### Limiti di integrazione

L&#39;integrazione è stata progettata per risolvere il caso d&#39;uso generale dello spostamento di dati tra Microsoft Dynamics 365 e Campaign, ma non è stata progettata per risolvere ogni caso d&#39;uso specifico per ciascun cliente:

* L&#39;integrazione non emette alcun elemento di privacy (ad esempio, GDPR) eliminato. La responsabilità di soddisfare le richieste di privacy degli utenti finali spetta al cliente; tali richieste devono essere effettuate sia in Campaign (tramite l&#39;Adobe Experience Platform Privacy Service ) che in Dynamics 365 in modo indipendente. Se necessario, l&#39;integrazione può rilasciare delle eliminazioni regolari per facilitare la sincronizzazione dei dati.   Per ulteriori informazioni, vedere [la sezione sulla privacy](#manage-privacy-requests).

* Nessun profilo o dati di entità personalizzati verrà sincronizzato da Campaign a Dynamics 365, ad eccezione delle informazioni di rifiuto (se configurate dal cliente).

* La gestione degli abbonamenti alle campagne (ad es., abbonamenti/annullamento di iscrizioni) non è supportata in modo nativo.

* La composizione e l&#39;attivazione delle campagne e-mail di Campaign da Dynamics 365 non è supportata.

* L&#39;integrazione **not** supporta la rimozione dei dati tra i modelli di dati Dynamics 365 e Campaign Standard. È previsto che l&#39;integrazione sincronizzerà una tabella di Dynamics 365 in una tabella di Campaign.
