---
title: Calcolo della data di invio
seo-title: Calcolo della data di invio
description: Calcolo della data di invio
seo-description: Scopri come inviare un messaggio in una data e in un'ora specifiche.
page-status-flag: never-activated
uuid: fbbb 37 a 0-7257-4407-a 4 c 9-f 76 bf 04460 d 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: sheduling-messages
discoiquuid: 02 a 87 cc 6-c 40 c -44 fe-bb 4 e-b 68870 a 4859 b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 28abc1e8aa31f3e0c7f09926f34a977d4c491fd8

---


# Computing the sending date{#computing-the-sending-date}

Puoi definire una formula per inviare il messaggio a ogni destinatario in una data e in un'ora specifiche.

## Customizing date formula {#customizing-date-formula}

Ad esempio, è possibile utilizzare l'ottimizzazione dell'ora di invio durante il processo di scorrimento.

Quando le e-mail vengono inviate utilizzando una nuova piattaforma, i provider di servizi Internet (ISP) sospettano di indirizzi IP non riconosciuti. Se vengono inviati improvvisamente numerosi messaggi e-mail, gli ISP spesso li contrassegnano come spam.

Per evitare di essere contrassegnati come spam, potete aumentare progressivamente il volume inviato distribuendo grandi quantità di e-mail in orari diversi. Questo dovrebbe garantire lo sviluppo uniforme della fase di avvio e consentire di ridurre il tasso complessivo di indirizzi non validi.

Ad esempio, potete segmentare il pubblico di destinazione in modo casuale per inviarlo in cinque batch. Invierete un primo batch che rappresenti il 10% del pubblico di destinazione il 1 giugno alle 10:00, un secondo batch 24 ore dopo con il 15% dell'audience e così via.

Potete pianificare questo utilizzo mediante un flusso di lavoro.

![](assets/send-time_opt_workflow1.png)

1. Accedi all'elenco delle attività di marketing e crea un nuovo flusso di lavoro. See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Drag and drop a **Query** activity into your workflow and open it. See the [Query](../../automating/using/query.md) section.
1. Select an audience, for example all your Gold customers and click **[!UICONTROL Confirm]** to save the query.
1. Drag and drop a **Segmentation** activity into your workflow and open it. See the [Segmentation](../../automating/using/segmentation.md) section.
1. Definire cinque segmenti. Per ogni segmento:

   * Fill in the **[!UICONTROL Segment code]** field: manually enter the desired date and time for sending the message.

      Ad esempio, potete inviare il primo batch il 1 giugno alle 10:00 GMT +1. Use the following format: **YYYY-MM-DD hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      To send the next batch the day after, enter **2017-06-02 10:00:00+01** for the second segment.

      Per i segmenti rimanenti, definire i batch successivi come segue:

      * **2017-06-03 10:00:00+01**
      * **2017-06-04 10:00:00+01**
      * **2017-06-05 10:00:00+01**
   * Make sure you select the **[!UICONTROL Limit the population of this segment]** option.

      In the **[!UICONTROL Limitation]** tab, select **[!UICONTROL Random sampling]** and enter the desired percentage for each segment: 10 for the first batch, 15 for the second, and so on.

      ![](assets/send-time_opt_segment_limitation.png)


1. Once all segments are defined, select **[!UICONTROL Generate all segments in the same transition]** and click **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Drag and drop an **Email delivery** activity into your workflow and open it. See the [Email delivery](../../automating/using/email-delivery.md) section.
1. Click the **[!UICONTROL Schedule]** section in the email dashboard and select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. In the **[!UICONTROL Start sending from]** field, define a contact date.
1. From the send time optimization drop-down menu, choose **[!UICONTROL Send at a custom date defined by a formula]**.
1. Click the **[!UICONTROL Edit an expression]** button of the **[!UICONTROL Custom date formula]** field.

   ![](assets/send-time_opt_formula_define.png)

1. Create the following expression using the **[!UICONTROL ToDateTime]** function and the **[!UICONTROL Segment code]** field. È inoltre possibile digitare direttamente l'espressione, ma assicurarsi di utilizzare sintassi e ortografia corrette.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   The **[!UICONTROL ToDateTime]** function transforms the segment code from a text string to a date and time value.

   Confermate l'espressione per tornare alla schermata precedente.

   ![](assets/send-time_opt_formula_define_segment.png)

   In the **[!UICONTROL Schedule]** window, the custom date formula is displayed as follows:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Confermate la pianificazione, salvate la distribuzione ed eseguite il flusso di lavoro.

