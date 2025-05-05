---
title: Aggiornamenti alla documentazione
description: Scopri tutti gli aggiornamenti più recenti della documentazione di Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: a2a524eb3d90bbe41064bdcb078f69d483f90dac
workflow-type: ht
source-wordcount: '7258'
ht-degree: 100%

---

# Aggiornamenti alla documentazione{#documentation-updates}

Oltre alle [Note sulla versione](../../rn/using/release-notes.md) di Adobe Campaign, questa pagina elenca tutti i nuovi aggiornamenti presenti nella documentazione di Adobe Campaign Standard.


## Versione 24.1 - Inverno 2024 {#release-24-1}

Sono state pubblicate le note sulla versione di Campaign Standard 24.1 inverno 2024. [Ulteriori informazioni](release-notes.md)

## Dicembre 2023 {#doc-updates-dec-2023}

Alcune importanti modifiche al servizio Android Firebase Cloud Messaging (FCM) verranno rilasciate nel 2024 e influenzeranno la tua implementazione di Adobe Campaign. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

## Versione 23.2 - Autunno 2023 {#release-23-2}

* Sono state pubblicate le note sulla versione di Campaign Standard 23.2 autunno/inverno 2023. [Ulteriori informazioni](release-notes.md)

* Il codice JWT (JSON Web Tokens) è attualmente in fase di ammortamento e viene sostituito con OAuth. La transizione viene eseguita progressivamente nelle prossime versioni di Campaign e la documentazione verrà aggiornata per riflettere tali aggiornamenti.

## Ottobre 2023 {#doc-updates-oct-2023}

* È ora disponibile la nuova interfaccia utente Trigger di Experience Cloud. Offre un’esperienza intuitiva per gestire i comportamenti dei consumatori e personalizzare l’esperienza utente. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/experience-cloud/triggers/overview.html?lang=it){target="_blank"}.

* È stata aggiunta una nota sull’utilizzo dei profili di test di trappola combinati con regole di filtraggio o di eccesso. [Ulteriori informazioni](../../sending/using/using-traps.md)

## Versione 23.1 - Primavera/estate 2023 {#release-23-1}

Sono state pubblicate le note sulla versione di Campaign Standard 23.1, primavera/estate 2023. [Ulteriori informazioni](release-notes.md)

## Novembre 2022 {#doc-updates-november-2022}

È stata aggiunta una nota per consigliare di evitare spazi vuoti nel campo ID delle consegne. [Maggiori informazioni](../../channels/using/creating-an-email.md)

Sono state aggiunte informazioni nella sezione pagina delle attività del flusso di lavoro **[!UICONTROL Extract file]** per estrarre i dati in un file CSV con una codifica specifica. [Maggiori informazioni](../../automating/using/extract-file.md)

## Versione 22.3 - Autunno/inverno 2022 {#release-22-3}

Sono state pubblicate le note sulla versione di Campaign Standard 22.3 autunno/inverno 2022. [Maggiori informazioni](release-notes.md)

<!--Data retention periods have been updated to reflect changes coming with 22.3 release. [Read more](../../administration/using/data-retention.md)-->


## Versione 22.2 - Giugno 2022 {#release-22-2}

**Miglioramento incluso nella versione**

**Adobe Notification Service** - Campaign viene fornito con Adobe Notification Service che consente alle soluzioni Experience Cloud di segnalare agli utenti Experience Cloud le attività pertinenti. [Ulteriori informazioni](../../administration/using/sending-internal-notifications.md).

**Altre modifiche**

Le integrazioni con Adobe Experience Platform Data Connector e con il servizio Audience Destinations sono ora obsolete. [Ulteriori informazioni](deprecated-features.md)

