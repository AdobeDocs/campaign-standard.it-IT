---
title: Calcolo della data di invio
description: Scopri come inviare un messaggio a una data e a un’ora specifiche.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7a0cd10a-24e6-44d1-842c-2067bfbac838
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 1%

---

# Calcolo della data di invio{#computing-the-sending-date}

Puoi definire una formula per inviare il messaggio a ciascun destinatario in una data e in un’ora specifiche.

## Personalizzazione della formula della data {#customizing-date-formula}

Ad esempio, puoi utilizzare l’ottimizzazione del tempo di invio durante il processo di espansione.

Quando le e-mail vengono inviate utilizzando una nuova piattaforma, i provider di servizi Internet (ISP) sono sospetti riguardo agli indirizzi IP non riconosciuti. Se grandi volumi di e-mail vengono improvvisamente inviati, gli ISP spesso li contrassegnano come spam.

Per evitare di essere contrassegnati come spam, puoi aumentare progressivamente il volume inviato distribuendo grandi quantità di e-mail in tempi diversi. Questo dovrebbe garantire uno sviluppo fluido della fase di avvio e consentire di ridurre il tasso complessivo di indirizzi non validi.

Ad esempio, puoi segmentare il pubblico di destinazione in modo casuale per inviare la consegna in cinque batch. Il 1° giugno invierai un primo batch che rappresenta il 10% del pubblico di destinazione alle 10:00, un secondo batch 24 ore dopo con il 15% del pubblico e così via.

Puoi programmarlo utilizzando un flusso di lavoro.

![](assets/send-time_opt_workflow1.png)

1. Accedi all’elenco delle attività di marketing e crea un nuovo flusso di lavoro. Vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Trascina e rilascia una **Query** nel flusso di lavoro e aprilo. Consulta la sezione [Query](../../automating/using/query.md) sezione .
1. Seleziona un pubblico, ad esempio tutti i tuoi clienti Gold e fai clic su **[!UICONTROL Confirm]** per salvare la query.
1. Trascina e rilascia una **Segmentazione** nel flusso di lavoro e aprilo. Consulta la sezione [Segmentazione](../../automating/using/segmentation.md) sezione .
1. Definisci cinque segmenti. Per ciascun segmento:

   * Compila il **[!UICONTROL Segment code]** campo: immetti manualmente la data e l’ora desiderate per l’invio del messaggio.

      Ad esempio, per inviare il primo batch il 1° giugno alle 00:00 GMT+1. Utilizza il formato seguente: **AAAA-MM-GG hh:mm:ss+tz**.

      ![](assets/send-time_opt_segment_configuration.png)

      Per inviare il batch successivo il giorno successivo, immettere **2017-06-02 10:00:00+01** per il secondo segmento.

      Per i segmenti rimanenti, definisci i batch successivi come segue:

      * **06-03/2017:00:00+01**
      * **06/04/2017:00:00+01**
      * **2017-06-05 10:00:00+01**
   * Assicurati di selezionare le **[!UICONTROL Limit the population of this segment]** opzione .

      In **[!UICONTROL Limitation]** scheda , seleziona **[!UICONTROL Random sampling]** e immetti la percentuale desiderata per ciascun segmento: 10 per il primo lotto, 15 per il secondo e così via.

      ![](assets/send-time_opt_segment_limitation.png)


1. Una volta definiti tutti i segmenti, seleziona **[!UICONTROL Generate all segments in the same transition]** e fai clic su **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment_dates.png)

1. Trascina e rilascia una **Email delivery** nel flusso di lavoro e aprilo. Consulta la sezione [Email delivery](../../automating/using/email-delivery.md) sezione .
1. Fai clic sul pulsante **[!UICONTROL Schedule]** nel dashboard e-mail e seleziona **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. In **[!UICONTROL Start sending from]** campo , definisci una data di contatto.
1. Dal menu a discesa di ottimizzazione del tempo di invio, scegli **[!UICONTROL Send at a custom date defined by a formula]**.
1. Fai clic sul pulsante **[!UICONTROL Edit an expression]** pulsante **[!UICONTROL Custom date formula]** campo .

   ![](assets/send-time_opt_formula_define.png)

1. Crea la seguente espressione utilizzando **[!UICONTROL ToDateTime]** e **[!UICONTROL Segment code]** campo . È inoltre possibile digitare direttamente l’espressione, ma accertarsi di utilizzare la sintassi e l’ortografia corrette.

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   La **[!UICONTROL ToDateTime]** la funzione trasforma il codice del segmento da una stringa di testo a un valore di data e ora.

   Conferma l’espressione per tornare alla schermata precedente.

   ![](assets/send-time_opt_formula_define_segment.png)

   In **[!UICONTROL Schedule]** La formula della data personalizzata viene visualizzata come segue:

   ```
   ToDateTime([targetData/@segmentCode])
   ```

   ![](assets/send-time_opt_custom_formula.png)

1. Conferma la pianificazione, salva la consegna ed esegui il flusso di lavoro.

La consegna verrà inviata progressivamente a tutti i destinatari di destinazione nell’arco di cinque giorni.

>[!NOTE]
>
>Assicurati che tutte le date siano future durante la conferma dell’invio. In caso contrario, il messaggio verrà inviato non appena l’invio viene confermato.

