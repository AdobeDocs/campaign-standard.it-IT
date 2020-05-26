---
title: Importazione di dati con modelli di importazione
description: Scopri come raccogliere i dati per alimentare il database Campaign.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 1%

---


# Importazione di dati con modelli di importazione{#importing-data-with-import-templates}

L&#39;importazione di dati consente di raccogliere dati per alimentare il database Campaign.

In alternativa ai [flussi di lavoro](../../automating/using/get-started-workflows.md), Adobe Campaign offre una funzione di importazione semplificata che consente all&#39;utente di gestire alcuni tipi di importazione definiti da un amministratore.

Il principio di funzionamento è il seguente: un **amministratore** definisce e gestisce i modelli di importazione (consultate [Definizione dei modelli](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)di importazione). Questi modelli di importazione vengono quindi resi disponibili agli utenti con viste semplificate nel menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Questi utenti devono quindi semplicemente selezionare il tipo di importazione che desiderano eseguire e caricare il file con i dati da importare. Il flusso di lavoro definito dall’amministratore viene eseguito in modo trasparente per l’utente, che potrà accedere ai dettagli del risultato dell’importazione una volta completata.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Per ulteriori informazioni sui ruoli, consulta [questa sezione](../../administration/using/list-of-roles.md).

Le importazioni possono essere filtrate in base al modello da cui sono state eseguite, alla data di esecuzione e allo stato di esecuzione.

1. Dalla panoramica delle importazioni, fate clic sul **[!UICONTROL Create]** pulsante. Viene aperta la procedura guidata.
1. Selezionare il tipo di importazione che si desidera eseguire. I tipi di importazione corrispondono ai modelli di importazione disponibili.
1. Se necessario, scaricate nel computer il file di esempio collegato al modello per visualizzare i tipi di dati previsti nel file da importare.
1. Scaricate il file contenente i dati da importare nella procedura guidata.
1. Avviate l’importazione. La procedura guidata si chiude e si torna all’elenco delle importazioni effettuate con il modello utilizzato.
1. Aggiorna la pagina e seleziona l’importazione appena eseguita per visualizzare i dettagli dell’esecuzione.

   ![](assets/simplified_import1.png)

I dettagli dell&#39;esecuzione dell&#39;importazione sono ora disponibili. È possibile scaricare nel computer sia il file importato, sia il file contenente i dati rifiutati (dati non importati).

## Impostazione dei modelli di importazione {#setting-up-import-templates}

I modelli di importazione consentono all’amministratore di predefinire un certo numero di configurazioni tecniche di importazione. Questi modelli possono quindi essere resi disponibili agli utenti standard per eseguire e caricare file.

Un modello di importazione è definito dall&#39;amministratore funzionale e può essere gestito dal menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** .

![](assets/import_template_list.png)

Sono disponibili tre modelli di sola lettura predefiniti:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: questo modello può fungere da base per nuove importazioni per aggiornare le quarantena e i registri di consegna per Posta diretta. Il flusso di lavoro del modello contiene le attività seguenti:
* **[!UICONTROL Import data]**: questo modello può fungere da base per l&#39;inserimento di dati da un file nel database da parte di nuove importazioni. Il flusso di lavoro di questo modello contiene le attività seguenti:

   * **[!UICONTROL Load file]**: questa attività consente di caricare un file sul server Adobe Campaign.
   * **[!UICONTROL Update data]**: questa attività consente di inserire i dati dal file nel database.

