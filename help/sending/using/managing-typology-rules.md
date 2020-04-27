---
title: Gestione delle regole di tipologia
description: Scopri come utilizzare le regole di tipologia.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3

---


# Gestione delle regole di tipologia {#managing-typology-rules}

## Informazioni sulle regole di tipologia {#about-typology-rules}

Le regole di tipologia sono regole aziendali che consentono di eseguire controlli e filtrare il messaggio prima di inviarlo. I tipi disponibili di regole di tipologia sono:

* **Regole di filtro** : Questo tipo di regola consente di escludere una parte della destinazione del messaggio in base ai criteri definiti in una query, ad esempio profili o profili in quarantena già inviati da un certo numero di e-mail. For more on this, refer to [this section](../../sending/using/filtering-rules.md).

* **Regole di fatica** : Questo tipo di regole consente di definire un numero massimo di messaggi per profilo per evitare di richiederli in eccesso. For more on this, refer to [this section](../../sending/using/fatigue-rules.md).

* **Regole di controllo** : Questo tipo di regole consente all&#39;utente di verificare la validità e la qualità dei messaggi prima di essere inviati, come la visualizzazione del carattere, la dimensione del messaggio SMS, il formato dell&#39;indirizzo, ecc. For more on this, refer to [this section](../../sending/using/control-rules.md).

Le regole di tipologia sono disponibili nel menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]** .

Per impostazione predefinita, sono disponibili diverse regole di **filtraggio** e di **controllo** out-of-the-box. Sono descritti in dettaglio nelle sezioni [Regole](../../sending/using/fatigue-rules.md) di filtraggio e Regole [di](../../sending/using/control-rules.md) controllo.

In base alle esigenze, è possibile modificare le regole di tipologia esistenti o crearne di nuove, ad eccezione delle **[!UICONTROL Control]** regole, che sono di sola lettura e non possono essere modificate.

## Creazione di una regola di tipologia {#creating-a-typology-rule}

I passaggi principali per creare una regola di tipologia sono i seguenti:

1. Accedere al **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]** menu, quindi fare clic **[!UICONTROL Create]**.

   ![](assets/typology_create-rule.png)

1. Immettere la tipologia **[!UICONTROL Label]**, quindi specificare **[!UICONTROL Channel]** a quale regola applicare.

   ![](assets/typology-rule-label.png)

1. Specificate la regola di tipologia **[!UICONTROL Type]**, quindi configuratela in base alle vostre esigenze. La configurazione delle regole di tipologia varia a seconda del tipo. Per ulteriori informazioni, consultare le sezioni **[Regole](../../sending/using/filtering-rules.md)**di filtraggio e Regole**[ di](../../sending/using/fatigue-rules.md)** Fatigue.

1. Selezionare le tipologie in cui si desidera includere la nuova regola. A questo scopo, selezionate la **[!UICONTROL Typologies]** scheda, quindi fate clic sul **[!UICONTROL Create element]** pulsante.

   ![](assets/typology-typologies-tab.png)

1. Selezionate la tipologia desiderata, quindi fate clic **[!UICONTROL Confirm]**.

   ![](assets/typology-link.png)

1. Dopo aver selezionato tutte le tipologie, fare clic **[!UICONTROL Create]** per confermare la creazione della regola di tipologia.

## Ordine di esecuzione delle regole di tipologia {#typology-rules-execution-order}

Le regole di tipologia vengono eseguite in un ordine specificato durante le fasi di targeting, analisi e personalizzazione dei messaggi.

In modalità operativa standard, le regole vengono applicate nella sequenza seguente:

1. Regole di controllo, se applicate all&#39;inizio del targeting.
1. Regole di filtro:

   * Regole di applicazione native per la qualifica degli indirizzi: indirizzo definito / indirizzo non verificato / indirizzo inserito in lista nera / indirizzo in quarantena / qualità indirizzo non verificato.
   * Regole di filtro definite dall&#39;utente.

1. Regole di controllo, se applicate alla fine del targeting.
1. Regole di controllo, se applicate all’inizio della personalizzazione.
1. Regole di controllo, se applicate al termine della personalizzazione.

Tuttavia, è possibile adattare l&#39;ordine di esecuzione dello stesso tipo di regole in ogni tipologia. Infatti, quando più regole vengono eseguite durante la stessa fase di elaborazione dei messaggi, è possibile scegliere l&#39;ordine in cui vengono applicate.

Ad esempio, una regola di filtro il cui ordine di esecuzione è posizionato al numero 20 verrà eseguita prima di una regola di filtro il cui ordine di esecuzione è posizionato al numero 30.

Nel caso **[!UICONTROL Properties]** di una regola di tipologia, è possibile impostarne l&#39;ordine di esecuzione. Quando è necessario applicare più regole, l&#39;ordine di esecuzione di ciascuna regola determina quelle da elaborare per prime. Per ulteriori informazioni, fare riferimento alla sezione Ordine [di esecuzione delle regole di](#typology-rules-execution-order) tipo.

![](assets/typology_rule-active.png)

Una regola di tipologia può essere disattivata tramite la relativa **[!UICONTROL Properties]** se non si desidera che la regola venga applicata nel momento in cui i messaggi interessati dalla regola vengono analizzati.

![](assets/typology_rule-order.png)