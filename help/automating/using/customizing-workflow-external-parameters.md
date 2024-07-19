---
title: Personalizzazione di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '810'
ht-degree: 0%

---

# Personalizzazione di un flusso di lavoro con parametri esterni {#customizing-a-workflow-with-external-parameters}

Una volta attivato il flusso di lavoro, i parametri vengono acquisiti nelle variabili degli eventi e possono essere utilizzati per personalizzare le attività del flusso di lavoro.

Possono essere utilizzati, ad esempio, per definire il pubblico da leggere nell&#39;attività **[!UICONTROL Read audience]**, il nome del file da trasferire nell&#39;attività **[!UICONTROL Transfer file]** e così via. (vedi [questa pagina](../../automating/using/customizing-workflow-external-parameters.md)).

## Utilizzo delle variabili di eventi {#using-events-variables}

Le variabili di eventi vengono utilizzate in un&#39;espressione che deve rispettare la [sintassi standard](../../automating/using/advanced-expression-editing.md#standard-syntax).

La sintassi per l&#39;utilizzo delle variabili di eventi deve seguire il formato seguente e utilizzare il nome del parametro definito nell&#39;attività **[!UICONTROL External signal]** (vedere [Dichiarazione dei parametri nell&#39;attività External signal](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

In questa sintassi, la funzione **$** restituisce il tipo di dati **string**. Se si desidera specificare un altro tipo di dati, utilizzare le funzioni seguenti:

* **$long**: numero intero.
* **$float**: numero decimale.
* **$booleano**: true/false.
* **$datetime**: timestamp.

