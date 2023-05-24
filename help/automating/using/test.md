---
title: Test
description: L’attività Test attiva una transizione basata su un suo risultato.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 62a064f7-6d0b-49ca-9834-eccb5bf42496
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 82%

---

# Attività Test{#test}

## Descrizione {#description}

![](assets/test.png)

L’ attività **[!UICONTROL Test]** attiva una transizione basata su un suo risultato.

## Contesto di utilizzo {#context-of-use}

Un’attività **Test** abilita la prima transizione che soddisfa la condizione associata.

Se non viene soddisfatta alcuna condizione e se l’opzione **Usa transizione predefinita** è attivata, viene impostata una transizione predefinita.

![](assets/wkf_test_activity_example.png)

Le condizioni possono basarsi su **funzioni** o su **variabili**, ad esempio variabili di eventi dichiarate nell’attività **[!UICONTROL External signal]** del flusso di lavoro.

**Argomenti correlati:**

* [Elenco delle funzioni](../../automating/using/list-of-functions.md)
* [Chiamata di un flusso di lavoro con parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Test]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Definisci gli attributi di ciascuna condizione:

   Durante la modifica del campo **[!UICONTROL Condition]**, due pulsanti forniscono informazioni utili per richiamare variabili di eventi e modificare espressioni combinando variabili e funzioni:

   * ![](assets/extsignal_picker.png): seleziona la variabile degli eventi tra tutte le variabili disponibili nel flusso di lavoro (vedi [questa pagina](../../automating/using/customizing-workflow-external-parameters.md)).

      Ad esempio, puoi controllare il numero di file scaricati dopo un’ [Trasferimento file](../../automating/using/transfer-file.md) attività tramite **[!UICONTROL filesCount]** variabile.

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): modifica le espressioni con una combinazione di variabili e funzioni. Per ulteriori informazioni sull’editor espressioni, consulta [questa sezione](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)
