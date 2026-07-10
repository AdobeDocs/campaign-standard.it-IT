---
title: Linee guida CNIL sui pixel di tracciamento e-mail
description: Scopri le linee guida aggiornate di CNIL sui pixel di tracciamento delle e-mail e i controlli Adobe Campaign Standard che possono supportare le attività di conformità.
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---


# Informazioni sulle linee guida aggiornate di CNIL sui pixel di tracciamento e-mail {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**In questa pagina:** Scopri le raccomandazioni CNIL di aprile 2026 sui pixel di tracciamento delle e-mail e scopri i controlli di Adobe Campaign Standard (attivazione del tracciamento, tracciamento a livello di collegamento, modello di dati del consenso, meccanismi di rinuncia e reporting) che possono supportare le tue attività di conformità.

>[!ENDSHADEBOX]

Questo post è solo a scopo informativo. Non si tratta di una consulenza legale e non garantisce il rispetto delle leggi applicabili da parte dell&#39;utente. Le funzionalità del prodotto Adobe Campaign Standard descritte di seguito sono elementi di base che, configurati e gestiti in modo appropriato, possono supportare un’implementazione conforme. Ciascun cliente è responsabile della determinazione e del rispetto degli obblighi derivanti dalla legge applicabile.

## Panoramica {#overview}

Il 14 aprile 2026 la *Commission nationale de l&#39;informatique et des libertés* (CNIL), l&#39;autorità francese per la protezione dei dati, ha pubblicato una [raccomandazione sull&#39;uso dei pixel di tracciamento nelle e-mail](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). La guida chiarisce quando è necessario il consenso ed evidenzia l’importanza di pratiche di consenso appropriate per il tracciamento dei pixel dell’e-mail. Questo criterio potrebbe influire sulle pratiche di invio per qualsiasi entità che distribuisce e-mail agli abbonati con sede in Francia.

CNIL ha previsto un periodo di tre mesi dalla data della raccomandazione alle aziende di informare i propri destinatari e-mail (&quot;utenti&quot;) della presenza dei pixel di tracciamento, del loro scopo e del diritto degli utenti di rinunciare. Durante questo periodo di transizione, i clienti devono avvisare gli utenti in merito al tracciamento dei pixel e, se necessario, fornire una rinuncia. CNIL dovrebbe iniziare le attività di applicazione dopo il 14 luglio 2026.

Poiché il CNIL e altri enti normativi chiariscono le linee guida sui pixel di tracciamento e sui problemi correlati, Adobe continuerà a monitorare gli aggiornamenti e informerà i clienti sulle funzionalità tecniche dei prodotti Adobe che supportano il marketing via e-mail, incluso Adobe Campaign Standard.

Le applicazioni di esecuzione del marketing via e-mail di Adobe, tra cui Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign e Marketo Engage, forniscono controlli che possono aiutare i clienti a gestire il tracciamento delle aperture a livello di consegna o e-mail. I clienti sono responsabili della determinazione dei propri obblighi di conformità in base alle linee guida CNIL applicabili e ad altre leggi, ma queste funzionalità possono supportare le attività di conformità dei clienti.

### Cos’è un pixel di tracciamento e-mail {#tracking-pixel}

Un pixel di tracciamento e-mail è un’immagine trasparente 1x1 incorporata nel HTML di un’e-mail. Quando il client e-mail del destinatario carica l’immagine, il pixel invia un ping a un server che registra dati quali marca temporale, tipo di dispositivo, client e-mail e, a volte, un indirizzo IP per la posizione approssimativa. Il registro viene quindi associato al record di un destinatario, consentendo agli addetti al marketing di verificare se è stata aperta un’e-mail.

### Assistenza clienti {#support}

I clienti che necessitano di assistenza per implementare le modifiche descritte qui sopra possono interagire con il loro ecosistema Adobe esistente. Per domande tecniche sulle funzionalità Adobe a cui si fa riferimento, contatta il tuo Customer Success Manager o Technical Account Manager.

## Funzionalità Adobe Campaign Standard relative al tracciamento e-mail {#acs-functionality}

I clienti possono utilizzare i meccanismi nativi di tracciamento, schema e personalizzazione di Adobe Campaign Standard per risolvere alcuni elementi durante la configurazione dell’architettura.

### Classificazione e-mail {#email-classification}

Estendi il modello di consegna con un campo personalizzato che indica il tipo di e-mail (autenticazione, solo recapito messaggi, transazionale, marketing con consenso, ricerca B2B). In Campaign Standard, i modelli di consegna possono contenere campi personalizzati che confluiscono nella logica di reporting e flusso di lavoro. Questa classificazione determina quale tracciamento è appropriato per ogni invio.

[Scopri come creare e utilizzare i modelli di consegna](../../channels/using/creating-an-email.md)

### Modello dati di consenso {#consent-data-model}

