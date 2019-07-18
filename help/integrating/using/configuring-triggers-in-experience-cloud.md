---
title: Configurazione degli attivatori in Experience Cloud
seo-title: Configurazione degli attivatori in Experience Cloud
description: Configurazione degli attivatori in Experience Cloud
seo-description: 'Scopri come configurare l''integrazione di Adobe Experience Cloud Triggers per iniziare a inviare consegne personalizzate ai clienti in base ai comportamenti precedenti. '
page-status-flag: never-activated
uuid: 8 fd 7 b 804-9528-46 a 5-a 060-bf 16 b 8 dc 555 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-triggers
discoiquuid: 4163 dc 0 c -8103-4425-b 8 bf -7 aa 45 c 4 d 3 a 06
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring Triggers in Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activating the functionality {#activating-the-functionality}

La funzionalità deve essere attivata in Adobe Campaign da Adobe. Contattate il vostro partner di servizi Adobe o Executive Manager.

Il team Adobe avrà bisogno delle seguenti informazioni per attivare attivatori:

* Nome società Marketing Cloud
* ID organizzazione IMS
* Analytics Login Company (può essere uguale al Nome società di Marketing Cloud)

## Configuring solutions and services {#configuring-solutions-and-services}

Per utilizzare questa funzione, devi avere accesso alle soluzioni/servizi di base seguenti:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servizio core Experience Cloud Triggers

   ![](assets/trigger_uc_prereq_1.png)

* Servizio di base di Experience Cloud DTM

   ![](assets/trigger_uc_prereq_2.png)

* Servizio di base Experience Cloud ID e servizio di base Persone Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

È inoltre necessario disporre di un sito Web funzionante.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La delega sottodominio è un elemento chiave di consegna. Accertatevi che le e-mail di Adobe Campaign vengano inviate dallo stesso dominio usato dal sito Web.

You need to configure [Experience Cloud DTM Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-experience-cloud-people-core-service) and [Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-triggers-and-aliases-in-campaign) to run these use cases.

### Configuring Experience Cloud DTM Core Service {#configuring-experience-cloud-dtm-core-service}

1. In Experience Cloud DTM Core Service (Gestione tag dinamica), attiva Experience Cloud ID e Adobe Analytics per le pagine del tuo sito Web.

   ![](assets/trigger_uc_conf_1.png)

1. La riconciliazione degli ID tra il sito Web, Adobe Analytics e Adobe Campaign richiedono l'utilizzo di alias. Create un alias, ad esempio «visitorid».

   ![](assets/trigger_uc_conf_2.png)

### Configuring Experience Cloud People Core Service {#configuring-experience-cloud-people-core-service}

L'alias a cui fa riferimento in precedenza DTM deve essere creato nel servizio core Persone Experience Cloud tramite un attributo cliente. Assicuratevi di crearne uno nuovo e di fare riferimento allo stesso alias DTM nel codice di integrazione (ad esempio "visitorid").

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Useremo questo attributo cliente nell'origine dati in Adobe Campaign (passaggio successivo).

### Configuring triggers and aliases in Campaign {#configuring-triggers-and-aliases-in-campaign}

1. Make sure you have **[!UICONTROL Experience Cloud triggers]** visible on your Adobe Campaign Standard instance. In caso contrario, contatta gli amministratori di Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Alias consente di riconciliare un contatto in Analytics con un profilo in Campaign. Devi corrispondere agli alias definiti nel servizio Experience Cloud ID con un'origine dati condivisa in Campaign. You need to configure the aliases resolution in Adobe Campaign via a Data source ( **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Shared Data Sources]** ). Make sure you choose the correct data source in the **[!UICONTROL Data Source/Alias]** drop-down menu, which is mapped with the same Customer Attribute data source created in previous step.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Puoi riconciliare i trigger sia per gli utenti anonimi che per quelli registrati. Per gli utenti anonimi, il profilo dovrebbe esistere in Adobe Campaign ed è stato inviato un messaggio e-mail all'utente prima. Per questa ragione, la configurazione ID visitatore è sufficiente. Tuttavia, se desiderate riconciliare gli attivatori per gli utenti registrati, dovete impostare l'origine dati ID dichiarata. For more on this, refer to [Data Source configuration](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Creating a trigger in the Experience Cloud interface {#creating-a-trigger-in-the-experience-cloud-interface}

È necessario creare un attivatore Adobe Experience Cloud per utilizzarlo in Campaign.

Crea un nuovo trigger in Experience Cloud e assicurati di selezionare la suite di rapporti utilizzata nel tuo sito Web. Accertatevi di scegliere la dimensione corretta per attivare l'attivatore.

Refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html) and watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

## Triggers best practices and limitations {#triggers-best-practices-and-limitations}

Elenco delle best practice e delle limitazioni per l'utilizzo dell'integrazione Campaign - Triggers:

* Se disponete di più istanze di Campaign Standard, le attivazioni possono essere ricevute da tutte le istanze purché siano nello stesso ID organizzazione IMS. Analytics deve anche avere lo stesso ID organizzazione IMS.
* Non è possibile creare un trigger nel servizio di base attivatore utilizzando gli eventi provenienti da due suite di rapporti diverse.
* Gli attivatori si basano sui messaggi transazionali. I messaggi transazionali vengono utilizzati ogni volta che devi inviare un messaggio molto rapidamente. Non potete mettere in coda i messaggi transazionali, quindi ripeterli in batch.
* Gli attivatori non sono deterministici. Quando viene generato un trigger, invia tutti gli alias associati al cookie, quindi nel caso di browser condivisi quali chioschi, librerie, cyber cafes o dispositivi condivisi in casa (marito e moglie accedendo allo stesso dispositivo), non è possibile mappare sull'ID corretto. Tutti gli ID utilizzati per accedere con il browser vengono inviati a Campaign, che invia un messaggio in base alla prima riconciliazione. Se sono disponibili più "ID e-mail" per la riconciliazione, Campaign non invia un messaggio e-mail. Non esiste alcun modo per stabilire quale sia l'ID e-mail corretto a meno che non venga acquisito e inviato da Analytics.
* Non potete memorizzare il contenuto del payload in Campaign. Gli attivatori non possono essere utilizzati per aggiornare i dati di un profilo.
* Gli attributi del cliente non sono supportati in Triggers (cioè, solo i dati della suite di rapporti possono essere utilizzati per definire le regole aziendali attivatori).
* La raccolta di raccolte non è supportata in Campaign.

>[!CAUTION]
>
>Il tuo sito Web deve essere in esecuzione sullo stesso dominio del server Adobe Campaign. In caso contrario, non potete utilizzare ID visitatore per riconciliare e rivolgervi agli utenti che visitano il sito Web in modo anonimo.

