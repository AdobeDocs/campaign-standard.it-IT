---
title: Informazioni sulle regole di tipologia
description: Scopri come funzionano le regole di tipologia in Adobe Campaign.
page-status-flag: mai attivato
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regole di utilizzo
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: tipologia,panoramica;regolaTipologia,principale;regolaTipologia,panoramica
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni sulle regole di tipologia{#about-typology-rules}

Una tipologia è un insieme di regole, eseguite durante la fase di analisi dei messaggi, che consentono la convalida della destinazione, del contenuto e della configurazione dei seguenti elementi: oggetto, URL, immagini, collegamento di annullamento dell’iscrizione, dimensioni della prova, ecc.

In Adobe Campaign, ogni messaggio contiene un collegamento a una tipologia. Questo collegamento è definito nei parametri avanzati delle proprietà del modello di consegna (per ulteriori informazioni, consulta la sezione [Preparazione](../../administration/using/configuring-email-channel.md#preparation) ).

>[!NOTE]
>
>A ciascun messaggio è possibile assegnare solo una singola tipologia.

Per ogni tipologia, la **[!UICONTROL Typology rules]** sezione elenca il set di regole per questa tipologia.

![](assets/typology_typo-rule-list.png)

## Gestione delle tipologie {#managing-typologies}

Diverse tipologie sono presenti nell'applicazione per impostazione predefinita. In base alle vostre esigenze, potete creare tipologie personalizzate o modificare quelle esistenti.

1. Accedete al **[!UICONTROL List of typologies]** menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** .
1. Selezionate una tipologia per modificarne il contenuto e le proprietà o crearne una nuova.

   ![](assets/typology_list.png)

1. Definire il tipo di tipologia. Le tipologie possono essere di tipo Standard o Filtraggio.
1. Aggiungere le regole di tipologia necessarie utilizzando il **[!UICONTROL Add an element]** pulsante o rimuovere quelle che non si desidera utilizzare.

   È possibile modificare l'ordine in cui vengono applicate le regole per una determinata tipologia. A questo scopo, spostate gli elementi per modificare l'ordine in cui appaiono sullo schermo. I numeri corrispondenti all'ordine di esecuzione vengono quindi automaticamente ricalcolati. La modalità di applicazione della regola viene presentata nella sezione Ordine [di esecuzione delle regole di](#typology-rules-execution-order) tipo.

   Le regole visualizzate in questa schermata sono accessibili in modalità di sola lettura.

La tua tipologia è pronta per essere utilizzata. Puoi selezionarlo nelle proprietà del messaggio o nelle proprietà del modello di messaggio.

>[!NOTE]
>
>Il **[!UICONTROL IP affinity]** campo consente di gestire le affinità in base alla configurazione. Questi sono definiti nel file di configurazione dell'istanza. Se desiderate utilizzare le affinità, contattate l'amministratore.

## Regole di tipologia {#typology-rules}

Le regole di tipologia sono regole aziendali applicate durante la preparazione dei messaggi. Vengono utilizzati per verificare se un messaggio è valido e soddisfa i criteri di qualità. Controllano inoltre se ogni membro del pubblico di destinazione è idoneo a ricevere il messaggio.

Le regole di tipologia sono disponibili nel menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** .

Esistono due tipi di regole:

* **Regole di filtro** : consente di escludere una parte della destinazione del messaggio in base ai criteri definiti in una query, ad esempio profili o profili in quarantena già inviati da un certo numero di e-mail. Consultate [Regole](../../administration/using/filtering-rules.md)di filtro.
* **Regole di fatica** : consente di definire un numero massimo di messaggi per profilo per evitare richieste eccessive. Consultate [Regole](../../administration/using/fatigue-rules.md)di fatica.
* **Regole di controllo** : consentire all'utente di verificare la validità e la qualità dei messaggi prima dell'invio, ad esempio la visualizzazione dei caratteri, la dimensione dei messaggi SMS, il formato dell'indirizzo, ecc. Vedere [Regole](../../administration/using/control-rules.md)di controllo.

Una regola di tipologia può essere applicata a un solo canale o a tutti i canali.

![](assets/typology_channel.png)

Nel caso **[!UICONTROL Properties]** di una regola di tipologia, è possibile impostare il relativo ordine di esecuzione. Quando è necessario applicare più regole, l'ordine di esecuzione di ciascuna regola determina quelle da elaborare per prime. Per ulteriori informazioni, fare riferimento alla sezione Ordine [di esecuzione delle regole di](#typology-rules-execution-order) tipo.

![](assets/typology_rule-active.png)

Una regola di tipologia può essere disattivata tramite la relativa **[!UICONTROL Properties]** se non si desidera che la regola venga applicata nel momento in cui i messaggi interessati dalla regola vengono analizzati.

![](assets/typology_rule-order.png)

Nella **[!UICONTROL Targeting context]** categoria, potete selezionare la dimensione **** Targeting e la dimensione **** Filtraggio in base ai dati da destinare.

Per impostazione predefinita, il filtraggio viene eseguito sul **[!UICONTROL Profiles]**. Ad esempio, se la regola è indirizzata a un'applicazione mobile, **[!UICONTROL Filtering dimension]** è possibile modificarla in **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Ordine di esecuzione delle regole di tipologia {#typology-rules-execution-order}

Le regole di tipologia vengono eseguite in un ordine specificato durante le fasi di targeting, analisi e personalizzazione dei messaggi.

In modalità operativa standard, le regole vengono applicate nella sequenza seguente:

1. Regole di controllo, se applicate all'inizio del targeting.
1. Regole di filtro:

   * Regole di applicazione native per la qualifica degli indirizzi: indirizzo definito / indirizzo non verificato / indirizzo inserito in lista nera / indirizzo in quarantena / qualità indirizzo non verificato.
   * Regole di filtro definite dall'utente.

1. Regole di controllo, se applicate alla fine del targeting.
1. Regole di controllo, se applicate all’inizio della personalizzazione.
1. Regole di controllo, se applicate al termine della personalizzazione.

Tuttavia, è possibile adattare l'ordine di esecuzione dello stesso tipo di regole in ogni tipologia. Infatti, quando più regole vengono eseguite durante la stessa fase di elaborazione dei messaggi, è possibile scegliere l'ordine in cui vengono applicate.

Ad esempio, una regola di filtro il cui ordine di esecuzione è posizionato al numero 20 verrà eseguita prima di una regola di filtro il cui ordine di esecuzione è posizionato al numero 30.
