---
title: Configurazione degli attivatori in Experience Cloud
seo-title: Configurazione degli attivatori in Experience Cloud
description: Configurazione degli attivatori in Experience Cloud
seo-description: 'Scopri come configurare l’integrazione Adobe Experience Cloud Triggers per iniziare a inviare consegne personalizzate ai clienti in base ai comportamenti precedenti. '
page-status-flag: mai attivato
uuid: 8fd7b804-9528-46a5-a060-bf16b8dc555d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: utilizzo di attivatori per campagne
discoiquuid: 4163dc0c-8103-4425-b8bf-7aa45c4d3a06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Configurazione degli attivatori in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Attivazione della funzionalità {#activating-the-functionality}

La funzionalità deve essere attivata in Adobe Campaign da Adobe. Contatta il tuo responsabile commerciale Adobe o il partner di servizi professionali.

Per attivare i trigger, il team Adobe dovrà disporre delle seguenti informazioni:

* Nome società Marketing Cloud
* ID ORG IMS
* Società di accesso Analytics (può corrispondere al Nome società Marketing Cloud)

## Configurazione di soluzioni e servizi {#configuring-solutions-and-services}

Per utilizzare questa funzione, è necessario avere accesso alle soluzioni/ai servizi di base seguenti:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servizio di base di Experience Cloud Triggers

   ![](assets/trigger_uc_prereq_1.png)

* Servizio di base Experience Cloud DTM

   ![](assets/trigger_uc_prereq_2.png)

* ID visitatore Experience Cloud e servizio di base Experience Cloud People

   ![](assets/trigger_uc_prereq_3.png)

Dovete anche avere un sito Web funzionante.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La delega di sottodominio è un elemento chiave di recapito. Assicurati che i messaggi e-mail di Adobe Campaign vengano inviati dallo stesso dominio utilizzato dal sito Web.

Devi configurare il servizio [di base](#configuring-experience-cloud-dtm-core-service)Experience Cloud DTM, il servizio [di base](#configuring-experience-cloud-people-core-service) Experience Cloud People e [Campaign](#configuring-triggers-and-aliases-in-campaign) per eseguire questi casi di utilizzo.

### Configurazione del servizio di base Experience Cloud DTM {#configuring-experience-cloud-dtm-core-service}

1. In Experience Cloud DTM Core Service (Gestione tag dinamica), attiva Experience Cloud ID e Adobe Analytics per le pagine del tuo sito Web.

   ![](assets/trigger_uc_conf_1.png)

1. La riconciliazione degli ID tra il sito Web, Adobe Analytics e Adobe Campaign richiede l’uso dell’aliasing. Create un alias, ad esempio "visitorid".

   ![](assets/trigger_uc_conf_2.png)

### Configurazione del servizio di base Persone di Experience Cloud {#configuring-experience-cloud-people-core-service}

È necessario creare l’alias precedentemente indicato in Gestione dinamica dei tag nel servizio core Persone di Experience Cloud tramite un attributo cliente. Accertatevi di crearne uno nuovo e fate riferimento allo stesso alias DTM nel codice di integrazione (ad esempio "visitorid").

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Utilizzeremo questo attributo cliente nell'origine dati di Adobe Campaign (passaggio successivo).

### Configurazione di attivatori e alias in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Accertatevi di essere **[!UICONTROL Experience Cloud triggers]** visibili nell'istanza di Adobe Campaign Standard. In caso contrario, contatta gli amministratori di Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Gli alias consentono di riconciliare un contatto in Analytics con un profilo in Campaign. Devi far corrispondere gli alias definiti nel servizio Experience Cloud ID con un'origine dati condivisa in Campaign. Devi configurare la risoluzione degli alias in Adobe Campaign tramite un'origine dati ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Accertatevi di scegliere l'origine dati corretta nel menu a **[!UICONTROL Data Source/Alias]** discesa, mappato con la stessa origine dati Attributo cliente creata nel passaggio precedente.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puoi riconciliare le attivazioni per utenti anonimi e con accesso. Per gli utenti anonimi, il profilo dovrebbe esistere in Adobe Campaign e l'utente ha già ricevuto un'e-mail. A tal fine, la configurazione ID visitatore è sufficiente. Tuttavia, se vuoi riconciliare gli attivatori per gli utenti connessi, devi impostare l’origine dati ID dichiarato. Per ulteriori informazioni, consulta Configurazione [origine](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)dati.

## Creazione di un trigger nell'interfaccia di Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

È necessario creare un attivatore Adobe Experience Cloud per poterlo utilizzare in Campaign.

Crea un nuovo attivatore in Experience Cloud e accertati di selezionare la suite di rapporti utilizzata sul tuo sito Web. Accertatevi di scegliere la dimensione corretta in modo che l'attivatore venga attivato.

Consulta la documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) Adobe Experience Cloud e guarda questo [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Attiva procedure ottimali e limitazioni {#triggers-best-practices-and-limitations}

Elenco delle procedure ottimali e dei limiti per l'utilizzo dell'integrazione Campaign - Triggers:

* Se hai più istanze di Campaign Standard, i trigger possono essere ricevuti da tutte le istanze purché si trovino nello stesso ID organizzazione IMS. Analytics deve anche trovarsi sullo stesso ID organizzazione IMS.
* Non puoi creare un trigger nel servizio di base Trigger utilizzando eventi di due suite di rapporti diverse.
* Gli attivatori si basano sui messaggi transazionali. I messaggi transazionali vengono utilizzati ogni volta che è necessario inviare un messaggio molto rapidamente. Non è possibile mettere in coda i messaggi transazionali e quindi eseguirne il ciclo in batch.
* Gli attivatori non sono deterministici in natura. Quando viene generato un trigger, invia tutti gli alias associati al cookie, pertanto nel caso di browser condivisi come nei chioschi di vendita al dettaglio, nelle librerie, nei cyber-caffè o nei dispositivi condivisi a casa (accesso di marito e moglie dallo stesso dispositivo), non è possibile mappare l'ID corretto. Tutti gli ID utilizzati per accedere con il browser vengono inviati a Campaign, che invia un messaggio in base alla prima riconciliazione. Se sono presenti più "ID e-mail" idonei per la riconciliazione, Campaign non invia un'e-mail. Campaign non può sapere quale sia l'ID e-mail corretto a meno che non venga acquisito e inviato da Analytics.
* Non puoi archiviare il contenuto del payload in Campaign. Gli attivatori non possono essere utilizzati per aggiornare i dati di un profilo.
* Gli attributi del cliente non sono supportati negli attivatori (cioè, solo i dati della suite di rapporti possono essere utilizzati per definire le regole aziendali di Triggers).
* La raccolta di raccolte non è supportata in Campaign.

>[!CAUTION]
>
>Il sito Web deve essere in esecuzione sullo stesso dominio del server Adobe Campaign. In caso contrario, non potete usare l’ID visitatore per riconciliare e raggiungere gli utenti che visitano il sito Web in modo anonimo.