Sono state aggiunte informazioni sulla modalità di prova SMTP. [Ulteriori informazioni](../../administration/using/configuring-email-channel.md#smtp-test-mode)

## Marzo 2022 {#doc-updates-march-2022}

È stata aggiunta una nota per specificare che l’invio di bozze utilizzando la sostituzione dei profili aggiungerà dei record ai registri dei profili selezionati. [Ulteriori informazioni](../../sending/using/testing-messages-using-target.md)

## Versione 22.1 - Febbraio 2022 {#release-22-1}

**Miglioramenti inclusi nella versione**

È stato migliorato il meccanismo di esecuzione di nuovi tentativi per le consegne che comprendono contenuti importati da un URL. [Maggiori informazioni](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

È stato aggiornato il livello di accesso delle opzioni che controllano Audit: le opzioni precedenti per abilitare/disabilitare [Audit trail](../../administration/using/audit.md) non erano accessibili agli [amministratori funzionali](../../administration/using/users-management.md#functional-administrators). Con questa modifica al livello di accesso, gli amministratori funzionali possono accedere ai controlli dell’audit. [Maggiori informazioni](../../administration/using/audit.md#enable-disable-audit)

È stato aggiunto il nuovo elenco a discesa **Job historyi** (Storico dei process) alla dashboard dei messaggi. [Leggi tutto](../../sending/using/monitoring-a-delivery.md)

**Altre modifiche**

È stata aggiunta una nota di avvertenza sulle parole chiave che attivano le risposte SMS automatiche: possono contenere solo caratteri alfanumerici. [Maggiori informazioni](../../channels/using/managing-incoming-sms.md)

È stata aggiunta una nota alla sezione sulle e-mail per test A/B: se la popolazione totale è inferiore a 50k, ogni variante deve rappresentare almeno il 10% della popolazione totale. In caso contrario, i registri presenteranno un’avvertenza. [Maggiori informazioni](../../channels/using/designing-an-a-b-test-email.md)

È stata aggiornata la descrizione dell’opzione **[!UICONTROL Delete the source files after transfer]** nell’attività **Transfer file** (Trasferimento file), per ricordare all’utente di monitorare manualmente le dimensioni dei contenuti archiviati nella directory SFTP se l’opzione non è selezionata. [Maggiori informazioni](../../automating/using/transfer-file.md)

Sono stati aggiornati tutti i collegamenti obsoleti nelle sezioni **Privacy**. [Maggiori informazioni](../../start/using/privacy.md)

Nell’indice dei contenuti della documentazione di Campaign Standard è stato aggiunto un collegamento diretto alla documentazione del Pannello di controllo Campaign.

## Versione 21.3 - Settembre 2021 {#release-21-3---september-2021}

**Nuove funzionalità incluse nella versione**

Interfaccia Experience Cloud unificata e migliorata: [leggi tutto](../../start/using/interface-description.md#top-bar)

Nuova funzionalità Audit Trail: [leggi tutto](../../administration/using/audit.md)

Modalità diagnostica per flussi di lavoro: [leggi tutto](../../automating/using/managing-execution-options.md)

**Altri aggiornamenti alla documentazione per questa versione**

È stata aggiunta una nuova sezione su come rimuovere un indirizzo dall’elenco di quarantena. [Leggi tutto](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

La sezione **Quarantena rispetto a elenco Bloccati** è stata resa più chiara. [Leggi tutto](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## Luglio 2021 {#doc-updates-july-2021}

È stata aggiunta una nuova sezione per descrivere come consentire agli utenti di abbonarsi o annullare l’abbonamento a più servizi da una singola pagina di destinazione. [Leggi tutto](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

La sezione **Gestione dei dati del modulo della pagina di destinazione** è stata aggiornata e chiarita. [Leggi tutto](../../channels/using/managing-landing-page-form-data.md)

## Versione 21.2 - Giugno 2021 {#release-21-2---june-2021}

**Nuove funzionalità incluse nella versione**

Convalida delle pagine di destinazione: ora puoi aggiungere alle pagine di destinazione un’opzione di accettazione obbligatoria. [Leggi tutto](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

La sezione **Dimensione e-mail** è stata aggiornata con informazioni sulle dimensioni massime di un messaggio e-mail, che ora sono di 100 MB per impostazione predefinita. [Leggi tutto](../../sending/using/design-and-personalize.md#email-size)

**Altri aggiornamenti alla documentazione in arrivo con la versione**

Sono state aggiunte informazioni su come modificare la mappatura di destinazione in una notifica push transazionale. [Ulteriori informazioni](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## Maggio 2021 {#doc-updates-may-2021}

La sezione del rapporto **Profili attivi** è stata aggiornata. [Leggi tutto](../../audiences/using/active-profiles.md)

La pagina **Pianificazione del rilascio** è stata aggiornata con nuove date. [Leggi tutto](../../rn/using/release-planning.md)


## Aprile 2021 {#doc-updates-april-2021}

È stata aggiunta una nuova sezione su come lavorare con le origini e le destinazioni di Adobe Experience Platform per condividere i dati tra Campaign Standard e Adobe Real-time Customer Data Platform (RTCDP). [Leggi tutto](../../integrating/using/get-started-sources-destinations.md)

## Marzo 2021 {#doc-updates-march-2021}

Nuova pagina **Opzioni di assistenza e supporto**. [Leggi tutto](../../support.md)

La sezione in cui sono elencati i passaggi chiave per l’invio di un messaggio è stata migliorata con informazioni e riferimenti aggiuntivi. [Leggi tutto](../../channels/using/key-steps-to-send-a-message.md)

Sono state aggiunte informazioni per specificare che, quando si seleziona un pubblico in una query, la relativa definizione viene copiata e non inserita come riferimento. [Leggi tutto](../../audiences/using/selecting-an-audience-in-a-message.md)

Le informazioni relative al servizio Audience Destinations e al connettore dati Adobe Experience Platform sono state raggruppate in una nuova sezione.

L’origine dati **Declared ID** (ID dichiarato) può ora essere utilizzata anche con l’integrazione del servizio core People. Sono state aggiunte informazioni nella documentazione relativa all’integrazione del servizio core Campaign-Audience Manager o People. [Leggi tutto](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Sono state aggiunte informazioni su come implementare il tracciamento locale per le app mobili. [Leggi tutto](../../administration/using/local-tracking.md)

La sezione [Recapito messaggi](../../sending/using/about-deliverability.md) è stata aggiornata e ora include i collegamenti alla nuova [guida Adobe alle best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it). Tutte le informazioni generiche relative al recapito dei messaggi valide per varie soluzioni Adobe sono state spostate nell’[Appendice alla Guida alle best practice](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=it#additional-resources).

## Versione 21.1 - Febbraio 2021 {#release-21-1---february-2021}

**Nuove funzionalità incluse nella versione**

Email Feedback Service - [Leggi tutto](../../sending/using/confirming-the-send.md#message-indicators)

Miglioramenti per l’integrazione con Adobe Experience Manager - [Leggi tutto](../../integrating/using/creating-multilingual-email-aem.md)

Interfaccia unificata Experience Cloud - [Leggi tutto](../../start/using/interface-description.md#top-bar)

**Altri aggiornamenti alla documentazione in arrivo con la versione**

Sono state aggiunte informazioni su come cercare un profilo in base all’e-mail, al nome, al cognome o a qualsiasi campo personalizzato. [Leggi tutto](../../audiences/using/integrated-customer-profile.md)

Sono state aggiunte informazioni sulla nuova funzione GetOption, che consente di restituire il valore di una funzione specificata quando viene richiamato un flusso di lavoro con parametri esterni. [Leggi tutto](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

Sono state aggiunte informazioni sulla nuova variabile di output **[!UICONTROL filesCount]** disponibile dopo l’utilizzo di un’attività **[!UICONTROL Transfer file]**. [Leggi tutto](../../automating/using/transfer-file.md#output-variables)

La sezione per la **configurazione del canale e-mail** è stata aggiornata per chiarire quali sono le impostazioni e-mail più recenti applicabili. In fondo alla pagina sono elencati alcuni parametri legacy ancora in uso per alcuni clienti. [Leggi tutto](../../administration/using/configuring-email-channel.md)

Sono state aggiunte informazioni su come evitare che un flusso di lavoro pianificato possa essere riprianificato se sono ancora in sospeso una o più attività di un’esecuzione precedente. [Leggi tutto](../../automating/using/scheduled-workflows-execution.md)

## Dicembre 2020 {#doc-updates-december-2020}

La funzionalità **Oggetto predittivo** è ora obsoleta. [Leggi tutto](../../rn/using/deprecated-features.md)

La sezione **Guida introduttiva alla messaggistica transazionale** ora include [schemi ottimizzati](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) per una migliore comprensione del processo.

È ora disponibile un caso d’uso end-to-end che illustra il processo di implementazione della messaggistica transazionale. [Leggi tutto](../../channels/using/transactional-messaging-use-case.md)

La sezione **Privacy** è stata spostata [qui](../../start/using/privacy.md).

È disponibile una nuova pagina **Accessibilità**, con informazioni sul supporto dell’accessibilità nell’area di lavoro Adobe Campaign Standard. [Leggi tutto](../../start/using/accessibility.md)

È stato aggiunto un avviso che segnala che, al fine di ottenere prestazioni ottimali, il numero di messaggi sulle transazioni pubblicati deve essere inferiore a 100. [Leggi tutto](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

La pagina del protocollo e delle impostazioni del connettore SMS è stata spostata [qui](../../administration/using/sms-protocol.md).

La sezione **Utilizzo degli elenchi di prodotti in un messaggio sulle transazioni** è stata spostata [qui](../../designing/using/using-product-listings.md).

## Novembre 2020 {#doc-updates-november-2020}

La sezione **Dati personali e persone** è stata aggiornata con uno scenario di utilizzo che illustra l’interazione delle diverse persone in materia di dati personali. [Leggi tutto](../../start/using/privacy.md#use-case-scenario)

È stata aggiunta una nuova sezione in cui sono elencate le domande frequenti sulla privacy. [Leggi tutto](../../start/using/privacy-faq.md)

La sezione **Privacy** è stata spostata e arricchita con due nuove pagine: [Gestione della privacy](../../start/using/privacy-management.md) e [Gestione delle richieste di accesso a dati personali](../../start/using/privacy-requests.md).

La sezione **Messaggistica transazionale** è stata riorganizzata e raccolta in un’unica posizione per migliorare la navigazione. [Leggi tutto](../../channels/using/getting-started-with-transactional-msg.md)

Nella sezione Connettore dati di Adobe Experience Platform sono state aggiunte informazioni sull’errore di convalida della mappatura dati relativo alla gestione della privacy e su come risolverlo.

## Versione 20.4 - Ottobre 2020 {#release-20-4---october-2020}

**Nuove funzionalità incluse nella versione**

Gruppi di controllo. [Leggi tutto](../../sending/using/control-group.md)

API esterna (supporto OAuth). [Leggi tutto](../../automating/using/external-api.md)

Integrazione di Journey IA per la gestione dei percorsi cliente.[Leggi tutto](../../sending/using/predictive.md)

**Altri aggiornamenti alla documentazione in arrivo con la versione**

La sezione sulla chiamata di un flusso di lavoro con parametri esterni è stata arricchita con le nuove funzioni disponibili nell’editor espressioni. [Leggi tutto](../../automating/using/customizing-workflow-external-parameters.md)

Alle procedure consigliate per i flussi di lavoro è stato aggiunto un consiglio relativo al numero di attività da utilizzare per ogni flusso di lavoro. [Leggi tutto](../../automating/using/best-practices-workflows.md#number-activities)

È stata aggiunta una nuova sezione sulle best practice per le consegne. [Leggi tutto](../../sending/using/delivery-best-practices.md)

È stata aggiunta una sezione per descrivere i nuovi filtri che consentono di eseguire ricerche nelle configurazioni dell’evento in base al loro stato e alla data di ricezione dell’ultimo evento. [Leggi tutto](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## Settembre 2020 {#doc-updates-september-2020}

La sezione **Messaggi transazionali sull’evento** è stata riorganizzata e chiarita. [Leggi tutto](../../channels/using/editing-transactional-message.md)

È stata aggiunta una nota di avviso per informare gli utenti della limitazione delle autorizzazioni relativa all’accesso al registro. [Leggi tutto](../../administration/using/users-management.md)

È stata aggiunta una nuova sezione per descrivere nel dettaglio il processo di creazione di un nuovo marchio. [Leggi tutto](../../administration/using/branding.md#creating-a-brand)

È ora disponibile la nuova integrazione Campaign Standard - Microsoft Dynamics 365. [Leggi tutto](../../integrating/using/d365-acs-get-started.md)

Nel rapporto Profili attivi sono state aggiunte informazioni sulle origini anonime. [Leggi tutto](../../audiences/using/active-profiles.md)

## Agosto 2020 {#doc-updates-august-2020}

È disponibile una nuova sezione aggiornata nella guida introduttiva sull’utilizzo dei messaggi transazionali. [Leggi tutto](../../channels/using/getting-started-with-transactional-msg.md)

La sezione **Limitazioni della messaggistica transazionale** è stata spostata [qui](../../channels/using/transactional-messaging-limitations.md).

La sezione **Preparazione dell’invio** è stata spostata [qui](../../sending/using/preparing-the-send.md).

## Luglio 2020 {#doc-updates-july-2020}

È stata aggiunta una nuova sezione con le linee guida relative al monitoraggio di Campaign Standard. [Leggi tutto](../../administration/using/monitoring-guidelines.md)

È stata aggiornata la sezione Guardrail e limitazioni per API esterne. [Ulteriori informazioni](../../automating/using/external-api.md#guardrails)

La pagina di panoramica sulla Gestione della privacy è stata aggiornata con informazioni sulla Legge tailandese sulla protezione dei dati personali (PDPA) e sulla Lei Geral de Proteção de Dados (LGPD) brasiliana. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

La guida per i canali mobili è stata riorganizzata e migliorata. È stata aggiunta una nuova guida alla configurazione dei canali mobili con relativa documentazione tecnica. [Leggi tutto](../../administration/using/push-tracking.md)

La pagina Gestione della privacy in Campaign Standard è stata aggiornata con informazioni su come gestire le richieste di accesso a dati personali tramite l’integrazione del servizio core Privacy. [Leggi tutto](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

Nuove funzionalità di e-mail basate sull’intelligenza artificiale: ottimizzazione del tempo di invio e valutazione del profilo. [Leggi tutto](../../sending/using/predictive.md)

## Giugno 2020 {#doc-updates-june-2020}

I casi di utilizzo dei flussi di lavoro sono stati aggiornati e riorganizzati in sezioni tematiche. [Leggi tutto](../../automating/using/about-workflow-use-cases.md)

Sono stati aggiunti casi di utilizzo su come [crittografare](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt) e [decrittografare](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt) dati tramite il Pannello di controllo e i flussi di lavoro di Campaign.

I riferimenti al sito web di Supporto legacy sono stati sostituiti dal nuovo URL. [Ulteriori informazioni](../../support.md)

La configurazione personalizzata dell’account Litmus è stata rimossa dalla funzionalità di rendering in entrata. [Leggi tutto](../../sending/using/email-rendering.md)

L’integrazione Campaign Standard - Microsoft Dynamics 365 non è al momento disponibile. È in fase di sviluppo un nuovo connettore, che sarà disponibile in futuro. Le relative pagine di aiuto sono state rimosse. [Leggi tutto](../../integrating/using/d365-acs-get-started.md)

## Maggio 2020 {#doc-updates-may-2020}

La pagina di panoramica di Campaign Standard è stata arricchita e riorganizzata secondo argomenti tematici. [Ulteriori informazioni](../../start/using/about-campaign-standard.md)

La sezione Parametri del canale e-mail è stata integrata con maggiori informazioni relative ai campi delle maschere autorizzate e all’ID dei rapporti di consegna. [Ulteriori informazioni](../../administration/using/configuring-email-channel.md)

La configurazione di un’app mobile mediante gli SDK di Adobe Experience Platform è ora disponibile nella documentazione di base, con ulteriori informazioni relative al flusso di lavoro tecnico Sync Mobile app AEPSDK from Launch. [Leggi tutto](../../administration/using/configuring-a-mobile-application.md)

## Versione 20.3 - Maggio 2020 {#release-20-3---may-2020}

**Nuove funzionalità incluse nella versione**

Legge thailandese sulla tutela dei dati personali (PDPA) - [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html)

Attività API esterna (GA) - [Ulteriori informazioni](../../automating/using/external-api.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Sono state aggiunte informazioni sul campo **[!UICONTROL History in days]** delle proprietà dei flussi di lavoro, che adesso include i file scaricati dall’attività **[!UICONTROL Transfer file]**. [Ulteriori informazioni](../../automating/using/managing-execution-options.md)

Nella sezione relativa alla sostituzione del profilo sono state aggiunte le informazioni relative al limite di 500 caratteri del prefisso della riga oggetto. [Ulteriori informazioni](../../sending/using/testing-messages-using-target.md)

All’interno della documentazione di base è stata aggiunta una nuova sezione sulla privacy e sul consenso. [Ulteriori informazioni](../../start/using/privacy.md)

È stato inserito un caso d’uso per consentire la conversione delle e-mail dell’editor legacy all’interno di E-mail Designer. [Ulteriori informazioni](../../designing/using/converting-emails-from-legacy-editor.md)

È stata aggiunta una sezione per le domande frequenti su E-mail Designer. [Leggi tutto](../../designing/using/faq-email-designer.md)

## Aprile 2020 {#doc-updates-april-2020}

La documentazione relativa all’integrazione di Microsoft Dynamics 365 con Adobe Campaign Standard è ora disponibile all’interno della documentazione di base. [Ulteriori informazioni](../../integrating/using/d365-acs-get-started.md)

Sono state aggiunte nuove risorse nella pagina Home della documentazione. [Ulteriori informazioni](../../campaign-standard-home.md)

Le informazioni sul Servizio Experience Cloud ID (ECID) sono state inserite nella documentazione del Connettore dati di Adobe Experience Platform.

La sezione Messaggistica transazionale è stata arricchita con informazioni sulle modalità di accesso agli eventi transazionali più recenti e alle schermate aggiornate. [Ulteriori informazioni](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

La documentazione sulle tipologie e sulle regole relative è stata migliorata e aggiornata con informazioni aggiuntive sulle regole di tipologia integrate. [Ulteriori informazioni](../../sending/using/about-typology-rules.md)

Sono state inserite informazioni sull’azione **[!UICONTROL Transfer file]** dell’attività **[!UICONTROL File listing]**. [Ulteriori informazioni](../../automating/using/transfer-file.md)

La documentazione sui nuovi tentativi eseguiti dopo un errore temporaneo di consegna è stata aggiornata con ulteriori dettagli sulla modalità di gestione dei nuovi tentativi dopo aver effettuato l’aggiornamento a MTA avanzato. [Ulteriori informazioni](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

La sezione Eliminazione di un messaggio sulle transazioni è stata migliorata e chiarita. [Ulteriori informazioni](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

La sezione **Anteprima delle consegne** è stata aggiornata con gli esempi di consegne specifici dei dispositivi mobili. [Ulteriori informazioni](../../sending/using/previewing-messages.md)

Sono state aggiunte le best practice relative alla messaggistica transazionale e all’eliminazione degli eventi in tempo reale inutilizzati. [Ulteriori informazioni](../../channels/using/configuring-transactional-event.md#creating-an-event)

La sezione Configurazione del canale e-mail è stata aggiornata con chiarimenti su tutte le impostazioni e-mail che adesso sono gestite da MTA avanzato di Adobe Campaign. [Ulteriori informazioni](../../administration/using/configuring-email-channel.md)

La sezione Messaggistica transazionale è stata aggiornata con ulteriori informazioni sui diritti necessari per la modifica delle configurazioni degli eventi e sulle modalità di arricchimento delle raccolte nei messaggi transazionali. [Leggi tutto](../../channels/using/configuring-transactional-event.md).

## Versione 20.2 - Aprile 2020 {#release-20-2---april-2020}

**Nuove funzionalità incluse nella versione**

Integrazione BLOB di Azure - [Ulteriori informazioni](../../administration/using/external-accounts.md#microsoft-azure-external-account)

Verifica dei messaggi e-mail tramite profili di destinazione - [Ulteriori informazioni](../../sending/using/testing-messages-using-target.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stato aggiunto un limite al rendering dei messaggi in-app. [Ulteriori informazioni](../../channels/using/customizing-an-in-app-message.md)

Sono state aggiunte informazioni sulle modalità di utilizzo degli aggregati all’interno di un’attività **[!UICONTROL Query]**. [Ulteriori informazioni](../../automating/using/query.md#adding-an-aggregate)

È stata aggiunta una limitazione con MCPNS durante la configurazione di un’app mobile. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html)

È stata aggiunta una nuova sezione sulle linee guida di configurazione all’interno della guida di amministrazione. La sezione relativa ai browser e ai sistemi operativi compatibili è stata spostata dalla Guida introduttiva a questa sezione. All’interno di questa sezione è stata aggiunta anche la nota tecnica sugli endpoint di rete di Campaign Standard. [Ulteriori informazioni](../../administration/using/about-configuration-guidelines.md)

È ora disponibile una nuova sezione che illustra la procedura di eliminazione della configurazione di un evento. [Ulteriori informazioni](../../channels/using/publishing-transactional-event.md#deleting-an-event)

Le sezioni di messaggistica transazionale sono state aggiornate per riflettere i miglioramenti e gli aggiornamenti più recenti dell’interfaccia utente. [Ulteriori informazioni](../../channels/using/getting-started-with-transactional-msg.md)

Sono state aggiornate le informazioni relative ai guardrail per attività API esterne. [Ulteriori informazioni](../../automating/using/external-api.md)

## Marzo 2020 {#doc-updates-march-2020}

Nella documentazione di base sono state aggiunte informazioni più dettagliate sull’MTA avanzato, in particolare per quanto riguarda le regole di elaborazione delle e-mail e la qualifica della posta non recapitata. [Ulteriori informazioni](../../administration/using/configuring-email-channel.md#email-processing-rules)

La sezione dedicata all’archiviazione di e-mail con indirizzi Ccn è stata spostata e aggiornata. [Ulteriori informazioni](../../sending/using/archiving.md)

È stato eseguito l’aggiornamento della documentazione sulla configurazione di un’app mobile, unitamente alle pagine correlate, in modo da riflettere l’ammortamento di SDK V4. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=it)

È stata aggiornata e migliorata la documentazione relativa all’integrazione di Adobe Campaign Standard/Adobe Experience Manager. [Ulteriori informazioni](../../integrating/using/configure-experience-manager.md)

La documentazione di E-mail designer di Campaign e le pagine relative sono state aggiornate e ora riportano l’obsolescenza di [!DNL Adobe Creative SDK]. [Ulteriori informazioni](../../rn/using/deprecated-features.md)

È ora disponibile una nuova sezione dedicata alle best practice per il modello di dati Campaign Standard. [Ulteriori informazioni](../../developing/using/data-model-best-practices.md)

Sono state aggiunte informazioni sul diritto integrato del **[!UICONTROL Workflow]**. [Ulteriori informazioni](../../administration/using/list-of-roles.md)

Sono state aggiunte informazioni sulle proprietà di **[!UICONTROL History in days field]** disponibili all’interno dei flussi di lavoro. [Ulteriori informazioni](../../automating/using/about-workflow-execution.md)

## Versione 20.1 - Febbraio 2020 {#release-20-1---february-2020}

**Nuove funzionalità incluse nella versione**

Connettore dati Adobe Experience Platform (beta)

Audience Destinations (beta)

**Altri aggiornamenti alla documentazione inclusi nella versione**

La documentazione sulla gestione della privacy è stata aggiornata con le informazioni sulle modalità di creazione del campo di rinuncia CCPA relativo alle risorse di profilo personalizzate. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html)

Le note sulla versione sono state riorganizzate e migliorate. [Ulteriori informazioni](../../rn/using/release-notes.md)

Sono state aggiunte informazioni relative al gruppo di sicurezza Amministratori, specificando che l’unità organizzativa **[!UICONTROL All (all)]** è assegnata al gruppo e non può essere modificata. [Ulteriori informazioni](../../administration/using/managing-groups-and-users.md)

Sono state aggiunte informazioni sulla modalità di definizione di un fuso orario specifico da utilizzare per impostazione predefinita all’interno di un flusso di lavoro. [Ulteriori informazioni](../../automating/using/building-a-workflow.md)

Nella guida Utilizzo delle API sono state aggiunte le informazioni sul nuovo parametro **_forcePagination=true**, che consentono di eseguire la numerazione delle pagine di tabelle di grandi dimensioni. [Ulteriori informazioni](../../api/using/pagination.md)

È disponibile una nuova sezione che descrive gli avvisi che possono essere visualizzati in un dashboard dei messaggi. [Ulteriori informazioni](../../channels/using/message-dashboard.md#warnings)

È ora disponibile la documentazione di MTA avanzato di Adobe Campaign, che descrive l’infrastruttura di invio aggiornata, la quale offre miglioramenti in termini di consegna messaggi, velocità effettiva e gestione dei messaggi non recapitati. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-enhanced-mta.html)

Sono state aggiunte le note per indicare che gli URL del server dell’applicazione e del server della pagina mirror devono essere URL sicuri, affinché le anteprime della pagina di destinazione e della pagina mirror vengano visualizzate dall’interfaccia utente di Campaign. [Ulteriori informazioni](../../administration/using/branding.md#configuring-and-using-brands)

La sezione Esportazione dei registri è stata aggiornata per riflettere la disponibilità dell’ID del registro di consegna all’interno delle risorse dei registri di consegna e di tracciamento, consentendo un’esportazione di un identificatore univoco per ciascun registro. [Ulteriori informazioni](../../automating/using/exporting-logs.md)

## Gennaio 2020 {#doc-updates-january-2020}

La documentazione sul recapito messaggi è stata aggiornata con una nuova sezione relativa alla certificazione IP. <!--[Read more](../../sending/using/ip-certification.md)-->

È disponibile una nuova sezione che descrive come creare un flusso di lavoro per la consegna cross-channel. [Ulteriori informazioni](../../automating/using/workflow-cross-channel-delivery.md)

È stata aggiornata la sezione Calcolo indicatore per i report dinamici. [Ulteriori informazioni](../../reporting/using/indicator-calculation.md)

È stata aggiunta una nuova pagina sulle linee guida generali per le consegne su dispositivi mobili all’interno di Adobe Campaign Standard. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-mobile.html)

La documentazione di Utilizzo di Campaign ed Experience Manager è stata aggiornata con una nuova sezione **Suggerimenti sull’utilizzo dell’integrazione Campaign-Experience Manager**. [Ulteriori informazioni](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

La home page della documentazione API è stata migliorata con i reindirizzamenti ai vari argomenti. [Ulteriori informazioni](../../api/using/get-started-apis.md)

## Novembre - dicembre 2019 {#doc-updates-december-2019}

È stata aggiornata la documentazione relativa alla configurazione dell’account esterno S3. [Ulteriori informazioni](../../administration/using/external-accounts.md#amazon-s3-external-account)

È stata riorganizzata la sezione Progettazione di contenuti e-mail. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

La guida introduttiva alla consegna è stata aggiornata e integrata all’interno della documentazione di base. [Ulteriori informazioni](../../sending/using/about-deliverability.md)

La guida introduttiva sulla modalità di esportazione/importazione delle risorse personalizzate è stata integrata all’interno della documentazione di base. [Ulteriori informazioni](../../automating/using/exporting-importing-custom-resources.md)

È stato aggiunto un nuovo caso d’uso che descrive come creare un gruppo di controllo utilizzando un flusso di lavoro all’interno di Campaign Standard.

Le informazioni relative alle proprietà delle pagine di destinazione sono state spostate in una sezione dedicata. [Leggi tutto](../../channels/using/configuring-landing-page.md)

La documentazione del Pannello di controllo è stata integrata nel nuovo set di documentazione collaborativa. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it)

È stata aggiornata la tabella di **calcolo dell’indicatore**. [Ulteriori informazioni](../../reporting/using/indicator-calculation.md)

Il set di documenti API è stato integrato nella documentazione di Campaign Standard.[Ulteriori informazioni](../../api/using/get-started-apis.md)

È stata spostata e aggiornata la sezione di introduzione alla creazione di un messaggio e-mail personalizzato. [Leggi tutto](https://helpx.adobe.com/it/campaign/kb/acs-get-started-with-emails.html)

La guida introduttiva sulle best practice per le consegne è stata aggiornata. [Ulteriori informazioni](../../sending/using/delivery-best-practices.md)

Il modello dati è stato integrato nella documentazione di Campaign Standard. [Ulteriori informazioni](../../developing/using/datamodel-audience.md)

Il nuovo endpoint API **/customResources** è stato aggiunto alla documentazione API.[Ulteriori informazioni](../../api/using/interacting-with-custom-resources.md)

## Versione 19.4 - Ottobre 2019 {#release-19-4---october-2019}

**Nuove funzionalità incluse nella versione**

California Consumer Privacy Act (CCPA) - [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ccpa)

Integrazione con Microsoft Dynamics 365 (GA) - [Ulteriori informazioni](../../integrating/using/d365-acs-get-started.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

L’elenco dei messaggi di errore per Adobe Campaign è stato aggiornato. [Leggi tutto](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it)

La guida introduttiva al GDPR è stata migliorata e arricchita. È ora diventata una documentazione sulla gestione della privacy che include GDPR e CCPA. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-privacy.html)

È stato aggiunto un nuovo grafico che presenta il processo di pubblicazione della messaggistica transazionale. [Ulteriori informazioni](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

La guida introduttiva alle best practice di consegna è stata spostata e aggiornata. [Ulteriori informazioni](../../sending/using/delivery-best-practices.md)

È stata aggiunta una nuova sezione, che fornisce una panoramica dei vari metodi per arricchire il database di Campaign Standard. [Ulteriori informazioni](../../audiences/using/enriching-campaign-database.md)

È stata inserita una nuova sezione che descrive come assegnare uno stile ai collegamenti tramite E-mail Designer. [Ulteriori informazioni](../../designing/using/styles.md#about-styling-links)

Le informazioni relative alla privacy sono state aggiunte alla documentazione API [Fai clic qui](../../api/using/creating-a-privacy-request.md)

## Settembre - ottobre 2019 {#doc-updates-october-2019}

È stata aggiunta una nuova sezione relativa alle impostazioni di Campaign Standard. [Ulteriori informazioni](../../administration/using/about-campaign-standard-settings.md)

È stata aggiunta una nuova sezione che descrive come inviare un’e-mail di conferma automatica personalizzata ai profili abbonati a un servizio specifico. [Ulteriori informazioni](../../audiences/using/confirming-subscription-to-a-service.md)

La sezione Messaggistica transazionale è stata integrata con gli ultimi aggiornamenti dell’interfaccia utente, inclusa la modifica del contenuto con E-mail Designer. [Ulteriori informazioni](../../channels/using/editing-transactional-message.md)

Il capitolo delle pagine di destinazione è stato riorganizzato. La sezione è stata inoltre arricchita da una nuova parte che descrive i passaggi necessari per l’impostazione di una pagina di destinazione. [Ulteriori informazioni](../../channels/using/getting-started-with-landing-pages.md)

Nella sezione Notifiche push è stata aggiunta una nuova parte sulla modalità di creazione e aggiornamento delle informazioni sul profilo, sulla base dei dati di abbonamento alle app mobili. [Ulteriori informazioni](../../channels/using/updating-profile-with-mobile-app-data.md)

È stato aggiunto un nuovo esempio che illustra come inviare un messaggio e-mail contenente i dati aggiuntivi che sono stati recuperati da un’attività di caricamento file. [Ulteriori informazioni](../../automating/using/sending-email-enriched-fields.md)

È stata aggiunta una nuova sezione su come utilizzare le trappole. [Ulteriori informazioni](../../sending/using/using-traps.md).

Nella pagina è stata inserita una nota sull’opzione **Launch_URL_Campaign** che spiega come configurare un’app mobile tramite gli SDK di Adobe Experience Platform. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html?lang=it)

La guida di E-mail Designer è stata riorganizzata. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

## Agosto 2019 {#doc-updates-august-2019}

È stata aggiunta una nuova sezione con casi d’uso sui flussi di lavoro incentrati sulle query. [Ulteriori informazioni](../../automating/using/workflow-created-query-with-complement.md)

Nella sezione Risoluzione dei problemi del flusso di lavoro è stata inserita una procedura per la visualizzazione delle query SQL nella scheda Registro. [Ulteriori informazioni](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

È stato aggiunto un nuovo articolo della guida, contenente informazioni relative ai sottodomini e alla gestione dei certificati all’interno del Pannello di controllo. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=it)

È stata aggiornata la sezione che descrive i modelli di contenuto e i frammenti. [Ulteriori informazioni](../../designing/using/using-reusable-content.md#content-templates)

È stata aggiunta una nuova sezione sulla modalità di salvataggio del contenuto delle e-mail come modello all’interno di E-mail Designer. [Ulteriori informazioni](../../designing/using/using-reusable-content.md#saving-content-as-template)

## Versione 19.3 - Luglio 2019 {#release-19-3---july-2019}

**Nuove funzionalità incluse nella versione**

Attività API esterna (versione beta pubblica) - [Ulteriori informazioni](../../automating/using/external-api.md)

Report sul segmento del flusso di lavoro - [Ulteriori informazioni](../../reporting/using/creating-a-report-workflow-segment.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È attiva la Guida all’implementazione di Campaign Standard.[Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-standard-implementation-guide.html)

È stato creato un set di nuovi articoli della guida relativi all’implementazione e all’utilizzo del connettore Microsoft Dynamics 365. Al momento questa funzione presenta solo una disponibilità limitata.[Ulteriori informazioni](../../integrating/using/d365-acs-get-started.md)

È stata aggiunta una nota nella sezione [Chiamata di un flusso di lavoro con parametri](../../automating/using/calling-a-workflow-with-external-parameters.md) che riguarda la preparazione della consegna e il relativo periodo di aggregazione.

Sono state aggiunte informazioni sulle modalità di personalizzazione dell’etichetta di una consegna con le variabili evento dichiarate nell’attività del segnale esterno del flusso di lavoro. [Ulteriori informazioni](../../automating/using/external-signal.md)

È stata aggiunta una nuova sezione che descrive in dettaglio come creare un utente all’interno di Adobe Campaign Standard. [Ulteriori informazioni](../../administration/using/users-management.md)

È ora disponibile un nuovo articolo con suggerimenti per la semplificazione delle campagne di marketing, che comprende collegamenti alla documentazione del prodotto e video di esercitazione.[Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/simplify-campaign-management.html)

È stata aggiunta una procedura di risoluzione dei problemi per il reporting dinamico. [Ulteriori informazioni](../../reporting/using/troubleshooting.md)

È stato aggiunto un diagramma che illustra la gestione delle informazioni personali da parte dei vari modelli in-app. [Ulteriori informazioni](../../channels/using/preparing-and-sending-an-in-app-message.md)

È stata aggiunta una sezione sulla modalità di salvataggio del contenuto delle e-mail come frammento all’interno di E-mail Designer. [Ulteriori informazioni](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

È stato aggiunto un avviso relativo al modo in cui gli spazi vuoti aggiuntivi possono influenzare il layout del contenuto dell’e-mail. [Ulteriori informazioni](../../designing/using/personalization.md#creating-custom-content-blocks)

È stata inserita una nuova sezione sugli aggiornamenti consigliati per E-mail Designer. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

È stata aggiunta una nuova sezione sulle best practice per i flussi di lavoro. [Ulteriori informazioni](../../automating/using/best-practices-workflows.md)

È stato aggiornato l’elenco dei messaggi di errore per Campaign Standard e Classic. [Ulteriori informazioni](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it)

È stato aggiunto un avviso nella documentazione delle risorse personalizzate. È consigliabile utilizzare un massimo di 30 caratteri per gli ID di risorse personalizzati. Questo vale anche per campi di risorse personalizzati, chiavi, indici e collegamenti. [Ulteriori informazioni](../../developing/using/creating-or-extending-the-resource.md)

## Giugno - luglio 2019 {#doc-updates-2019}

È stata aggiunta una nuova pagina a Limitazioni della pagina di destinazione. [Ulteriori informazioni](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

È stato aggiunto un caso d’uso su come chiamare un profilo utilizzando una chiave di identificazione composita. [Ulteriori informazioni](../../developing/using/uc-calling-resource-id-key.md)

Durante la chiamata di un flusso di lavoro con parametri, è stato aggiunto un consiglio relativo all’utilizzo di consegne ricorrenti senza periodo di aggregazione. [Ulteriori informazioni](../../automating/using/calling-a-workflow-with-external-parameters.md)

È stato aggiornato l’elenco dei messaggi di errore per Campaign Standard e Classic. [Ulteriori informazioni](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it)

È stato aggiunto un avviso nella documentazione delle risorse personalizzate. È consigliabile utilizzare un massimo di 30 caratteri per gli ID di risorse personalizzati. Questo vale anche per campi di risorse personalizzati, chiavi, indici e collegamenti. [Ulteriori informazioni](../../developing/using/creating-or-extending-the-resource.md)

## Versione 19.2 - Maggio 2019 {#release-19-2---may-2019}

**Nuove funzionalità incluse nella versione**

Pannello di controllo - [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it)

Notifiche locali - [Ulteriori informazioni](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

Miglioramento del flusso di lavoro - Aggiungere un payload all’attività del segnale esterno - [Ulteriori informazioni](../../automating/using/calling-a-workflow-with-external-parameters.md)

Miglioramento delle pagine di destinazione - Google reCAPTCHA - [Ulteriori informazioni](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stato aggiornato l’articolo Delega nome di dominio. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/domain-name-delegation.html)

Per condividere le prossime date di rilascio, è stato pubblicato un nuovo articolo di Pianificazione del rilascio. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-release-planning.html)

Sono stati aggiornati i collegamenti di aiuto contestuali disponibili direttamente all’interno di Adobe Campaign.

La [pagina](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=it) seguente diventa la pagina ufficiale dei video di Adobe Campaign Standard.

È stata aggiunta una sezione sulla conservazione dei dati, con i valori di conservazione predefiniti per le tabelle standard. [Ulteriori informazioni](../../administration/using/data-retention.md)

È stata inserita una sezione sugli aggiornamenti e sulle operazioni di manutenzione. [Ulteriori informazioni](../../administration/using/updates-and-maintenance-operations.md)

Nell’attività **Trasferisci file** sono state aggiunte informazioni sulla nuova opzione di ordinamento. [Ulteriori informazioni](../../automating/using/transfer-file.md)

È stata aggiornata la [documentazione API REST](../../api/using/get-started-apis.md):

* È stata aggiunta una nuova sezione con informazioni generiche sui motivi per cui utilizzare le API REST di Campaign Standard.
* È stata resa disponibile una raccolta di richieste API preconfigurate, che rappresenta i casi d’uso più comuni.
* È stata aggiunta una nuova sezione sulla modalità di gestione delle unità organizzative.
* Sono state inserite le informazioni su come creare un servizio.
* Sono state aggiunte le informazioni su come richiamare un flusso di lavoro con parametri.

Sono state inserite le informazioni sulla nuova attività **Test**. [Ulteriori informazioni](../../automating/using/test.md)

La guida Automazione è stata aggiornata con i collegamenti alle relative attività del flusso di lavoro. [Ulteriori informazioni](../../automating/using/workflow-interface.md#palette)

È stata aggiornata la sezione Calcolo indicatore per i report dinamici. [Ulteriori informazioni](../../reporting/using/indicator-calculation.md)

È stata aggiunta una tabella di compatibilità per il reporting dinamico per una migliore comprensione della compatibilità tra dimensioni e metriche. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=it)

È stato aggiornato l’elenco delle funzioni per i flussi di lavoro. [Ulteriori informazioni](../../automating/using/list-of-functions.md)

Il capitolo Progettazione del contenuto è stato riorganizzato e migliorato con una nuova sezione che illustra chiaramente i diversi metodi per progettare un’e-mail con E-mail Designer sulla base dei contenuti esistenti. [Ulteriori informazioni](../../designing/using/using-existing-content.md)

È stata aggiunta una nuova sezione sulla modalità di salvataggio del contenuto delle e-mail come frammento all’interno di E-mail Designer. [Ulteriori informazioni](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

La sezione Gestione dei collegamenti è stata aggiornata con le informazioni aggiuntive su come gestire gli URL tracciati con E-mail Designer. [Ulteriori informazioni](../../designing/using/links.md#inserting-a-link)

È stata aggiunta una nuova sezione per descrivere il processo specifico di esecuzione di nuovi tentativi dei messaggi sulle transazioni. [Ulteriori informazioni](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

La sezione Pubblicazione di una risorsa con estensione API è stata chiarita e aggiornata con le ultime modifiche dell’interfaccia utente. [Ulteriori informazioni](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

La sezione Archiviazione delle e-mail è stata rinominata e riorganizzata. [Ulteriori informazioni](../../sending/using/archiving.md)

È stata aggiornata la sezione Creazione di un messaggio e-mail per riflettere le ultime modifiche apportate all’interfaccia. [Ulteriori informazioni](../../channels/using/creating-an-email.md)

L’articolo del Knowledge Base relativo al [protocollo e alle impostazioni del connettore SMS](https://helpx.adobe.com/it/campaign/kb/sms-connector-protocol-and-settings.html) è stato aggiornato con la nuova opzione aggiunta all’account esterno SMS per limitare il numero di istanze MTA consentite per la connessione al provider SMPP.

La guida Introduzione è stata arricchita e riorganizzata. [Ulteriori informazioni](../../start/using/about-campaign-standard.md)

È stata aggiornata la pagina Funzioni obsolete e rimosse. [Ulteriori informazioni](../../rn/using/deprecated-features.md)

La sezione relativa all’integrazione di Dreamweaver è stata aggiornata e migliorata. [Ulteriori informazioni](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## Versione 19.1 - Febbraio 2019 {#release-19-1---february-2019}

**Nuove funzionalità incluse nella versione**

Miglioramenti al reporting dei canali push - [Ulteriori informazioni](../../reporting/using/push-notification-report.md)

Integrazione di Launch per l’app mobile - [Ulteriori informazioni](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

Messaggistica in-app mobile - [Ulteriori informazioni](../../channels/using/about-in-app-messaging.md)

Miglioramenti del flusso di lavoro - Per ulteriori informazioni, [consulta qui](../../automating/using/workflow-interface.md#duplicating-workflow-activities) e [qui](../../automating/using/load-file.md#configuration)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Nel capitolo Modifica del contenuto dell’e-mail è stata aggiunta la nuova esperienza di onboarding per la creazione di contenuti e-mail e altri miglioramenti a E-mail Designer. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

È stata aggiunta una nuova sezione sulle limitazioni dei messaggi transazionali. [Ulteriori informazioni](../../channels/using/transactional-messaging-limitations.md)

È stata aggiunta una nuova sezione che confronta le diverse opzioni di creazione delle e-mail all’interno di Adobe Campaign. [Ulteriori informazioni](../../designing/using/using-integrations.md#email-design-options-comparison)

La sezione Creazione di blocchi di contenuto personalizzati è stata migliorata con i dettagli sulle dimensioni di targeting. [Ulteriori informazioni](../../designing/using/personalization.md#creating-custom-content-blocks)

È stato aggiunto un avviso che indica che E-mail Designer non supporta Internet Explorer 11. [Ulteriori informazioni](../../administration/using/about-configuration-guidelines.md)

Nella sezione Eliminazione di una risorsa sono stati aggiunti avvisi sull’impatto della riprogettazione. [Ulteriori informazioni](../../developing/using/deleting-a-resource.md)

È stato aggiornato il capitolo su come aggiungere o estendere una risorsa. [Ulteriori informazioni](../../developing/using/creating-or-extending-the-resource.md)

È stato aggiunto un caso d’uso su come estendere la risorsa personalizzata dei profili. [Ulteriori informazioni](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

Sono state aggiunte informazioni sulle modalità di collegamento delle risorse personalizzate. [Ulteriori informazioni](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

È stata aggiunta una nuova nota tecnica su come visualizzare un’immagine da una notifica push di Adobe Campaign Standard. [Ulteriori informazioni](../../administration/using/image-push-notification.md)

È stata aggiunta una nuova nota tecnica sull’implementazione del tracciamento push. [Ulteriori informazioni](../../administration/using/push-tracking.md)

È stato aggiornato l’elenco dei messaggi di errore per Campaign Standard e Classic. [Ulteriori informazioni](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=it)

È stata aggiornata la documentazione sull’integrazione Triggers - Campaign. [Ulteriori informazioni](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Sono stati aggiornati i collegamenti di aiuto contestuali disponibili direttamente all’interno di Adobe Campaign.

È stata inserita una nota sull’aggiunta di una marca temporale nel nome del file contenente i rifiuti. [Ulteriori informazioni](../../automating/using/load-file.md#configuration)

Sono state aggiunte informazioni durante l’importazione di campi composti da colonne dalla lunghezza fissa. [Ulteriori informazioni](../../automating/using/load-file.md#configuration)

Sono state inserite informazioni sull’opzione che consente di mantenere i rifiuti all’interno di un file. Questa opzione ora consente di applicare una fase di post-elaborazione al file contenente i rifiuti. [Ulteriori informazioni](../../automating/using/load-file.md#configuration)

È stata aggiunta una nuova sezione sulla modalità di duplicazione delle attività del flusso di lavoro mediante le operazioni di copia e incolla. [Ulteriori informazioni](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

Sono state inserite informazioni sulla nuova opzione presente nelle attività Query ( [Ulteriori informazioni](../../automating/using/query-samples.md)) e Segmentation ( [Ulteriori informazioni](../../automating/using/segmentation.md)), che consente di aggiungere una transizione in uscita al termine dell’attività, in caso di mancato recupero dei dati.

Nella sezione dell’attività Aggiornare dati, sono state inserite informazioni relative al nuovo campo Dimensione batch, le quali consentono di definire la dimensione batch massima dei dati da caricare. [Ulteriori informazioni](../../automating/using/update-data.md#configuration)

Nella sezione dell’attività Estrarre file, sono state aggiunte informazioni relative alla nuova opzione, la quale consente di disabilitare il processo di generazione dei file, qualora la transizione in uscita sia vuota. [Ulteriori informazioni](../../automating/using/extract-file.md#configuration)

## Versione 19.0 - Gennaio 2019 {#release-19-0---january-2019}

**Nuove funzionalità incluse nella versione**

Disponibilità generale di E-mail Designer - [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

Elenco prodotti nei messaggi e-mail sulle transazioni - [Ulteriori informazioni](../../designing/using/using-product-listings.md)

Visualizzazione mobile di E-mail Designer - [Ulteriori informazioni](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

Miglioramenti della versione beta della messaggistica in-app - [Ulteriori informazioni](../../channels/using/about-in-app-messaging.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stata aggiornata la guida Progettazione del contenuto per riflettere la disponibilità generale di E-mail Designer e la rimozione dell’editor dei contenuti dell’e-mail legacy. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

È stata aggiornata la documentazione delle notifiche [in-app](../../channels/using/about-in-app-messaging.md) e [push](../../channels/using/about-push-notifications.md).

Sono state aggiunte ulteriori informazioni sui vari tipi di pubblico all’interno di Adobe Campaign. [Ulteriori informazioni](../../audiences/using/about-audiences.md)

È stato aggiornato il capitolo Utenti e sicurezza per riflettere la rimozione delle unità geografiche. [Ulteriori informazioni](../../administration/using/organizational-units.md)

Nell’attività di caricamento dei dati sono state aggiunte informazioni sulla nuova opzione, le quali consentono l’applicazione di una fase di post-elaborazione al file contenente i record rifiutati (ad es. la compressione del formato ZIP). [Ulteriori informazioni](../../automating/using/load-file.md)

Nell’attività Aggiornare dati sono state aggiunte informazioni sul nuovo campo, le quali consentono di configurare la dimensione batch massima dei dati da caricare. [Ulteriori informazioni](../../automating/using/update-data.md)

Aggiornamento della documentazione di [Importazione contenuto da un URL](../../designing/using/using-existing-content.md#importing-content-from-a-url) con informazioni relative alla finestra di E-mail Designer.

Microsoft Edge (ultima versione) è stato aggiunto all’elenco dei browser compatibili per i computer. [Ulteriori informazioni](../../administration/using/about-configuration-guidelines.md)

Nell’attività Estrarre file sono state aggiunte informazioni sulla nuova opzione, le quali impediscono la generazione di un file se la transizione in entrata è vuota. [Ulteriori informazioni](../../automating/using/extract-file.md)

La sezione Configurazione di un’app mobile tramite SDK V4 è stata spostata [qui](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

La sezione Configurazione di un’app mobile mediante gli SDK di Adobe Experience Platform è stata trasferita [qui](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

I video sono stati aggiornati e spostati [qui](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=it).

È stata aggiornata la sezione Tipo di utenti. [Ulteriori informazioni](../../administration/using/users-management.md)

## Versione 18.9 - Settembre 2018 {#release-18-9---september-2018}

**Nuove funzionalità incluse nella versione**

Messaggistica in-app (versione beta) - [Ulteriori informazioni](../../channels/using/about-in-app-messaging.md)

Integrazione di Adobe Launch per le app mobili (versione beta) - [Ulteriori informazioni](../../sending/using/managing-typologies.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Aggiornamento della guida alle notifiche push con modifiche all’interfaccia. [Ulteriori informazioni](../../channels/using/about-push-notifications.md)

Sono state aggiunte informazioni sulle modalità di eliminazione di un pubblico. [Ulteriori informazioni](../../audiences/using/creating-audiences.md#deleting-audiences)

Aggiornamento della sezione integrata del report della notifica push. [Ulteriori informazioni](../../reporting/using/push-notification-report.md)

## Versione 18.7 - Luglio 2018 {#release-18-7---july-2018}

**Nuove funzionalità incluse nella versione**

[Flag ad alta priorità](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android) e [filtro della tipologia](../../sending/using/managing-typologies.md) per gli utenti abbonati alle app mobili.

Importazione automatizzata dei contenuti da un URL in fase di preparazione. [Ulteriori informazioni](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stata aggiunta una nuova nota tecnica sul protocollo e sulle impostazioni del connettore SMS. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=it)

È stata aggiornata l’integrazione di Experience Manager con la documentazione di Adobe Campaign. [Ulteriori informazioni](../../reporting/using/creating-a-custom-profile-dimension.md)

La guida &quot;Progettazione del contenuto&quot; è stata completamente riorganizzata, nello specifico per presentare i due editor che consentono di progettare contenuti per le e-mail. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

Scopri come rendere pienamente modificabili i contenuti esterni tramite Creative SDK, effettuando la creazione di frammenti dalle e-mail esistenti. [Ulteriori informazioni](../../designing/using/designing-from-scratch.md)

L’elenco degli attributi HTML per la piena conformità con Creative Designer è ora disponibile in questa [sezione](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer).

Sono state aggiunte informazioni sulla lingua predefinita per i modelli multilingue. [Ulteriori informazioni](../../channels/using/multilingual-messages-template.md)

A partire dalla versione 18.7, la guida Utenti e sicurezza è stata aggiornata per riflettere la rimozione della funzionalità dell’unità geografica per le nuove istanze Campaign Standard, oltre che delle istanze esistenti prive di unità geografiche. [Ulteriori informazioni](../../rn/using/deprecated-features.md)

## Versione 18.6 - Giugno 2018 {#release-18-6---june-2018}

**Nuove funzionalità incluse nella versione**

La documentazione API è stata aggiornata con le informazioni sulla **cronologia** delle API. È stato aggiunto un caso d’uso sulla modalità di recupero della pagina mirror per una consegna inviata a un profilo. [Ulteriori informazioni](../../api/using/interacting-with-marketing-history.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stata aggiornata e riorganizzata la documentazione sull’integrazione Triggers - Campaign. [Ulteriori informazioni](../../integrating/using/about-adobe-experience-cloud-triggers.md)

È stato aggiunto un caso d’uso dettagliato per la creazione di una dimensione di profilo personalizzata. [Ulteriori informazioni](../../reporting/using/creating-a-custom-profile-dimension.md)

È stata riorganizzata la documentazione Utilizzo di Campaign e Audience Manager o del servizio core People. [Ulteriori informazioni](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

È stata aggiornata la definizione del ruolo Prepara consegne. [Ulteriori informazioni](../../administration/using/list-of-roles.md)

Nella sezione dell’attività query è stato aggiunto un esempio su come eseguire il targeting dei profili che hanno selezionato un collegamento specifico all’interno di una consegna. [Ulteriori informazioni](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

Nella documentazione API è stata aggiunta una sezione relativa ai **filtri personalizzati**. [Ulteriori informazioni](../../api/using/filtering.md)

## Versione 18.5 - Maggio 2018 {#release-18-5---may-2018}

**Nuove funzionalità incluse nella versione**

RGPD: integrazione dei servizi core - [Ulteriori informazioni](../../start/using/privacy-management.md)

Miglioramenti push - feedback dettagliato sulla consegna - [Ulteriori informazioni](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

Estensione dei registri di consegna - [Ulteriori informazioni](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

Reporting dinamico con dati di profilo personalizzati - [Ulteriori informazioni](../../channels/using/creating-a-multilingual-push-notification.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stato aggiunto l’elenco delle metriche Campaign presenti all’interno di Analytics. [Ulteriori informazioni](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Sono state aggiunte informazioni all’opzione Licenses del menu Administration. [Ulteriori informazioni](../../administration/using/licenses.md)

Sono state aggiunte informazioni sull’utilizzo di campi di personalizzazione all’interno di una notifica push. [Ulteriori informazioni](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

È stato eseguito l’aggiornamento della guida dettagliata sulle best practice di consegna. [Ulteriori informazioni](../../sending/using/delivery-best-practices.md)

Sono state aggiunte informazioni sui tipi di registro di tracciamento. [Ulteriori informazioni](../../sending/using/tracking-messages.md#tracking-logs)

La sezione attività di query è stata aggiornata con esempi di query. [Ulteriori informazioni](../../automating/using/query.md#query-samples)

La sezione dedicata all’elenco Bloccati è stata rinominata “Informazioni sui processi di consenso e rinuncia”. La sezione è stata aggiornata con le informazioni relative alle modalità di gestione del consenso a canali specifici e di impostazione delle pagine di destinazione per la gestione del consenso e della rinuncia. [Ulteriori informazioni](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Scopri le best practice per l’utilizzo dei server SFTP ospitati da Adobe. [Ulteriori informazioni](../../administration/using/external-accounts.md#sftp-external-account)

È stato aggiornato l’elenco degli SKU di Analytics supportati per l’integrazione con Triggers. [Ulteriori informazioni](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

Sono state unite alcune pagine della documentazione dell’editor dei contenuti, in modo da offrire una visualizzazione più completa delle varie azioni disponibili. [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

## Versione 18.3 - Marzo 2018 {#release-18-3---march-2018}

**Nuove funzionalità incluse nella versione**

Regolamento generale sulla protezione dei dati UE (RGPD) - [Ulteriori informazioni](../../start/using/privacy.md)

Creative Designer per e-mail - [Ulteriori informazioni](../../designing/using/designing-content-in-adobe-campaign.md)

Consegne push multilingue - [Ulteriori informazioni](../../channels/using/creating-a-multilingual-push-notification.md)

Utilizzo delle risorse personalizzate nella messaggistica transazionale - [Ulteriori informazioni](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Le funzionalità dei gruppi API RGPD consentono l’elaborazione automatica delle richieste RGPD. [Ulteriori informazioni](../../api/using/creating-a-privacy-request.md)

Sono state aggiunte informazioni sulla modalità di impostazione delle pagine di destinazione, al fine di consentire l’inserimento dei destinatari nell’elenco Bloccati. [Ulteriori informazioni](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

È stata riorganizzata la sezione [Configurazione della messaggistica transazionale](../../channels/using/configuring-transactional-event.md) ed è stato aggiunto un [caso d’uso dettagliato](../../channels/using/transactional-messaging-use-case.md).

È stata inserita una nota tecnica per apprendere la modalità di generazione di un file CSV multilingue da usare per le notifiche push. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push.html).

Sono state aggiunte informazioni sul modello di importazione **Aggiornamento quarantene di direct mailing e registri di consegna**. [Ulteriori informazioni](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

È stato aggiornato l’elenco dei flussi di lavoro tecnici. [Ulteriori informazioni](../../administration/using/technical-workflows.md)

È stata aggiornata la sezione attività di pianificazione. [Ulteriori informazioni](../../automating/using/scheduler.md)

È stato aggiornato l’elenco dei materiali della guida relativi all’integrazione delle soluzioni Adobe e Campaign. [Ulteriori informazioni](../../integrating/using/get-started-campaign-integrations.md).

Aggiornamento della guida contestuale interna al prodotto di Campaign Standard.

## Versione 18.2 - Febbraio 2018 {#release-18-2---february-2018}

**Nuove funzionalità incluse nella versione**

Abbonamento: attiva o annulla l’abbonamento a servizi multipli di un elenco di profili - [Ulteriori informazioni](../../automating/using/subscription-services.md)

Attività Enrichment: arricchisci i dati in base alle transizioni precedenti - [Ulteriori informazioni](../../automating/using/enrichment.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stata modificata la maggior parte degli URL per le integrazioni di soluzioni Campaign e Adobe. Controlla i tuoi segnalibri. [Ulteriori informazioni](../../integrating/using/get-started-campaign-integrations.md)

Il modello dati v1 è ora disponibile con la struttura SQL per le risorse integrate - [Ulteriori informazioni](../../developing/using/datamodel-introduction.md)

Sono state aggiunte informazioni sulle modalità di preparazione di un messaggio in una consegna [Ulteriori informazioni](../../sending/using/preparing-the-send.md)

Le note sulla versione sono state riorganizzate su varie pagine, in modo da ottenere una visualizzazione più globale di tutte le varie versioni.

La sezione **[!UICONTROL Working with typologies]** è stata aggiornata per migliorarne la visibilità. [Ulteriori informazioni](../../sending/using/about-typology-rules.md)

È ora disponibile una nuova opzione che consente di migliorare le prestazioni quando definisci numerosi dati aggiuntivi in una **[!UICONTROL Query]** . [Ulteriori informazioni](../../automating/using/query-samples.md)

L’esempio di importazione del profilo è stato aggiornato con alcuni suggerimenti per consentire ai profili di la ricezione di direct mailing. [Ulteriori informazioni](../../automating/using/about-data-import-and-export.md)

È disponibile una nuova attività nei flussi di lavoro: **[!UICONTROL Enrichment]**. [Ulteriori informazioni](../../automating/using/enrichment.md)

L’attività **[!UICONTROL Subscription Services]** è stata aggiornata per supportare più casi d’uso, incluso l’utilizzo di un singolo file per aggiornare gli abbonamenti a più servizi. [Ulteriori informazioni](../../automating/using/subscription-services.md)

È stato aggiunto un caso d’uso dettagliato sulla modalità di preparazione di una consegna. [Ulteriori informazioni](../../sending/using/preparing-the-send.md)

È stata rimossa la sezione che include l’elenco delle autorizzazioni. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=it) (PDF).

È stato aggiunto un caso d’uso dettagliato sulle modalità d’utilizzo della risposta automatica SMS. [Ulteriori informazioni](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

Sono state aggiunte informazioni sulla modalità di invio di una consegna in base ai fusi orari degli utenti nell’ambito di un flusso di lavoro ricorrente. [Ulteriori informazioni](../../automating/using/recurring-push-notifications.md)

Riorganizzazione della sezione **[!UICONTROL Customizing a push notification]** con casi d’uso dettagliati. [Ulteriori informazioni](../../channels/using/customizing-a-push-notification.md)

Nuova sezione dedicata alla gestione dell’elenco Bloccati. [Ulteriori informazioni](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Sono state aggiornate le informazioni sugli errori di consegna e quarantena. [Ulteriori informazioni](../../sending/using/monitoring-a-delivery.md)

Nuove sezioni dedicate alle [mappature di destinazione](../../administration/using/target-mappings-in-campaign.md) e a [dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).

## Versione 18.1 - Gennaio 2018 {#release-18-1---january-2018}

**Nuove funzionalità incluse nella versione**

Reporting per la gestione dell’affaticamento - [Ulteriori informazioni](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

Condivisione dei report - [Ulteriori informazioni](../../reporting/using/reporting-interface.md#share-tab)

Miglioramenti push - Per ulteriori informazioni, [consulta qui](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification) e [qui](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)

Consegne ottimizzate in base al fuso orario - [Ulteriori informazioni](../../automating/using/scheduler.md)

Attivazione attività segnale API - [Ulteriori informazioni](../../api/using/triggering-a-signal-activity.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stata aggiornata la sezione relativa alla creazione del servizio. [Ulteriori informazioni](../../audiences/using/creating-a-service.md)

Sono stati aggiunti i casi d’uso per una migliore comprensione dei gruppi e delle unità di sicurezza. [Ulteriori informazioni](../../administration/using/organizational-units.md)

Sono state migliorate le definizioni e i calcoli di dimensioni, metriche e segmenti all’interno dei report dinamici. [Ulteriori informazioni](../../reporting/using/list-of-components.md)

Sono state aggiunte le informazioni relative al recupero dei messaggi SMS in arrivo tramite il flusso di lavoro. [Ulteriori informazioni](../../administration/using/configuring-sms-channel.md)

Sono state inserite le informazioni sulle impostazioni di storicizzazione dell’attività Trasferire file. [Ulteriori informazioni](../../automating/using/transfer-file.md)

Sono state aggiornate le istruzioni per configurare l’integrazione con Audience Manager o con il servizio core People. [Ulteriori informazioni](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

## Versione 17.10 - Ottobre 2017 {#release-17-10---october-2017}

**Nuove funzionalità incluse nella versione**

Gestione dell’affaticamento - [Ulteriori informazioni](../../sending/using/fatigue-rules.md)

Creazione di contenuti: importazione da un URL - [Ulteriori informazioni](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stato aggiornato il campione di test A/B. [Ulteriori informazioni](../../channels/using/designing-an-a-b-test-email.md)

Nuova nota tecnica sulla modalità di creazione o aggiornamento dei dati del profilo quando un’app mobile invia i dati “Raccogli PII”. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/push-notifications/updating-profile-with-mobile-app-data.html)

È stata aggiunta una sezione sulle nuove funzionalità di tracciamento delle esportazioni. [Ulteriori informazioni](../../administration/using/auditing-export-logs.md)

Sono state aggiunte delle precisazioni sull’esportazione di pacchetti integrati. [Ulteriori informazioni](../../automating/using/managing-packages.md)

È stato eseguito l’aggiornamento della definizione degli account esterni e dei relativi esempi. [Ulteriori informazioni](../../administration/using/external-accounts.md)

Sono state aggiornate numerose schermate per riflettere le modifiche nelle categorie dell’editor delle query.

La sezione [Avvisi di consegna](../../sending/using/receiving-alerts-when-failures-happen.md) è stata spostata e riorganizzata.

La sezione “Risorse personalizzate” è stata chiarita con una procedura più dettagliata su come [definire i filtri](../../developing/using/configuring-filter-definition.md).

È stata aggiornata e chiarita la [nota tecnica](https://helpx.adobe.com/it/campaign/kb/integrate-mobile-sdk.html) su come integrare con un’app mobile l’SDK di Adobe Marketing Cloud Mobile, in modo da ricevere le notifiche push di Adobe Campaign Standard.

È stata aggiunta una nota tecnica che illustra la struttura del payload ricevuto all’interno di un’app mobile. [Ulteriori informazioni.](../../administration/using/push-payload.md)

La [sezione](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) Configurazione canale push è stata aggiornata con nuovi dati di payload sulla versione del sistema operativo da aggiungere durante la definizione dei postback all’interno dell’interfaccia di Adobe Mobile Services.

La documentazione SMS è stata aggiornata con alcuni chiarimenti aggiunti alla sezione [risposte automatiche](../../channels/using/managing-incoming-sms.md#managing-stop-sms) SMS.

È stata inserita una nuova sezione dedicata alla gestione del flusso di lavoro tramite API. [Ulteriori informazioni](../../api/using/controlling-a-workflow.md)

È presente una nuova sezione dedicata alle chiavi primarie e all’utilizzo di un ID società come chiave nell’API. [Ulteriori informazioni](../../api/using/get-started-apis.md)

Sono state aggiunte informazioni sui filtri semplici e multipli all’interno dell’API. [Ulteriori informazioni](../../api/using/filtering.md)

## Versione 17.9 - Settembre 2017 {#release-17-9---september-2017}

**Nuove funzionalità incluse nella versione**

Libreria di modelli e-mail - [Ulteriori informazioni](../../designing/using/using-reusable-content.md#content-templates)

Reporting dinamico con i dati del profilo - [Ulteriori informazioni](../../reporting/using/about-dynamic-reports.md)

Miglioramento dell’abbonamento di massa - [Ulteriori informazioni](../../automating/using/subscription-services.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Elenco dettagliato di tutti i componenti disponibili in Report dinamici e alcune modifiche nelle formule. [Ulteriori informazioni](../../reporting/using/list-of-components.md)

Elenco dettagliato di KPI (Key Performance Indicator) condivisi con Adobe Analytics. [Ulteriori informazioni](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Nuovo video sui report dinamici.

Sono state aggiunte le raccomandazioni per l’account S3. [Ulteriori informazioni](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

È stata aggiornata la sezione sui vari tipi di utenti. [Ulteriori informazioni](../../administration/using/users-management.md)

È stata aggiornata la sezione sulla personalizzazione delle immagini sorgente. [Ulteriori informazioni](../../designing/using/personalization.md#personalizing-an-image-source)

È stata aggiunta la documentazione al report dei profili attivi. [Ulteriori informazioni](../../audiences/using/active-profiles.md)

La documentazione relativa agli [Avvisi di consegna](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons) è stata aggiornata con una sezione dedicata alla risoluzione dei problemi, che illustra alcuni suggerimenti sulle azioni da intraprendere al momento della ricezione degli avvisi.

È disponibile una nuova guida introduttiva: presenta alcune delle best practice da poter adottare per la consegna con Adobe Campaign, dalla creazione e dal targeting fino all’invio e al monitoraggio. [Ulteriori informazioni](../../sending/using/delivery-best-practices.md)

La documentazione relativa ai messaggi di follow-up è stata aggiornata con un caso d’uso migliore. [Ulteriori informazioni](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

È stata aggiunta la documentazione relativa all’ID ACS. [Ulteriori informazioni](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Sono state aggiunte nuove funzioni di cifratura e hashing con esempi. [Ulteriori informazioni](../../automating/using/list-of-functions.md)

È stata aggiornata la sezione sull’attività del flusso di lavoro di Trasferire file. [Ulteriori informazioni](../../automating/using/transfer-file.md)

Sono state aggiunte informazioni all’opzione &quot;Richiedi conferma prima di inviare i messaggi&quot; nell’attività del flusso di lavoro Email delivery. [Ulteriori informazioni](../../automating/using/email-delivery.md)

## Versione 17.7 - Luglio 2017 {#release-17-7---july-2017}

**Nuove funzionalità incluse nella versione**

Consegne multilingue (e-mail e SMS) - [Ulteriori informazioni](../../channels/using/creating-a-multilingual-email.md)

Notifiche di Adobe Campaign - [Ulteriori informazioni](../../administration/using/sending-internal-notifications.md)

Avvisi sulla consegna - [Ulteriori informazioni](../../sending/using/receiving-alerts-when-failures-happen.md)

Crittografia dell’ID dichiarato nelle origini dati - [Ulteriori informazioni](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Condivisione di KPI (Key Performance Indicator) da Campaign ad Analytics - [Ulteriori informazioni](../../integrating/using/about-campaign-analytics-integration.md)

Canale direct mailing - Rendi al mittente, [Ulteriori informazioni](../../channels/using/return-to-sender.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Le guide introduttive e i video sulle procedure sono stati raggruppati in una sezione dedicata.

È stata aggiornata la documentazione relativa al rendering di e-mail. [Ulteriori informazioni](../../sending/using/email-rendering.md)

È stata aggiornata la tabella di calcolo dell’indicatore del report. [Ulteriori informazioni](../../reporting/using/indicator-calculation.md)

La documentazione sul reporting è stata aggiornata con quattro nuove metriche. [Ulteriori informazioni](../../reporting/using/list-of-components.md)

È stata aggiunta la documentazione sulla generazione di ID univoci per i profili. [Ulteriori informazioni](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Il doppio meccanismo di consenso è ora documentato attraverso una procedura dettagliata. [Ulteriori informazioni](../../channels/using/setting-up-a-double-opt-in-process.md)

È stata aggiornata la sezione Elenco di ruoli. [Ulteriori informazioni](../../administration/using/list-of-roles.md)

## Versione 17.5 - Maggio 2017 {#release-17-5---may-2017}

**Nuove funzionalità incluse nella versione**

Direct mailing - [Ulteriori informazioni](../../channels/using/about-direct-mail.md)

E-mail con indirizzi Ccn - [Ulteriori informazioni](../../sending/using/archiving.md)

**Altri aggiornamenti alla documentazione inclusi nella versione**

La guida &quot;Consegne&quot; è stata riorganizzata e rinominata &quot;Canali&quot;. [Ulteriori informazioni](../../channels/using/get-started-communication-channels.md)

Numerose schermate sono state aggiornate per riflettere le modifiche all’interfaccia.

È ora disponibile una nuova nota tecnica: &quot;Integrazione dell’SDK di Adobe Mobile con la tua app mobile&quot;. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/integrate-mobile-sdk.html)

Sono state aggiunte le istruzioni per configurare il servizio core People o l’integrazione Audience Manager con Adobe Campaign. [Leggi tutto](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

È stata eseguita la revisione della tabella Autorizzazioni per rendere più chiara la funzione di alcuni ruoli. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=it)

Sono stati aggiornati i collegamenti di aiuto contestuali disponibili direttamente all’interno di Adobe Campaign.

## Versione 17.4 - Aprile 2017 {#release-17-4---april-2017}

**Nuove funzionalità incluse nella versione**

Funzionalità di editing immagine migliorate con Creative SDK - [Ulteriori informazioni](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

Notifiche push transazionali - [Ulteriori informazioni](../../channels/using/transactional-push-notifications.md)

Notifiche push ricorrenti - [Ulteriori informazioni](../../automating/using/push-notification-delivery.md)

Connettore Amazon Simple Storage Service (S3) - [Ulteriori informazioni](../../administration/using/external-accounts.md)

Integrazione live di Dreamweaver - [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=it)

**Altri aggiornamenti alla documentazione inclusi nella versione**

È stata aggiunta una sezione ai vari tipi di utenti di Adobe Campaign. [Ulteriori informazioni](../../administration/using/users-management.md)

La Guida al Flusso di lavoro è stata riorganizzata ed estesa. Scopri facilmente come [generare](../../automating/using/building-a-workflow.md) ed [eseguire](../../automating/using/about-workflow-execution.md) un flusso di lavoro, come [eseguire il targeting](../../automating/using/about-targeting-activities.md) e [gestire](../../automating/using/about-targeting-activities.md#enriching-data) i tuoi dati, come [importare ed esportare](../../automating/using/about-data-import-and-export.md) i dati e come utilizzare i dati del flusso di lavoro per aggiornare il database o per inviare consegne.

Ora è disponibile il calcolo degli indicatori di report per i report dinamici, tra cui la descrizione completa e la formula di calcolo. [Ulteriori informazioni](../../reporting/using/indicator-calculation.md)

Nuova sezione dedicata alla configurazione di Adobe Mobile Services per l’utilizzo delle notifiche push e dei dati dei punti di interesse all’interno di Adobe Campaign. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html)

Sono state aggiornate le sezioni di configurazione e implementazione delle app mobili, inclusi i passaggi più dettagliati per la configurazione e l’invio delle notifiche push. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html)

È stata aggiornata la sezione su come lavorare con le immagini all’interno di Campaign. [Ulteriori informazioni](../../designing/using/images.md#setting-up-image-properties)

È stata aggiornata l’integrazione con Adobe Analytics per dispositivi mobili (punto di interesse), inclusi i passaggi di configurazione e il caso d’uso. [Ulteriori informazioni](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## Versione 17.2 - Marzo 2017 {#release-17-2---march-2017}

**Nuove funzionalità incluse nella versione**

Reporting dinamico - [Ulteriori informazioni](../../reporting/using/about-dynamic-reports.md)

Integrazione di Dreamweaver (Labs) - [Ulteriori informazioni](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=it)

Ottimizzazione manuale del tempo di invio - [Ulteriori informazioni](../../sending/using/optimizing-the-sending-time.md)

Notifiche push: miglioramenti - [Ulteriori informazioni](../../channels/using/about-push-notifications.md)

Flussi di lavoro: nuova attività del segnale - [Ulteriori informazioni](../../automating/using/external-signal.md)

Flussi di lavoro: nuova attività Read audience - [Ulteriori informazioni](../../automating/using/read-audience.md)

Dati dei punti di interesse - [Ulteriori informazioni](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

Risorse collegate nelle API REST - [Ulteriori informazioni](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Integrazione Triggers: sono stati aggiunti due casi d’uso. [Ulteriori informazioni](../../integrating/using/abandonment-triggers-use-cases.md)

Per migliorare la user experience, abbiamo riprogettato la documentazione API per sviluppatori con nuove informazioni e snippet di codice. [Ulteriori informazioni](../../api/using/get-started-apis.md)

Scopri alcuni esempi delle nuove attività del flusso di lavoro [Read audience](../../automating/using/read-audience.md) e [External signal](../../automating/using/external-signal.md).

## Versione 17.1 - Gennaio 2017 {#release-17-1---january-2017}

**Nuove funzionalità incluse nella versione**

Esportazione registro per reporting esterno - [Ulteriori informazioni](../../automating/using/exporting-logs.md)

API di messaggistica transazionale - [Ulteriori informazioni](../../api/using/get-started-apis.md)

Funzionalità di marketing per i messaggi transazionali: [ulteriori informazioni](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**Altri aggiornamenti alla documentazione inclusi nella versione**

Attività flusso di lavoro Incremental query: nuova modalità incrementale - [Ulteriori informazioni](../../automating/using/incremental-query.md)

Aggiornamento attività del flusso di lavoro di pianificazione - [Ulteriori informazioni](../../automating/using/scheduler.md)

Modifica URL: servizio core Assets - [Ulteriori informazioni](../../integrating/using/working-with-campaign-and-assets-core-service.md)

Modifica URL: servizio core People - [Ulteriori informazioni](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

È stata riorganizzata la guida sui profili e tipi di pubblico. [Ulteriori informazioni](../../audiences/using/get-started-profiles-and-audiences.md)
