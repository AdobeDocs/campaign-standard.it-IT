---
title: Arricchimento dei dati del profilo con i dati contenuti in un file
description: Questo esempio mostra come arricchire i dati del profilo con i dati di acquisto contenuti in un file.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5c19884-5a3e-4676-899c-53074a3b0efc
source-git-commit: 7bc90f353a804680eb58514737d65cdd0d873fc5
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 77%

---

# Arricchimento dei dati del profilo con i dati contenuti in un file {#enriching-profile-data-with-data-contained-in-a-file}

Questo esempio mostra come arricchire i dati del profilo con i dati di acquisto presenti in un file. In questo caso, presupponiamo che i dati di acquisto vengono memorizzati in un sistema di terze parti. Ciascun profilo può contenere vari acquisti memorizzati all’interno del file. L’obiettivo finale del flusso di lavoro è quello di inviare un’e-mail ai profili di destinazione che hanno acquistato almeno due elementi, in modo da ringraziarli della loro fedeltà.

Il flusso di lavoro è configurato come segue:

![](assets/enrichment_example_workflow.png)

* Attività [Query](../../automating/using/query.md) che esegue il targeting dei profili che riceveranno il messaggio.
* Attività [Load file](../../automating/using/load-file.md) che carica i dati di acquisto. Ad esempio:

  ```
  tcode;tdate;customer;product;tamount
  aze123;21/05/2017;dannymars@example.com;TV;799
  aze124;28/05/2017;dannymars@example.com;Headphones;8
  aze125;31/07/2017;john.smith@example.com;Headphones;8
  aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
  aze127;02/01/2018;dannymars@example.com;Case Cover;79
  aze128;04/03/2017;clara.smith@example.com;Phone;149
  ```

  Con questo file di esempio, utilizza l’indirizzo e-mail per riconciliare i dati con i profili del database. Puoi anche eseguire l’abilitazione di ID univoci, come descritto nel [presente documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Attività [Enrichment](../../automating/using/enrichment.md) che crea un collegamento tra i dati della transazione caricati dal file e i profili selezionati in **[!UICONTROL Query]**. Il collegamento è definito nella scheda **[!UICONTROL Advanced relations]** dell’attività. Il collegamento è basato sulla transizione proveniente dall’attività **[!UICONTROL Load file]**. Come criteri di riconciliazione, utilizza il campo &quot;e-mail&quot; della risorsa profilo e la colonna &quot;cliente&quot; del file importato.

  ![](assets/enrichment_example_workflow2.png)

  Una volta creato il collegamento, vengono aggiunti due set di **[!UICONTROL Additional data]**:

   * Una raccolta di due righe corrispondenti alle ultime due transazioni di ciascun profilo. Per questa raccolta, il nome del prodotto, la data della transazione e il prezzo del prodotto vengono inseriti come dati aggiuntivi. Ai dati viene applicato un ordinamento decrescente. Per creare la raccolta, dalla scheda **[!UICONTROL Additional data]**:

     Scegli il collegamento precedentemente definito nella scheda **[!UICONTROL Advanced relations]** dell’attività.

     ![](assets/enrichment_example_workflow3.png)

     Seleziona **[!UICONTROL Collection]** e specifica il numero di righe da recuperare, in questo esempio sono 2. In questa schermata, puoi personalizzare **[!UICONTROL Alias]** e **[!UICONTROL Label]** della raccolta. Questi valori saranno visibili nelle seguenti attività del flusso di lavoro, ogni volta che si farà riferimento a questa raccolta.

     ![](assets/enrichment_example_workflow4.png)

     Come **[!UICONTROL Data]** da mantenere per la raccolta, seleziona le colonne che verranno utilizzate per la consegna finale.

     ![](assets/enrichment_example_workflow6.png)

     Per avere la certezza di recuperare le transazioni più recenti, applica un ordinamento decrescente alla data della transazione.

     ![](assets/enrichment_example_workflow7.png)

   * Un aggregato che conta il numero totale di transazioni per ciascun profilo. Tale aggregato verrà utilizzato successivamente per filtrare i profili in cui sono registrate almeno due transazioni. Per creare l’aggregato, dalla scheda **[!UICONTROL Additional data]**:

     Scegli il collegamento precedentemente definito nella scheda **[!UICONTROL Advanced relations]** dell’attività.

     ![](assets/enrichment_example_workflow3.png)

     Seleziona **[!UICONTROL Aggregate]**.

     ![](assets/enrichment_example_workflow8.png)

     Come **[!UICONTROL Data]** da mantenere, definisci un aggregato **Conta tutto**. Se necessario, specifica un alias personalizzato per individuarlo più rapidamente nelle seguenti attività.

     ![](assets/enrichment_example_workflow9.png)

* Un&#39;attività [Segmentation](../../automating/using/segmentation.md) con un solo segmento, che recupera i profili della destinazione iniziale contenenti almeno due transazioni registrate. Sono esclusi i profili con una sola transazione. A tal fine, la query della segmentazione viene eseguita sull’aggregato definito in precedenza.

  ![](assets/enrichment_example_workflow5.png)

* Un&#39;attività [Email delivery](../../automating/using/email-delivery.md) che utilizza i dati aggiuntivi definiti in **[!UICONTROL Enrichment]** per recuperare in modo dinamico gli ultimi due acquisti effettuati dal profilo. Durante l’inserimento di un campo di personalizzazione, i dati aggiuntivi si trovano nel nodo **Dati aggiuntivi (TargetData)**.

  ![](assets/enrichment_example_workflow10.png)

**Argomento correlato:**

* [Arricchimento dei profili dei clienti con dati esterni](https://helpx.adobe.com/it/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