* **[!UICONTROL Import list]**: questo modello può fungere da base per le nuove importazioni per creare un pubblico di tipo **Elenco** dai dati contenuti in un file. Il flusso di lavoro di questo modello contiene le attività seguenti:

   * **[!UICONTROL Load file]**: questa attività consente di caricare un file sul server Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: questa attività consente di collegare una dimensione di targeting ai dati importati. Questo consente di creare un pubblico di tipo **Elenco** . Se la dimensione di targeting dei dati importati non è nota, il pubblico è **Tipo di file** . Consultate [Impostazione del targeting di dimensioni e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: questa attività consente di salvare i dati importati sotto forma di pubblico di tipo **Elenco** . Il nome dell&#39;audience salvata corrisponde al nome del file importato dall&#39;utente, e verrà aggiunto un suffisso che specifica la data e l&#39;ora dell&#39;importazione. Ad esempio: &#39;profile_20150406_151448&#39;.

Questi modelli predefiniti sono di sola lettura e non sono visibili agli utenti standard. Per creare un modello che sarà disponibile agli utenti, effettuate le seguenti operazioni:

1. Duplica un modello predefinito. Il modello duplicato contiene tre schede:

   * **[!UICONTROL Properties]**: i parametri generali del modello di importazione. Questa scheda consente di abilitare il modello e caricare un file di esempio.
   * **[!UICONTROL Workflow]**: flusso di lavoro di importazione. Questa scheda consente di definire le attività del flusso di lavoro. Tali attività non sono visibili durante le importazioni semplificate effettuate dagli utilizzatori.
   * **[!UICONTROL Executed imports]**: elenco delle importazioni effettuate utilizzando questo modello. Potete visualizzare lo stato, i dettagli e i risultati di ogni importazione eseguita utilizzando questo modello. Da questo elenco potete accedere direttamente al flusso di lavoro (eseguito in modo trasparente per l’utente).

1. Dalla **[!UICONTROL Properties]** scheda, rinominare il modello e aggiungere una descrizione. Gli utenti potranno visualizzare la descrizione quando il modello è disponibile.

   ![](assets/simplified_import_model1.png)

1. Vai alla **[!UICONTROL Workflow]** scheda. Da qui potete arricchire il flusso di lavoro offerto per impostazione predefinita aggiungendo nuove attività in base alle vostre esigenze.

   Per ulteriori informazioni su come configurare le attività del flusso di lavoro, consulta la sezione relativa al caso di utilizzo descritta in questa sezione: [Esempio: Importa modello](../../automating/using/creating-import-workflow-templates.md)flusso di lavoro. Questo caso di utilizzo ti aiuterà a configurare un flusso di lavoro che può essere riutilizzato per importare profili provenienti da un CRM nel database Adobe Campaign.

1. Salvate il modello in modo che la configurazione del flusso di lavoro venga presa in considerazione correttamente.
1. Caricate un file di esempio dalla **[!UICONTROL Properties]** scheda. Il file caricato può contenere solo colonne necessarie per le importazioni future o per i dati di esempio. I dati contenuti nel file di esempio consentono di verificare l’importazione semplificata una volta definito il flusso di lavoro.

   ![](assets/import_template_sample.png)

   Questo file di esempio sarà quindi disponibile per gli utenti che utilizzano il modello per effettuare un&#39;importazione. Saranno in grado di scaricarlo sul loro computer, ad esempio per riempirlo con i dati da importare. Tenete presente questo aspetto quando aggiungete un file di esempio.

1. Salvate il modello. Il file di esempio viene ora preso in considerazione. In qualsiasi momento è possibile scaricarlo nel computer per controllare il contenuto o modificarlo selezionando l&#39; **[!UICONTROL Drop a new sample file]** opzione.

   ![](assets/simplified_import_model2.png)

1. Tornate alla **[!UICONTROL Workflow]** scheda e aprite l&#39; **[!UICONTROL Load file]** attività per controllare e regolare la configurazione delle colonne del file di esempio caricato al passaggio precedente.
1. Verificare l’importazione avviando il flusso di lavoro. Il file di esempio caricato al punto **5** deve contenere dei dati.

   I dati del file di esempio vengono quindi effettivamente importati. Assicurarsi che i dati utilizzati siano piccoli e fittizi per garantire che il database non sia compromesso.

1. Passate al registro di esecuzione del flusso di lavoro, disponibile nella barra delle azioni. Se si verifica un errore, verificare che le attività siano configurate correttamente.

   ![](assets/simplified_import_model3.png)

1. Nella **[!UICONTROL Properties]** scheda, impostare **[!UICONTROL Import template status]** **[!UICONTROL Available]** su , quindi salvare il modello. Per interrompere l’utilizzo di questo modello, potete impostare **[!UICONTROL Import template status]** su **[!UICONTROL Archived]**.

Il flusso di lavoro del modello può essere modificato caricando nuovamente il file di esempio e controllando la **[!UICONTROL Load file]** configurazione.

Il modello di importazione è ora disponibile per gli utenti e può essere utilizzato per caricare i file.

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Esempio: Importa modello di flusso di lavoro](../../automating/using/creating-import-workflow-templates.md)
