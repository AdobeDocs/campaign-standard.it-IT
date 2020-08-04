---
title: Casi di utilizzo degli attivatori di abbandono
description: Scopri come utilizzare l’integrazione di Experience Cloud Triggers con questi vari casi d’uso.
page-status-flag: never-activated
uuid: 9e236165-afd5-4155-9151-c1941dc0af99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: 1b9aeec5-70bb-4d72-a3e9-12342abf08f7
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '993'
ht-degree: 100%

---


# Casi di utilizzo degli attivatori di abbandono{#abandonment-triggers-use-cases}

Questa sezione presenta diversi casi d’uso che possono essere implementati utilizzando l’integrazione tra Adobe Campaign ed Experience Cloud Triggers. Sono disponibili due esempi di casi d’uso:

* [Attivatore di abbandono navigazione](#browse-abandonment-trigger): invia una comunicazione ai clienti che hanno abbandonato la visita del tuo sito web.
* [Attivatore di abbandono ricerca](#search-abandonment-trigger): coinvolgi nuovamente i visitatori che hanno effettuato una ricerca sul tuo sito web, ma che non hanno concluso un acquisto.

>[!NOTE]
>
>I casi d’uso descritti in questa sezione si basano sull’ID visitatore di Experience Cloud. È inoltre possibile implementarli con l’ID dichiarato di Experience Cloud. Sono supportati anche gli ID dichiarati crittografati e con hash. Puoi inviare e-mail/SMS a un profilo inesistente all’interno di Campaign semplicemente decrittografando l’indirizzo e-mail/numero di cellulare crittografato. In questo caso, tuttavia, non è possibile utilizzare la personalizzazione con i dati del profilo.

## Prerequisiti {#pre-requisites}

Per implementare questi casi d’uso, devi avere accesso alle seguenti soluzioni/servizi core:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servizio core Triggers di Experience Cloud
* Servizio core DTM di Experience Cloud
* ID visitatore di Experience Cloud e servizio core People di Experience Cloud

Devi anche disporre di un sito web funzionante.

Per ulteriori informazioni, consulta [Configurazione di soluzioni e servizi](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Attivatore di abbandono navigazione {#browse-abandonment-trigger}

In questo caso d’uso, creeremo un semplice trigger che verrà attivato ogni volta che un cliente abbandona una visita sul tuo sito web. Questo esempio presuppone che DTM stia già effettuando la raccolta e il push dei dati ad Adobe Analytics e che siano stati creati tutti gli eventi.

### Creazione di un trigger Experience Cloud {#creating-an-experience-cloud-trigger}

1. Seleziona **[!UICONTROL Manage Triggers]** dal menu del servizio core Activation di Experience Cloud.

   ![](assets/trigger_uc_browse_1.png)

1. Scegli un tipo di trigger ( **[!UICONTROL Abandonment]** nel nostro caso d’uso).

   ![](assets/trigger_uc_browse_2.png)

1. Per questo caso d’uso, abbiamo bisogno di un semplice attivatore di abbandono. Lo scopo aziendale è quello di identificare i visitatori che navigano nel nostro sito web di prenotazione viaggi, che guardano la pagina &quot;Offerte&quot; ma che non prenotano alcun viaggio. Una volta identificato questo pubblico, vogliamo raggiungerlo entro breve tempo. In questo esempio, scegliamo di inviare il trigger dopo 10 minuti.

   ![](assets/trigger_uc_browse_3.png)

### Utilizzo del trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign}

Ora che abbiamo creato un trigger Experience Cloud, lo utilizziamo all’interno di Adobe Campaign.

In Adobe Campaign, devi creare un trigger collegato a quello che hai creato in Experience Cloud.

1. Per creare il trigger all’interno di Adobe Campaign, fai clic sul logo **[!UICONTROL Adobe Campaign]**, nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Fai clic su **[!UICONTROL Create]**.
1. Seleziona il trigger creato in precedenza e fai clic su **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Scegli il canale **[!UICONTROL Email]** e la dimensione di targeting di **[!UICONTROL Real-time event]** e fai clic su **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. Pubblica il trigger su Adobe Campaign. Questo processo creerà automaticamente un modello di messaggio transazionale.

   ![](assets/trigger_uc_browse_6.png)

1. Per visualizzare il modello del messaggio, fai clic sul pulsante **[!UICONTROL More]** in alto a destra, quindi seleziona **[!UICONTROL Trigger Transactional Template]**.

1. Personalizza il contenuto e i dettagli del mittente.

   ![](assets/trigger_uc_browse_8.png)

1. Pubblica il modello di messaggio. Il trigger è ora attivo e funzionante.

   ![](assets/trigger_uc_browse_0.png)

### Esecuzione dello scenario {#running-the-scenario}

1. Questo caso d’uso inizia con un’e-mail iniziale inviata al tuo pubblico tramite Adobe Campaign.

   ![](assets/trigger_uc_browse_9.png)

1. Il destinatario apre il messaggio e-mail.

   ![](assets/trigger_uc_browse_10.png)

1. Fa clic su un collegamento, che lo porta al tuo sito web. In questo esempio, il banner conduce il destinatario alla pagina Home del tuo sito web di prenotazione di viaggi.

   ![](assets/trigger_uc_browse_11.png)

1. Il destinatario va alla pagina &quot;Offerte&quot;, ma improvvisamente interrompe la sua visita. Dopo 10 minuti, Adobe Campaign attiva l’invio del messaggio sulle transazioni.

   ![](assets/trigger_uc_browse_12.png)

1. Puoi controllare i registri di Experience Cloud in qualsiasi momento per vedere quante volte è stato attivato il trigger.

   ![](assets/trigger_uc_browse_13.png)

1. Puoi anche visualizzare il report del trigger di Adobe Campaign.

   ![](assets/trigger_uc_browse_14.png)

## Attivatore di abbandono ricerca {#search-abandonment-trigger}

In questo caso d’uso, creeremo un trigger per coinvolgere nuovamente i visitatori che sono andati sul nostro sito web di prenotazione viaggi, hanno cercato una destinazione, non hanno trovato risultati convincenti e non hanno effettuato alcuna prenotazione. Il processo generale è il medesimo del precedente caso d’uso (vedi [Attivatore di abbandono navigazione](#browse-abandonment-trigger)). Adesso ci concentreremo su come personalizzare il messaggio e-mail di remarketing.

### Creazione di un trigger Experience Cloud {#creating-an-experience-cloud-trigger-1}

Per creare il trigger di Experience Cloud, segui i passaggi descritti nel caso d’uso precedente. Consulta [Creazione di un trigger Experience Cloud](#creating-an-experience-cloud-trigger). La differenza principale è la definizione del trigger.

![](assets/trigger_uc_search_1.png)

La sezione **[!UICONTROL Include Meta Data]** ti consente di trasmettere al payload del trigger tutti i dati raccolti da Analytics. In questo esempio, creiamo una eVar personalizzata (ad esempio, eVar 3) per raccogliere il termine di ricerca immesso dal visitatore. Tale termine verrà quindi utilizzato nel messaggio e-mail sulle transazioni inviato allo stesso visitatore.

### Utilizzo del trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. Per creare il trigger in Adobe Campaign, segui i passaggi descritti nel caso d’uso precedente. Consulta [Utilizzo del trigger in Adobe Campaign](#using-the-trigger-in-adobe-campaign). La differenza principale sta nel modo in cui accediamo e utilizziamo all’interno di Adobe Campaign i metadati inviati nel payload del trigger.
1. Nell’attivatore di abbandono ricerca creato in Adobe Campaign, fai clic sull’icona **[!UICONTROL Event content and enrichment]** per visualizzare il payload inviato ad Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. Come puoi vedere, l’eVar personalizzata viene trasmessa al payload del trigger e mappata alla tabella **Contesto dell’evento (ctx)**. Ora possiamo accedervi per personalizzare il messaggio sulle transazioni.

   ![](assets/trigger_uc_search_3.png)

1. In questo esempio, scegliamo di includere il termine di ricerca di destinazione sia nella riga dell’oggetto che nel corpo dell’e-mail.

   ![](assets/trigger_uc_search_4.png)

1. Quando selezioni un campo personalizzato, cerca i metadati del payload nella tabella **Evento transazionale** (rtEvent), quindi nella tabella secondaria **Contesto evento** (ctx).

   ![](assets/trigger_uc_search_5.png)

### Esecuzione dello scenario {#running-the-scenario-1}

1. Il visitatore si dirige sul sito web di prenotazione viaggi e cerca una destinazione. In questo esempio, il visitatore sta cercando un viaggio in Giappone, ma non trova alcun risultato. È un’opportunità per raggiungere questo visitatore e consigliargli un piano di viaggio alternativo.

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >In questo caso d’uso, supponiamo che il visitatore/destinatario abbia già aperto e fatto clic su un’e-mail proveniente dallo stesso sito web. Ciò ci consente di utilizzare e raccogliere l’ID visitatore, per poi mapparlo al destinatario. Dobbiamo eseguire questa procedura solo una volta.

1. Pochi minuti dopo, lo stesso visitatore/destinatario riceve un messaggio di remarketing. Il messaggio include la destinazione ricercata di recente.

   ![](assets/trigger_uc_search_7.png)

