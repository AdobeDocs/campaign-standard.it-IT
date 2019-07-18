---
title: Regole di affaticamento
seo-title: Regole di affaticamento
description: Regole di affaticamento
seo-description: Crea regole di affaticamento per gestire la comunicazione con i profili.
page-status-flag: never-activated
uuid: fa 5 e 3 ded -36 c 2-4 f 16-b 97 a -119 b 85 adf 679
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: working-with-typology-rules
discoiquuid: 4337 a 80 b -0 fb 9-4 a 37-postal 3-fe 2121 a 66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Fatigue rules{#fatigue-rules}

## About fatigue rules {#about-fatigue-rules}

Le regole di affaticamento consentono agli esperti di marketing di impostare regole aziendali multicanale globali che escluderanno automaticamente i profili superflui dalle campagne.

Per implementare le regole di affaticamento, definite un numero massimo di messaggi per profilo e selezionate un periodo in cui applicare la regola. Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di messaggi già inviati.

>[!NOTE]
>
>Per applicare le regole di affaticamento, è necessario definire una data di contatto per la consegna. Se scegli di inviare subito i messaggi, la regola di affaticamento non verrà applicata.

Argomenti correlati:

* [Preparazione](../../administration/using/configuring-email-channel.md#preparation)
* [Gestione di tipologie](../../administration/using/about-typology-rules.md#managing-typologies)
* [Regole per i tipi di telefono](../../administration/using/about-typology-rules.md#typology-rules)

## Creating a fatigue rule {#creating-a-fatigue-rule}

To create and configure a **[!UICONTROL Fatigue]** typology rule, apply the following steps:

1. Click the Adobe Campaign logo, in the top left corner of the interface, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. From the list of typology rules, click **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. In the **[!UICONTROL Rule type]** field, select **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. In the **[!UICONTROL Channel]** field, select which channel your rule will apply to. You can either select a single channel (email, SMS, direct mail, mobile application) or select **[!UICONTROL All channels]**. See [Choosing the channel](../../administration/using/fatigue-rules.md#choosing-the-channel).

   ![](assets/fatigue5.png)

1. In the **[!UICONTROL General]** tab, define the method for calculating the maximum number of messages per profile. Potete scegliere una soglia costante o una variabile. Puoi anche definire la soglia per i profili e le consegne. For more on this, refer to [Defining the threshold](../../administration/using/fatigue-rules.md#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Choose a **[!UICONTROL Sliding period]** on which the typology rule will apply. For more on this, refer to [Setting the sliding period](../../administration/using/fatigue-rules.md#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   In questo esempio (vedere le videate precedenti), scegliamo di inviare un numero massimo di 4 messaggi in un periodo di 15 giorni.

1. In the **[!UICONTROL Application criteria]** tab, you can choose to apply this rule to all deliveries or restrict the applicability of the rule according to the message to send. La regola viene eseguita solo se la condizione dell'applicazione è soddisfatta. Ad esempio, è possibile applicare la regola solo sui messaggi con un'etichetta che inizia con una determinata parola o con un ID che contiene determinate lettere. See [Restricting the applicability of a filtering rule](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. Select the **[!UICONTROL Typologies]** tab and link your typology rule to the typology used for your deliveries. See [Managing typologies](../../administration/using/about-typology-rules.md#managing-typologies) and [Typology rules](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La tipologia può essere definita nel modello di consegna, da applicare automaticamente a tutte le consegne create con questo modello.

Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, in base al numero di consegne già inviate. Potete visualizzare i risultati dell'esecuzione della regola fatigue nei registri di consegna. See [Viewing the fatigue results](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results).

![](assets/fatigue16.png)

>[!CAUTION]
>
>Affinché le regole di affaticamento funzionino, è necessario definire una data di contatto per la distribuzione. Se scegli di inviare subito i messaggi, la regola di affaticamento non verrà applicata.

## Choosing the channel {#choosing-the-channel}

Sono disponibili regole di affaticamento per diversi canali. The channel is defined in the **[!UICONTROL Channel]** field of the typology rule settings. You can either select a single channel or select **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**Canali disponibili**

Sono disponibili i seguenti canali:

* E-mail
* Mobile (SMS)
* Posta diretta
* Applicazione mobile: questo canale consente di inviare notifiche push ai profili o agli abbonati di app. Se scegli di inviare notifiche ai profili, saranno compatibili con le regole di affaticamento multicanale.

   >[!CAUTION]
   >
   >Le regole di fatigue non sono compatibili con le notifiche push inviate agli abbonati all'app. Se invii messaggi agli abbonati di app, le regole di affaticamento non verranno applicate.

* Tutti i canali: questa opzione consente di applicare la regola a tutti i canali. Ad esempio, puoi decidere di inviare un massimo di 3 messaggi al mese su qualsiasi canale. Se avete inviato 2 e-mail a un profilo ultima settimana e provate a inviare una notifica push oggi, lo stesso profilo verrà escluso.

**Tipi di consegna**

Le regole di affaticamento sono compatibili con tutti i tipi di consegna: consegne una tantum, consegne ricorrenti, consegne di flussi di lavoro e messaggi transazionali.

**I messaggi transazionali** possono essere utilizzati per inviare messaggi del servizio mirati a un evento (rtevent) nonché ai messaggi di marketing (profili di targeting), ad esempio un messaggio di remarketing. Le regole di fatigue sono compatibili solo con i messaggi di marketing (profili di targeting). I messaggi transazionali degli eventi non contengono informazioni sul profilo, pertanto non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con profili). With the support of marketing messages in transactional messaging, you can **apply a fatigue rule to all channels including marketing transactional messages**.

## Defining the threshold {#defining-the-threshold}

Ogni regola di affaticamento definisce una soglia, ovvero il numero massimo di messaggi che possono essere inviati a un profilo in un determinato periodo. Una volta raggiunta questa soglia, non sarà più possibile eseguire consegne fino alla fine del periodo considerato. Questo processo consente di escludere automaticamente un profilo da una consegna se un messaggio supera la soglia del set, evitando così eccessiva precauzione.

I valori di soglia possono essere costanti o variabili. Ciò significa che, per un determinato periodo, le soglie possono variare da un profilo all'altro, o addirittura per lo stesso profilo.

**Utilizzo di una soglia di correzione**

La soglia rappresenta il numero massimo di messaggi che possono essere inviati a un profilo durante il periodo interessato.

Per impostazione predefinita, la soglia è costante e è necessario indicare un numero massimo di messaggi autorizzati dalla regola.

![](assets/fatigue2.png)

**Utilizzo di una soglia variabile**

To define a variable threshold, select the **[!UICONTROL Depends on the recipient]** value in the **[!UICONTROL Threshold type]** field.

![](assets/fatigue15.png)

Sono quindi disponibili due opzioni:

* selezionare un campo profilo: la soglia varia per ogni profilo in base al campo selezionato. For example, if you have extended the profiles resource with a 'Communication frequency' field, click the button on the right of the **[!UICONTROL Threshold computation formula]** field and select your field. Per ogni profilo, la soglia assumerà il valore del campo «Communication Frequency».

   ![](assets/fatigue21.png)

* define a formula: click the second button on the right of the **[!UICONTROL Threshold computation formula]** field to define an advanced threshold calculation formula. Ad esempio, puoi indicizzare il numero di messaggi autorizzati in base al segmento a cui appartiene il profilo. Ciò significa che un profilo appartenente al segmento Web potrebbe ricevere più messaggi rispetto ad altri profili. An **[!UICONTROL Iif (@origin='Web', 5, 3)]** type formula authorizes the delivery of 5 messages to profiles of the Web segment and 3 for other segments.

   ![](assets/fatigue14.png)

**Miglioramento della soglia di profili e consegne**

Per impostazione predefinita, tutti i messaggi sono presi in considerazione per il calcolo della soglia. Check the **[!UICONTROL Refine Threshold on profiles and deliveries]** box to filter the profiles and deliveries to count when preparing the delivery.

In the following example, only male profiles are counted and only deliveries with a label starting with **Newsletters** are counted.

![](assets/fatigue13.png)

Refining the threshold on deliveries is different than restricting the applicability of the entire rule ( **[!UICONTROL Application criteria]** tab):

* **[!UICONTROL Application criteria]**: scegliete di eseguire la regola o non in base a criteri specifici. Ad esempio, se la condizione dell'applicazione è'Etichetta inizia con Newsletter ', la regola si applica solo alle consegne che rispettano questa condizione. Se l'etichetta della consegna inizia con «Promozione», la regola non viene eseguita.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: Tutte le consegne che utilizzano questa regola di tipologia eseguiranno la regola, ma tu decidi, tra le consegne passate e pianificate, quali desideri conteggiare. Ad esempio, se la restrizione è'Etichetta inizia con Newsletter ', la regola verrà eseguita anche se l'etichetta di consegna inizia con «Promo». Esso conta, nel periodo scorrevole selezionato, il numero di consegne la cui etichetta inizia con'Newsletter '.

## Setting the sliding period {#setting-the-sliding-period}

Le regole di fatigue sono definite nei periodi di scorrimento n-day. The period is configured in the **[!UICONTROL Sliding period]** section, for example 2 weeks, 7 days or 5 hours.

![](assets/fatigue6.png)

Quando la regola viene eseguita, vengono prese in considerazione sia le consegne passate che quelle pianificate. Questo garantisce che, in un determinato periodo di scorrimento, la soglia non venga mai superata.

For example, if you define a 48-hour period, the system will be looking 48 hours **before the contact date ** and 48 hours **after the contact date**. Pertanto, il periodo selezionato viene raddoppiato per consentire l'integrazione delle consegne future e di quelle precedenti.

To restrict the deliveries taken into account to a 2-week period, enter **Day** and **7** or 1 week in the **Sliding period** section. Nel calcolo vengono prese in considerazione le consegne inviate fino a 7 giorni prima della data di consegna e pianificate fino a 7 giorni dopo la data di consegna in cui viene applicata la regola.

## Viewing the fatigue results {#viewing-the-fatigue-results}

Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, in base al numero di consegne già inviate. To view fatigue rule execution results, click the button in the bottom right corner of the **[!UICONTROL Deployment]** block.

![](assets/fatigue22.png)

Sono disponibili tre schede, che mostrano i dettagli dei risultati di esecuzione di fatigue compreso il nome della regola applicata:

* Registri di consegna:

   ![](assets/fatigue17.png)

* Registri di esclusione:

   ![](assets/fatigue18.png)

* L'esclusione causa:

   ![](assets/fatigue19.png)

## Viewing the fatigue rule summary report {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign offre un rapporto dedicato sulle regole di affaticamento per aiutarti a capire come vengono applicati alle tue campagne. Questo consente di imparare in che modo le campagne influiscono l'un l'altro e di apportare le regolazioni corrette.

**[!UICONTROL Fatigue rules summary]** Il rapporto è accessibile dal **[!UICONTROL Reports]** pulsante, nell'angolo in alto a destra di ogni programma, campagna e messaggio.

![](assets/fatigue27.png)

Nella parte sinistra dello schermo, potete filtrare i dati del rapporto nella data di contatto delle consegne. Per impostazione predefinita, il periodo selezionato inizia 15 giorni prima della data corrente e termina 15 giorni dopo. Potete anche filtrare una regola di affaticamento specifica.

Nel grafico a torta sono visualizzate le seguenti informazioni nel periodo selezionato:

* **[!UICONTROL Total targeted]**: la destinazione totale prima della preparazione del messaggio
* **[!UICONTROL Excluded]**: il numero totale di esclusioni a causa dell'applicazione della regola di tipo fatigue
* **[!UICONTROL Other exclusions]**: il numero totale di esclusioni a causa di altre regole di tipologia
* **[!UICONTROL To deliver]**: il numero totale dei messaggi da inviare dopo la preparazione del messaggio ( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** )

A destra del grafico, viene visualizzato il numero di esclusioni, suddivise per regola di affaticamento.

Nella tabella inferiore sono visualizzate tutte le consegne nel periodo selezionato. Per ogni consegna potete vedere le regole di affaticamento applicate e le esclusioni corrispondenti. Le consegne prive di una data di contatto vengono visualizzate anche nella tabella.

* **[!UICONTROL 0]** indica che la regola di affaticamento è applicata ma senza esclusione.
* **[!UICONTROL -N]** indica che si sono verificati esclusioni N.
* un campo vuoto significa che la regola di affaticamento non è applicata.

>[!NOTE]
>
>I dati visualizzati non sono contestuali per il programma, il messaggio o la campagna da cui accedete al report. Questo rapporto visualizza tutte le regole e le consegne di affaticamento per tutte le unità aziendali. In questo modo potete ottenere una visualizzazione globale di tutte le consegne per comprendere in che modo le campagne vengono influenzate da altri.

## Examples {#examples}

Esistono diverse opzioni per l'implementazione di gestione affaticata. Di seguito sono riportati alcuni esempi di ciò che potete fare:

* Create a fatigue rule using a **constant threshold** that applies to **all channels**:

   Supponiamo che crei una regola multicanale con una soglia costante di 3 per un periodo di 7 giorni.

   La settimana scorsa, i profili premium ricevevano un messaggio e-mail di promozione e un messaggio e-mail di remarketing transazionali. Hai anche pianificato un SMS che verrà inviato per la settimana successiva. Oggi decidi di inviare una notifica push per tutti i tuoi profili. I profili premium saranno esclusi dal push di oggi perché è già stato raggiunto il numero massimo di messaggi nel periodo di 2 settimane.

   ![](assets/fatigue23.png)

* Create a fatigue rule using a **variable threshold** based on a **profile field**:

   Hai esteso la risorsa dei profili con un campo «Limite communication», per definire una soglia diversa per ogni profilo. Nella regola di affaticamento, definite una soglia variabile basata su questo campo e selezionate un periodo di 2 giorni. Prendiamo due esempi di profili: John ha un limite di comunicazione pari a 1 e David ha una soglia pari a 2. Entrambe le sessioni hanno già ricevuto un messaggio e-mail per la newsletter ieri. Decidi di inviare un'altra e-mail oggi stesso. Solo David la riceverà, perché John è stato escluso dalla destinazione.

   ![](assets/fatigue24.png)

* Create a fatigue rule using a **threshold computation formula**:

   Vuoi modificare la soglia in base all'età dei tuoi profili. Se un profilo è inferiore a 40, si desidera definire un limite di 4 e per i profili precedenti, un limite di 2. Invece di definire questa soglia per ogni profilo con un campo esteso, puoi creare una formula direttamente nella regola di affaticamento per calcolare la soglia in base ai profili dell'età. In our example, the formula would be **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Questa sezione include anche un esempio passo passo di una regola di affaticamento utilizzando una formula di calcolo della soglia.

* Create a fatigue rule that **refines the threshold** on profiles and deliveries:

   Hai esteso la risorsa dei profili con un campo «Score» e hai esteso anche la risorsa delle consegne con un campo «Tipo». Desiderate definire una soglia costante pari a 3, ma escludere dal conteggio tutte le consegne del tipo "Alert" o "Black Friday" e tutti i profili con un punteggio maggiore di 10. Quando la regola viene eseguita, verrà conteggiata, tra le consegne passate e pianificate, tutte le consegne che non sono del tipo Alert (Avviso) o «Black Friday» inviato a profili il cui punteggio è inferiore a 10.

   ![](assets/fatigue26.png)

Ecco un esempio passo-passo di una regola di affaticamento utilizzando una formula di calcolo della soglia.

In questo caso d'uso, desideriamo creare una regola di tipo tipologico per impedire la consegna di più di 2 messaggi settimanali a profili premium e 2 messaggi settimanali ai profili standard.

To identify customers and prospects, we extended the profiles resource with the **[!UICONTROL Status]** field, which contains 0 for premium profiles and 1 for standard profiles.

Per creare la regola, effettuate le seguenti operazioni:

1. Create a new **Fatigue** type typology rule.
1. In the **[!UICONTROL Threshold]** section, we want to create a formula to calculate the threshold depending on each profile. Select the **[!UICONTROL Depends on the recipient]** value in the **[!UICONTROL Threshold type]** field, then click the icon the second button on the right of the **[!UICONTROL Threshold computation formula]** field.

   ![](assets/fatigue7.png)

1. In the **[!UICONTROL List of functions]** section, double-click the **Iif** function in the **[!UICONTROL Others]** node.

   ![](assets/fatigue8.png)

1. Then select the profile's **Status** in the **[!UICONTROL Available fields]** section.

   ![](assets/fatigue9.png)

1. Enter the desired values to create the following formula: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Questa formula consente di assegnare il valore 2 se lo stato è uguale a 0 e il valore 4 per tutti gli altri stati.

1. Click **[!UICONTROL Confirm]** to approve the formula.
1. Indicate the **[!UICONTROL Sliding period]** on which the rule will apply: 7 days in this case, to restrict the deliveries taken into account to a 2-week period.

   ![](assets/fatigue11.png)

1. Ora collegate la regola appena creata a una tipologia per applicarla alle consegne. To do this, select the **[!UICONTROL Typologies]** tab, click **[!UICONTROL Create element]** and select the typology used for your deliveries.

   ![](assets/fatigue12.png)

1. Salvate la regola per approvare la creazione.

La regola verrà applicata a tutte le consegne in base alla tipologia.
