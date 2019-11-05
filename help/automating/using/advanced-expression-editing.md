---
title: Modifica avanzata delle espressioni
description: La procedura guidata di edizione query consente di definire espressioni avanzate.
page-status-flag: mai attivato
uuid: a635f999-27ce-41e0-a88c-8a3882e31efe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: filter-data
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,panoramica;audience,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Modifica avanzata delle espressioni{#advanced-expression-editing}

## Informazioni sulla modifica avanzata delle espressioni {#about-advanced-expression-editing}

La modifica di un'espressione implica l'immissione manuale delle condizioni per formare una regola.

Questa modalità consente di utilizzare funzioni avanzate. Queste funzioni consentono di manipolare i valori utilizzati per eseguire query specifiche, come la manipolazione di date, stringhe, campi numerici, l'ordinamento e così via.

È inoltre possibile utilizzare le variabili di eventi quando si modifica un'espressione. Per ulteriori informazioni, vedere la sezione [Personalizzazione delle attività con variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) di eventi.

È possibile modificare le espressioni per:

* Definire una query tramite l' **[!UICONTROL Advanced mode]** opzione disponibile quando viene aggiunta una regola.

   ![](assets/expression_editor_2.png)

* Modificare un'espressione in un flusso di lavoro. Ad esempio, per aggiungere dati aggiuntivi a un'attività.
* Modificate una condizione di visibilità per definire la modalità di visualizzazione di un blocco nell'editor di contenuti HTML. In questo caso, l'espressione viene modificata in formato JavaScript e non offre l'uso di funzioni avanzate come standard.

## Modificare un'espressione {#edit-an-expression}

L'edizione con espressione avanzata consente di definire manualmente un'espressione che corrisponde specificatamente alle esigenze dell'utente.

Le espressioni di modifica possono essere utilizzate nella finestra Pubblico durante la creazione di un'e-mail o in un'attività Query durante la creazione di un flusso di lavoro.

1. Per accedere alla finestra di modifica delle espressioni, utilizzare uno dei metodi descritti nella sezione [Informazioni sulla modifica](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) delle espressioni avanzate. Comprende i seguenti elementi:

   * Campo di input in cui è definita l'espressione.
   * Elenco di campi disponibili che possono essere utilizzati nell'espressione e che corrispondono alla dimensione di targeting della query (consultate Dimensioni e risorse [di](../../automating/using/query.md#targeting-dimensions-and-resources)targeting).
   * Elenco delle funzioni disponibili, ordinate per categoria.
   ![](assets/expression_editor_1.png)

1. Modificare l'espressione immettendo un'espressione direttamente nel campo corrispondente o utilizzando gli elenchi di campi e funzioni disponibili.

   Facendo doppio clic su un campo o un'espressione, questo viene aggiunto all'espressione in cui è posizionato il cursore.

   È possibile utilizzare le variabili degli eventi dei flussi di lavoro per creare un'espressione. Per ulteriori informazioni, vedere la sezione [Personalizzazione delle attività con variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) di eventi.

1. Se necessario, assegnare alla regola un nome specifico. Il nome immesso verrà visualizzato come nome della regola nell'area di lavoro dell'editor di query.

La modifica di un'espressione consente di personalizzare l'espressione Audiences in modo da indirizzare la popolazione come necessario.

**Argomenti correlati:**

* [Sintassi delle espressioni](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Sintassi delle espressioni {#expression-syntax}

### Sintassi standard {#standard-syntax}

Le espressioni standard sono composte da una o più condizioni che rispettano i seguenti elementi di sintassi:

* Ogni condizione assume la forma di **&lt;valore1&gt; &lt;operatore di confronto&gt; &lt;valore2&gt;** con cui:

   * **&lt;value1&gt;** è un campo o una funzione. Ad esempio, **@created** per la data di creazione di un profilo oppure **Year(@created)** per l'anno in cui è stato creato un profilo.
   * **&lt;operatore di confronto&gt;** è uno degli operatori elencati nella sezione [Operatori](../../automating/using/advanced-expression-editing.md#comparison-operators) di confronto. Questo operatore definisce il metodo di confronto tra **&lt;value1&gt;** e **&lt;value2&gt;**.
   * **&lt;value2&gt;** è un campo, una funzione o un valore immesso manualmente.
   >[!NOTE]
   >
   >I dati del tipo **&lt;value1&gt;** e **&lt;value2&gt;** devono essere identici. Ad esempio, se **&lt;value1&gt;** è una data, anche **&lt;value2&gt;** deve essere una data.

* Se si desidera utilizzare diverse condizioni, è possibile combinarle utilizzando operatori logici.

   * **[!UICONTROL AND]**: due condizioni sono intersecate.
   * **[!UICONTROL OR]**: due condizioni sono combinate.

Ad esempio:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

In questo esempio, vengono impostati come destinazione i profili la cui data di creazione è compresa tra il mese e l'anno correnti.

### Sintassi JavaScript {#javascript-syntax}

Quando si definiscono le condizioni di visibilità di un blocco di testo dell'editor di contenuti HTML, è necessario utilizzare un'espressione con sintassi di tipo JavaScript.

Le espressioni JavaScript sono composte da una o più condizioni e utilizzano i seguenti elementi di sintassi:

* Ogni condizione assume la forma di **&lt;context&gt; &lt;operatore di confronto&gt; &lt;value2&gt;** con cui:

   * **&lt;context&gt;** è un campo o una funzione che consente di specificare il contesto. Ad esempio **context.profile.@email** per l'indirizzo e-mail di un profilo o per **context.profile.firstName.length()** per il numero di caratteri del nome di un profilo.
   * **&lt;operatore di confronto&gt;** è uno degli operatori elencati nella sezione [Operatori](../../automating/using/advanced-expression-editing.md#comparison-operators) di confronto. Questo operatore definisce il metodo di confronto tra **&lt;context&gt;** e **&lt;value2&gt;**.
   * **&lt;value2&gt;** è un campo, una funzione o un valore immesso manualmente.
   >[!NOTE]
   I dati del tipo **&lt;context&gt;** e **&lt;value2&gt;** devono essere identici. Ad esempio, se **&lt;context&gt;** è una data, anche **&lt;value2&gt;** deve essere una data.

* Se si desidera utilizzare diverse condizioni, è possibile combinarle utilizzando operatori logici.

   * **[!UICONTROL &&]**: due condizioni sono intersecate.
   * **[!UICONTROL ||]**: due condizioni sono combinate.

Ad esempio:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In questo esempio, profili di età superiore a 21 anni il cui nome è stato fornito (simbolizzato dal fatto che il campo **firstName** contiene almeno un carattere).

## Operatori di confronto {#comparison-operators}

Per alcune regole, l'editor di query consente di scegliere un valore per definire la condizione.

Le condizioni devono essere collegate ai valori utilizzando uno dei seguenti operatori.

<table> 
 <thead> 
  <tr> 
   <th> Operatore<br /> </th> 
   <th> Sintassi standard<br /> </th> 
   <th> Sintassi JavaScript<br /> </th> 
   <th> Descrizione<br /> </th> 
   <th> Esempio<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Uguale a</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> Il primo valore deve essere completamente identico al secondo valore.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> recupera i profili il cui cognome è 'Martin', con solo questi caratteri identici.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maggiore di</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> Il primo valore deve essere categoricamente maggiore del secondo.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> recupera i profili più vecchi di '50', quindi '51', '52', ecc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Minore</span> di <br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> Il primo valore deve essere categoricamente minore del secondo.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> recupera tutti i profili creati nel database meno di 100 giorni fa.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maggiore o uguale a</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> Il primo valore deve essere maggiore o uguale al secondo valore.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> recupera i profili di oltre 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Minore o uguale</span> a <br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> Il primo valore deve essere minore o uguale al secondo valore.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> recupera i profili di età non superiore a 60 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Diverso </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> Il primo valore deve essere diverso dal secondo.<br /> </td> 
   <td> <strong>@language != L'inglese</strong> recupera i profili che non sono stati definiti come anglofoni.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contiene</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/D<br /> </td> 
   <td> Il primo valore deve contenere il secondo valore.<br /> </td> 
   <td> <strong>@domain IN mail</strong>. In questo caso, tutti i nomi di dominio con il valore 'mail' vengono restituiti nel risultato. Di conseguenza, il nome di dominio 'gmail.com' farà parte dei risultati restituiti.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Simile</span><br /> </td> 
   <td> SIMILE<br /> </td> 
   <td> N/D<br /> </td> 
   <td> <span class="uicontrol">Analogamente</span> è molto simile all'operatore <span class="uicontrol">Contiene</span> . Consente di inserire un carattere jolly <span class="uicontrol">%</span> nel valore ricercato.<br /> </td> 
   <td> <strong>@lastName SIMILE a Mart%n</strong>. In questo caso, il carattere di sostituzione <strong>%</strong> serve come "scherzetto" per trovare il nome "Martin" nel caso ipotetico che l'ortografia non sia corretta.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Non piace</span><br /> </td> 
   <td>  NOT<br /> </td> 
   <td> N/D<br /> </td> 
   <td> È simile a <span class="uicontrol">Like</span>. Consente di non recuperare il valore immesso. Anche in questo caso, il valore immesso deve contenere il carattere jolly <span class="uicontrol">%</span> .<br /> </td> 
   <td> <strong>@lastName NON Smi%h</strong>. Qui i destinatari corrispondono al nome 'Smi%h' (quindi Smith, ecc.) non vengono restituiti come risultato.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">È vuoto</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/D<br /> </td> 
   <td> Il primo valore deve corrispondere a un valore vuoto.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> recupera tutti i profili il cui numero di telefono cellulare non è stato fornito.<br /> </td> 
  </tr> 
 </tbody> 
</table>

