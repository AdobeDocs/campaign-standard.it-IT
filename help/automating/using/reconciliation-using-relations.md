---
title: Riconciliazione dei dati tramite relazioni
description: L’esempio seguente illustra un flusso di lavoro che aggiorna il database utilizzando i dati di acquisto in un file.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7d0e3f17-ef04-4890-b63b-6957fc6cd648
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 81%

---

# Riconciliazione dei dati tramite relazioni {#reconciliation-relations}

L’esempio seguente illustra un flusso di lavoro che aggiorna il database utilizzando i dati di acquisto in un file. I dati di acquisto contengono dati che si riferiscono a elementi di altre dimensioni, come e-mail del cliente e codici prodotto.

>[!NOTE]
>
>Le risorse **Transactions** e **Products** utilizzate in questo esempio non esistono nel database di Adobe Campaign per impostazione predefinita. Sono state quindi create in precedenza utilizzando la funzione [Custom resources](../../developing/using/data-model-concepts.md). Nel file importato, i profili corrispondenti agli indirizzi e-mail e i prodotti sono stati caricati in precedenza nel database.

Il flusso di lavoro è costituito dalle seguenti attività:

![](assets/reconciliation_example1.png)

* A [Carica file](../../automating/using/load-file.md) che carica e rileva i dati del file da importare. Il file importato contiene i dati seguenti:

   * Data della transazione
   * Indirizzo e-mail del cliente
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

* A [Reconciliation](../../automating/using/reconciliation.md) attività per associare i dati di acquisto a profili di database e prodotti. È pertanto necessario definire una relazione tra dati del file e la tabella del profilo, nonché con la tabella del prodotto. Questa configurazione viene eseguita nella scheda **[!UICONTROL Relations]** dell’attività:

   * Relazione con **Profiles**: la colonna **client** del file è collegata al campo **e-mail** della dimensione **Profiles**.
   * Relazione con **Products**: la colonna **product** del file è collegata al campo **productCode** della dimensione **Profiles**.

  Le colonne vengono aggiunte ai dati in entrata per rimandare alle chiavi esterne delle dimensioni collegate.

  ![](assets/reconciliation_example3.png)

* Un [Aggiorna dati](../../automating/using/update-data.md) attività ti consente di definire i campi del database da aggiornare utilizzando i dati importati. Poiché i dati erano già stati identificati come appartenenti alla dimensione **Transactions** nell’attività precedente, in questo caso puoi utilizzare l’opzione di identificazione **[!UICONTROL Directly using the targeting dimension]**.

  Utilizzando l’opzione che rileva automaticamente i campi da aggiornare, i collegamenti configurati nell’attività precedente (a profili e prodotti) vengono aggiunti all’elenco di **[!UICONTROL Fields to update]**. Inoltre devi assicurarti che il campo corrispondente alla data della transazione sia correttamente aggiunto a questo elenco.

  ![](assets/reconciliation_example5.png)

  ![](assets/reconciliation_example4.png)
