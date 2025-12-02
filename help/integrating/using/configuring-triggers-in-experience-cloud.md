---
title: Configurazione di Triggers in Experience Cloud
description: Scopri come configurare l’integrazione Adobe Experience Cloud Triggers per iniziare a inviare consegne personalizzate ai clienti in base ai loro comportamenti precedenti.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 6%

---

# Configurazione di Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Attivazione della funzionalità {#activating-the-functionality}

La funzionalità deve essere attivata in Adobe Campaign da Adobe. Contatta il responsabile dell’account Adobe o un partner di servizi professionali.

Per attivare i trigger, il team di Adobe avrà bisogno delle seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione 
* Società di accesso ad Analytics (può essere la stessa del nome della società Marketing Cloud)

## Configurazione di soluzioni e servizi {#configuring-solutions-and-services}

Per utilizzare questa funzione, devi avere accesso alle seguenti soluzioni/servizi core:

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
>La configurazione del sottodominio è un elemento chiave del recapito messaggi. Assicurati che le e-mail di Adobe Campaign siano inviate dallo stesso dominio utilizzato dal sito web.

Devi configurare [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) e [Campaign](#configuring-triggers-and-aliases-in-campaign) per eseguire questi casi d&#39;uso.

### Configurazione del servizio core DTM di Experience Cloud {#configuring-experience-cloud-dtm-core-service}

1. Nel servizio core DTM di Experience Cloud (Dynamic Tag Management), attiva Experience Cloud ID e Adobe Analytics per le pagine del tuo sito web.

   ![](assets/trigger_uc_conf_1.png)

1. La riconciliazione degli ID tra il sito web, Adobe Analytics e Adobe Campaign richiede l’utilizzo dell’alias. Crea un alias, ad esempio &quot;visitorid&quot;.

   ![](assets/trigger_uc_conf_2.png)

### Configurazione del servizio core People di Experience Cloud {#configuring-experience-cloud-people-core-service}

L’alias a cui si fa riferimento in precedenza in DTM deve essere creato nel servizio core People di Experience Cloud tramite un attributo del cliente. Assicurati di crearne uno nuovo e di fare riferimento allo stesso alias DTM nel codice di integrazione (ad esempio &quot;visitorid&quot;).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Questo attributo cliente verrà utilizzato nell’origine dati in Adobe Campaign (passaggio successivo).

### Configurazione di trigger e alias in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Verifica che **[!UICONTROL Experience Cloud triggers]** sia visibile nell&#39;istanza Adobe Campaign Standard. In caso contrario, contatta gli amministratori di Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Gli alias consentono di riconciliare un contatto in Analytics con un profilo in Campaign. Devi far corrispondere gli alias definiti nel servizio Experience Cloud ID con un Source di dati condivisi in Campaign. È necessario configurare la risoluzione degli alias in Adobe Campaign tramite un&#39;origine dati ( **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Shared Data Sources]** ). Accertarsi di scegliere l&#39;origine dati corretta nel menu a discesa **[!UICONTROL Data Source/Alias]**, mappato con la stessa origine dati Attributi del cliente creata nel passaggio precedente.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puoi riconciliare i trigger per gli utenti anonimi e per quelli connessi. Per gli utenti anonimi, il profilo deve esistere in Adobe Campaign e un’e-mail è stata inviata prima all’utente. Per questo, è sufficiente la configurazione dell’ID visitatore. Tuttavia, se desideri riconciliare i trigger per gli utenti connessi, devi impostare Declared ID Data Source. Per ulteriori informazioni, consulta [Configurazione di Data Source](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creazione di un trigger nell’interfaccia di Experience Cloud {#creating-a-trigger-in-the-experience-cloud-interface}

È necessario creare un trigger di Adobe Experience Cloud per poterlo utilizzare in Campaign.

Crea un nuovo trigger in Experience Cloud e accertati di selezionare la suite di rapporti utilizzata sul tuo sito web. Assicurati di scegliere la dimensione giusta in modo che il trigger si attivi.

Consulta la [documentazione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html).

## Best practice e limitazioni relative agli attivatori {#triggers-best-practices-and-limitations}

Elenco delle best practice e limitazioni per l’utilizzo dell’integrazione Campaign - Triggers:

* Se disponi di più istanze di Campaign Standard, i trigger possono essere ricevuti da tutte le istanze purché si trovino nella stessa organizzazione. Anche Analytics deve appartenere alla stessa organizzazione.
* Non puoi creare un trigger nel servizio core Trigger utilizzando eventi di due suite di rapporti diverse.
* Gli attivatori si basano su messaggi transazionali. I messaggi transazionali vengono utilizzati ogni volta che devi inviare un messaggio molto rapidamente. Non è possibile mettere in coda i messaggi transazionali e quindi eseguirne il ciclo in batch.
* Gli attivatori non sono di natura deterministica. Quando viene generato un trigger, vengono inviati tutti gli alias associati al cookie. Pertanto, nel caso di browser condivisi, ad esempio nei chioschi di vendita al dettaglio, nelle librerie, nei cyber café o nei dispositivi condivisi a casa (marito e moglie accedono dallo stesso dispositivo), non è possibile eseguire la mappatura sull’ID corretto. Tutti gli ID utilizzati per accedere con il browser vengono inviati a Campaign, che invia un messaggio in base alla prima riconciliazione. Se esistono più &quot;ID e-mail&quot; idonei per la riconciliazione, Campaign non invia un’e-mail. Campaign non può sapere quale sia l’ID e-mail corretto a meno che non venga acquisito e inviato da Analytics.
* Non è possibile memorizzare il contenuto del payload in Campaign. Gli attivatori non possono essere utilizzati per aggiornare i dati di un profilo.
* Gli attributi del cliente non sono supportati in Triggers (ovvero, per definire le regole aziendali Triggers è possibile utilizzare solo i dati della suite di rapporti).
* La raccolta di raccolte non è supportata in Campaign.

>[!CAUTION]
>
>Il sito web deve essere in esecuzione sullo stesso dominio del server Adobe Campaign. In caso contrario, non puoi utilizzare l’ID visitatore per riconciliare e raggiungere gli utenti che visitano il sito web in modo anonimo.