Quando si utilizza una variabile in un’attività, l’interfaccia fornisce assistenza per chiamarla.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): selezionare la variabile degli eventi tra tutte le variabili disponibili nel flusso di lavoro.

  ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): modificare le espressioni combinando variabili e funzioni (vedere [questa pagina](../../automating/using/advanced-expression-editing.md)).

  ![](assets/wkf_test_activity_variables_expression.png)

  Questo elenco fornisce funzioni che ti consentono di eseguire filtri complessi. Queste funzioni sono descritte in [questa sezione](../../automating/using/list-of-functions.md).

  È inoltre possibile utilizzare le funzioni seguenti, disponibili in tutte le attività che consentono di utilizzare variabili di eventi dopo la chiamata di un flusso di lavoro con parametri esterni (vedere [questa sezione](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

  | Nome | Descrizione | Sintassi |
  | ---------|----------|---------|
  | EndWith | Indica se una stringa (primo parametro) termina con una stringa specifica (secondo parametro). | EndWith(&lt;Stringa>,&lt;Stringa>) |
  | startWith | Indica se una stringa (primo parametro) inizia con una stringa specifica (secondo parametro). | startWith(&lt;Stringa>,&lt;Stringa>) |
  | Extract | Restituisce i primi caratteri di una stringa utilizzando un separatore. | Extract(&lt;Stringa>,&lt;Separatore>) |
  | ExtractRight | Restituisce gli ultimi caratteri di una stringa utilizzando un separatore. | ExtractRight(&lt;Stringa>,&lt;Separatore>) |
  | DateFormat | Formatta una data utilizzando il formato specificato nel secondo parametro (ad esempio: &#39;%4Y%2M%2D&#39;) | DateFormat(&lt;Data>,&lt;Formato>) |
  | NomeFile | Restituisce il nome di un percorso di file. | FileName(&lt;Stringa>) |
  | FileExt | Restituisce l&#39;estensione di un percorso di file. | FileExt(&lt;Stringa>) |
  | GetOption | Restituisce il valore della funzione specificata. | GetOption(&lt;nomeOpzione>) |
  | IsNull | Indica se una stringa o una data è null. | IsNull(&lt;Stringa/data>) |
  | UrlUtf8Encode | Codifica un URL in UTF8. | UrlUtf8Encode(&lt;Stringa>) |

## Personalizzazione di attività con variabili di eventi {#customizing-activities-with-events-variables}

Le variabili di eventi possono essere utilizzate per personalizzare diverse attività, elencate nella sezione seguente. Per ulteriori informazioni su come chiamare una variabile da un&#39;attività, consulta [questa sezione](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

Attività **[!UICONTROL Read audience]**: definisci il pubblico di destinazione in base alle variabili degli eventi. Per ulteriori informazioni su come utilizzare l&#39;attività, consulta [questa sezione](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

Attività **[!UICONTROL Test]**: crea condizioni in base alle variabili degli eventi. Per ulteriori informazioni su come utilizzare l&#39;attività, consulta [questa sezione](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

Attività **[!UICONTROL Transfer file]**: personalizzare il file da trasferire in base alle variabili degli eventi. Per ulteriori informazioni su come utilizzare l&#39;attività, consulta [questa sezione](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

Attività **[!UICONTROL Query]**: è possibile fare riferimento ai parametri in una query utilizzando espressioni che combinano variabili di eventi e funzioni. Per eseguire questa operazione, aggiungere una regola, quindi fare clic sul collegamento **[!UICONTROL Advanced mode]** per accedere alla finestra di modifica delle espressioni (vedere [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)).

Per ulteriori informazioni su come utilizzare l&#39;attività, consulta [questa sezione](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** attività: personalizza le consegne in base alle variabili degli eventi.

>[!NOTE]
>
>I valori dei parametri di consegna vengono recuperati a ogni preparazione della consegna.
>
>La preparazione delle consegne ricorrenti si basa sul **periodo di aggregazione** della consegna. Ad esempio, se il periodo di aggregazione è &quot;per giorno&quot;, la consegna verrà ripreparata solo una volta al giorno. Se il valore di un parametro di consegna viene modificato durante il giorno, non verrà aggiornato nella consegna, in quanto è già stato preparato una volta.
>
>Se prevedi di chiamare il flusso di lavoro più volte al giorno, utilizza l&#39;opzione [!UICONTROL No aggregation], in modo che i parametri di consegna vengano aggiornati ogni volta. Per ulteriori informazioni sulla configurazione delle consegne ricorrenti, consulta [questa sezione](/help/automating/using/email-delivery.md#configuration).

Per personalizzare una consegna in base alle variabili degli eventi, devi innanzitutto dichiarare nell’attività di consegna le variabili che desideri utilizzare:

1. Selezionare l&#39;attività, quindi fare clic sul pulsante ![](assets/dlv_activity_params-24px.png) per accedere alle impostazioni.
1. Seleziona la scheda **[!UICONTROL General]**, quindi aggiungi le variabili degli eventi che saranno disponibili come campi di personalizzazione nella consegna.

   ![](assets/extsignal_activities_delivery.png)

1. Fai clic sul pulsante **[!UICONTROL Confirm]**.

Le variabili degli eventi dichiarati sono ora disponibili dall’elenco dei campi di personalizzazione. Puoi utilizzarli nella consegna per eseguire le azioni seguenti:

* Definisci il nome del modello da utilizzare per la consegna.

  >[!NOTE]
  >
  >Questa azione è disponibile solo per **consegne ricorrenti**.

  ![](assets/extsignal_activities_template.png)

* Personalizzare la consegna: quando si seleziona un campo di personalizzazione per configurare una consegna, le variabili degli eventi sono disponibili nell&#39;elemento **[!UICONTROL Workflow parameters]**. Puoi utilizzarli come qualsiasi campo di personalizzazione, ad esempio per definire l’oggetto della consegna, il mittente e così via.

  La personalizzazione della consegna è descritta in [questa sezione](../../designing/using/personalization.md).

  ![](assets/extsignal_activities_perso.png)

**Codici di segmento**: definisci il codice di segmento in base alle variabili di eventi.

>[!NOTE]
>
>Questa azione può essere eseguita da qualsiasi attività che ti consente di definire un codice di segmento come, ad esempio, **[!UICONTROL Query]** o **[!UICONTROL Segmentation]** attività.

![](assets/extsignal_activities_segment.png)

**Etichetta di consegna**: definisci l&#39;etichetta di consegna in base alle variabili degli eventi.

![](assets/extsignal_activities_label.png)
