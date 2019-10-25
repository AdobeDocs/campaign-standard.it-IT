---
title: Regole di fatica
seo-title: Regole di fatica
description: Regole di fatica
seo-description: Crea regole di affaticamento per gestire la comunicazione eccessiva con i profili.
page-status-flag: mai attivato
uuid: fa5e3ded-36c2-4f16-b97a-119b85adf679
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regole di utilizzo
discoiquuid: 4337a80b-0fb9-4a37-bce3-fe2121a66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Regole di fatica{#fatigue-rules}

## Informazioni sulle regole di affaticamento {#about-fatigue-rules}

Le regole di Fatigue consentono agli esperti di marketing di impostare regole di business globali tra canali che escluderanno automaticamente i profili richiesti in eccesso dalle campagne.

Per implementare le regole di affaticamento, è necessario definire un numero massimo di messaggi per profilo e selezionare un periodo in cui applicare la regola. Durante la preparazione della consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di messaggi già inviati.

>[!NOTE]
>
>Per applicare le regole di affaticamento, è necessario definire una data di contatto per la consegna. Se scegli di inviare i messaggi immediatamente, la regola di affaticamento non verrà applicata.

Argomenti correlati:

* [Preparazione](../../administration/using/configuring-email-channel.md#preparation)
* [Gestione delle tipologie](../../administration/using/about-typology-rules.md#managing-typologies)
* [Regole di tipologia](../../administration/using/about-typology-rules.md#typology-rules)
* [Ottimizzazione della frequenza di comunicazione per evitare affaticamento del contatto](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

## Creazione di una regola di affaticamento {#creating-a-fatigue-rule}

Per creare e configurare una regola **[!UICONTROL Fatigue]** di tipo, attenetevi alla seguente procedura:

1. Fai clic sul logo Adobe Campaign, nell'angolo superiore sinistro dell'interfaccia, quindi seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. Nell'elenco delle regole di tipologia, fare clic su **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. Nel **[!UICONTROL Rule type]** campo selezionare **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. Nel **[!UICONTROL Channel]** campo, selezionate il canale a cui applicare la regola. Potete selezionare un singolo canale (e-mail, SMS, direct mail, applicazione mobile) oppure **[!UICONTROL All channels]**. Consultate [Scelta del canale](#choosing-the-channel).

   ![](assets/fatigue5.png)

1. Nella **[!UICONTROL General]** scheda, definire il metodo di calcolo del numero massimo di messaggi per profilo. Potete scegliere una soglia costante o una variabile. Puoi anche definire la soglia per profili e consegne. Per ulteriori informazioni, vedere [Definizione della soglia](#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Scegliere una **[!UICONTROL Sliding period]** regola di tipologia da applicare. Per ulteriori informazioni, vedere [Impostazione del periodo](#setting-the-sliding-period)di scorrimento.

   ![](assets/fatigue6.png)

   In questo esempio (vedere le schermate precedenti), abbiamo scelto di inviare un numero massimo di 4 messaggi per un periodo di 15 giorni.

1. Nella **[!UICONTROL Application criteria]** scheda, puoi scegliere di applicare questa regola a tutte le consegne o limitare l'applicabilità della regola in base al messaggio da inviare. La regola verrà eseguita solo se viene soddisfatta la condizione dell'applicazione. Ad esempio, puoi applicare la regola solo ai messaggi con un'etichetta che inizia con una determinata parola o con un ID che contiene determinate lettere. Consultate [Limitazione dell'applicabilità di una regola](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule)di filtro.

   ![](assets/fatigue20.png)

1. Selezionate la **[!UICONTROL Typologies]** scheda e collegate la regola di tipologia alla tipologia utilizzata per le consegne. Consultate [Gestione delle tipologie](../../administration/using/about-typology-rules.md#managing-typologies) e delle [regole](../../administration/using/about-typology-rules.md#typology-rules)di tipologia.

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La tipologia può essere definita nel modello di consegna, da applicare automaticamente a tutte le consegne create utilizzando questo modello.

Durante la preparazione della consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di consegne già inviate. Potete visualizzare i risultati dell'esecuzione della regola di affaticamento nei registri di consegna. Consultate [Visualizzazione dei risultati](#viewing-the-fatigue-results)della fatica.

![](assets/fatigue16.png)

>[!CAUTION]
>
>Affinché le regole di affaticamento funzionino, è necessario definire una data di contatto per la consegna. Se scegli di inviare i messaggi immediatamente, la regola di affaticamento non verrà applicata.

## Scelta del canale {#choosing-the-channel}

Le regole di fatica sono disponibili per diversi canali. Il canale è definito nel **[!UICONTROL Channel]** campo delle impostazioni delle regole di tipologia. Potete selezionare un singolo canale o **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**Canali disponibili**

Sono disponibili i seguenti canali:

* E-mail
* Mobile (SMS)
* Posta diretta
* Applicazione mobile: questo canale consente di inviare notifiche push ai profili o agli abbonati alle app. Se scegli di inviare notifiche ai profili, saranno compatibili con le regole di affaticamento multicanale.

   >[!CAUTION]
   >
   >Le regole di Fatigue non sono compatibili con le notifiche push inviate agli abbonati all'app. Se invii messaggi agli abbonati alle app, le regole di affaticamento non saranno applicabili.

* Tutti i canali: questa opzione consente di applicare la regola a tutti i canali. Ad esempio, puoi decidere di inviare un massimo di 3 messaggi al mese su qualsiasi canale. Se la scorsa settimana avete inviato 2 e-mail a un profilo e provate a inviare una notifica push, lo stesso profilo verrà escluso.

**Tipi di consegna**

Le regole di Fatigue sono compatibili con tutti i tipi di consegna: consegne una tantum, consegne ricorrenti, consegne di flussi di lavoro e messaggi transazionali.

**I messaggi** transazionali possono essere utilizzati per inviare messaggi di servizio destinati a un evento (rtEvent) e messaggi di marketing (profili di targeting), ad esempio un messaggio di remarketing. Le regole di Fatigue sono compatibili solo con i messaggi di marketing (profili di targeting). I messaggi relativi alle transazioni di eventi non contengono informazioni sul profilo, pertanto non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con i profili). Grazie al supporto dei messaggi di marketing nei messaggi transazionali, puoi **applicare una regola di affaticamento a tutti i canali, compresi i messaggi** di marketing transazionali.

## Definizione della soglia {#defining-the-threshold}

Ogni regola di affaticamento definisce una soglia, ovvero il numero massimo di messaggi che possono essere inviati a un profilo in un dato periodo. Una volta raggiunta tale soglia, non potranno più essere effettuate consegne fino alla fine del periodo in esame. Questo processo consente di escludere automaticamente un profilo da una consegna se un messaggio supera la soglia impostata, evitando in tal modo un eccesso di richieste.

I valori di soglia possono essere costanti o variabili. Ciò significa che per un determinato periodo le soglie possono variare da un profilo all'altro, o anche per lo stesso profilo.

**Utilizzo di una soglia di correzione**

La soglia rappresenta il numero massimo di messaggi che possono essere inviati a un profilo durante il periodo in questione.

Per impostazione predefinita, la soglia è costante ed è necessario indicare un numero massimo di messaggi autorizzati dalla regola.

![](assets/fatigue2.png)

**Utilizzo di una soglia variabile**

Per definire una soglia di variabile, selezionare il **[!UICONTROL Depends on the recipient]** valore nel **[!UICONTROL Threshold type]** campo.

![](assets/fatigue15.png)

Sono disponibili due opzioni:

* selezionare un campo profilo: la soglia varia per ciascun profilo in base al campo selezionato. Ad esempio, se hai esteso la risorsa dei profili con un campo 'Frequenza comunicazioni', fai clic sul pulsante a destra del **[!UICONTROL Threshold computation formula]** campo e seleziona il campo. Per ciascun profilo, la soglia assume il valore del campo "Frequenza comunicazione".

   ![](assets/fatigue21.png)

* definire una formula: fare clic sul secondo pulsante a destra del **[!UICONTROL Threshold computation formula]** campo per definire una formula di calcolo della soglia avanzata. Ad esempio, puoi indicizzare il numero di messaggi autorizzati in base al segmento al quale il profilo appartiene. Ciò significa che un profilo appartenente al segmento 'Web' potrebbe ricevere più messaggi rispetto ad altri profili. Una formula **[!UICONTROL Iif (@origin='Web', 5, 3)]** di tipo autorizza la consegna di 5 messaggi ai profili del segmento Web e 3 per altri segmenti.

   ![](assets/fatigue14.png)

**Ottimizzazione della soglia per profili e consegne**

Per impostazione predefinita, tutti i messaggi vengono presi in considerazione per il calcolo della soglia. Selezionate la **[!UICONTROL Refine Threshold on profiles and deliveries]** casella per filtrare i profili e le consegne da conteggiare durante la preparazione della consegna.

Nell'esempio seguente, vengono contati solo i profili maschili e vengono conteggiate solo le consegne con un'etichetta che inizia con **Newsletter** .

![](assets/fatigue13.png)

La definizione della soglia sulle consegne è diversa dalla limitazione dell'applicabilità dell'intera regola ( **[!UICONTROL Application criteria]** scheda):

* **[!UICONTROL Application criteria]**: scegliete di eseguire la regola o meno in base a criteri specifici. Ad esempio, se la condizione dell'applicazione è "Etichetta inizia con Newsletter", la regola si applica solo alle consegne che rispettano questa condizione. Se l'etichetta della consegna inizia con "Promozione", la regola non verrà eseguita.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: tutte le consegne che utilizzano questa regola di tipo eseguiranno la regola, ma si decide, tra le consegne passate e pianificate, quali si desidera contare. Ad esempio, se il limite è 'Etichetta inizia con Newsletter', la regola verrà eseguita anche se l'etichetta di consegna inizia con 'Promo'. Conta, nel periodo scorrevole selezionato, il numero di consegne la cui etichetta inizia con "Newsletter".

## Impostazione del periodo di scorrimento {#setting-the-sliding-period}

Le regole di Fatigue sono definite nei periodi di scorrimento giornalieri. Il periodo è configurato nella **[!UICONTROL Sliding period]** sezione, ad esempio 2 settimane, 7 giorni o 5 ore.

![](assets/fatigue6.png)

Durante l'esecuzione della regola, vengono prese in considerazione sia le consegne passate che le consegne programmate. Questo garantisce che, in un dato periodo di scorrimento, la soglia non venga mai superata.

Ad esempio, se definisci un periodo di 48 ore, il sistema controllerà 48 ore **prima della data** del contatto e 48 ore **dopo la data** del contatto. Pertanto, il periodo selezionato è raddoppiato per consentire l'integrazione delle consegne future e di quelle precedenti.

Per limitare le consegne prese in considerazione a un periodo di 2 settimane, immettere **Giorno** e **7** o 1 settimana nella sezione **Periodo** di presentazione. Le consegne inviate fino a 7 giorni prima della data di consegna e programmate fino a 7 giorni dopo la data di consegna alla quale si applica la regola saranno prese in considerazione nel calcolo.

## Visualizzazione dei risultati della fatica {#viewing-the-fatigue-results}

Durante la preparazione della consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di consegne già inviate. Per visualizzare i risultati dell'esecuzione della regola di affaticamento, fare clic sul pulsante nell'angolo inferiore destro del **[!UICONTROL Deployment]** blocco.

![](assets/fatigue22.png)

Sono disponibili tre schede che mostrano i dettagli dei risultati dell'esecuzione della fatica, compreso il nome della regola applicata:

* Registri di consegna:

   ![](assets/fatigue17.png)

* Registri di esclusione:

   ![](assets/fatigue18.png)

* Cause di esclusione:

   ![](assets/fatigue19.png)

## Visualizzazione del rapporto di riepilogo della regola di affaticamento {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign offre un rapporto dedicato sulle regole di affaticamento per aiutarti a capire come vengono applicate alle campagne. Questo consente di comprendere l'impatto reciproco delle campagne e di apportare le giuste regolazioni.

Il **[!UICONTROL Fatigue rules summary]** rapporto è accessibile dal **[!UICONTROL Reports]** pulsante, nell'angolo superiore destro di ciascun programma, campagna e messaggio.

![](assets/fatigue27.png)

Nella parte sinistra dello schermo, puoi filtrare i dati del rapporto sulla data di contatto delle consegne. Per impostazione predefinita, il periodo selezionato inizia 15 giorni prima della data corrente e termina 15 giorni dopo. Potete anche filtrare una regola di affaticamento specifica.

Il grafico a torta visualizza le seguenti informazioni sul periodo selezionato:

* **[!UICONTROL Total targeted]**: obiettivo totale prima della preparazione dei messaggi
* **[!UICONTROL Excluded]**: il numero totale di esclusioni dovute all'applicazione della regola di affaticamento
* **[!UICONTROL Other exclusions]**: il numero totale di esclusioni dovute ad altre regole di tipologia
* **[!UICONTROL To deliver]**: il numero totale dei messaggi da inviare dopo la preparazione dei messaggi ( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** )

Sulla destra del grafico, troverete il numero di esclusioni, suddiviso per regola di affaticamento.

Nella tabella inferiore sono visualizzate tutte le consegne nel periodo selezionato. Per ogni consegna, puoi vedere le regole di affaticamento applicate e le esclusioni corrispondenti. Le consegne che non hanno una data di contatto sono visualizzate nella tabella.

* **[!UICONTROL 0]** significa che la regola di affaticamento è applicata ma non vi è stata alcuna esclusione.
* **[!UICONTROL -N]** significa che non si sono verificate esclusioni.
* un campo vuoto indica che la regola di affaticamento non era applicabile.

>[!NOTE]
>
>I dati visualizzati non sono contestuali al programma, al messaggio o alla campagna a cui si accede dal rapporto. Questo rapporto mostra tutte le regole di affaticamento e le consegne per tutte le unità organizzative. Questo consente di ottenere una visione globale di tutte le consegne, per comprendere in che modo le campagne vengono influenzate dagli altri.

## Esempi {#examples}

Ci sono molte possibilità in termini di implementazione della gestione della fatica. Di seguito sono riportati alcuni esempi delle operazioni che è possibile eseguire:

* Create una regola di affaticamento utilizzando una soglia **** costante applicabile a **tutti i canali**:

   Supponiamo che tu crei una regola multicanale con una soglia costante di 3 su un periodo scorrevole di 7 giorni.

   La settimana scorsa, i profili premium hanno ricevuto un'e-mail di promozione e un'e-mail di remarketing transazionale. Hai anche pianificato un SMS che verrà inviato la settimana prossima. Oggi decidi di inviare una notifica push per tutti i tuoi profili. I profili premium saranno esclusi dal push di oggi perché è già stato raggiunto il numero massimo di messaggi in un periodo di 2 settimane.

   ![](assets/fatigue23.png)

* Crea una regola di affaticamento utilizzando una soglia **** variabile basata su un campo **di** profilo:

   Hai esteso la risorsa dei profili con un campo "Limite comunicazione", per definire una soglia diversa per ciascun profilo. Nella regola di affaticamento, definite una soglia variabile basata su questo campo e selezionate un periodo di scorrimento di 2 giorni. Prendiamo due esempi di profili: John ha un limite di comunicazione di 1 e David ha una soglia di 2. Entrambi hanno già ricevuto ieri un'e-mail con la newsletter. Decidete di inviare loro un'altra e-mail oggi stesso. Solo David lo riceverà, perché John è stato escluso dal bersaglio.

   ![](assets/fatigue24.png)

* Create una regola di fatica utilizzando una formula **di calcolo della** soglia:

   Desiderate modificare la soglia in base all'età dei profili. Se un profilo è inferiore a 40, è necessario definire un limite di 4 e, per i profili meno recenti, un limite di 2. Invece di definire questa soglia per ciascun profilo con un campo esteso, puoi creare una formula direttamente nella regola di affaticamento per calcolare la soglia in base all'età dei profili. Nel nostro esempio, la formula sarebbe **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Questa sezione include anche un esempio passo-passo di una regola di affaticamento che utilizza una formula di calcolo della soglia.

* Crea una regola di affaticamento che **affina la soglia** su profili e consegne:

   Hai esteso la risorsa dei profili con un campo "Valutazione" e hai anche esteso la risorsa delle consegne con un campo "Tipo". Si desidera definire una soglia costante di 3 ma si desidera escludere dal conteggio tutte le consegne del tipo "Avviso" o "Black Friday" e tutti i profili con un punteggio superiore a 10. Quando la regola verrà eseguita, verrà conteggiato, tra le consegne passate e pianificate, tutte le consegne che non sono del tipo "Avviso" o "Black Friday" inviate a profili con punteggio inferiore a 10.

   ![](assets/fatigue26.png)

Di seguito è riportato un esempio passo-passo di una regola di affaticamento che utilizza una formula di calcolo della soglia.

In questo caso di utilizzo, vogliamo creare una regola di tipologia per impedire la consegna di più di 2 messaggi alla settimana ai profili premium e di 2 messaggi alla settimana ai profili standard.

Per identificare clienti e potenziali clienti, abbiamo esteso la risorsa dei profili con il **[!UICONTROL Status]** campo, che contiene 0 per i profili premium e 1 per i profili standard.

Per creare la regola, eseguire i seguenti passaggi:

1. Create una nuova regola di tipo **Fatigue** Type typology.
1. Nella **[!UICONTROL Threshold]** sezione vogliamo creare una formula per calcolare la soglia in base a ciascun profilo. Selezionare il **[!UICONTROL Depends on the recipient]** valore nel **[!UICONTROL Threshold type]** campo, quindi fare clic sull'icona il secondo pulsante a destra del **[!UICONTROL Threshold computation formula]** campo.

   ![](assets/fatigue7.png)

1. Nella **[!UICONTROL List of functions]** sezione fare doppio clic sulla funzione **Iif** nel **[!UICONTROL Others]** nodo.

   ![](assets/fatigue8.png)

1. Quindi selezionate **Stato** del profilo nella **[!UICONTROL Available fields]** sezione.

   ![](assets/fatigue9.png)

1. Immettere i valori desiderati per creare la formula seguente: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Questa formula consente di assegnare il valore 2 se lo stato è uguale a 0 e il valore 4 per tutti gli altri stati.

1. Fare clic **[!UICONTROL Confirm]** per approvare la formula.
1. Indicare **[!UICONTROL Sliding period]** su quale regola si applicherà: 7 giorni in questo caso, per limitare le consegne prese in considerazione a un periodo di 2 settimane.

   ![](assets/fatigue11.png)

1. Collegate ora la regola appena creata a una tipologia per applicarla alle consegne. A questo scopo, seleziona la **[!UICONTROL Typologies]** scheda, fai clic su **[!UICONTROL Create element]** e seleziona la tipologia utilizzata per le consegne.

   ![](assets/fatigue12.png)

1. Salvate la regola per approvare la creazione.

La regola verrà applicata a tutte le consegne in base alla tipologia.
