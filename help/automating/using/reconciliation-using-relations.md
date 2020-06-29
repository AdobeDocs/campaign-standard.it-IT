---
title: Riconciliazione dei dati mediante le relazioni
description: L'esempio seguente illustra un flusso di lavoro che aggiorna il database utilizzando i dati di acquisto in un file.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Riconciliazione dei dati mediante le relazioni {#reconciliation-relations}

L&#39;esempio seguente illustra un flusso di lavoro che aggiorna il database utilizzando i dati di acquisto in un file. I dati di acquisto contengono dati che fanno riferimento a elementi di altre dimensioni, come le e-mail del cliente e i codici prodotto.

>[!NOTE]
>
>Le risorse **Transazioni** e **Prodotti** utilizzate in questo esempio non esistono nel database del Adobe Campaign  per impostazione predefinita. Sono stati quindi creati in precedenza utilizzando la funzione Risorse [](../../developing/using/data-model-concepts.md) personalizzate. I profili corrispondenti agli indirizzi e-mail nel file importato, così come i prodotti, sono stati caricati in precedenza nel database.

Il flusso di lavoro è costituito dalle seguenti attività:

![](assets/reconciliation_example1.png)

* Un&#39;attività [Carica file](../../automating/using/load-file.md) , che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

   * Data transazione
   * Indirizzo e-mail client
   * Codice del prodotto acquistato

   ```
   date;client;product
   2015-05-19 09:00:00;mail1@email.com;ZZ1
   2015-05-19 09:01:00;mail2@email.com;ZZ2
   2015-05-19 09:01:01;mail3@email.com;ZZ2
   2015-05-19 09:01:02;mail4@email.com;ZZ2
   2015-05-19 09:02:00;mail5@email.com;ZZ3
   2015-05-19 09:03:00;mail6@email.com;ZZ4
   2015-05-19 09:04:00;mail7@email.com;ZZ5
   2015-05-19 09:05:00;mail8@email.com;ZZ7
   2015-05-19 09:06:00;mail9@email.com;ZZ6
   ```

* Un&#39;attività di [riconciliazione](../../automating/using/reconciliation.md) per eseguire il binding dei dati di acquisto con i profili di database e i prodotti. È pertanto necessario definire una relazione tra i dati del file e la tabella del profilo, nonché la tabella del prodotto. Questa configurazione viene eseguita nella **[!UICONTROL Relations]** scheda dell&#39;attività:

   * Relazione con i **profili**: la colonna **client** del file è collegata al campo **e-mail** della dimensione **Profili** .
   * Relazione con i **prodotti**: la colonna **prodotto** del file è collegata al campo **productCode** della dimensione **Profili** .
   Le colonne vengono aggiunte ai dati in entrata per fare riferimento alle chiavi esterne delle dimensioni collegate.

   ![](assets/reconciliation_example3.png)

* Un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) consente di definire i campi del database da aggiornare utilizzando i dati importati. Poiché i dati erano già stati identificati come appartenenti alla dimensione **Transazioni** nell&#39;attività precedente, qui è possibile utilizzare l&#39;opzione di **[!UICONTROL Directly using the targeting dimension]** identificazione.

   Utilizzando l&#39;opzione che rileva automaticamente i campi da aggiornare, i collegamenti configurati nell&#39;attività precedente (a profili e prodotti) vengono aggiunti all&#39;elenco di **[!UICONTROL Fields to update]**. È inoltre necessario assicurarsi che il campo corrispondente alla data della transazione sia correttamente aggiunto a questo elenco.

   ![](assets/reconciliation_example5.png)

   ![](assets/reconciliation_example4.png)
