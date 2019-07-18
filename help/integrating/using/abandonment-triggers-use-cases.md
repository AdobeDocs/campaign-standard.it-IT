---
title: Casi d'abbandono attivatori
seo-title: Casi d'abbandono attivatori
description: Casi d'abbandono attivatori
seo-description: Scopri come utilizzare l'integrazione di Experience Cloud Triggers con questi casi d'uso diversi.
page-status-flag: never-activated
uuid: 9 e 236165-afd 5-4155-9151-c 1941 dc 0 af 99
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-triggers
discoiquuid: 1 b 9 aeec 5-70 bb -4 d 72-a 3 e 9-12342 abf 08 f 7
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Abandonment Triggers use cases{#abandonment-triggers-use-cases}

Questa sezione presenta casi d'uso diversi che possono essere implementati mediante l'integrazione tra Adobe Campaign e Experience Cloud Triggers. Sono disponibili due esempi di casi d'uso:

* [Sfoglia attivatore di abbandono](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger): inviare una comunicazione ai clienti che hanno abbandonato la visita sul tuo sito Web.
* [Trigger di abbandono della ricerca](../../integrating/using/abandonment-triggers-use-cases.md#search-abandonment-trigger): riutilizzarsi con i visitatori che hanno eseguito una ricerca sul tuo sito Web, ma non hanno effettuato un acquisto.

>[!NOTE]
>
>I casi di utilizzo descritti in questa sezione si basano sull'ID visitatore di Experience Cloud. È inoltre possibile implementarle con l'ID dichiarato di Experience Cloud. Sono inoltre supportati gli ID dichiarati con hash e crittografati. Puoi inviare e-mail/SMS a un profilo che non esiste in Campaign, decrittografando direttamente l'indirizzo e-mail o il numero di telefono crittografati. In questo caso, non è possibile utilizzare la personalizzazione utilizzando i dati del profilo.

## Pre-requisites {#pre-requisites}

Per implementare questi casi di utilizzo, devi avere accesso alle soluzioni/servizi di base seguenti:

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Mobile Apps, Select o Standard.
* Servizio core Experience Cloud Triggers
* Servizio di base di Experience Cloud DTM
* Servizio di base Experience Cloud ID e servizio di base Persone Experience Cloud

È inoltre necessario disporre di un sito Web funzionante.

For more information, refer to [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services).

## Browse abandonment Trigger {#browse-abandonment-trigger}

In questo caso d'uso, creeremo un semplice trigger che verrà attivato ogni volta che un cliente abbandona una visita sul sito Web. Questo esempio presuppone che sia già presente Gestione dinamica dei tag e che sia necessario inviare dati ad Adobe Analytics e tutti gli eventi creati.

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger}

1. Select **[!UICONTROL Manage Triggers]** from the Experience Cloud Activation Core Service menu.

   ![](assets/trigger_uc_browse_1.png)

1. Choose a trigger type ( **[!UICONTROL Abandonment]** in our use case).

   ![](assets/trigger_uc_browse_2.png)

1. Per questo caso d'uso, è necessario un semplice trigger di abbandono. Lo scopo di business è identificare i visitatori che sfogliano il nostro sito Web di prenotazione, guardare la pagina «Trattative» ma non prenotare alcun viaggio. Una volta identificato questo pubblico, desideriamo riutilizzarlo entro un breve periodo di tempo. In questo esempio, scegliiamo di inviare il trigger dopo un periodo di 10 minuti.

   ![](assets/trigger_uc_browse_3.png)

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign}

Ora che hai creato un attivatore Experience Cloud, utilizziamolo in Adobe Campaign.

In Adobe Campaign, devi creare un trigger collegato a quello creato in Experience Cloud.

1. To create the Trigger in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud triggers]**.

   ![](assets/remarketing_1.png)

1. Click **[!UICONTROL Create]**.
1. Select the Trigger you created earlier and click **[!UICONTROL Next]**.

   ![](assets/trigger_uc_browse_5.png)

1. Select the **[!UICONTROL Email]** channel and the **[!UICONTROL Real-time event]** targeting dimension and click **[!UICONTROL Create]**.

   ![](assets/trigger_uc_browse_6bis.png)

1. Pubblicate il trigger in Adobe Campaign. Questo processo crea automaticamente un modello di messaggio transazionale.

   ![](assets/trigger_uc_browse_6.png)

1. To dislay the message template, click the **[!UICONTROL More]** button, on the top right, then click **[!UICONTROL Trigger Transactional Template]**.
1. Personalizzate i suoi dettagli sul contenuto e sul mittente.

   ![](assets/trigger_uc_browse_8.png)

1. Pubblicate il modello di messaggio. Il trigger ora è live e funzionante.

   ![](assets/trigger_uc_browse_0.png)

