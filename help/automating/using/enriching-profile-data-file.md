---
title: Arricchimento dei dati del profilo con i dati contenuti in un file
description: Questo esempio mostra come arricchire i dati del profilo con i dati di acquisto contenuti in un file.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---


# Arricchimento dei dati del profilo con i dati contenuti in un file {#enriching-profile-data-with-data-contained-in-a-file}

Questo esempio mostra come arricchire i dati del profilo con i dati di acquisto contenuti in un file. Qui si considera che i dati di acquisto sono memorizzati in un sistema di terze parti. Ciascun profilo può contenere diversi acquisti memorizzati nel file. L&#39;obiettivo finale del flusso di lavoro è quello di inviare un&#39;e-mail ai profili di destinazione che hanno acquistato almeno due elementi per ringraziarli della loro fedeltà.

Il flusso di lavoro è configurato come segue:

![](assets/enrichment_example_workflow.png)

* Un&#39;attività [Query](../../automating/using/query.md) che esegue il targeting dei profili che riceveranno il messaggio.
* Un&#39;attività [Carica file](../../automating/using/load-file.md) che carica i dati di acquisto. Ad esempio:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Con questo file di esempio, utilizzeremo l&#39;indirizzo e-mail per riconciliare i dati con i profili del database. Potete inoltre abilitare ID univoci come descritto in [questo documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Un&#39;attività di [arricchimento](../../automating/using/enrichment.md) che crea un collegamento tra i dati della transazione caricati dal file e i profili selezionati nella **[!UICONTROL Query]**. Il collegamento è definito nella **[!UICONTROL Advanced relations]** scheda dell&#39;attività. Il collegamento è basato sulla transizione proveniente dall&#39; **[!UICONTROL Load file]** attività. Utilizza il campo &quot;email&quot; della risorsa profilo e la colonna &quot;customer&quot; del file importato come criteri di riconciliazione.

   ![](assets/enrichment_example_workflow2.png)

   Una volta creato il collegamento, **[!UICONTROL Additional data]** vengono aggiunti due set:

   * Un insieme di due righe corrispondenti alle due ultime transazioni di ciascun profilo. Per questa raccolta, il nome del prodotto, la data della transazione e il prezzo del prodotto vengono aggiunti come dati aggiuntivi. Sui dati viene applicato un ordinamento decrescente. Per creare la raccolta, dalla **[!UICONTROL Additional data]** scheda:

      Selezionate il collegamento precedentemente definito nella **[!UICONTROL Advanced relations]** scheda dell&#39;attività.

      ![](assets/enrichment_example_workflow3.png)

      Selezionare **[!UICONTROL Collection]** e specificare il numero di righe da recuperare (2 in questo esempio). In questa schermata, potete personalizzare l&#39;oggetto **[!UICONTROL Alias]** e l&#39;oggetto **[!UICONTROL Label]** della raccolta. Questi valori saranno visibili nelle seguenti attività del flusso di lavoro quando si fa riferimento a questa raccolta.

      ![](assets/enrichment_example_workflow4.png)

      Per **[!UICONTROL Data]** mantenere la raccolta, selezionate le colonne che verranno utilizzate per la consegna finale.

      ![](assets/enrichment_example_workflow6.png)

      Applica un ordinamento decrescente alla data della transazione per essere certi di recuperare le transazioni più recenti.

      ![](assets/enrichment_example_workflow7.png)

   * Un aggregato che conta il numero totale di transazioni per ciascun profilo. Questo aggregato verrà utilizzato successivamente per filtrare i profili in cui sono registrate almeno due transazioni. Per creare l&#39;aggregazione, dalla **[!UICONTROL Additional data]** scheda:

      Selezionate il collegamento precedentemente definito nella **[!UICONTROL Advanced relations]** scheda dell&#39;attività.

      ![](assets/enrichment_example_workflow3.png)

      Selezionare **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Per **[!UICONTROL Data]** mantenere, definire un aggregato **Count All** . Se necessario, specificate un alias personalizzato per individuarlo più rapidamente nelle seguenti attività.

      ![](assets/enrichment_example_workflow9.png)

* Un&#39;attività di [segmentazione](../../automating/using/segmentation.md) con un solo segmento, che recupera i profili della destinazione iniziale con almeno due transazioni registrate. Sono esclusi i profili con una sola transazione. A tal fine, la query della segmentazione viene eseguita sull&#39;aggregazione definita in precedenza.

   ![](assets/enrichment_example_workflow5.png)

* Un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail che utilizza i dati aggiuntivi definiti in **[!UICONTROL Enrichment]** per recuperare in modo dinamico gli ultimi due acquisti effettuati dal profilo. I dati aggiuntivi si trovano nel nodo **Dati** aggiuntivi (TargetData)quando si aggiunge un campo di personalizzazione.

   ![](assets/enrichment_example_workflow10.png)

**Argomento correlato:**

* [Arricchimento dei profili cliente con dati esterni](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
