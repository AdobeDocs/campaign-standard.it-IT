---
title: Chiamata di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 5%

---


# Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

Una volta attivato il flusso di lavoro, i parametri vengono assimilati nelle variabili degli eventi e possono essere utilizzati per personalizzare le attività del flusso di lavoro.

Possono, ad esempio, essere utilizzati per definire il pubblico da leggere nell&#39; **[!UICONTROL Read audience]** attività, il nome del file da trasferire nell&#39; **[!UICONTROL Transfer file]** attività, ecc. (see [](../../automating/using/customizing-workflow-external-parameters.md)).

## Uso delle variabili di evento {#using-events-variables}

Le variabili evento sono utilizzate all&#39;interno di un&#39;espressione che deve rispettare la sintassi [](../../automating/using/advanced-expression-editing.md#standard-syntax)Standard.

La sintassi per l&#39;utilizzo delle variabili di evento deve seguire il formato seguente e utilizzare il nome del parametro definito nell&#39; **[!UICONTROL External signal]** attività (vedere [Dichiarazione dei parametri nell&#39;attività](../../automating/using/declaring-parameters-external-signal.md)di segnale esterno):

```
$(vars/@parameterName)
```

In questa sintassi, la funzione **$** restituisce il tipo di dati **stringa** . Per specificare un altro tipo di dati, utilizzare le seguenti funzioni:

* **$long**: numero intero.
* **$float**: numero decimale.
* **$boolean**: true/false.
* **$datetime**: timestamp.

Quando si utilizza una variabile in un&#39;attività, l&#39;interfaccia fornisce aiuto per chiamarla.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): selezionate la variabile degli eventi tra tutte le variabili disponibili nel flusso di lavoro.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): modifica le espressioni con una combinazione di variabili e funzioni. Per ulteriori informazioni sull’editor espressioni, consulta [questa sezione](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**Argomenti correlati:**

* [Modificare un’espressione](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [Sintassi standard](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Personalizzazione delle attività con le variabili degli eventi {#customizing-activities-with-events-variables}

Le variabili evento possono essere utilizzate per personalizzare diverse attività, elencate nella sezione seguente. Per ulteriori informazioni su come chiamare una variabile da un&#39;attività, consultate [questa sezione](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** activity: definire l&#39;audience di cui eseguire il targeting in base alle variabili di evento.

Per ulteriori informazioni sull&#39;utilizzo dell&#39;attività, consultate la sezione [](../../automating/using/read-audience.md)dedicata.

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** activity: creare condizioni basate su variabili di eventi.

Per ulteriori informazioni sull&#39;utilizzo dell&#39;attività, consultate la sezione [](../../automating/using/test.md)dedicata.

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** activity: personalizzare il file da trasferire in base alle variabili degli eventi.

Per ulteriori informazioni sull&#39;utilizzo dell&#39;attività, consultate la sezione [](../../automating/using/transfer-file.md)dedicata.

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** activity: in una query è possibile fare riferimento ai parametri utilizzando espressioni che combinano variabili di eventi e funzioni. A questo scopo, aggiungete una regola e fate clic sul **[!UICONTROL Advanced mode]** collegamento per accedere alla finestra di modifica delle espressioni (consultate Modifica [delle espressioni](../../automating/using/advanced-expression-editing.md)avanzate).

Per ulteriori informazioni sull&#39;utilizzo dell&#39;attività, consultate la sezione [](../../automating/using/query.md)dedicata.

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** attività: personalizzare le consegne in base alle variabili degli eventi.

>[!NOTE]
>
>I valori dei parametri di consegna vengono recuperati ogni volta che la consegna viene preparata.
>
>La preparazione delle consegne ricorrenti si basa sul periodo **di** aggregazione delle consegne. Ad esempio, se il periodo di aggregazione è &quot;per giorno&quot;, la consegna verrà preparata solo una volta al giorno. Se il valore di un parametro di consegna viene modificato durante il giorno, non verrà aggiornato nella consegna, come è già stato preparato una volta.
>
>Se prevedete di richiamare il flusso di lavoro più volte al giorno, utilizzate l&#39; [!UICONTROL No aggregation] opzione in modo che i parametri di consegna vengano aggiornati ogni volta. Per ulteriori informazioni sulla configurazione delle consegne ricorrenti, consulta [questa sezione](/help/automating/using/email-delivery.md#configuration).

Per personalizzare una consegna basata su variabili di eventi, è innanzitutto necessario dichiarare nell&#39;attività di consegna le variabili che si desidera utilizzare:

1. Selezionate l&#39;attività, quindi fate clic sul ![](assets/dlv_activity_params-24px.png) pulsante per accedere alle impostazioni.
1. Selezionate la **[!UICONTROL General]** scheda, quindi aggiungete le variabili di evento che saranno disponibili come campi di personalizzazione nella distribuzione.

   ![](assets/extsignal_activities_delivery.png)

1. Fai clic sul pulsante **[!UICONTROL Confirm]**.

Le variabili degli eventi dichiarati ora sono disponibili nell&#39;elenco dei campi di personalizzazione. Puoi utilizzarli nella consegna per eseguire le azioni seguenti:

* Definite il nome del modello da utilizzare per la consegna.

   >[!NOTE]
   >
   >Questa azione è disponibile solo per consegne **ricorrenti** .

   ![](assets/extsignal_activities_template.png)

* Personalizza la consegna: quando si seleziona un campo di personalizzazione per configurare una consegna, nell&#39; **[!UICONTROL Workflow parameters]** elemento sono disponibili variabili di eventi. Puoi usarli come qualsiasi campo di personalizzazione, ad esempio per definire l’oggetto di consegna, il mittente e così via.

   La personalizzazione della distribuzione è dettagliata in [questa sezione](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Codici** segmento: definisce il codice del segmento in base alle variabili degli eventi.

>[!NOTE]
>
>Questa azione può essere eseguita da qualsiasi attività che consente di definire un codice di segmento come, ad esempio, **[!UICONTROL Query]** o **[!UICONTROL Segmentation]** attività.

![](assets/extsignal_activities_segment.png)

**Etichetta** consegna: definire l&#39;etichetta di consegna in base alle variabili degli eventi.

![](assets/extsignal_activities_label.png)
