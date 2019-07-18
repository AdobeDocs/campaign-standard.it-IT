---
title: Test
seo-title: Test
description: Test
seo-description: L'attività Test abilita una transizione in base a un risultato di test.
page-status-flag: never-activated
uuid: 1562 ec 7 a -253 a -4 f 4 f-b 66 a-c 2948 b 57775 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 2650 bf 1 f -0 bce -4049-a 226-2369 f 6666 b 95
context-tags: jstest, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Test{#test}

## Description {#description}

![](assets/test.png)

The **[!UICONTROL Test]** activity enables a transition based on a test result.

## Context of use {#context-of-use}

A **Test** activity activates the first transition that satisfies the condition associated to it.

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

Conditions can be based on **functions**, or on **variables**, for example events variables that have been declared into the workflow's **[!UICONTROL External signal]** activity.

**Argomenti correlati:**

* [Elenco delle funzioni](../../automating/using/list-of-functions.md)
* [Chiamata di un flusso di lavoro con parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Test]** activity into the workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Definire gli attributi di ciascuna condizione:

   When editing the **[!UICONTROL Condition]** field, two buttons provide help to call events variables and edit expressions combining variables and functions:

   * ![](assets/extsignal_picker.png): Selezionate la variabile degli eventi tra tutte le variabili disponibili nel flusso di lavoro (consultate [Personalizzazione di un flusso di lavoro con parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): modificare le espressioni combinando variabili e funzioni. For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

