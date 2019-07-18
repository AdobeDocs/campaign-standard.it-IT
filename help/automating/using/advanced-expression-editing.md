---
title: Modifica avanzata delle espressioni
seo-title: Modifica avanzata delle espressioni
description: Modifica avanzata delle espressioni
seo-description: La procedura guidata di creazione di query consente di definire espressioni avanzate.
page-status-flag: never-activated
uuid: a 635 f 999-27 ce -41 e 0-a 88 c -8 a 3882 e 31 efe
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: filtering-data
discoiquuid: 4375153 c -0621-4 d 4 c-bfcc -66 d 157 f 04 f 6 c
context-tags: Queryfilter, overview; audience, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Advanced expression editing{#advanced-expression-editing}

## About advanced expression editing {#about-advanced-expression-editing}

La modifica di un'espressione implica l'immissione manuale di condizioni per formare una regola.

Questa modalità consente di utilizzare funzioni avanzate. Queste funzioni consentono di manipolare i valori utilizzati per eseguire query specifiche quali la manipolazione di date, stringhe, campi numerici, ordinamento ecc.

Durante la modifica dell'espressione è inoltre possibile utilizzare variabili di eventi. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

Potete modificare le espressioni per:

* Define a query, via the **[!UICONTROL Advanced mode]** option which is available when a rule is added.

   ![](assets/expression_editor_2.png)

* Modificare un'espressione in un flusso di lavoro. Ad esempio, per aggiungere dati aggiuntivi a un'attività.
* Modificate una condizione di visibilità per definire il modo in cui viene visualizzato un blocco nell'editor di contenuto HTML. In questo caso, l'espressione viene modificata in formato javascript e non offre l'utilizzo di funzioni avanzate come standard.

## Edit an expression {#edit-an-expression}

L'edizione con espressione avanzata consente di definire manualmente un'espressione che soddisfa specifiche esigenze.

Le espressioni di modifica possono essere utilizzate nella finestra Pubblico quando create un'e-mail o in un'attività Query durante la creazione di un flusso di lavoro.

1. Access the expression editing window via one of the methods detailed in the [About advanced expression editing](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) section. Comprende i seguenti elementi:

   * Campo di input in cui è definita l'espressione.
   * The list of available fields that can be used in the expression and correspond to the targeting dimension of the query (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * Elenco delle funzioni disponibili, ordinate per categoria.
   ![](assets/expression_editor_1.png)

1. Modificare l'espressione immettendo un'espressione direttamente nel campo corrispondente o utilizzando gli elenchi dei campi e delle funzioni disponibili.

   Facendo doppio clic su un campo o un'espressione, quest'ultimo viene aggiunto all'espressione in cui è posizionato il cursore.

   È possibile utilizzare le variabili degli eventi dei flussi di lavoro per creare un'espressione. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. Se necessario, assegna alla regola un nome specifico. Il nome immesso verrà visualizzato come nome della regola nell'area di lavoro dell'editor query.

La modifica di un'espressione consente di personalizzare l'espressione Audiences per eseguire il targeting della popolazione in base alle esigenze.

**Argomenti correlati:**

* [Sintassi espressione](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Expression Syntax {#expression-syntax}

### Standard syntax {#standard-syntax}

Le espressioni standard sono costituite da una o più condizioni che rispettano i seguenti elementi sintassi:

* Each condition takes the form of **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; valore 1 &gt;** è un campo o una funzione. For example **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt; Operatore di confronto &gt;** è uno degli operatori elencati nella [sezione degli operatori](../../automating/using/advanced-expression-editing.md#comparison-operators) di confronto. This operator defines the comparison method between **&lt;value1&gt;** and **&lt;value2&gt;**.
   * **&lt; valore 2 &gt;** è un campo, una funzione o un valore che viene immesso manualmente.
   >[!NOTE]
   >
   >The **&lt;value1&gt;** and **&lt;value2&gt;** type data must be identical. For example, if **&lt;value1&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* Se si desidera utilizzare più condizioni, è possibile combinarle utilizzando operatori logici.

   * **[!UICONTROL AND]**: due condizioni vengono intersecate.
   * **[!UICONTROL OR]**: due condizioni sono combinate.

Ad esempio:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

In questo esempio, i profili la cui data di creazione si trova nel mese e nell'anno in corso sono mirati.

### JavaScript syntax {#javascript-syntax}

Quando si definiscono le condizioni di visibilità di un blocco di testo dell'editor di contenuto HTML, è necessario utilizzare un'espressione con sintassi tipo javascript.

Le espressioni javascript sono costituite da una o più condizioni e utilizzano i seguenti elementi sintassi:

* Each condition takes the form of **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; context &gt;** è un campo o una funzione che consente di specificare il contesto. For example **context.profile.@email** for a profile's email address or **context.profile.firstName.length()** for the number of characters of a profile's first name.
   * **&lt; Operatore di confronto &gt;** è uno degli operatori elencati nella [sezione degli operatori](../../automating/using/advanced-expression-editing.md#comparison-operators) di confronto. This operator defines the comparison method between **&lt;context&gt;** and **&lt;value2&gt;**.
   * **&lt; valore 2 &gt;** è un campo, una funzione o un valore che viene immesso manualmente.
   >[!NOTE]
   The **&lt;context&gt;** and **&lt;value2&gt;** type data must be identical. For example, if **&lt;context&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* Se si desidera utilizzare più condizioni, è possibile combinarle utilizzando operatori logici.

   * **[!UICONTROL &&]**: due condizioni vengono intersecate.
   * **[!UICONTROL ||]**: due condizioni sono combinate.

Ad esempio:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In this example, profiles older than 21 years of age and whose first name has been provided (symbolized by the fact that the **firstName** field contains at least one character).

## Comparison operators {#comparison-operators}

Per alcune regole, l'editor query consente di scegliere un valore per definire la condizione.

Le condizioni devono essere collegate ai valori utilizzando uno dei seguenti operatori.

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standard syntax<br /> </th> 
   <th> JavaScript syntax<br /> </th> 
   <th> Description<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Uguale a</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> The first value must be completely identical to the second value.<br /> </td> 
   <td> <strong>@ Lastname = Martin</strong> recupera profili il cui cognome è'Martin ', con solo questi caratteri identici.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maggiore di</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> The first value must categorically be more than the second value.<br /> </td> 
   <td> <strong>@ age &gt; 50</strong> recupera i profili che sono precedenti a '50 ', quindi «51»,'52 ', ecc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Minore di</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> The first value must categorically be less than the second value.<br /> </td> 
   <td> <strong>@ created &lt; daysago (100)</strong> recupera tutti i profili creati nel database meno di 100 giorni fa.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Maggiore o uguale a</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> The first value must be more than or equal to the second value.<br /> </td> 
   <td> <strong>@ age &gt; = 30</strong> recupera profili di età non inferiore a 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Minore o uguale a</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> The first value must be less than or equal to the second value.<br /> </td> 
   <td> <strong>@ age &lt; = 60</strong> recupera i profili di età non inferiore a 60.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Diversi </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> The first value must be different from the second value.<br /> </td> 
   <td> <strong>@ language!= English</strong> retrieves profiles that have not been defined as English speaking.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contiene</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must contain the second value.<br /> </td> 
   <td> <strong>@ domain IN. </strong> Qui vengono restituiti nel risultato tutti i nomi di dominio con il valore «posta». Consequently, the 'gmail.com' domain name will make up part of the returned results.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Come</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">Simile all</span> 'operatore <span class="uicontrol">Contiene</span> . It lets you insert a <span class="uicontrol">%</span> wild card character in the value that is being searched.<br /> </td> 
   <td> <strong>@ Lastname LIKE Mart % n</strong>. Here, the substitution character <strong>%</strong> serves as a "joker" to find the name "Martin" in the hypothetical case that the spelling is not correct.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Non come</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. Consente di non recuperare il valore immesso. Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@ Lastname NOT Smi % h</strong>. Qui i destinatari corrispondono al nome'Smi % h '(so Smith, ecc.) are not returned as a result.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">È vuoto</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must correspond to an empty value.<br /> </td> 
   <td> <strong>@ Mobilephone IS NULL</strong> recupera tutti i profili il cui numero di telefono cellulare non è stato fornito.<br /> </td> 
  </tr> 
 </tbody> 
</table>

