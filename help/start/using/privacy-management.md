---
solution: Campaign Standard
product: campaign
title: Gestione della privacy in Adobe Campaign Standard
description: Ulteriori informazioni sulle funzioni di gestione della privacy di Adobe Campaign Standard.
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Privacy
role: User
level: Intermediate
exl-id: 84cf8f6e-9ba0-4cd5-80e2-a61cefa31e0a
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: ht
source-wordcount: '965'
ht-degree: 100%

---

# Gestione della privacy {#privacy-management}

Adobe Campaign offre una serie di strumenti per aiutarti a rispettare le [normative sulla privacy](#privacy-management-regulations) (inclusi GDPR, CCPA, PDPA, LGPD).

Di seguito sono riportate le cinque funzionalità principali offerte da Adobe Campaign per garantire la conformità al GDPR e alle altre normative sulla privacy:

![](assets/privacy-gdpr-use-cases.png)

* **Diritto di accesso**

* **Diritto di eliminazione**

Per ulteriori informazioni, consulta [Diritto di accesso e diritto all’oblio](#right-access-forgotten).

* **Gestione del consenso**

* **Conservazione dei dati**

* **Rights Management**

Per ulteriori informazioni, consulta [Consenso, conservazione e ruoli](#consent-retention-roles).

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## Normative sulla gestione della privacy {#privacy-management-regulations}

 Le funzionalità di Adobe Campaign consentono di rispettare le seguenti normative:

* **Il GDPR** ([Regolamento generale sulla protezione dei dati](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_it)) è la normativa sulla privacy dell’Unione europea che armonizza e modernizza i requisiti in materia di protezione dei dati per i paesi dell’UE. Visita i collegamenti riportati sotto per informazioni generali sul GDPR:

   * https://www.adobe.com/it/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/it/marketing-cloud/campaign/general-data-protection-regulation.html

* **Il CCPA** ([California Consumer Privacy Act](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) fornisce ai residenti della California nuovi diritti in merito alle loro informazioni personali e impone responsabilità in materia di protezione dei dati a determinate entità che conducono attività commerciali in California.
* **Il PDPA** ([Personal Data Protection Act](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)) è la nuova legge sulla privacy che armonizza e modernizza i requisiti di protezione dei dati in Thailandia.
* **La LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) entrerà in vigore all’inizio del 2021 per tutte le aziende che raccolgono o elaborano dati personali in Brasile.

Queste normative si applicano ai clienti di Adobe Campaign che detengono dati per gli interessati residenti nei rispettivi paesi o aree geografiche di cui sopra (UE, California, Thailandia, Brasile).

>[!NOTE]
>
>Per ulteriori informazioni sui dati personali e sulle diverse entità che gestiscono i dati (titolare del trattamento, responsabile del trattamento e interessato), consulta [Dati personali e utenti tipo](../../start/using/privacy.md#personal-data).

## Diritto di accesso e diritto all’oblio {#right-access-forgotten}

Per aiutarti a garantire l’idoneità alle normative sulla privacy, Adobe Campaign consente di gestire le richieste di **accesso** ed **eliminazione**.

* Il **diritto di accesso** è il diritto dell’interessato di ottenere conferma da parte del titolare del trattamento sul fatto che i dati personali che lo riguardano siano trattati o meno, su dove avvenga il trattamento e sullo scopo del trattamento. Il titolare del trattamento è tenuto a fornire gratuitamente una copia dei dati personali in formato elettronico.

* Anche noto come eliminazione dei dati, il **diritto all’oblio** (richiesta di eliminazione) autorizza l’interessato a richiedere che il titolare del trattamento cancelli i suoi dati personali, cessi l’ulteriore diffusione dei dati ed eventualmente faccia cessare il trattamento dei dati da parte di terzi.

Per informazioni su come creare richieste di **accesso** ed **eliminazione** e su come queste vengono elaborate da Adobe Campaign, fai riferimento ai [passaggi di implementazione](../../start/using/privacy-requests.md#about-privacy-requests).

Tutorial sulla gestione della privacy in Campaign Standard sono inoltre disponibili [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=it#privacy).

>[!NOTE]
>
>Per ulteriori informazioni sui dati personali e sulle diverse entità che gestiscono i dati (titolare del trattamento, responsabile del trattamento e interessato), consulta [Dati personali e utenti tipo](../../start/using/privacy.md#personal-data).

## Consenso, conservazione e ruoli {#consent-retention-roles}

Oltre alle più recenti funzionalità relative al **diritto di accesso** e al **diritto all’oblio**, Adobe Campaign offre altre funzioni essenziali per la privacy:

* [Gestione del consenso](#consent-management): funzionalità di abbonamento per la gestione delle preferenze
* [Conservazione dei dati](#data-retention): periodi di conservazione dei dati in tutte le tabelle di registro standard e la possibilità di impostare periodi di conservazione aggiuntivi con i flussi di lavoro
* [Gestione dei diritti](#rights-management): accesso ai dati gestito in base a diritti denominati

### Gestione del consenso {#consent-management}

Per consenso si intende l’autorizzazione da parte dell’interessato al trattamento dei suoi dati personali. L’ottenimento del consenso necessario per il trattamento dei dati è responsabilità del titolare del trattamento. Sebbene Adobe Campaign fornisca alcune funzionalità per aiutare i clienti a gestire il consenso relativo al servizio, Adobe non è si assume la responsabilità del consenso. I clienti devono collaborare con i propri dipartimenti legali per determinare i processi e le pratiche per ottenere il consenso necessario.

Le funzioni per gestire alcuni aspetti del consenso sono da sempre funzioni core di Adobe Campaign. Attraverso il processo di gestione degli abbonamenti, i clienti possono tenere traccia dei destinatari che hanno acconsentito all’abbonamento, sia che si tratti di newsletter, promozioni giornaliere o settimanali, o qualsiasi altro tipo di programma di marketing.

![](assets/privacy-consent-management.png)

Per ulteriori informazioni sulla gestione del consenso, consulta [Informazioni sugli abbonamenti](../../audiences/using/about-subscriptions.md) e [Introduzione alle pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md).

Oltre a utilizzare gli strumenti di gestione del consenso forniti da Adobe Campaign, puoi verificare se un consumatore ha rinunciato alla vendita di informazioni personali. Vedi [questa sezione](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Conservazione dei dati {#data-retention}

Per quanto riguarda la conservazione, le tabelle di registro integrate in Campaign dispongono di periodi di conservazione preimpostati che in genere limitano l’archiviazione dei dati a un massimo di sei mesi.

Di seguito sono riportati i valori di conservazione predefiniti per le tabelle integrate. Ricorda che la configurazione della conservazione è impostata dagli amministratori tecnici di Adobe durante l’implementazione e che i valori possono variare per ciascuna implementazione, in base ai requisiti dei clienti.

* **Tracciamento consolidato**: 6 mesi
* **Registri di consegna**: 6 mesi
* **Registri di tracciamento**: 6 mesi
* **Eventi**: 1 mese
* **Statistiche sull’elaborazione degli eventi**: 6 mesi
* **Eventi archiviati**: 6 mesi
* **Entità temporanee**: 7 giorni
* **Eventi pipeline ignorati**: 1 mese
* **Avvisi di consegna**: 1 mese
* **Controllo delle esportazioni**: 6 mesi

Analogamente all’eliminazione, quando utilizzi la funzionalità standard del flusso di lavoro puoi impostare periodi di conservazione per qualsiasi tabella personalizzata.

Rivolgiti ai consulenti o agli amministratori tecnici di Adobe per ulteriori informazioni sulla conservazione o per impostare la conservazione per tabelle personalizzate.

### Rights Management {#rights-management}

 Adobe Campaign consente di gestire i diritti assegnati ai vari operatori Campaign tramite diversi ruoli predefiniti o personalizzati.

Uno dei vantaggi offerti è la possibilità di gestire chi può accedere a diversi tipi di dati all’interno dell’azienda. Ad esempio, puoi fare in modo che diversi esperti di marketing che coprono aree geografiche diverse accedano solo ai dati della propria area geografica.

Allo stesso modo, questa funzionalità consente di configurare diverse funzionalità per ogni utente, ad esempio limitare chi può inviare le consegne o, per quanto riguarda la gestione della privacy, chi può modificare o esportare i dati.

![](assets/privacy-user-management.png)

Per ulteriori informazioni sulla gestione degli accessi, consulta [questa sezione](../../administration/using/about-access-management.md).
