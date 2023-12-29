---
title: Privacy e consenso in Adobe Campaign Standard
description: Questa sezione fornisce una panoramica sulla gestione della privacy, dei dati personali e del consenso in Adobe Campaign Standard, nonché degli strumenti disponibili per facilitarla.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: User
level: Intermediate
exl-id: 0fc71c2f-f294-43f7-825c-73ab4d43fcf7
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '1377'
ht-degree: 100%

---

# Privacy e consenso{#privacy-and-consent}

## Raccomandazioni generali {#general-recommendations}

Adobe Campaign è uno strumento utile per la raccolta e l’elaborazione di grandi quantità di dati, compresi informazioni personali e dati riservati. Ecco perché è fondamentale gestire attentamente la privacy.

* Fai sempre uso delle informazioni personali in modo responsabile ed etico.

* Non inviare e-mail, notifiche push e messaggi SMS non richiesti (“spam”). Adobe crede fermamente nei principi del permission marketing per promuovere la fedeltà e il valore del ciclo di vita del cliente, e pertanto vieta severamente l’utilizzo di Adobe Campaign per l’invio di messaggi non richiesti.

### Normative sulla privacy {#privacy-regulations}

Per gestire correttamente la privacy e i dati personali, attieniti alle normative applicabili alle regioni in cui operi. Tali normative comprendono:
* [GDPR](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_it) (Regolamento generale europeo sulla protezione dei dati)
* [DPA](https://www.gov.uk/data-protection) (implementazione del GDPR nel Regno Unito)
* [Direttiva europea relativa alla vita privata e alle comunicazioni elettroniche](https://eur-lex.europa.eu/legal-content/IT/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business) (legge statunitense che definisce le regole e i requisiti per le e-mail commerciali)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (legge sulla protezione dei dati personali in Thailandia)

>[!NOTE]
>
>Per ulteriori informazioni sul modo in cui le normative GDPR, CCPA e PDPA interessano Adobe Campaign, consulta [questa pagina](../../start/using/privacy-management.md#privacy-management-regulations).

### Privacy di Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign fa parte delle soluzioni Adobe Experience Cloud. Il modo in cui viene gestita la privacy in Campaign rispetta i principi generali di Adobe Experience Cloud, come ad esempio quanto segue:

* **Quali informazioni vengono raccolte durante l’utilizzo di Adobe Experience Cloud**

  In qualità di azienda che utilizza le soluzioni Adobe Experience Cloud, puoi scegliere quali informazioni raccogliere e inviare all’account Adobe Experience Cloud. Alcuni esempi dei tipi di informazioni che possono essere raccolti includono attività di navigazione web, indirizzi IP, informazioni sulla posizione inviate dai dispositivi mobili, tassi di successo delle campagne, articoli acquistati o inseriti nel carrello, ecc.

  >[!NOTE]
  >
  >Come tutti i prodotti Adobe, Campaign raccoglie informazioni sugli utenti dell’app e del sito web. Per ulteriori informazioni, consulta l’[Informativa sulla privacy di Adobe](https://www.adobe.com/it/privacy/policy.html).

* **Utilizzare Adobe Experience Cloud per raccogliere informazioni**

   * Le soluzioni Adobe Experience Cloud utilizzano cookie e tecnologie simili, come web beacon (noti anche come tag o pixel), per consentirti di raccogliere informazioni. Per ulteriori informazioni sui cookie e sulle funzionalità di tracciamento con Adobe Campaign, consulta [questa sezione](#tracking-capabilities).
   * Puoi anche utilizzare le tecnologie Adobe Experience Cloud nelle tue app mobili. Per ulteriori informazioni sull’invio di consegne su dispositivi mobili con Campaign, consulta [questa pagina](../../channels/using/mobile-guide.md).

* **Scelte degli utenti in materia di privacy relative all’utilizzo di Adobe Experience Cloud**

   Adobe richiede che tu fornisca ai clienti le informative sulla privacy che descrivono:

   * Le tue prassi in materia di privacy in relazione ad Adobe Experience Cloud
   * In che modo gli utenti possono impostare le proprie preferenze per la raccolta o l’utilizzo delle proprie informazioni in relazione ad Adobe Experience Cloud

  >[!NOTE]
  >
  >Come per tutti i prodotti di Adobe, gli utenti di Campaign possono scegliere di rinunciare alla condivisione di informazioni raccolte su di loro tramite app e siti web. Per ulteriori informazioni, consulta le [domande frequenti relative all’utilizzo di Adobe Experience Cloud](https://www.adobe.com/it/privacy/experience-cloud-usage-info-faq.html).

Per ulteriori dettagli sulla privacy di Adobe Experience Cloud, consulta [questa pagina](https://www.adobe.com/it/privacy/experience-cloud.html).

## Dati personali e utenti tipo {#personal-data}

Nella gestione della privacy è importante definire quali dati devono essere gestiti con cura e chi si occupa della gestione.
* **I dati personali** sono informazioni che possono identificare direttamente o indirettamente un individuo.
* **I dati personali riservati** sono informazioni relative a etnia, opinioni politiche, credenze religiose, precedenti penali, informazioni genetiche, dati sanitari, orientamento sessuale e informazioni biometriche di un individuo, nonché ad appartenenze a sindacati.

Le [normative principali](#privacy-regulations) si riferiscono alle diverse entità che gestiscono i dati come segue:
* Il **titolare del trattamento** è l’autorità che determina i mezzi e lo scopo della raccolta, dell’utilizzo e della condivisione dei dati personali.
* Il **responsabile del trattamento** è qualsiasi individuo o parte che raccoglie, utilizza o condivide dati personali come indicato dal titolare del trattamento.
* L’**interessato** è qualsiasi individuo i cui dati personali vengono raccolti, utilizzati o condivisi e che può essere identificato direttamente o indirettamente in base a tali dati personali.

Pertanto, in quanto azienda che raccoglie e condivide dati personali, ricopri il ruolo di titolare del trattamento, i tuoi clienti costituiscono gli interessati e Adobe Campaign agisce come responsabile del trattamento quando tratta i loro dati personali secondo le istruzioni da te fornite. In quanto titolare del trattamento, sei responsabile della gestione del rapporto con gli interessati, ad esempio durante la gestione delle [richieste di accesso a dati personali](#privacy-requests).

È necessario prestare maggiore attenzione alla protezione dei dati personali durante l’integrazione di Campaign con altre soluzioni Experience Cloud, come [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager o Servizio core People](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) o con altre soluzioni quali [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md), in cui i tipi di pubblico possono essere trasferiti da un sistema all’altro.

## Acquisizione dei dati {#data-acquisition}

 Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

* Assicurati che i destinatari ricevano le comunicazioni solo se lo desiderano. Per farlo, accetta al più presto le richieste di rifiuto e verifica il consenso mediante un processo di doppio consenso. Per ulteriori informazioni, consulta [Gestione del consenso e del rifiuto in Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) e [Impostazione di un processo di doppio consenso](../../channels/using/setting-up-a-double-opt-in-process.md).
* Non importare elenchi fraudolenti e utilizza “trappole” per verificare che il file client non venga utilizzato in modo fraudolento. Per ulteriori informazioni, consulta [Utilizzo delle “trappole”](../../sending/using/using-traps.md).
* Tramite la gestione del consenso e dei diritti puoi tenere traccia delle preferenze dei destinatari e gestire chi all’interno dell’organizzazione può accedere ai dati. Per ulteriori informazioni, consulta [questa sezione](#consent).
* Facilita e gestisci le richieste di accesso a dati personali dei destinatari. Per ulteriori informazioni, consulta [questa sezione](#privacy-requests).

## Gestione della privacy {#privacy-management}

La gestione della privacy si riferisce a tutti i processi e agli strumenti che possono aiutarti a rispettare le normative sulla privacy (GDPR, CCPA, ecc.). Per una panoramica sulla gestione della privacy, visita [questa pagina](../../start/using/privacy-management.md#privacy-management-regulations).

 Adobe Campaign offre varie serie di funzioni dedicate alla gestione della privacy:
* Gestione del consenso, conservazione dei dati e ruoli degli utenti. Vedi [questa sezione](#consent).
* Richieste di accesso a dati personali (diritto di accesso e diritto all’oblio). Vedi [questa sezione](#privacy-requests).
* Rinuncia alla vendita di informazioni personali (relativa al CCPA). Vedi [questa sezione](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

In [questa sezione](#personal-data) sono illustrate le principali funzionalità di Campaign relative alla privacy e un esempio degli utenti tipo coinvolti.


### Consenso, conservazione e ruoli {#consent}

Adobe Campaign offre da sempre funzioni importanti necessarie per la privacy:

* **Gestione del consenso**: attraverso il processo di gestione degli abbonamenti, puoi gestire le preferenze dei destinatari e tenere traccia dei destinatari che hanno acconsentito all’abbonamento e di che tipo di abbonamento si tratta. Per ulteriori informazioni, consulta [Abbonamenti](../../audiences/using/about-subscriptions.md) e [Pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md).
* **Conservazione dei dati**: tutte le tabelle di registro standard integrate dispongono di periodi di conservazione preimpostati, che in genere limitano l’archiviazione dei dati a un massimo di 6 mesi. Puoi impostare ulteriori periodi di conservazione con i flussi di lavoro. Per maggiori informazioni, rivolgiti ai consulenti o agli amministratori tecnici di Adobe.
* **Gestione dei diritti**: Adobe Campaign consente di gestire i diritti assegnati ai vari operatori Campaign tramite diversi ruoli predefiniti o personalizzati. Questo consente di gestire chi può modificare, esportare o accedere a diversi tipi di dati all’interno dell’azienda. Per ulteriori informazioni, consulta [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md).

Per ulteriori informazioni su queste funzioni e su come gestirle in Adobe Campaign, consulta [questa pagina](../../start/using/privacy-management.md#consent-retention-roles).

### Richieste di accesso a dati personali {#privacy-requests}

 Adobe Campaign offre funzionalità aggiuntive per consentirti di attenerti a determinate richieste di accesso a dati personali in qualità di titolare del trattamento:

* Il **diritto di accesso** è il diritto dell’interessato di ottenere conferma da parte del titolare del trattamento sul fatto che i dati personali che lo riguardano siano trattati o meno, su dove avvenga il trattamento e sullo scopo del trattamento.

* Il **diritto all’oblio** (richiesta di cancellazione) autorizza l’interessato a richiedere che il titolare del trattamento cancelli i suoi dati personali.

>[!NOTE]
>
>Questi strumenti sono a tua disposizione per aiutarti a rispettare le normative sulla privacy (GDPR, CCPA e PDPA). Per ulteriori informazioni su queste diverse normative, consulta [questa pagina](../../start/using/privacy-management.md#privacy-management-regulations).

Le richieste di **accesso** ed **eliminazione** vengono presentate in [questa pagina](../../start/using/privacy-management.md#right-access-forgotten). I passaggi di implementazione per creare queste richieste sono illustrati in [questa pagina](../../start/using/privacy-requests.md#about-privacy-requests). Sono inoltre disponibili alcuni tutorial in [questa pagina](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=it).

## Funzionalità di tracciamento {#tracking-capabilities}

Grazie alle funzionalità di tracciamento, Adobe Campaign consente di monitorare il comportamento dei destinatari delle consegne utilizzando cookie di sessione e cookie permanenti. Per ulteriori informazioni sul tracciamento, consulta [questa pagina](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Normative quali il Regolamento generale sulla protezione dei dati (GDPR) affermano che le aziende necessitano del consenso degli utenti del sito web per installare i cookie. È necessario informare gli utenti che i siti sono dotati di strumenti di monitoraggio web tramite una richiesta di autorizzazione.

Puoi anche aggiungere [collegamenti tracciati](../../designing/using/links.md#about-tracked-urls) nei messaggi per misurare l’impatto della consegna e il comportamento dei destinatari nel rapporto integrato sugli [indicatori di tracciamento](../../reporting/using/tracking-indicators.md) o creare [rapporti dedicati](../../reporting/using/about-dynamic-reports.md).
