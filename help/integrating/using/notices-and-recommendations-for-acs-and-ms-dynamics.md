---
title: '"Utilizzo di Campaign Standard e Microsoft Dynamics 365: Avvisi e raccomandazioni"'
description: Informazioni su avvisi e suggerimenti per l'utilizzo di Campaign Standard e Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 620be6615d162672948c3dccdae2752b8c999c47

---


# Utilizzo di Campaign Standard e Microsoft Dynamics 365: Avvisi e raccomandazioni

## Supporto di regione

Questa integrazione è disponibile nelle regioni America del Nord, EMEA e APAC.

Se ti trovi nelle aree EMEA o APAC, alcuni dei tuoi dati saranno elaborati negli Stati Uniti come parte di questa integrazione. For more information, refer to [this section](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Origine della verità per la sincronizzazione dei contatti unidirezionali

Per la sincronizzazione di entità Contatto e personalizzata, questa integrazione considera Dynamics 365 come l&#39;origine della verità. Eventuali modifiche agli attributi sincronizzati devono essere apportate in Microsoft Dynamics 365, non in Adobe Campaign Standard. Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte in Campaign durante la sincronizzazione, in quanto la sincronizzazione avviene in una sola direzione.  Inoltre, la sincronizzazione contatti è progettata per estrarre tutti i record Contatto, sia che siano contrassegnati come attivi o inattivi in Microsoft Dynamics 365.

## Gestione delle richieste di privacy

Questa integrazione è progettata per trasferire i dati utente finale (compresi, tra l&#39;altro, quelli personali, se contenuti nei dati dell&#39;utente finale) tra Microsoft Dynamics 365 e Adobe Campaign Standard.  In qualità di titolare del trattamento dei dati, la tua azienda è responsabile del rispetto di tutte le leggi e le normative sulla privacy applicabili alla raccolta e all&#39;uso dei dati personali.

Per questa integrazione, è necessario elaborare ogni richiesta di oggetto dati in ciascun sistema in modo indipendente affinché la modifica possa riflettersi in entrambi i database. La modifica deve essere prima eseguita in Microsoft Dynamics 365 e quindi in Adobe Campaign Standard. L&#39;unica eccezione è che una richiesta di eliminazione correlata alla privacy verrà aggiunta alla coda Strumenti per la privacy in Campaign Standard quando un contatto viene eliminato in Dynamics 365.

Di seguito sono riportati i collegamenti per aiutarvi a implementare le richieste di accesso e/o di eliminazione relative alla privacy in ogni sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## Eliminazione dei contatti

Poiché Dynamics 365 è l&#39;origine della verità, le eliminazioni di contatti in Dynamics 365 si rifletteranno in Campaign.

Quando un contatto viene eliminato in Dynamics 365, l&#39;integrazione mette in coda una richiesta di eliminazione correlata alla privacy nella schermata Richieste/strumenti per la privacy della campagna.  Se hai disabilitato il processo in due fasi per le richieste di eliminazione relative alla privacy, Campaign si occuperà dell&#39;eliminazione.

Tuttavia, se il processo in due fasi è attivato, sarà necessario accedere alla schermata Richieste per la privacy/strumenti, dopo l&#39;esecuzione dei flussi di lavoro tecnici per la privacy, e confermare se i record possono essere eliminati.  Solo allora Campaign si occuperà dell&#39;eliminazione.

Per ulteriori dettagli, consulta [Come eseguire le richieste di eliminazione correlate alla privacy in Adobe Campaign Standard](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>Se il processo in due fasi è abilitato per le richieste di privacy in Campaign, le eliminazioni in Dynamics 365 non si rifletteranno automaticamente in Campaign.  Dovrai entrare nella schermata di richiesta della privacy per confermare le eliminazioni.

>[!NOTE]
>
>Questa integrazione crea una richiesta utilizzando l&#39;ID esterno (ovvero l&#39;ID contatto Dynamics 365) come identificatore del record/profilo.

## Rifiuto

A causa delle differenze negli attributi di rifiuto tra Dynamics 365 e Campaign e delle differenze nei requisiti aziendali di ciascun cliente, la mappatura della rinuncia è stata lasciata come esercizio per il completamento del cliente. È importante garantire che le opzioni di rifiuto siano mappate correttamente tra i sistemi in modo che le preferenze di rifiuto dell&#39;utente finale vengano mantenute e che non ricevano una comunicazione tramite un canale da cui hanno rinunciato.

Tieni presente che solo gli attributi Campaign con il prefisso &quot;blackList&quot; (ad esempio, blackListEmail) o l&#39;attributo specifico per la rinuncia CCPA possono essere utilizzati nelle mappature di rinuncia.  In Dynamics 365, la maggior parte dei campi di rinuncia ha il prefisso &quot;doNot&quot;; tuttavia, se i tipi di dati sono compatibili, è anche possibile utilizzare gli attributi personalizzati creati a scopo di rifiuto.

Durante il provisioning dell&#39;integrazione, avrete la possibilità di specificare quale configurazione di rifiuto avete bisogno per la vostra azienda:

* Dynamics 365 è l&#39;origine della verità per i opt-out: gli attributi di rifiuto verranno sincronizzati in una direzione da Dynamics 365 a Campaign Standard
* Campaign Standard è l&#39;origine di verità per i opt-out: gli attributi di rifiuto verranno sincronizzati in una direzione da Campaign Standard a Dynamics 365
* Dynamics 365 E Campaign Standard sono entrambi fonti di verità: gli attributi di rifiuto verranno sincronizzati bidirezionalmente tra Campaign Standard e Dynamics 365

Seguite le istruzioni post-provisioning riportate nella guida [utente](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) Unifi per mappare correttamente questi valori.

La configurazione bidirezionale di rinuncia utilizza la logica per determinare quale valore scrivere in entrambi i sistemi.  La logica confronta le marche temporali tra i due sistemi (modifica a livello di record in Dynamics 365, modifica a livello di attributo in Campaign) per determinare quale sistema prevale.  Se Campaign contiene la marca temporale più recente, il valore Campaign prevale.  Se Dynamics 365 contiene la marca temporale più recente o se è uguale, optout=TRUE vincerà (supponendo che uno dei valori sia TRUE).

**Rifiuti ai sensi della California Consumer Protection Act (CCPA) e di una legislazione analoga.**

La funzione di configurazione della rinuncia bidirezionale non è attualmente in grado di supportare il rispetto di alcuni requisiti legali previsti dalle leggi sulla protezione dei dati e/o da altre leggi sulla privacy dei dati. I clienti che devono rispettare l&#39;APP o requisiti legali simili relativi alle rinunce sono responsabili dell&#39;implementazione della propria soluzione di terze parti per eseguire sincronizzazioni bidirezionali.

>[!NOTE]
>
>Se la società non richiede il supporto bidirezionale per la rinuncia, si consiglia di selezionare un’opzione di rifiuto unidirezionale.

>[!NOTE]
>
>Rivedete e, se appropriato, aggiornate le regole di tipologia predefinite e specifiche in Adobe Campaign prima di apportare le modifiche qui, per assicurarvi che tali modifiche siano correttamente applicate a tutte le comunicazioni in uscita. Ad esempio, accertatevi che le mappature delle preferenze di rifiuto riflettano accuratamente le scelte di intenti/comunicazione del destinatario e non interrompano inavvertitamente la consegna di relazioni o messaggi transazionali come le conferme dell&#39;ordine del cliente.

## Dati campagna esistenti

Questa integrazione sincronizzerà Contatti ed entità personalizzate da Dynamics 365 a Campaign. I record delle campagne creati al di fuori dell&#39;integrazione (ovvero, non creati dal processo di sincronizzazione) non verranno toccati dall&#39;integrazione, compresi i record delle campagne esistenti al momento della configurazione dell&#39;integrazione.

Poiché questa integrazione utilizza il **[!UICONTROL externalId]** campo in Campaign Standard per sincronizzare i record dei profili delle campagne con i record dei contatti di Dynamics 365, questo campo Campaign (**[!UICONTROL externalId]** ) deve essere popolato con Dynamics 365 **[!UICONTROL contactId]** per i record che si desidera sincronizzare da Dynamics 365.  Per mantenere la sincronizzazione, anche le entità personalizzate dovranno avere questo campo presente e popolato correttamente.  Ricorda, tuttavia, che Dynamics 365 continuerà ad essere l&#39;origine della verità e che i dati del profilo Campaign possono essere sovrascritti quando l&#39;integrazione rileva gli aggiornamenti sul lato Dynamics 365.  Possono essere necessari altri passaggi per abilitare l&#39;integrazione, a seconda della distribuzione esistente; si consiglia pertanto di collaborare strettamente con il contatto tecnico di Adobe.

>[!NOTE]
>
>A causa della complessità delle distribuzioni dei clienti esistenti, è consigliabile collaborare con il contatto tecnico Adobe al momento della pianificazione e della configurazione dell&#39;integrazione.
