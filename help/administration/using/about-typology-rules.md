---
title: Informazioni sulle regole di digitazione
seo-title: Informazioni sulle regole di digitazione
description: Informazioni sulle regole di digitazione
seo-description: Scopri in che modo le regole di tipologie funzionano in Adobe Campaign.
page-status-flag: never-activated
uuid: a 98 ebc 36-172 d -4 f 46-b 6 ee-b 2636 a 1007 c 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: working-with-typology-rules
discoiquuid: 2590 d 94 c -51 ef -4 c 0 f-b 1 ec-c 2837 e 94 da 40
context-tags: informazioni dettagliate, panoramica; Typologyrule, main; Typologyrule, overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# About typology rules{#about-typology-rules}

Una tipologia è un insieme di regole, eseguite durante la fase di analisi messaggio, che consentono la destinazione, il contenuto e la configurazione dei seguenti elementi da convalidare: oggetto, URL, immagini, collegamento non sottoscrizione, dimensione di prova ecc.

In Adobe Campaign, ogni messaggio contiene un collegamento a un tipo di sondaggio. This link is defined in the advanced parameters of the delivery template's properties (for more on this, refer to the [Preparation](../../administration/using/configuring-email-channel.md#preparation) section).

>[!NOTE]
>
>A ogni messaggio è consentito assegnare solo una singola tipologia.

For each typology, the **[!UICONTROL Typology rules]** section lists the set of rules for this typology.

![](assets/typology_typo-rule-list.png)

## Managing typologies {#managing-typologies}

Per impostazione predefinita sono presenti diverse tipologie di testo nell'applicazione. In base alle esigenze, potete creare le vostre tipologie di testo o modificare quelli esistenti.

1. Access the **[!UICONTROL List of typologies]** from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu.
1. Selezionate un tipo di testo per modificarne il contenuto e le proprietà o crearne uno nuovo.

   ![](assets/typology_list.png)

1. Definire il tipo di tipologia. I typolgies possono essere Standard o Filtro tipolizza.
1. Add the typology rules you need using the **[!UICONTROL Add an element]** button or remove the ones you do not want to use.

   Potete modificare l'ordine in cui le regole vengono applicate per una determinata tipologia. A tal fine, spostate gli elementi per modificare l'ordine di visualizzazione sullo schermo. I numeri corrispondenti all'ordine di esecuzione vengono ricalcolati automaticamente. The rule application mode is presented in the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

   Le regole visualizzate in questa schermata sono accessibili in modalità di sola lettura.

La tipologia è pronta per essere utilizzata. Potete selezionarlo nelle proprietà del messaggio o nelle proprietà del modello di messaggio.

>[!NOTE]
>
>**[!UICONTROL IP affinity]** Il campo consente di gestire le affinità in base alla configurazione. Questi sono definiti nel file di configurazione dell'istanza. Se desiderate utilizzare le affinità, contattate l'amministratore.

## Typology rules {#typology-rules}

Le regole tipografiche sono regole aziendali applicate durante la preparazione del messaggio. Vengono utilizzati per verificare se un messaggio è valido e soddisfa i criteri di qualità. Inoltre, controlla se ogni membro del pubblico di destinazione è idoneo a ricevere il messaggio.

Typology rules are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** menu.

Esistono due tipi di regole:

* **Regole di filtro** : consente di escludere una parte della destinazione del messaggio in base ai criteri definiti in una query, ad esempio profili posti in quarantena o profili ai quali è già stato inviato un certo numero di messaggi e-mail. See [Filtering rules](../../administration/using/filtering-rules.md).
* **Regole fatigue** : consente di definire un numero massimo di messaggi per profilo per evitare che tali messaggi vengano ignorati. See [Fatigue rules](../../administration/using/fatigue-rules.md).
* **Regole di controllo** : consentire all'utente di controllare la validità e la qualità dei messaggi prima dell'invio, come visualizzazione dei caratteri, dimensioni del messaggio SMS, formato dell'indirizzo ecc. See [Control rules](../../administration/using/control-rules.md).

Una regola tipografica può essere applicata a un solo canale o a tutti i canali.

![](assets/typology_channel.png)

In the **[!UICONTROL Properties]** of a typology rule, you can set its execution order. Quando dovete applicare più regole, l'ordine di esecuzione di ciascuna regola determina quelli da elaborare per primo. For more on this, refer to the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

![](assets/typology_rule-active.png)

A typology rule can be deactivated through its **[!UICONTROL Properties]** if you do not want the rule to be applied at the moment that the messages concerned by the rule are analyzed.

![](assets/typology_rule-order.png)

In the **[!UICONTROL Targeting context]** category, you can select the **Targeting dimension** and **Filtering dimension** depending on the data that you want to target.

By default, filtering is carried out on the **[!UICONTROL Profiles]**. For example, if the rule is aimed at a mobile application, the **[!UICONTROL Filtering dimension]** can be changed to **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

>[!NOTE]
>
>Poiché il contenuto delle regole di controllo non può essere modificato, si tratta essenzialmente di regole di filtro.

## Typology rules execution order {#typology-rules-execution-order}

Le regole di digitazione vengono eseguite in un ordine specificato durante le fasi di targeting, analisi e personalizzazione dei messaggi.

In modalità standard, le regole vengono applicate nella sequenza seguente:

1. Regole di controllo, se applicate all'inizio del targeting.
1. Regole di filtro:

   * Regole native dell'applicazione per la qualifica dell'indirizzo: indirizzo definito/indirizzo non verificato/indirizzo in blacklist/indirizzo/indirizzo in quarantena.
   * Regole di filtro definite dall'utente.

1. Regole di controllo, se applicate alla fine del targeting.
1. Regole di controllo, se applicate all'inizio della personalizzazione.
1. Regole di controllo, se applicate alla fine della personalizzazione.

Tuttavia, potete adattare l'ordine di esecuzione dello stesso tipo di regole in ogni tipologia. In realtà, quando più regole vengono eseguite durante la stessa fase di elaborazione del messaggio, potete scegliere l'ordine in cui vengono applicate.

Ad esempio, una regola di filtro con l'ordine di esecuzione posizionato sul numero 20 verrà eseguita prima di una regola di filtro il cui ordine di esecuzione è posizionato al numero 30.
