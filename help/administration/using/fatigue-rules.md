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
source-git-commit: 48c725de297e3a8b2fc05be65f59cd23b2cfd7d7

---


# Regole di affaticamento{#fatigue-rules}

## Informazioni sulle regole di affaticamento {#about-fatigue-rules}

Le regole di affaticamento consentono agli esperti di marketing di impostare regole aziendali multicanale globali che escluderanno automaticamente i profili superflui dalle campagne.

Per implementare le regole di affaticamento, definite un numero massimo di messaggi per profilo e selezionate un periodo in cui applicare la regola. Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di messaggi già inviati.

>[!NOTE]
>
>Per applicare le regole di affaticamento, è necessario definire una data di contatto per la consegna. Se scegli di inviare subito i messaggi, la regola di affaticamento non verrà applicata.

Argomenti correlati:

* [Preparazione](../../administration/using/configuring-email-channel.md#preparation)
* [Gestione di tipologie](../../administration/using/about-typology-rules.md#managing-typologies)
* [Regole per i tipi di telefono](../../administration/using/about-typology-rules.md#typology-rules)

## Creazione di una regola di tipo fatigue {#creating-a-fatigue-rule}

Per creare e configurare una regola **[!UICONTROL Fatigue]** di tipo tipologia, effettuate le seguenti operazioni:

1. Fai clic sul logo Adobe Campaign, nell'angolo in alto a sinistra dell'interfaccia, quindi seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. Dall'elenco delle regole di composizione, fate clic **[!UICONTROL Create]** su.

   ![](assets/fatigue.png)

1. Nel **[!UICONTROL Rule type]** campo, selezionare **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. Nel **[!UICONTROL Channel]** campo, selezionate il canale a cui applicare la regola. Puoi selezionare un singolo canale (e-mail, SMS, posta diretta, applicazione mobile) o selezionare **[!UICONTROL All channels]**. Consultate [Scelta del canale](../../administration/using/fatigue-rules.md#choosing-the-channel).

   ![](assets/fatigue5.png)

1. Nella **[!UICONTROL General]** scheda, definire il metodo per calcolare il numero massimo di messaggi per profilo. Potete scegliere una soglia costante o una variabile. Puoi anche definire la soglia per i profili e le consegne. Per ulteriori informazioni, consultate [Definizione della soglia](../../administration/using/fatigue-rules.md#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Scegliete una **[!UICONTROL Sliding period]** su cui applicare la regola relativa alla tipologia. Per ulteriori informazioni, consultate [Impostazione del periodo di scorrimento](../../administration/using/fatigue-rules.md#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   In questo esempio (vedere le videate precedenti), scegliamo di inviare un numero massimo di 4 messaggi in un periodo di 15 giorni.

1. Nella **[!UICONTROL Application criteria]** scheda, potete scegliere di applicare questa regola a tutte le consegne o limitare l'applicabilità della regola in base al messaggio da inviare. La regola viene eseguita solo se la condizione dell'applicazione è soddisfatta. Ad esempio, è possibile applicare la regola solo sui messaggi con un'etichetta che inizia con una determinata parola o con un ID che contiene determinate lettere. Consultate [Limitazione dell'applicabilità di una regola di filtro](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. Selezionate la **[!UICONTROL Typologies]** scheda e collegate la regola di digitazione al testo usato per le consegne. Consultate [Gestione di tipolazioni](../../administration/using/about-typology-rules.md#managing-typologies) e [regole Typology](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La tipologia può essere definita nel modello di consegna, da applicare automaticamente a tutte le consegne create con questo modello.

Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, in base al numero di consegne già inviate. Potete visualizzare i risultati dell'esecuzione della regola fatigue nei registri di consegna. Consultate [Visualizzazione dei risultati](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results)di affaticamento.

![](assets/fatigue16.png)

>[!CAUTION]
>
>Affinché le regole di affaticamento funzionino, è necessario definire una data di contatto per la distribuzione. Se scegli di inviare subito i messaggi, la regola di affaticamento non verrà applicata.

## Scelta del canale {#choosing-the-channel}

Sono disponibili regole di affaticamento per diversi canali. Il canale è definito nel **[!UICONTROL Channel]** campo delle impostazioni delle regole di composizione. Potete selezionare un singolo canale o selezionare **[!UICONTROL All channels]**.

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

**I messaggi transazionali** possono essere utilizzati per inviare messaggi del servizio mirati a un evento (rtevent) nonché ai messaggi di marketing (profili di targeting), ad esempio un messaggio di remarketing. Le regole di fatigue sono compatibili solo con i messaggi di marketing (profili di targeting). I messaggi transazionali degli eventi non contengono informazioni sul profilo, pertanto non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con profili). Grazie al supporto dei messaggi di marketing nei messaggi transazionali, puoi **applicare una regola fatigue a tutti i canali, compresi i messaggi transazionali di marketing**.

## Definizione della soglia {#defining-the-threshold}

Ogni regola di affaticamento definisce una soglia, ovvero il numero massimo di messaggi che possono essere inviati a un profilo in un determinato periodo. Una volta raggiunta questa soglia, non sarà più possibile eseguire consegne fino alla fine del periodo considerato. Questo processo consente di escludere automaticamente un profilo da una consegna se un messaggio supera la soglia del set, evitando così eccessiva precauzione.

I valori di soglia possono essere costanti o variabili. Ciò significa che, per un determinato periodo, le soglie possono variare da un profilo all'altro, o addirittura per lo stesso profilo.

**Utilizzo di una soglia di correzione**

La soglia rappresenta il numero massimo di messaggi che possono essere inviati a un profilo durante il periodo interessato.

Per impostazione predefinita, la soglia è costante e è necessario indicare un numero massimo di messaggi autorizzati dalla regola.

![](assets/fatigue2.png)

**Utilizzo di una soglia variabile**

Per definire una soglia di variabile, selezionare il **[!UICONTROL Depends on the recipient]** valore nel **[!UICONTROL Threshold type]** campo.

![](assets/fatigue15.png)

Sono quindi disponibili due opzioni:

* selezionare un campo profilo: la soglia varia per ogni profilo in base al campo selezionato. Ad esempio, se avete esteso la risorsa dei profili con un campo «Frequenza communication», fate clic sul pulsante a destra del **[!UICONTROL Threshold computation formula]** campo e selezionate il campo. Per ogni profilo, la soglia assumerà il valore del campo «Communication Frequency».

   ![](assets/fatigue21.png)

* definire una formula: fare clic sul secondo pulsante sul lato destro del **[!UICONTROL Threshold computation formula]** campo per definire una formula di calcolo della soglia avanzata. Ad esempio, puoi indicizzare il numero di messaggi autorizzati in base al segmento a cui appartiene il profilo. Ciò significa che un profilo appartenente al segmento Web potrebbe ricevere più messaggi rispetto ad altri profili. Una **[!UICONTROL Iif (@origin='Web', 5, 3)]** formula di tipo autorizza l'invio di 5 messaggi ai profili del segmento Web e 3 per altri segmenti.

   ![](assets/fatigue14.png)

**Miglioramento della soglia di profili e consegne**

Per impostazione predefinita, tutti i messaggi sono presi in considerazione per il calcolo della soglia. Selezionate **[!UICONTROL Refine Threshold on profiles and deliveries]** la casella per filtrare i profili e le consegne al momento della preparazione della distribuzione.

Nell'esempio seguente, vengono conteggiati solo i profili maschile e vengono conteggiati solo le consegne con un'etichetta che inizia con **le newsletter** .

![](assets/fatigue13.png)

La modifica della soglia delle consegne è diversa dall'applicazione dell'intera regola ( **[!UICONTROL Application criteria]** tabulazione):

* **[!UICONTROL Application criteria]**: scegliete di eseguire la regola o non in base a criteri specifici. Ad esempio, se la condizione dell'applicazione è'Etichetta inizia con Newsletter ', la regola si applica solo alle consegne che rispettano questa condizione. Se l'etichetta della consegna inizia con «Promozione», la regola non viene eseguita.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: Tutte le consegne che utilizzano questa regola di tipologia eseguiranno la regola, ma tu decidi, tra le consegne passate e pianificate, quali desideri conteggiare. Ad esempio, se la restrizione è'Etichetta inizia con Newsletter ', la regola verrà eseguita anche se l'etichetta di consegna inizia con «Promo». Esso conta, nel periodo scorrevole selezionato, il numero di consegne la cui etichetta inizia con'Newsletter '.

## Impostazione del periodo scorrevole {#setting-the-sliding-period}

Le regole di fatigue sono definite nei periodi di scorrimento n-day. Il periodo è configurato nella **[!UICONTROL Sliding period]** sezione, ad esempio 2 settimane, 7 giorni o 5 ore.

![](assets/fatigue6.png)

Quando la regola viene eseguita, vengono prese in considerazione sia le consegne passate che quelle pianificate. Questo garantisce che, in un determinato periodo di scorrimento, la soglia non venga mai superata.

Ad esempio, se si definisce un periodo di 48 ore, il sistema avrà una durata di 48 ore **prima della data di contatto** e 48 ore **dopo la data di contatto**. Pertanto, il periodo selezionato viene raddoppiato per consentire l'integrazione delle consegne future e di quelle precedenti.

Per limitare le consegne considerate a un periodo di 2 settimane, immettere **Giorno** e **7** o 1 settimane **nella** sezione Periodo di scorrimento. Nel calcolo vengono prese in considerazione le consegne inviate fino a 7 giorni prima della data di consegna e pianificate fino a 7 giorni dopo la data di consegna in cui viene applicata la regola.

## Visualizzazione dei risultati di affaticamento {#viewing-the-fatigue-results}

Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, in base al numero di consegne già inviate. Per visualizzare i risultati di esecuzione della regola fatigue, fate clic sul pulsante nell'angolo inferiore destro del **[!UICONTROL Deployment]** blocco.

![](assets/fatigue22.png)

Sono disponibili tre schede, che mostrano i dettagli dei risultati di esecuzione di fatigue compreso il nome della regola applicata:

* Registri di consegna:

   ![](assets/fatigue17.png)

* Registri di esclusione:

   ![](assets/fatigue18.png)

* L'esclusione causa:

   ![](assets/fatigue19.png)

## Visualizzazione del rapporto di riepilogo delle regole di affaticamento {#viewing-the-fatigue-rule-summary-report}

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

## Esempi {#examples}

Esistono diverse opzioni per l'implementazione di gestione affaticata. Di seguito sono riportati alcuni esempi di ciò che potete fare:

* Create una regola di fatigue **utilizzando una soglia** costante applicata **a tutti i canali**:

   Supponiamo che crei una regola multicanale con una soglia costante di 3 per un periodo di 7 giorni.

   La settimana scorsa, i profili premium ricevevano un messaggio e-mail di promozione e un messaggio e-mail di remarketing transazionali. Hai anche pianificato un SMS che verrà inviato per la settimana successiva. Oggi decidi di inviare una notifica push per tutti i tuoi profili. I profili premium saranno esclusi dal push di oggi perché è già stato raggiunto il numero massimo di messaggi nel periodo di 2 settimane.

   ![](assets/fatigue23.png)

* Crea una regola di affaticamento utilizzando una **soglia variabile** basata su **un campo profilo**:

   Hai esteso la risorsa dei profili con un campo «Limite communication», per definire una soglia diversa per ogni profilo. Nella regola di affaticamento, definite una soglia variabile basata su questo campo e selezionate un periodo di 2 giorni. Prendiamo due esempi di profili: John ha un limite di comunicazione pari a 1 e David ha una soglia pari a 2. Entrambe le sessioni hanno già ricevuto un messaggio e-mail per la newsletter ieri. Decidi di inviare un'altra e-mail oggi stesso. Solo David la riceverà, perché John è stato escluso dalla destinazione.

   ![](assets/fatigue24.png)

* Create una regola di fatigue utilizzando una **formula di calcolo della soglia**:

   Vuoi modificare la soglia in base all'età dei tuoi profili. Se un profilo è inferiore a 40, si desidera definire un limite di 4 e per i profili precedenti, un limite di 2. Invece di definire questa soglia per ogni profilo con un campo esteso, puoi creare una formula direttamente nella regola di affaticamento per calcolare la soglia in base ai profili dell'età. Nell'esempio, la formula **[!UICONTROL Iif (@age<40, 4, 2)]** sarebbe.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Questa sezione include anche un esempio passo passo di una regola di affaticamento utilizzando una formula di calcolo della soglia.

* Crea una regola di affaticamento che **regola la soglia** su profili e consegne:

   Hai esteso la risorsa dei profili con un campo «Score» e hai esteso anche la risorsa delle consegne con un campo «Tipo». Desiderate definire una soglia costante pari a 3, ma escludere dal conteggio tutte le consegne del tipo "Alert" o "Black Friday" e tutti i profili con un punteggio maggiore di 10. Quando la regola viene eseguita, verrà conteggiata, tra le consegne passate e pianificate, tutte le consegne che non sono del tipo Alert (Avviso) o «Black Friday» inviato a profili il cui punteggio è inferiore a 10.

   ![](assets/fatigue26.png)

Ecco un esempio passo-passo di una regola di affaticamento utilizzando una formula di calcolo della soglia.

In questo caso d'uso, desideriamo creare una regola di tipo tipologico per impedire la consegna di più di 2 messaggi settimanali a profili premium e 2 messaggi settimanali ai profili standard.

Per identificare clienti e potenziali clienti, abbiamo esteso la risorsa dei profili con il **[!UICONTROL Status]** campo, che contiene 0 per i profili premium e 1 per i profili standard.

Per creare la regola, effettuate le seguenti operazioni:

1. Create una nuova **regola di tipo Tipo fatigue** .
1. Nella **[!UICONTROL Threshold]** sezione, vogliamo creare una formula per calcolare la soglia a seconda di ciascun profilo. Selezionate il **[!UICONTROL Depends on the recipient]** valore nel **[!UICONTROL Threshold type]** campo, quindi fate clic sull'icona il secondo pulsante sul lato destro del **[!UICONTROL Threshold computation formula]** campo.

   ![](assets/fatigue7.png)

1. Nella **[!UICONTROL List of functions]** sezione, fare doppio clic sulla **funzione Iif** nel **[!UICONTROL Others]** nodo.

   ![](assets/fatigue8.png)

1. Quindi selezionate **lo stato del profilo** nella **[!UICONTROL Available fields]** sezione.

   ![](assets/fatigue9.png)

1. Inserite i valori desiderati per creare la formula seguente: **Iif (@ status = 0,2,4)**

   ![](assets/fatigue10.png)

   Questa formula consente di assegnare il valore 2 se lo stato è uguale a 0 e il valore 4 per tutti gli altri stati.

1. Fate clic per **[!UICONTROL Confirm]** approvare la formula.
1. Indica il **[!UICONTROL Sliding period]** punto in cui applicare la regola: 7 giorni in questo caso, per limitare le consegne considerate a un periodo di 2 settimane.

   ![](assets/fatigue11.png)

1. Ora collegate la regola appena creata a una tipologia per applicarla alle consegne. A tal fine, selezionate la **[!UICONTROL Typologies]** scheda, fate clic **[!UICONTROL Create element]** e selezionate il testo usato per le consegne.

   ![](assets/fatigue12.png)

1. Salvate la regola per approvare la creazione.

La regola verrà applicata a tutte le consegne in base alla tipologia.