## Utilizzo di un’espressione {#using-an-expression}

L’ottimizzazione del tempo di invio è utile anche per le campagne che coinvolgono un call center. Puoi assicurarti che tutti i messaggi non vengano ricevuti contemporaneamente. Questo consente alla tua organizzazione di elaborare il numero di chiamate in base alla sua capacità.

Ad esempio, desideri inviare un’e-mail invitando i clienti a contattare un call center per ottenere un’offerta promozionale. Per evitare di sopraffare il call center, decidi di segmentare il pubblico di destinazione in modo casuale per inviare il tuo messaggio e-mail in quattro batch.

Puoi programmarlo utilizzando un flusso di lavoro.

![](assets/send-time_opt_workflow2.png)

1. Accedi all’elenco delle attività di marketing e crea un nuovo flusso di lavoro. Vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Trascina e rilascia una **Query** nel flusso di lavoro e aprilo. Consulta la sezione [Query](../../automating/using/query.md) sezione .
1. Seleziona un pubblico, ad esempio più di 35 profili e fai clic su **[!UICONTROL Confirm]** per salvare la query.
1. Trascina e rilascia una **Segmentazione** nel flusso di lavoro e aprilo. Consulta la sezione [Segmentazione](../../automating/using/segmentation.md) sezione .
1. Definisci quattro segmenti. Per ciascun segmento:

   * Definisci i codici dei segmenti come segue:

      * 8:00 - 10:00: **0**. Il messaggio verrà inviato al primo trimestre della popolazione target alle 8 (data di contatto).
      * 10:00 - 12:00: **2**. Il messaggio verrà inviato al secondo trimestre della popolazione target alle 10:00 (data di contatto + 2 ore).
      * 14:00 - 16:00: **6**. In chiusura del call center tra le 12:00 e le 14:00, il messaggio verrà inviato al terzo trimestre della popolazione target alle ore 14:00 (data di contatto + 6 ore).
      * 16:00 - 18:00: **8**. Il messaggio verrà inviato all&#39;ultimo trimestre della popolazione target alle ore 16:00 (data di contatto + 8 ore).

      >[!NOTE]
      >
      >La data di contatto verrà definita nell’attività Email delivery più avanti nel flusso di lavoro.

   * Assicurati di selezionare le **[!UICONTROL Limit the population of this segment]** opzione .
   * In **[!UICONTROL Limitation]** scheda , seleziona **[!UICONTROL Random sampling]** e immetti la percentuale desiderata per ciascun segmento: **25**.


1. Una volta definiti tutti i segmenti, seleziona **[!UICONTROL Generate all segments in the same transition]** e fai clic su **[!UICONTROL Confirm]**.

   ![](assets/send-time_opt_segment.png)

1. Trascina e rilascia una **Email delivery** nel flusso di lavoro e aprilo. Consulta la sezione [Email delivery](../../automating/using/email-delivery.md) sezione .
1. Fai clic sul pulsante **[!UICONTROL Schedule]** nel dashboard e-mail.
1. Seleziona **[!UICONTROL Messages to be sent automatically on the date specified below]**.
1. In **[!UICONTROL Start sending from]** campo , definisci una data di contatto.

   In questo esempio, seleziona il 25 maggio alle 8.00.

1. Dal menu a discesa di ottimizzazione del tempo di invio, scegli **[!UICONTROL Send at a custom date defined by a formula]** e fai clic su **[!UICONTROL Edit an expression]** pulsante .

   ![](assets/send-time_opt_formula_expression.png)

1. In **[!UICONTROL Expression editor]**, imposta la data e i codici del segmento per calcolare i dati per ciascun cliente.

   Nell’elenco delle funzioni, seleziona **[!UICONTROL AddHours]**.

   ![](assets/send-time_opt_formula_expression_addhours.png)

   Nei campi disponibili, seleziona **[!UICONTROL Current delivery]** > **[!UICONTROL Delivery scheduling]** > **[!UICONTROL Contact date]**.

   ![](assets/send-time_opt_formula_expression_contact_date.png)

   Ciò ti consente di recuperare la data e l’ora specificate nella **[!UICONTROL Start sending from]** campo .

   Nell’elenco delle funzioni, seleziona **[!UICONTROL ToInteger]**. Nei campi disponibili, seleziona **[!UICONTROL Additional data]** > **[!UICONTROL Segment code]**.

   ![](assets/send-time_opt_formula_expression_segment_code.png)

   Questo consente di recuperare i numeri specificati nei codici dei segmenti.

   Dovresti ottenere la seguente formula:

   ```
   AddHours([currentDelivery/scheduling/@contactDate], ToInteger([targetData/@segmentCode]))
   ```

1. Conferma il salvataggio dell’espressione. Conferma la pianificazione, salva la consegna ed esegui il flusso di lavoro.

* Il primo segmento riceverà il messaggio alla data di contatto (25 maggio alle 8.00).
* Il secondo segmento riceverà il messaggio due ore dopo (25 maggio alle 10:00).
* Il terzo segmento riceverà il messaggio sei ore dopo (25 maggio alle 2:00).
* Il quarto segmento riceverà il messaggio otto ore dopo (25 maggio alle 16:00).
