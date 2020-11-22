---
solution: Campaign Standard
product: campaign
title: Configurazione di Triggers in Experience Cloud
description: 'Scopri come configurare l’integrazione di Adobe Experience Cloud Triggers per iniziare a inviare consegne personalizzate ai clienti in base ai comportamenti precedenti. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 8%

---


# Configurazione di Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Attivazione della funzionalità {#activating-the-functionality}

La funzionalità deve essere attivata in  Adobe Campaign  Adobe. Contatta il tuo  responsabile commerciale di Adobe o il partner di servizi professionali.

Per attivare i trigger, il team del Adobe  avrà bisogno delle seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione IMS
* Società di accesso Analytics (può corrispondere al Nome società Marketing Cloud)

## Configurazione di soluzioni e servizi {#configuring-solutions-and-services}

Per utilizzare questa funzione, è necessario avere accesso alle soluzioni/ai servizi di base seguenti:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servizio core Triggers di Experience Cloud

   ![](assets/trigger_uc_prereq_1.png)

* Servizio core DTM di Experience Cloud

   ![](assets/trigger_uc_prereq_2.png)

* ID visitatore di Experience Cloud e servizio core People di Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

Devi anche disporre di un sito web funzionante.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La configurazione del sottodominio è un elemento chiave di recapito. Accertatevi che i messaggi e-mail di  Adobe Campaign vengano inviati dallo stesso dominio utilizzato dal sito Web.

Devi configurare [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) e [Campaign](#configuring-triggers-and-aliases-in-campaign) per eseguire questi casi di utilizzo.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. In  Experience Cloud DTM Core Service (Gestione tag dinamica), attivate  ID Experience Cloud e  Adobe Analytics per le pagine del sito Web.

   ![](assets/trigger_uc_conf_1.png)

1. La riconciliazione degli ID tra il sito Web,  Adobe Analytics e  Adobe Campaign richiede l’uso dell’aliasing. Create un alias, ad esempio &quot;visitorid&quot;.

   ![](assets/trigger_uc_conf_2.png)

### Configurazione  servizio di base Persone Experienci Cloud {#configuring-experience-cloud-people-core-service}

È necessario creare l&#39;alias precedentemente indicato in Gestione dinamica dei tag nel servizio core Persone del Experience Cloud  tramite un attributo cliente. Accertatevi di crearne uno nuovo e fate riferimento allo stesso alias DTM nel codice di integrazione (ad esempio &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Utilizzeremo questo attributo cliente nell&#39;origine dati in  Adobe Campaign (passaggio successivo).

### Configurazione di attivatori e alias in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Accertatevi di essere **[!UICONTROL Experience Cloud triggers]** visibili nell’istanza di Adobe Campaign Standard . In caso contrario, contattate gli amministratori  Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Gli alias consentono di riconciliare un contatto in Analytics con un profilo in Campaign. Devi far corrispondere gli alias definiti nel servizio ID Experience Cloud  con un&#39;origine dati condivisa in Campaign. Devi configurare la risoluzione degli alias in  Adobe Campaign tramite un&#39;origine dati ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Accertatevi di scegliere l&#39;origine dati corretta nel menu a **[!UICONTROL Data Source/Alias]** discesa, mappato con la stessa origine dati Attributo cliente creata nel passaggio precedente.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puoi riconciliare le attivazioni per utenti anonimi e con accesso. Per gli utenti anonimi, il profilo dovrebbe esistere in  Adobe Campaign ed è già stato inviato un messaggio e-mail all&#39;utente. A tal fine, la configurazione ID visitatore è sufficiente. Tuttavia, se vuoi riconciliare gli attivatori per gli utenti connessi, devi impostare l’origine dati ID dichiarato. Per ulteriori informazioni, consulta Configurazione [origine](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)dati.

## Creazione di un trigger nell&#39;interfaccia del Experience Cloud  {#creating-a-trigger-in-the-experience-cloud-interface}

È necessario creare un attivatore Adobe Experience Cloud per poterlo utilizzare in Campaign.

Crea un nuovo attivatore in  Experience Cloud e accertati di selezionare la suite di rapporti utilizzata nel sito Web. Accertatevi di scegliere la dimensione corretta in modo che l&#39;attivatore venga attivato.

Fate riferimento alla documentazione [di](https://docs.adobe.com/content/help/it-IT/core-services/interface/activation/triggers.html) Adobe Experience Cloud e guardate questo [video](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two).

## Attiva procedure ottimali e limitazioni {#triggers-best-practices-and-limitations}

Elenco delle procedure ottimali e dei limiti per l&#39;utilizzo dell&#39;integrazione Campaign - Triggers:

* Se disponete di più istanze di Campaign Standard, le attivazioni possono essere ricevute da tutte le istanze purché si trovino nello stesso ID organizzazione IMS. Analytics deve inoltre trovarsi sullo stesso ID organizzazione IMS.
* Non è possibile creare un trigger nel servizio di base Trigger utilizzando eventi di due suite di rapporti diverse.
* Gli attivatori si basano sui messaggi transazionali. I messaggi transazionali vengono utilizzati ogni volta che è necessario inviare un messaggio molto rapidamente. Non è possibile mettere in coda i messaggi transazionali e quindi eseguirne il ciclo in batch.
* Gli attivatori non sono deterministici in natura. Quando viene generato un trigger, invia tutti gli alias associati al cookie, pertanto nel caso di browser condivisi come nei chioschi di vendita al dettaglio, nelle librerie, nei cyber-caffè o nei dispositivi condivisi a casa (accesso di marito e moglie dallo stesso dispositivo), non è possibile mappare l&#39;ID corretto. Tutti gli ID utilizzati per accedere con il browser vengono inviati a Campaign, che invia un messaggio in base alla prima riconciliazione. Se sono presenti più &quot;ID e-mail&quot; idonei per la riconciliazione, Campaign non invia un&#39;e-mail. Campaign non può sapere quale sia l&#39;ID e-mail corretto a meno che non venga acquisito e inviato da Analytics.
* Non puoi archiviare il contenuto del payload in Campaign. Gli attivatori non possono essere utilizzati per aggiornare i dati di un profilo.
* Gli attributi del cliente non sono supportati negli attivatori (cioè, solo i dati della suite di rapporti possono essere utilizzati per definire le regole aziendali di Triggers).
* La raccolta di raccolte non è supportata in Campaign.

>[!CAUTION]
>
>Il sito Web deve essere in esecuzione sullo stesso dominio del server Adobe Campaign . In caso contrario, non potete usare l’ID visitatore per riconciliare e raggiungere gli utenti che visitano il sito Web in modo anonimo.

