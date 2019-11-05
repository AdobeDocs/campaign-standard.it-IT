---
title: Test
description: L'attività Test consente una transizione basata su un risultato del test.
page-status-flag: mai attivato
uuid: 1562ec7a-253a-4f4f-b66a-c2948b5775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 2650bf1f-0bce-4049-a226-2369f666b95
context-tags: jstest,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Test{#test}

## Descrizione {#description}

![](assets/test.png)

L' **[!UICONTROL Test]** attività consente una transizione basata su un risultato di test.

## Contesto di utilizzo {#context-of-use}

Un'attività **Test** attiva la prima transizione che soddisfa la condizione associata.

Se non viene soddisfatta alcuna condizione e se l'opzione **Usa transizione** predefinita è attivata, verrà attivata una transizione predefinita.

![](assets/wkf_test_activity_example.png)

Le condizioni possono essere basate su **funzioni**, o su **variabili**, ad esempio variabili di eventi dichiarate nell' **[!UICONTROL External signal]** attività del flusso di lavoro.

**Argomenti correlati:**

* [Elenco delle funzioni](../../automating/using/list-of-functions.md)
* [Chiamata di un flusso di lavoro con parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configurazione {#configuration}

1. Trascinate un' **[!UICONTROL Test]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Definire gli attributi di ciascuna condizione:

   Durante la modifica del **[!UICONTROL Condition]** campo, due pulsanti forniscono informazioni utili per richiamare variabili di eventi e modificare espressioni combinando variabili e funzioni:

   * ![](assets/extsignal_picker.png): selezionate la variabile degli eventi tra tutte le variabili disponibili nel flusso di lavoro (consultate [Personalizzazione di un flusso di lavoro con parametri](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)esterni)

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): modificare le espressioni combinando variabili e funzioni. Per ulteriori informazioni sull'Editor espressioni, consulta [questa sezione](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

