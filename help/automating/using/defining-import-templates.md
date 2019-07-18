---
title: Definizione dei modelli di importazione
seo-title: Definizione dei modelli di importazione
description: Definizione dei modelli di importazione
seo-description: I modelli di importazione consentono di ridurre le impostazioni necessarie e di importare più rapidamente i dati.
page-status-flag: never-activated
uuid: 651 eb 57 c-adac -4 e 3 e-b 454-b 39 aea 1 f 0484
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: import-and-exporting-data
discoiquuid: 85 d 13147-fb 31-446 a -8476-f 112 c 841 fb 82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Defining import templates{#defining-import-templates}

I modelli di importazione consentono all'amministratore di predefinire un determinato numero di configurazioni di importazione tecniche. Questi modelli possono essere quindi resi disponibili agli utenti standard per eseguire e caricare i file.

An import template is defined by the functional administrator and can be managed under the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Import templates]** menu.

![](assets/import_template_list.png)

Sono disponibili tre modelli di sola lettura:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: Questo modello può servire come base per le nuove importazioni per aggiornare le conversioni e i registri di consegna per Posta diretta. Il flusso di lavoro del modello contiene le attività seguenti:
* **[!UICONTROL Import data]**: Questo modello può servire come base per inserire dati da un file nel database. Il flusso di lavoro di questo modello contiene le attività seguenti:

   * **[!UICONTROL Load file]**: questa attività consente di caricare un file sul server Adobe Campaign.
   * **[!UICONTROL Update data]**: questa attività consente di inserire dati dal file nel database.

* **[!UICONTROL Import list]**: this template can serve as a basis for new imports to create a **List** type audience from data in a file. Il flusso di lavoro di questo modello contiene le attività seguenti:

   * **[!UICONTROL Load file]**: questa attività consente di caricare un file sul server Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: questa attività consente di collegare una dimensione di targeting ai dati importati. This then allows you to create a **List** type audience. If the targeting dimension of the imported data is not known, the audience is **File** type. See [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: questa attività consente di salvare i dati importati sotto forma di pubblico di tipo **Elenco** . Il nome del pubblico salvato corrisponde al nome del file importato dall'utente e viene aggiunto un suffisso specificando la data e l'ora dell'importazione. Ad esempio: ' profiles_ 20150406_ 151448 '.

Questi modelli predefiniti sono di sola lettura e non sono visibili agli utenti standard. Per creare un modello che sarà disponibile agli utenti, effettuate le seguenti operazioni:

1. Duplica un modello predefinito. Il modello duplicato contiene tre schede:

   * **[!UICONTROL Properties]**: i parametri generali del modello di importazione. Questa scheda consente di abilitare il modello e di caricare un file di esempio.
   * **[!UICONTROL Workflow]**: flusso di lavoro di importazione. Questa scheda consente di definire le attività del flusso di lavoro. Queste attività non sono visibili durante le importazioni semplificate eseguite dagli utenti.
   * **[!UICONTROL Executed imports]**: elenco di importazioni eseguite con questo modello. Potete visualizzare lo stato, i dettagli e i risultati di ogni importazione eseguita utilizzando questo modello. Potete accedere direttamente al flusso di lavoro (eseguito in modo trasparente per l'utente) dall'elenco.

1. From the **[!UICONTROL Properties]** tab, rename the template and add a description. Gli utenti potranno visualizzare la descrizione quando il modello è disponibile.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Da qui potete arricchire il flusso di lavoro offerto per impostazione predefinita aggiungendo nuove attività in base alle vostre esigenze.

   For more on how to configure the workflow activities, refer to the use case describe in this section: [Example: Import workflow template](../../automating/using/importing-data.md#example--import-workflow-template). Questo caso d'uso ti aiuterà a impostare un flusso di lavoro da riutilizzare per importare profili provenienti da un CRM nel database Adobe Campaign.

1. Salvate il modello in modo che la configurazione del flusso di lavoro venga considerata correttamente.
1. Upload a sample file from the **[!UICONTROL Properties]** tab. Il file caricato può disporre solo delle colonne necessarie per le importazioni future o di dati di esempio. I dati nel file di esempio consentono di verificare l'importazione semplificata una volta definito il flusso di lavoro.

   ![](assets/import_template_sample.png)

   Questo file di esempio sarà quindi disponibile per gli utenti che utilizzano il modello per eseguire un'importazione. Potranno scaricarlo sul computer, ad esempio per compilarlo con dati da importare. Accertatevi di tenerlo presente quando aggiungete un file di esempio.

1. Salvate il modello. Il file di esempio è ora preso in considerazione. At any moment you can download it to your computer to check the content, or modify it by checking the **[!UICONTROL Drop a new sample file]** option.

   ![](assets/simplified_import_model2.png)

1. Go back to the **[!UICONTROL Workflow]** tab and open the **[!UICONTROL Load file]** activity to check and adjust the column configuration of the sample file that was uploaded at the previous step.
1. Verificare l'importazione avviando il flusso di lavoro. The sample file uploaded at step **5** has to contain data.

   I dati del file di esempio vengono quindi importati effettivamente. Verificate che i dati utilizzati siano piccoli e fittizi per garantire che il database non venga compromesso.

1. Andate al registro dell'esecuzione del flusso di lavoro, disponibile nella barra delle azioni. Se si verifica un errore, verificare che le attività siano configurate correttamente.

   ![](assets/simplified_import_model3.png)

1. In the **[!UICONTROL Properties]** tab, set the **[!UICONTROL Import template status]** to **[!UICONTROL Available]**, then save the template. To stop using this template, you can set the **[!UICONTROL Import template status]** to **[!UICONTROL Archived]**.

The template workflow can be modified by re-uploading the sample file and checking the **[!UICONTROL Load file]** configuration.

Il modello di importazione è ora disponibile per gli utenti e può essere utilizzato per caricare i file.

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/discovering-workflows.md)
* [Importazione di dati](../../automating/using/importing-data.md)
* [Esempio: Modello di flusso di lavoro di importazione](../../automating/using/importing-data.md#example--import-workflow-template)

