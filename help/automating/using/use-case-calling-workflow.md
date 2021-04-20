---
solution: Campaign Standard
product: campaign
title: Chiamata di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 1%

---


# Caso d’uso {#use-case}

Il caso d’uso seguente mostra come chiamare il flusso di lavoro con i parametri all’interno dei flussi di lavoro.

L’obiettivo è quello di attivare un flusso di lavoro da una chiamata API con parametri esterni. Questo flusso di lavoro caricherà i dati nel database da un file e creerà un pubblico associato. Una volta creato il pubblico, viene attivato un secondo flusso di lavoro per inviare un messaggio personalizzato con i parametri esterni definiti nella chiamata API.

Per eseguire questo caso d’uso, devi eseguire le azioni seguenti:

1. **Effettua una** chiamata API per attivare il flusso di lavoro 1 con parametri esterni. Vedere [Passaggio 1: Configurazione della chiamata API](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **Crea flusso di lavoro 1**: il flusso di lavoro trasferirà un file e lo caricherà nel database. In seguito, verificherà se i dati sono vuoti o meno e alla fine salverà i profili in un pubblico. Infine, attiverà il flusso di lavoro 2. Vedere [Passaggio 2: Configurazione del flusso di lavoro 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Crea flusso di lavoro 2**: il flusso di lavoro leggerà il pubblico creato nel flusso di lavoro 1, quindi invierà un messaggio personalizzato ai profili con un codice di segmento personalizzato con i parametri. Vedere [Passaggio 3: Configurazione del flusso di lavoro 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Prerequisiti {#prerequisites}

Prima di configurare i flussi di lavoro, devi creare i flussi di lavoro 1 e 2 con un’attività **[!UICONTROL External signal]** in ciascuno di essi. In questo modo, potrai eseguire il targeting di queste attività di segnale durante la chiamata dei flussi di lavoro.

## Passaggio 1: Configurazione della chiamata API {#step-1--configuring-the-api-call}

Effettua una chiamata API per attivare il flusso di lavoro 1 con i parametri . Per ulteriori informazioni sulla sintassi della chiamata API, consulta la documentazione [Campaign Standard REST APIs](../../api/using/triggering-a-signal-activity.md).

Nel nostro caso, vogliamo chiamare il flusso di lavoro con i parametri seguenti:

* **fileToTarget**: il nome del file da importare nel database.
* **discountDesc**: la descrizione da visualizzare nella consegna per lo sconto.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

## Passaggio 2: Configurazione del flusso di lavoro 1 {#step-2--configuring-workflow-1}

Il flusso di lavoro 1 verrà generato come segue:

* **[!UICONTROL External signal]** attività: dove i parametri esterni devono essere dichiarati per essere utilizzati all’interno del flusso di lavoro.
* **[!UICONTROL Transfer file]** attività: importa il file con il nome definito nei parametri .
* **[!UICONTROL Load file]** attività: carica i dati dal file importato nel database.
* **[!UICONTROL Update data]** attività: inserire o aggiornare il database con i dati del file importato.
* **[!UICONTROL Test]** attività: verifica se sono presenti dati importati.
* **[!UICONTROL Save audience]** attività: se il file contiene dati, salva i profili in un pubblico.
* **[!UICONTROL End activity]** attività: chiama Workflow 2 con i parametri che desideri utilizzare al suo interno.

![](assets/extsignal_uc_wkf1.png)

Per configurare il flusso di lavoro, effettua le seguenti operazioni:

1. Dichiara i parametri definiti nella chiamata API. A questo scopo, apri l’attività **[!UICONTROL External signal]**, quindi aggiungi i nomi e i tipi dei parametri.

   ![](assets/extsignal_uc1.png)

1. Aggiungi un&#39;attività **[!UICONTROL Transfer file]** per importare dati nel database. A questo scopo, trascina e rilascia l&#39;attività, aprila, quindi seleziona la scheda **[!UICONTROL Protocol]** .
1. Seleziona l&#39;opzione **[!UICONTROL Use a dynamic file path]**, quindi utilizza il parametro **fileToTarget** come file da trasferire:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Carica i dati dal file nel database.

   A questo scopo, trascina e rilascia un’attività **[!UICONTROL Load file]** nel flusso di lavoro, quindi configurala in base alle tue esigenze.

1. Inserire e aggiornare il database con i dati del file importato.

   A questo scopo, trascina e rilascia un’attività **[!UICONTROL Update data]**, quindi seleziona la scheda **[!UICONTROL Identification]** per aggiungere un criterio di riconciliazione (nel nostro caso il campo **email** ).

   ![](assets/extsignal_uc3.png)

1. Seleziona la scheda **[!UICONTROL Fields to update]** , quindi specifica i campi da aggiornare nel database (nel nostro caso i campi **firstname** e **email** ).

   ![](assets/extsignal_uc4.png)

1. Controlla se i dati vengono recuperati dal file. A questo scopo, trascina e rilascia un’attività **[!UICONTROL Test]** nel flusso di lavoro, quindi fai clic sul pulsante **[!UICONTROL Add an element]** per aggiungere una condizione.
1. Denomina e definisci la condizione. Nel nostro caso, vogliamo verificare se la transizione in uscita contiene dati con la sintassi seguente:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Se i dati vengono recuperati, salvarli in un pubblico. A questo scopo, aggiungi un’attività **[!UICONTROL Save audience]** alla transizione **Target non vuota**, quindi aprila.
1. Seleziona l&#39;opzione **[!UICONTROL Use a dynamic label]**, quindi utilizza il parametro **fileToTarget** come etichetta del pubblico:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Trascina e rilascia un’attività **[!UICONTROL End]** che chiamerà Flusso di lavoro 2 con parametri, quindi aprila.
1. Seleziona la scheda **[!UICONTROL External signal]** , quindi specifica il flusso di lavoro da attivare e l’attività del segnale associata.
1. Definisci i parametri da utilizzare all’interno del flusso di lavoro 2 e i relativi valori associati.

   Nel nostro caso, vogliamo trasmettere i parametri originariamente definiti nella chiamata API (**fileToTarget** e **discountDesc**) e un parametro aggiuntivo **segmentCode** con un valore costante (&quot;20% di sconto&quot;).

   ![](assets/extsignal_uc7.png)

Il flusso di lavoro 1 è configurato, ora puoi generare il flusso di lavoro 2. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

## Passaggio 3: Configurazione del flusso di lavoro 2 {#step-3--configuring-workflow-2}

Il flusso di lavoro 2 verrà generato come segue:

* **[!UICONTROL External signal]** attività: dove i parametri devono essere dichiarati per poter essere utilizzati all’interno del flusso di lavoro.
* **[!UICONTROL Read audience]** attività: legge il pubblico salvato nel flusso di lavoro 1.
* **[!UICONTROL Email delivery]** attività: invia un messaggio ricorrente al pubblico di destinazione, personalizzato con parametri.

![](assets/extsignal_uc_wkf2.png)

Per configurare il flusso di lavoro, effettua le seguenti operazioni:

1. Dichiara i parametri definiti nel flusso di lavoro 1.

   A questo scopo, apri l’attività **[!UICONTROL External signal]**, quindi aggiungi il nome e il tipo di ogni parametro definito nell’attività **[!UICONTROL End]** del flusso di lavoro 1.

   ![](assets/extsignal_uc8.png)

1. Utilizza il pubblico salvato nel Flusso di lavoro 1. A questo scopo, trascina e rilascia un’attività **[!UICONTROL Read audience]** nel flusso di lavoro, quindi aprila.
1. Seleziona l&#39;opzione **[!UICONTROL Use a dynamic audience]**, quindi utilizza il parametro **fileToTarget** come nome del pubblico da leggere:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Denomina la transizione in uscita in base al parametro **segmentCode** .

   A questo scopo, seleziona la scheda **[!UICONTROL Transition]** , quindi l’opzione **[!UICONTROL Use a dynamic segment code]** .

1. Utilizza il parametro **segmentCode** come nome della transizione in uscita:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Trascina e rilascia un’attività **[!UICONTROL Email delivery]** per inviare un messaggio al pubblico.
1. Identifica i parametri da utilizzare nel messaggio per personalizzarlo con il parametro **discountDesc** . A questo scopo, apri le opzioni avanzate dell’attività, quindi aggiungi il nome e il valore del parametro.

   ![](assets/extsignal_uc10b.png)

1. Ora puoi configurare il messaggio. Apri l’attività, quindi seleziona **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Seleziona il modello da utilizzare, quindi definisci le proprietà dell’e-mail in base alle tue esigenze.
1. Utilizza il parametro **discountDesc** come campo di personalizzazione. A questo scopo, selezionalo dall’elenco dei campi di personalizzazione.

   ![](assets/extsignal_uc13.png)

1. Ora puoi completare la configurazione del messaggio, quindi inviarlo come di consueto.

   ![](assets/extsignal_uc14.png)

## Esecuzione dei flussi di lavoro {#executing-the-workflows}

Una volta generati i flussi di lavoro, puoi eseguirli. Assicurati che i due flussi di lavoro siano avviati prima di eseguire la chiamata API.
