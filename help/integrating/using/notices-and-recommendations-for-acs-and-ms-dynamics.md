---
title: Gestione dei dati di Campaign e Microsoft Dynamics 365
description: Campaign Standard e Microsoft Dynamics 365 gestiscono i dati comuni
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
source-git-commit: 621c29ae08770b50629ba3d27116f93f8b5c3f62
workflow-type: tm+mt
source-wordcount: '1439'
ht-degree: 0%

---


# Gestisci i dati tra Campaign e Microsoft Dynamics 365

## Origine della verità per la sincronizzazione unidirezionale

Per la sincronizzazione delle entità di contatto e personalizzata, questa integrazione considera Dynamics 365 come l&#39;origine della verità.  Eventuali modifiche agli attributi sincronizzati devono essere apportate in Dynamics 365, non in Campaign.  Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte in Campaign durante la sincronizzazione, in quanto la sincronizzazione avviene in una sola direzione.

## Eliminazione dei contatti

Se necessario, l&#39;integrazione può essere configurata per eseguire chiamate di eliminazione profilo a Campaign quando un contatto viene eliminato in Dynamics 365, per mantenere l&#39;integrità dei dati.

Tuttavia, l’eliminazione di un profilo è diversa dall’eliminazione della privacy. Un&#39;eliminazione della privacy in Campaign rimuoverà il record del profilo della campagna e le relative voci di registro; mentre, un&#39;eliminazione regolare del profilo eliminerà solo il record del profilo ACS, lasciando i resti indietro nei registri delle campagne.

Se la funzione di eliminazione del profilo è abilitata nell&#39;integrazione, per elaborare correttamente le richieste di privacy degli interessati dovranno essere seguiti passaggi aggiuntivi. Fare riferimento ai passaggi descritti nella [sezione seguente](#manage-privacy-requests).

## Privacy

### Gestire le richieste di privacy {#manage-privacy-requests}