Estendere la risorsa Profilo tramite il meccanismo di risorse personalizzate di Campaign Standard (**Amministrazione > Sviluppo > Risorse personalizzate**) per includere flag di consenso per scopo, marche temporali del consenso e la data dell&#39;apertura più recente (solo data — nessun componente orario). Una risorsa personalizzata separata collegata al profilo acquisisce il registro eventi di consenso di sola aggiunta che supporta la prova di consenso individuale. Poiché le pagine di destinazione di Campaign Standard possono scrivere direttamente nei campi Profilo, lo stato di consenso corrente è gestibile in modo nativo; il registro dei consensi viene scritto tramite l&#39;API REST di Adobe Campaign Standard (`/profileAndServicesExt`) una volta inviata una preferenza.

[Scopri come creare o estendere una risorsa](../../developing/using/creating-or-extending-the-resource.md)

[Scopri come interagire con le risorse personalizzate tramite API](../../api/using/interacting-with-custom-resources.md)

### Emissione pixel {#pixel-emission}

Adobe Campaign Standard controlla il tracciamento a livello di consegna tramite l&#39;interruttore **[!UICONTROL Activate tracking]** nelle proprietà della consegna o del modello. Per le consegne in cui il tracciamento delle aperture non è consentito (solo autenticazione, e-mail di richiesta), questa opzione è disabilitata. Per le consegne in cui è appropriata l&#39;emissione di pixel per uno scopo, un approccio consiste nel disabilitare il pixel inserito automaticamente standard e utilizzare blocchi di contenuto contenenti elementi immagine tracciati condizionali 1×1, uno per scopo, in cui a ogni immagine viene assegnata una categoria URL (`PIX_DELIV`, `PIX_PERF`, `PIX_PROFILE`, `PIX_FRAUD`) e viene visualizzato solo quando il flag di consenso corrispondente del destinatario è true.

[Scopri come configurare i parametri di tracciamento e-mail](configuring-email-channel.md#tracking-parameters)

[Scopri come gestire gli URL tracciati in E-mail Designer](../../designing/using/links.md#about-tracked-urls)

[Scopri come aggiungere blocchi di contenuto](../../designing/using/personalization.md#adding-a-content-block)

### Ritiro {#withdrawal}

Aggiungi un collegamento **Gestisci preferenze tracker** a ogni piè di pagina e-mail, diverso dal collegamento per annullare l&#39;iscrizione. Il collegamento punta a una pagina di destinazione di Campaign Standard autenticata tramite il meccanismo `recipientId` o `urlSubscription`; il destinatario attiva i propri flag di consenso per scopo e invia. Una volta confermata, una piccola chiamata all’API REST di Campaign Standard scrive l’evento di ritiro nel registro dei consensi. Il consiglio indica che questo collegamento è esso stesso esente dal requisito di tracciamento per motivi di sicurezza.

[Scopri come impostare le pagine di destinazione di consenso e rinuncia](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[Scopri come iniziare a utilizzare le pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md)

### Prova del consenso {#consent-proof}

Ogni modifica del consenso (acquisizione alla registrazione, aggiornamento dalla pagina delle preferenze, scadenza) crea una riga nella risorsa personalizzata del registro del consenso, contenente il codice della versione del testo, la marca temporale di acquisizione, l’origine di acquisizione e l’ambito. Questo registro può essere interrogato tramite Campaign Standard Explorer, esposto tramite l’API REST ed esportabile per la revisione dell’oggetto Criteri di gruppo tramite un flusso di lavoro pianificato.

[Scopri come interagire con le risorse personalizzate tramite API](../../api/using/interacting-with-custom-resources.md)

### Governance della richiesta {#re-solicitation}

Un campo `cusLastPixelRefusalDate` personalizzato nel profilo, combinato con una regola di filtro della tipologia che esclude i profili in cui tale campo si trova entro un periodo di tempo scelto, impedisce la sollecitazione dei destinatari che hanno rifiutato in quel periodo di tempo. Un flusso di lavoro pianificato gestisce gli intervalli di scadenza del consenso dei clienti contrassegnando i record non aggiornati e scrivendo gli eventi di scadenza nel registro di consenso.

[Scopri come utilizzare le regole di tipologia](../../sending/using/about-typology-rules.md)

[Scopri come gestire le regole di tipologia](../../sending/using/managing-typology-rules.md)

### Generazione rapporti {#reporting}

I rapporti dinamici di Campaign Standard sono basati su categorie URL e dimensioni di profilo. Le categorie di URL per scopo introdotte sopra emergono nei rapporti dinamici come nuove dimensioni, consentendo agli operatori di suddividere i dati in base allo scopo. La distinzione tra tracciamento consentito e non autorizzato è visibile in modalità nativa una volta che le categorie URL sono implementate.

[Scopri come iniziare a utilizzare i rapporti dinamici](../../reporting/using/about-dynamic-reports.md)

[Scopri gli indicatori di tracciamento](../../reporting/using/tracking-indicators.md)
