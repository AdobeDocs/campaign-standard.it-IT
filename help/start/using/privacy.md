---
title: Privacy e consenso in  Adobe Campaign Standard
description: Questa sezione fornisce una panoramica della privacy, dei dati personali e della gestione del consenso in  Adobe Campaign Standard, nonché degli strumenti disponibili per gestirli.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 7f0af4deeaf641e2aded9278b97eb498edd85d08
workflow-type: tm+mt
source-wordcount: '1456'
ht-degree: 3%

---


# Privacy and Consent{#privacy-and-consent}

## Raccomandazioni generali {#general-recommendations}

 Adobe Campaign è uno strumento potente per la raccolta e il trattamento di grandi quantità di dati, tra cui dati personali e sensibili. Ecco perché la privacy deve essere gestita con attenzione.

* Fare sempre un uso responsabile ed etico delle informazioni personali.

* Non inviare e-mail, notifiche push e messaggi SMS non richiesti (&quot;spam&quot;).  Adobe crede fermamente nei principi di marketing delle autorizzazioni per promuovere il valore e la fedeltà della vita dei clienti, e pertanto vieta severamente l&#39;uso di  Adobe Campaign nell&#39;invio di messaggi non richiesti.

### Norme sulla privacy {#privacy-regulations}

Per gestire correttamente la privacy e gestire i dati personali, lavorare nell&#39;ambito delle normative applicabili alle regioni in cui si opera. Tali regolamenti comprendono:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Regolamento generale europeo sulla protezione dei dati)
* [DPA](https://www.gov.uk/data-protection) (implementazione del GDPR da parte del Regno Unito)
* [Direttiva europea relativa alla vita privata e alle comunicazioni elettroniche](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (legge statunitense che fissa le regole e i requisiti per le e-mail commerciali)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;Chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (legge tailandese sulla protezione dei dati personali)

>[!NOTE]
>
>Per ulteriori informazioni sulle modalità di applicazione di GDPR, CCPA e PDPA a  Adobe Campaign, consulta [questa sezione](../../start/using/privacy-management.md#privacy-management-regulations).

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

 Adobe Campaign fa parte delle soluzioni Adobe Experience Cloud. Il modo in cui viene gestita la privacy in Campaign rispetta i principi generali di Adobe Experience Cloud, come ad esempio quanto segue:

* **Quali informazioni vengono raccolte quando si utilizza Adobe Experience Cloud?**

   In qualità di azienda che utilizza le soluzioni Adobe Experience Cloud, potete scegliere quali informazioni raccogliere e inviare al vostro account Adobe Experience Cloud. Alcuni esempi dei tipi di informazioni che possono essere raccolti sono l&#39;attività di navigazione Web, gli indirizzi IP, le informazioni sulla posizione dai dispositivi mobili, i tassi di successo della campagna, gli elementi acquistati o inseriti nel carrello, ecc.

   >[!NOTE]
   >
   >Come per tutti i prodotti  Adobe, Campaign raccoglie informazioni sugli utenti dell&#39;app e del sito Web. Per ulteriori informazioni, consulta l’ [Informativa](https://www.adobe.com/privacy/policy.html)sulla privacy di Adobe.

* **Utilizzo di Adobe Experience Cloud per la raccolta delle informazioni**

   * Le soluzioni Adobe Experience Cloud utilizzano cookie e tecnologie simili, come web beacon (noti anche come tag o pixel), per consentire la raccolta delle informazioni. Per ulteriori informazioni sui cookie e sulle funzionalità di tracciamento con  Adobe Campaign, consulta [questa sezione](#tracking-capabilities).
   * Puoi anche utilizzare le tecnologie Adobe Experience Cloud nelle tue app mobili. Per ulteriori informazioni sull&#39;invio di materiale mobile con Campaign, consulta [questa pagina](https://helpx.adobe.com/it/campaign/kb/acs-mobile.html).

* **Scelte sulla privacy degli utenti relative all&#39;utilizzo di Adobe Experience Cloud**

    Adobe ti chiede di fornire ai clienti le politiche sulla privacy che descrivono:

   * Le tue prassi sulla privacy in relazione ad Adobe Experience Cloud
   * Come gli utenti possono impostare le proprie preferenze per la raccolta o l&#39;utilizzo delle proprie informazioni in relazione ad Adobe Experience Cloud

   >[!NOTE]
   >
   >Per quanto riguarda tutti  prodotti di Adobe, gli utenti di Campaign possono scegliere di non condividere le informazioni raccolte su di essi tramite app e siti Web. Per ulteriori informazioni, consulta le Domande frequenti relative all’utilizzo di [Adobe Experience Cloud](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html).

Per ulteriori dettagli sulla privacy di Adobe Experience Cloud, consultate [questa pagina](https://www.adobe.com/it/privacy/experience-cloud.html).

## Dati personali e personale {#personal-data}

Durante la gestione della privacy, è importante definire quali dati devono essere gestiti con cura e da chi.
* **Dati** personali sono informazioni che possono identificare direttamente o indirettamente un individuo vivente.
* **Dati** personali sensibili sono informazioni relative alla razza, alle opinioni politiche, alle convinzioni religiose, al contesto penale, alle informazioni genetiche, ai dati sulla salute, alla preferenza sessuale, alle informazioni biometriche, nonché all’appartenenza a un sindacato.

I [principali regolamenti](#privacy-regulations) si riferiscono alle diverse entità che gestiscono i dati come segue:
* Un **titolare del trattamento** dei dati è l&#39;autorità che determina i mezzi e lo scopo della raccolta, dell&#39;uso e della condivisione dei dati personali.
* Un **processore** dati è qualsiasi individuo o parte che raccoglie, utilizza o condivide dati personali come indicato dal Titolare del trattamento.
* Un **Soggetto** dati è qualsiasi individuo vivente i cui dati personali sono raccolti, utilizzati o condivisi e che può essere identificato, direttamente o indirettamente, in riferimento a tali dati personali.

Pertanto, in quanto azienda che raccoglie e condivide dati personali, sei il Titolare del trattamento dei dati, i tuoi clienti sono i Soggetti dati e  Adobe Campaign agisce come un Processore dei dati quando tratta i loro dati personali come da te diretto. In quanto titolare del trattamento dei dati, è responsabilità dell&#39;utente gestire la relazione con gli interessati, ad esempio per la gestione delle richieste [di](#privacy-requests)privacy.

Durante l&#39;integrazione di Campaign con altre soluzioni  Experience Cloud in cui i tipi di pubblico possono essere trasferiti da un sistema all&#39;altro, come il servizio [Destinazioni](../../audiences/using/aep-about-audience-destinations-service.md)Pubblico, [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager o il servizio](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)core Persone, o con altre soluzioni come [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md), devi prestare maggiore attenzione alla protezione dei dati personali.

## Acquisizione dati {#data-acquisition}

 Adobe Campaign consente di raccogliere dati, comprese informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

* Chiedi sempre ai destinatari di ricevere le comunicazioni. A tal fine, è necessario rispettare al più presto le richieste di rifiuto e verificare il consenso mediante un processo di doppio consenso. Per ulteriori informazioni, consulta [Gestione del consenso e del rifiuto in Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) e [Impostazione di un doppio processo](../../channels/using/setting-up-a-double-opt-in-process.md)di consenso.
* Non importate elenchi fraudolenti e utilizzate i trap per verificare che il file client non venga utilizzato in modo fraudolento. Per ulteriori informazioni, vedere [Utilizzo delle trappole](../../sending/using/using-traps.md).
* Tramite la gestione del consenso e dei diritti, puoi tenere traccia delle preferenze dei destinatari e gestire chi all&#39;interno dell&#39;organizzazione può accedere ai dati. Per ulteriori informazioni, consulta [questa sezione](#consent).
* Facilitare e gestire le richieste di privacy dei destinatari. Per ulteriori informazioni, consulta [questa sezione](#privacy-requests).

## Gestione della privacy {#privacy-management}

La gestione della privacy si riferisce a tutti i processi e gli strumenti che possono aiutarti a rispettare le normative sulla privacy (GDPR, CCPA, ecc.). Ottieni una panoramica di Gestione della Privacy su [questa pagina](../../start/using/privacy-management.md).

 Adobe Campaign offre diverse serie di funzioni dedicate alla gestione della privacy:
* Gestione del consenso, conservazione dei dati e ruoli utente. Vedi [questa sezione](#consent).
* Richieste sulla privacy (Diritto di accesso e Diritto di essere Dimenticato). Vedi [questa sezione](#privacy-requests).
* Rinuncia alla vendita di informazioni personali (specifiche CCPA). Vedi [questa sezione](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ccpa).

In [questa sezione](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow)sono illustrate le principali funzionalità di Privacy di Campaign e un esempio delle persone coinvolte.


### Consenso, mantenimento e ruoli {#consent}

In origine,  Adobe Campaign offre importanti caratteristiche essenziali per la privacy:

* **Gestione** del consenso: Attraverso il processo di gestione delle iscrizioni, potete gestire le preferenze dei destinatari e tenere traccia dei destinatari che hanno acconsentito a quale tipo di iscrizioni. Per ulteriori informazioni, consultate [Iscrizioni](../../audiences/using/about-subscriptions.md) e pagine [di](../../channels/using/getting-started-with-landing-pages.md)destinazione.
* **Conservazione** dei dati: Tutte le tabelle di registro standard integrate hanno periodi di conservazione preimpostati, in genere limitano la memorizzazione dei dati a un massimo di 6 mesi. Con i flussi di lavoro è possibile impostare ulteriori periodi di conservazione. Per maggiori informazioni, rivolgiti ai consulenti del Adobe  o agli amministratori tecnici.
* **Gestione** dei diritti:  Adobe Campaign consente di gestire i diritti assegnati ai vari operatori Campaign tramite ruoli predefiniti o personalizzati diversi. Questo consente di gestire chi all’interno della società può accedere, modificare o esportare diversi tipi di dati. Per ulteriori informazioni, consultate [Informazioni sulla gestione](../../administration/using/about-access-management.md)degli accessi.

Per ulteriori informazioni su queste funzionalità e su come gestirle in  Adobe Campaign, consulta [questa sezione](../../start/using/privacy-management.md#consent-retention-roles).

### Richieste sulla privacy {#privacy-requests}

 Adobe Campaign offre funzionalità aggiuntive per facilitare la preparazione di un utente in qualità di titolare del trattamento per determinate richieste di privacy:

* Il **diritto di accesso** è il diritto per l&#39;interessato di ottenere dalla conferma del Titolare dei Dati se i dati personali che li riguardano sono trattati, dove e perché.

* Il **Diritto di essere Dimenticato** (richiesta di cancellazione) autorizza l&#39;interessato a far cancellare i propri dati personali.

>[!NOTE]
>
>Questo set di strumenti è disponibile qui per aiutarti a rispettare la privacy per GDPR, CCPA e PDPA. Per ulteriori informazioni su queste diverse normative, consulta [questa sezione](../../start/using/privacy-management.md#privacy-management-regulations).

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

Le richieste **di accesso** ed **eliminazione** vengono presentate in [questa pagina](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess). Le fasi di implementazione per creare queste richieste sono dettagliate in [questa pagina](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Sono disponibili anche Tutorials [qui](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Funzionalità di tracciamento {#tracking-capabilities}

Grazie alle sue funzionalità di tracciamento,  Adobe Campaign consente di monitorare il comportamento dei destinatari della consegna utilizzando cookie di sessione e cookie permanenti. For more on tracking, see [this section](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Regolamenti come il Regolamento generale sulla protezione dei dati (General Data Protection Regulation, GDPR) affermano che le aziende richiedono l&#39;accordo degli utenti del sito Web prima di installare qualsiasi cookie. È necessario informare gli utenti che i siti sono dotati di strumenti di monitoraggio Web tramite una richiesta di autorizzazione.

Puoi anche aggiungere [i collegamenti](../../designing/using/links.md#about-tracked-urls) tracciati nei messaggi per misurare l&#39;impatto del comportamento della consegna e del destinatario nel rapporto integrato degli indicatori [di](../../reporting/using/tracking-indicators.md) tracciamento o per creare rapporti [](../../reporting/using/about-dynamic-reports.md)dedicati.