La consegna verrà inviata progressivamente a tutti i destinatari con targeting oltre cinque giorni.

>[!NOTE]
>
>Accertatevi che tutte le date siano in futuro quando confermate l'invio. In caso contrario, il messaggio verrà inviato non appena l'invio viene confermato.

## Using an expression {#using-an-expression}

L'ottimizzazione dell'ora di invio è utile anche per campagne che coinvolgono un call center. Puoi assicurarvi che tutti i messaggi non vengano ricevuti allo stesso tempo. Questo consente all'organizzazione di elaborare il numero di chiamate in base alla capacità.

Ad esempio, potete inviare un'e-mail invitando i clienti a contattare un call center per ottenere un'offerta promozionale. Per evitare il call center, decidi di segmentare in modo casuale il pubblico di destinazione per inviare l'e-mail in quattro batch.

Potete pianificare questo utilizzo mediante un flusso di lavoro.

![](assets/send-time_opt_workflow2.png)

1. Accedi all'elenco delle attività di marketing e crea un nuovo flusso di lavoro. See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Drag and drop a **Query** activity into your workflow and open it. See the [Query](../../automating/using/query.md) section.
1. Select an audience, for example over 35 profiles and click **[!UICONTROL Confirm]** to save the query.
1. Drag and drop a **Segmentation** activity into your workflow and open it. See the [Segmentation](../../automating/using/segmentation.md) section.
1. Definire quattro segmenti. Per ogni segmento:

   * Definite i codici dei segmenti come segue:

      * 8:00 AM - 10:00 AM: **0**. Il messaggio viene inviato al primo trimestre della popolazione di destinazione alle 8:00 (data di contatto).
      * 10:00 AM - 12:00 PM: **2**. Il messaggio viene inviato al secondo trimestre della popolazione di destinazione alle 10:00 (data di contatto + 2 ore).
      * 2:00 PM - 4:00 PM: **6**. Il call center viene chiuso tra le 12:00 PM e le 2:00 PM, il messaggio verrà inviato al terzo trimestre della popolazione di destinazione alle 2:00 PM (data di contatto + 6 ore).
      * 4:00 PM - 6:00 PM: **8**. Il messaggio viene inviato all'ultimo trimestre della popolazione di destinazione alle 4:00 PM (data di contatto + 8 ore).
      >[!NOTE]
      >
      >La data di contatto sarà definita nell'attività di consegna e-mail più avanti nel flusso di lavoro.

   * Make sure you select the **[!UICONTROL Limit the population of this segment]** option.
   * In the **[!UICONTROL Limitation]** tab, select **[!UICONTROL Random sampling]** and enter the desired percentage for each segment: **25**.


1. Once all segments are defined, select **[!UICONTROL Generate all segments in the same transition]** and click **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Drag and drop an **Email delivery** activity into your workflow and open it. See the [Email delivery](../../automating/using/email-delivery.md) section.
1. Click the **[!UICONTROL Schedule]** section in the email dashboard.
1. Select **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. In the **[!UICONTROL Start sending from]** field, define a contact date.

   In questo esempio, seleziona il 25 maggio alle 8:00.

1. From the send time optimization drop-down menu, choose **[!UICONTROL Send at a custom date defined by a formula]** and click the **[!UICONTROL Edit an expression]** button.

   ![](assets/send-time_opt_formula_expression.png)

1. In the **[!UICONTROL Expression editor]**, set the date and the segment codes to compute the data for each customer.

   In the list of functions, select **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   In the available fields, select **[!UICONTROL Current delivery]** &gt; **[!UICONTROL Delivery scheduling]** &gt; **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   This enables you to retrieve the date and time specified in the **[!UICONTROL Start sending from]** field.

   In the list of functions, select **[!UICONTROL ToInteger]**. In the available fields, select **[!UICONTROL Additional data]** &gt; **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   Questo consente di recuperare i numeri specificati nei codici dei segmenti.

   Dovresti ottenere la formula seguente:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Confermate il salvataggio dell'espressione. Confermate la pianificazione, salvate la distribuzione ed eseguite il flusso di lavoro.

* Il primo segmento riceve il messaggio sulla data di contatto (25 maggio alle 8:00 AM).
* Il secondo segmento riceve il messaggio due ore dopo (25 maggio alle 10:00 AM).
* Il terzo segmento riceve il messaggio sei ore dopo (25 maggio alle 2:00 PM).
* Il quarto segmento riceve il messaggio otto ore dopo (25 maggio alle 4:00 PM).