### Running the scenario {#running-the-scenario}

1. Questo caso d'uso inizia con un'e-mail iniziale inviata al pubblico con Adobe Campaign.

   ![](assets/trigger_uc_browse_9.png)

1. Il destinatario apre il messaggio e-mail.

   ![](assets/trigger_uc_browse_10.png)

1. Fa clic su un collegamento che lo porta al sito Web. In questo esempio, il banner porta il destinatario nella home page del sito Web che esegue la prenotazione.

   ![](assets/trigger_uc_browse_11.png)

1. Il destinatario passa alla pagina «Topics», ma improvvisamente interrompe la visita. Dopo un periodo di 10 minuti, Adobe Campaign attiva l'invio del messaggio transazionale.

   ![](assets/trigger_uc_browse_12.png)

1. In qualsiasi momento, puoi controllare i registri di Experience Cloud per vedere quante volte è stato attivato il trigger.

   ![](assets/trigger_uc_browse_13.png)

1. Puoi anche visualizzare il rapporto Attivatore Adobe Campaign.

   ![](assets/trigger_uc_browse_14.png)

## Search abandonment Trigger {#search-abandonment-trigger}

In questo caso d'uso, creeremo un trigger per coinvolgere nuovamente i visitatori che hanno visitato il nostro sito Web dedicato alla prenotazione, la ricerca di una destinazione, nessun risultato riuscito e l'assenza di un libro in seguito. The general process is the same as in the previous use case (see [Browse abandonment Trigger](../../integrating/using/abandonment-triggers-use-cases.md#browse-abandonment-trigger)). Ci concentreremo su come personalizzare il messaggio e-mail di remarketing.

### Creating an Experience Cloud Trigger {#creating-an-experience-cloud-trigger-1}

Segui i passaggi descritti nel precedente caso d'uso per creare Experience Cloud Triggers. See [Creating an Experience Cloud Trigger](../../integrating/using/abandonment-triggers-use-cases.md#creating-an-experience-cloud-trigger). La differenza principale è la definizione del trigger.

![](assets/trigger_uc_search_1.png)

The **[!UICONTROL Include Meta Data]** section allows you to pass any data collected from Analytics to the Trigger payload. In questo esempio, creeremo un evar personalizzato (ad esempio, evar 3) per raccogliere il termine di ricerca immesso dal visitatore. Questo termine verrà quindi usato nel messaggio e-mail transazionali inviato allo stesso visitatore.

### Using the trigger in Adobe Campaign {#using-the-trigger-in-adobe-campaign-1}

1. Segui i passaggi descritti nel precedente caso d'uso per creare il trigger in Adobe Campaign. See [Using the trigger in Adobe Campaign](../../integrating/using/abandonment-triggers-use-cases.md#using-the-trigger-in-adobe-campaign). La differenza principale è la modalità di accesso e utilizzo, in Adobe Campaign, i metadati push inviati nel payload Attivatore.
1. In the Search Abandonment trigger you created in Adobe Campaign, click on the **[!UICONTROL Event content and enrichment]** icon to view the payload pushed to Adobe Campaign.

   ![](assets/trigger_uc_search_2.png)

1. As you can see, the custom eVar is passed in the Trigger payload and mapped to the **Event Context** table (ctx). Ora possiamo accedervi per personalizzare il messaggio transazionale.

   ![](assets/trigger_uc_search_3.png)

1. In questo esempio, scegliiamo di includere il termine di ricerca di destinazione nella riga dell'oggetto e nel corpo dell'e-mail.

   ![](assets/trigger_uc_search_4.png)

1. When selecting a personalized field, look for your payload meta data in the **Transactional event** (rtEvent) table then in the **Event context** (ctx) sub table.

   ![](assets/trigger_uc_search_5.png)

### Running the scenario {#running-the-scenario-1}

1. Il visitatore accede al sito Web di prenotazione e cerca una destinazione. In questo esempio, il visitatore cerca un viaggio in Giappone ma non ottiene alcun risultato. Questa è l'opportunità per contattare il visitatore e raccomandare un piano di viaggio alternativo.

   ![](assets/trigger_uc_search_6.png)

   >[!NOTE]
   >
   >In questo caso d'uso, si presuppone che il visitatore/il destinatario abbia già aperto e fatto clic su un'e-mail proveniente dallo stesso sito Web. Questo consente di utilizzare e raccogliere visitorid e di mapparlo sul destinatario. Dobbiamo farlo solo una volta.

1. Alcuni istanti, lo stesso visitatore/destinatario riceve un messaggio di remarketing. Il messaggio include la destinazione di ricerca di recente.

   ![](assets/trigger_uc_search_7.png)