Questa integrazione è progettata per trasferire i dati degli utenti finali (compresi, tra l&#39;altro, quelli personali, se contenuti nei dati degli utenti finali), tra Microsoft Dynamics 365 e  Adobe Campaign Standard. In qualità di titolare del trattamento dei dati, la tua azienda è responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili alla raccolta e all&#39;uso dei dati personali.

L&#39;integrazione non emette alcun soggetto di dati per la privacy (ad esempio, GDPR), elimina o gestisce qualsiasi altra richiesta di privacy (ad eccezione del rifiuto). Durante l&#39;elaborazione delle richieste di privacy, devi farlo sia in Dynamics 365 che in Campaign (tramite l&#39;Adobe Experience Platform Privacy Service ), in modo indipendente.

Se hai configurato l&#39;integrazione per eseguire regolarmente chiamate di eliminazione dei profili a Campaign quando un contatto viene eliminato in Dynamics 365, devi seguire i passaggi indicati di seguito. Verificare che durante questo processo non siano apportati aggiornamenti al record in questione.

1. Emissione della richiesta di eliminazione della privacy ad [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Monitorare la richiesta fino al completamento

1. Verifica che il record non sia più nell&#39;istanza Campaign

1. (Presto dopo) Problema di eliminazione della privacy in Dynamics 365

1. Verifica che il record sia stato rimosso da entrambi i sistemi

Di seguito sono riportati i collegamenti per aiutarvi a implementare le richieste di accesso e/o di eliminazione relative alla privacy in ogni sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Privacy e risorse collegate {#privacy-linked-resources}

Se un record di risorse personalizzate della campagna contiene informazioni personali applicabili all&#39;uso di Campaign da parte del cliente, tale record deve essere collegato a un record di profilo della campagna corrispondente (direttamente o tramite un&#39;altra risorsa personalizzata), in modo che un&#39;eliminazione correlata alla privacy nel record di profilo possa anche eliminare il record di risorse personalizzate collegato contenente informazioni personali; le opzioni di collegamento ed eliminazione tra le entità devono essere configurate per consentire la rimozione in cascata dei record collegati. Le informazioni personali non devono essere inserite in una risorsa personalizzata non collegata al profilo.

Scopri come mappare le risorse della campagna e le entità Dynamics 365 [in questa sezione](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

## Rifiuto

A causa delle differenze negli attributi di rifiuto tra Dynamics 365 e Campaign e delle differenze nei requisiti aziendali di ciascun cliente, la mappatura della rinuncia è stata lasciata come esercizio per il completamento del cliente.  È importante garantire che le opzioni di rifiuto siano mappate correttamente tra i sistemi in modo che le preferenze di rifiuto dell&#39;utente finale vengano mantenute e che non ricevano una comunicazione tramite un canale da cui hanno rinunciato.

Tieni presente che solo gli attributi Campaign con il prefisso &quot; inserire nell&#39;elenco Bloccati&quot; (ad esempio, blockListEmail) o l&#39;attributo specifico per la rinuncia CCPA possono essere utilizzati nelle mappature di rifiuto.  In Dynamics 365, la maggior parte dei campi di rinuncia ha il prefisso &quot;donot&quot;; tuttavia, se i tipi di dati sono compatibili, è anche possibile utilizzare altri attributi a scopo di rifiuto.

Durante il provisioning dell&#39;integrazione, avrete la possibilità di specificare quale configurazione di rifiuto avete bisogno per la vostra azienda:

* Dynamics 365 è l&#39;origine della verità per i opt-out: gli attributi di rifiuto verranno sincronizzati in una direzione da Dynamics 365 a Campaign
* Campaign è la fonte di verità per i opt-out: gli attributi di rifiuto verranno sincronizzati in una direzione da Campaign a Dynamics 365
* Dynamics 365 E Campaign sono entrambi fonti di verità: gli attributi di rifiuto verranno sincronizzati bidirezionalmente tra Campaign e Dynamics 365

In alternativa, se si dispone di un processo separato per gestire la sincronizzazione di rinuncia tra i sistemi, il flusso di dati di rinuncia dell&#39;integrazione può essere disattivato.

La configurazione bidirezionale di rinuncia utilizza la logica per determinare quale valore scrivere in entrambi i sistemi. La logica confronta le marche temporali tra i due sistemi (modifica a livello di record in Dynamics 365, modifica a livello di attributo in Campaign) per determinare quale sistema prevale. Se Campaign contiene la marca temporale più recente, il valore Campaign prevale. Se Dynamics 365 contiene la marca temporale più recente o se è uguale, optout=TRUE vincerà (supponendo che uno dei valori sia TRUE).

>[!NOTE]
>
>Rivedete e, se appropriato, aggiornate le regole di tipologia predefinite e specifiche in  Adobe Campaign prima di apportare le modifiche qui per garantire che tali modifiche siano correttamente applicate a tutte le comunicazioni in uscita. Ad esempio, accertatevi che le mappature delle preferenze di rifiuto riflettano accuratamente le scelte di intenti/comunicazione del destinatario e non interrompano inavvertitamente la consegna di relazioni o messaggi transazionali come le conferme dell&#39;ordine del cliente.

Se hai selezionato la configurazione bidirezionale o Campaign to Dynamics 365 opt-out, i dati di rifiuto della campagna verranno esportati periodicamente tramite flusso di lavoro nell&#39;area di archiviazione SFTP della campagna (vedi &quot;Campaign SFTP Usage below&quot;). Nel caso in cui i flussi di lavoro di rifiuto della campagna si arrestino, sarà necessario riavviare manualmente il più presto possibile per ridurre la possibilità di mancata sincronizzazione.

## Utilizzo SFTP campagna

Lo storage SFTP della campagna dovrà essere utilizzato dall&#39;integrazione nei casi di utilizzo indicati di seguito.  Sarà necessario assicurarsi che il tuo account SFTP disponga di capacità di storage adeguate per poter gestire questi casi d&#39;uso.  Superare la capacità di storage SFTP concessa in licenza potrebbe compromettere gravemente l&#39;utilizzo funzionale di Campaign, l&#39;integrazione e/o l&#39;account SFTP.

| Caso d’uso | Descrizione |
|---|---|
| Caricamento dati iniziale | Le tabelle di Dynamics 365 con più di 500 KB di record dovranno essere esportate nell&#39;archivio SFTP della campagna per essere importate tramite il flusso di lavoro. Da quel momento in poi, l&#39;integrazione utilizzerà le API per gli aggiornamenti incrementali. |
| Rinuncia bidirezionale e Campaign to Dynamics 365 unidirezionale | I flussi di dati unidirezionali di rinuncia e di rifiuto della campagna per Dynamics 365 utilizzeranno l&#39;archiviazione SFTP della campagna. Un flusso di lavoro ACS esporta le modifiche incrementali nella cartella SFTP. Da qui, l&#39;integrazione recupererà i record e il processo. |
| Ripristino di emergenza | Nell&#39;improbabile caso di un disastro del sistema, verrà seguito il caso di utilizzo &quot;Carico dati iniziale&quot; per alimentare gli aggiornamenti incrementali a Campaign che sono stati persi. |

## Dati campagna esistenti

Questa integrazione sincronizzerà i contatti e le entità personalizzate da Dynamics 365 a Campaign. I record delle campagne creati al di fuori dell&#39;integrazione (ovvero, non creati dal processo di sincronizzazione) non verranno modificati dall&#39;integrazione, inclusi i record delle campagne esistenti al momento della configurazione dell&#39;integrazione.

Poiché questa integrazione utilizza il **[!UICONTROL externalId]** campo in Campaign per sincronizzare i record dei profili delle campagne con i record dei contatti di Dynamics 365, questo campo Campaign (**[!UICONTROL externalId]** ) deve essere popolato con Dynamics 365 **[!UICONTROL contactId]** per i record che si desidera sincronizzare da Dynamics 365.  Anche le entità personalizzate vengono sincronizzate utilizzando un ID univoco di Dynamics 365. L&#39;entità personalizzata Campaign dovrà includere questo attributo ID come colonna di tabella. La colonna externalId può essere utilizzata per memorizzare questo valore attributo, ma non è necessaria per le entità personalizzate di Campaign.

Ricorda che Dynamics 365 è ancora l&#39;origine della verità e che i dati del profilo Campaign possono essere sovrascritti quando l&#39;integrazione rileva gli aggiornamenti sul lato Dynamics 365.  Possono essere necessari altri passaggi per abilitare l&#39;integrazione, a seconda della distribuzione esistente; si consiglia pertanto di collaborare strettamente con il contatto tecnico  Adobe.

>[!NOTE]
>
>A causa della complessità delle implementazioni dei clienti esistenti, è consigliabile utilizzare il contatto tecnico  Adobe al momento della pianificazione e della configurazione dell&#39;integrazione.

## Frequenza sincronizzazione dati

L&#39;integrazione utilizza un&#39;architettura che consente agli aggiornamenti di essere rilevati e aggiunti alla &quot;coda&quot; di elaborazione subito dopo che si verificano in Dynamics 365 (ad es., streaming, non elaborazione batch). Per questo motivo, non è necessario specificare le frequenze di esecuzione del flusso di dati o i programmi.

L&#39;eccezione a questo è rappresentata dai flussi di dati bidirezionali e Campaign to Dynamics 365 opt-out. Per queste configurazioni di rifiuto, i record ACS aggiornati vengono esportati in SFTP tramite il flusso di lavoro ACS una volta al giorno, dopo di che lo strumento di integrazione legge il file ed elabora il record.

## Accordo sull&#39;utilizzo dei dati

Se ti trovi nelle aree EMEA o APAC, alcuni dei tuoi dati saranno elaborati negli Stati Uniti come parte di questa integrazione. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
