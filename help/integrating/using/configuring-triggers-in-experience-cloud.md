---
solution: Campaign Standard
product: campaign
title: Configurazione di Triggers in Experience Cloud
description: 'Scopri come configurare l’integrazione di Adobe Experience Cloud Triggers per iniziare a inviare consegne personalizzate ai clienti in base ai loro comportamenti precedenti. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '864'
ht-degree: 8%

---


# Configurazione di Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Attivazione della funzionalità {#activating-the-functionality}

La funzionalità deve essere attivata in Adobe Campaign per Adobe. Contatta il tuo responsabile dell&#39;account Adobe o un partner di servizi professionali.

Per attivare i trigger, il team di Adobe dovrà disporre delle seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione IMS
* Società di accesso di Analytics (può essere la stessa del nome dell’azienda del Marketing Cloud)

## Configurazione di soluzioni e servizi {#configuring-solutions-and-services}

Per utilizzare questa funzione, devi avere accesso alle seguenti soluzioni/servizi di base:

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
>La configurazione del sottodominio è un elemento chiave per il recapito messaggi. Assicurati che le e-mail di Adobe Campaign siano inviate dallo stesso dominio utilizzato dal sito web.

Devi configurare [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) e [Campaign](#configuring-triggers-and-aliases-in-campaign) per eseguire questi casi d’uso.

### Configurazione del servizio core DTM di Experience Cloud {#configuring-experience-cloud-dtm-core-service}

1. In Experience Cloud DTM Core Service (Dynamic Tag Management), attiva Experience Cloud ID e Adobe Analytics per le pagine del tuo sito web.

   ![](assets/trigger_uc_conf_1.png)

1. La riconciliazione degli ID tra il sito web, Adobe Analytics e Adobe Campaign richiede l’uso dell’aliasing. Crea un alias, ad esempio &quot;visitorid&quot;.

   ![](assets/trigger_uc_conf_2.png)

### Configurazione del servizio core People di Experience Cloud {#configuring-experience-cloud-people-core-service}

L’alias precedentemente indicato in DTM deve essere creato nel servizio core Persone di Experience Cloud tramite un attributo cliente. Assicurati di crearne uno nuovo e fai riferimento allo stesso alias DTM nel codice di integrazione (ad esempio &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Useremo questo attributo cliente nell&#39;origine dati in Adobe Campaign (passaggio successivo).

### Configurazione di trigger e alias in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Assicurati di avere **[!UICONTROL Experience Cloud triggers]** visibile sull&#39;istanza Adobe Campaign Standard. In caso contrario, contatta gli amministratori Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Gli alias consentono di riconciliare un contatto in Analytics con un profilo in Campaign. Devi far corrispondere gli alias definiti nel servizio Experience Cloud ID con un’origine dati condivisa in Campaign. Devi configurare la risoluzione degli alias in Adobe Campaign tramite un’origine dati ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Assicurati di scegliere l&#39;origine dati corretta nel menu a discesa **[!UICONTROL Data Source/Alias]**, che è mappato con la stessa origine dati Attributi cliente creata nel passaggio precedente.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puoi riconciliare i trigger per gli utenti anonimi e quelli registrati. Per gli utenti anonimi, il profilo dovrebbe esistere in Adobe Campaign e un messaggio e-mail è stato inviato all’utente in precedenza. A questo scopo, la configurazione dell’ID visitatore è sufficiente. Tuttavia, se desideri riconciliare i trigger per gli utenti connessi, devi impostare Declared ID Data Source. Per ulteriori informazioni, consulta [Configurazione origine dati](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creazione di un trigger nell’interfaccia Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

È necessario creare un trigger di Adobe Experience Cloud per poterlo utilizzare in Campaign.

Crea un nuovo trigger in Experience Cloud e assicurati di selezionare la suite di rapporti utilizzata sul sito web. Assicurati di scegliere la dimensione giusta in modo che l’attivatore si attivi.

Consulta la [documentazione Adobe Experience Cloud](https://docs.adobe.com/content/help/it-IT/core-services/interface/activation/triggers.html) e guarda questo [video](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two).

## Best practice e limitazioni dei trigger {#triggers-best-practices-and-limitations}

Elenco delle best practice e limitazioni per l’utilizzo dell’integrazione Campaign - Triggers:

* Se disponi di più istanze di Campaign Standard, i trigger possono essere ricevuti da tutte le istanze purché si trovino nello stesso ID organizzazione IMS. Anche Analytics deve trovarsi nello stesso ID organizzazione IMS.
* Non puoi creare un trigger nel servizio core Trigger utilizzando eventi provenienti da due suite di rapporti diverse.
* I trigger si basano sui messaggi transazionali. I messaggi transazionali vengono utilizzati ogni volta che devi inviare un messaggio molto rapidamente. Non è possibile mettere in coda i messaggi transazionali e quindi eseguirne il ciclo in batch.
* Gli attivatori non sono deterministici in natura. Quando viene generato un trigger, invia tutti gli alias associati al cookie, quindi nel caso di browser condivisi come nei chioschi di vendita al dettaglio, nelle librerie, nei cyber caffè o nei dispositivi condivisi a casa (marito e moglie che accedono dallo stesso dispositivo) non è possibile eseguire la mappatura all’ID corretto. Tutti gli ID utilizzati per accedere con il browser vengono inviati a Campaign che invia un messaggio in base alla prima riconciliazione. Se sono presenti più &quot;ID e-mail&quot; idonei per la riconciliazione, Campaign non invia un’e-mail. Campaign può sapere in che modo si trova l’ID e-mail corretto solo se viene acquisito e inviato da Analytics.
* Non puoi archiviare il contenuto del payload in Campaign. I trigger non possono essere utilizzati per aggiornare i dati di un profilo.
* Gli attributi del cliente non sono supportati in Triggers (significa che solo i dati della suite di rapporti possono essere utilizzati per definire le regole di business di Triggers).
* La raccolta di raccolte non è supportata in Campaign.

>[!CAUTION]
>
>Il sito web deve essere in esecuzione sullo stesso dominio del server Adobe Campaign. In caso contrario, non puoi utilizzare l’id visitatore per riconciliare e raggiungere gli utenti che visitano il sito web in modo anonimo.

