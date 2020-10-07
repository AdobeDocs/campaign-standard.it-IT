---
title: Importazione di dati con modelli di importazione
description: Scopri come raccogliere dati per alimentare il database di Campaign.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 99%

---


# Importazione di dati con modelli di importazione{#importing-data-with-import-templates}

L’importazione di dati ti consente di raccogliere dati per alimentare il database di Campaign.

In alternativa ai [flussi di lavoro](../../automating/using/get-started-workflows.md), Adobe Campaign offre una funzione di importazione semplificata che consente all’utente di gestire determinati tipi di importazione definiti da un amministratore.

Il principio di funzionamento è il seguente: un **amministratore** definisce e gestisce modelli di importazione (consulta [Definizione dei modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)). Questi modelli di importazione vengono quindi resi disponibili agli utenti con viste semplificate nel menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]**.

Tali utenti devono quindi semplicemente selezionare il tipo di importazione che desiderano eseguire e caricare il file con i dati da importare. Il flusso di lavoro definito dall’amministratore viene eseguito in modo trasparente per l’utente, che può accedere ai dettagli del risultato al termine dell’importazione.

>[!NOTE]
>
>La funzione di importazione di dati può essere gestita dagli utenti con i ruoli **[!UICONTROL GENERIC IMPORT (import)]** e **[!UICONTROL WORKFLOW (workflow)]**. Per ulteriori informazioni sui ruoli, consulta [questa sezione](../../administration/using/list-of-roles.md).

Le importazioni possono essere filtrate in base al modello da cui sono state eseguite, alla data di esecuzione e allo stato di esecuzione.

1. Dalla panoramica delle importazioni, fai clic sul pulsante **[!UICONTROL Create]**. Viene avviata la procedura guidata.
1. Seleziona il tipo di importazione che desideri eseguire. I tipi di importazione corrispondono ai modelli di importazione disponibili.
1. Se necessario, scarica sul tuo computer il file campione collegato al modello per visualizzare i tipi di dati previsti nel file da importare.
1. Scarica il file contenente i dati da importare nella procedura guidata.
1. Avvia l’importazione. La procedura guidata viene chiusa e viene visualizzato l’elenco delle importazioni eseguite con il modello utilizzato.
1. Aggiorna la pagina e seleziona l’importazione appena eseguita per visualizzare i dettagli dell’esecuzione.

   ![](assets/simplified_import1.png)

I dettagli dell’esecuzione dell’importazione sono ora disponibili. È possibile scaricare sul computer sia il file importato, sia il file contenente i dati rifiutati (dati non importati).

## Impostazione dei modelli di importazione {#setting-up-import-templates}

I modelli di importazione permettono all’amministratore di predefinire un certo numero di configurazioni tecniche di importazione. Tali modelli possono quindi essere resi disponibili agli utenti standard per eseguire e caricare i file.

Il modello di importazione è definito dall’amministratore funzionale e può essere gestito dal menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]**.

![](assets/import_template_list.png)

Sono disponibili tre modelli predefiniti di sola lettura:

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: questo modello può fungere da base per le nuove importazioni e consente di aggiornare le quarantene e i registri di consegna per la direct mailing. Il flusso di lavoro del modello contiene le attività seguenti:
* **[!UICONTROL Import data]**: questo modello può servire da base per consentire alle nuove importazioni di inserire i dati da un file al database. Il flusso di lavoro di questo modello contiene le attività seguenti:

   * **[!UICONTROL Load file]**: questa attività ti permette di caricare un file sul server Adobe Campaign.
   * **[!UICONTROL Update data]**: questa attività ti consente di inserire i dati dal file al database.

* **[!UICONTROL Import list]**: questo modello può fungere da base per permettere alle nuove importazioni di creare un pubblico di tipo **Elenco** dai dati contenuti all’interno di un file. Il flusso di lavoro di questo modello contiene le attività seguenti:

   * **[!UICONTROL Load file]**: questa attività ti permette di caricare un file sul server Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: questa attività ti consente di collegare ai dati importati una dimensione di targeting. A sua volta, ciò ti permette di creare un pubblico di tipo **Elenco**. Se la dimensione di targeting dei dati importati non è nota, il pubblico sarà del tipo **File**. Consulta [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: questa attività ti permette di salvare i dati importati sotto forma di pubblico di tipo **Elenco**. Il nome del pubblico salvato corrisponde al nome del file importato dall’utente, cui verrà aggiunto un suffisso che indica la data e l’ora dell’importazione. Ad esempio: “profiles_20150406_151448”.

Questi modelli predefiniti sono di sola lettura e non sono visibili agli utenti standard. Per creare un modello che sarà disponibile agli utenti, effettua le seguenti operazioni:

1. Duplica un modello predefinito. Il modello duplicato contiene tre schede:

   * **[!UICONTROL Properties]**: i parametri generali del modello di importazione. Questa scheda ti consente di abilitare il modello e di caricare un file di esempio.
   * **[!UICONTROL Workflow]**: flusso di lavoro di importazione. Questa scheda ti permette di definire le attività del flusso di lavoro. Tali attività non sono visibili durante le importazioni semplificate effettuate dagli utenti.
   * **[!UICONTROL Executed imports]**: elenco delle importazioni effettuate utilizzando questo modello. Puoi visualizzare lo stato, i dettagli e i risultati di ogni importazione eseguita utilizzando questo modello. Da questo elenco puoi accedere direttamente al flusso di lavoro, che viene eseguito in modo trasparente per l’utente.

1. Dalla scheda **[!UICONTROL Properties]**, rinomina il modello e aggiungi una descrizione. Gli utenti potranno visualizzare la descrizione quando il modello è disponibile.

   ![](assets/simplified_import_model1.png)

1. Vai alla scheda **[!UICONTROL Workflow]**. Da qui puoi arricchire il flusso di lavoro offerto per impostazione predefinita aggiungendovi nuove attività in base alle tue esigenze.

   Per ulteriori informazioni su come configurare le attività del flusso di lavoro, fai riferimento al caso d’uso descritto in questa sezione: [Esempio: importare un modello di flusso di lavoro](../../automating/using/creating-import-workflow-templates.md). Questo caso d’uso ti aiuterà a configurare un flusso di lavoro che può essere riutilizzato per importare nel database Adobe Campaign i profili provenienti da un sistema di gestione delle relazioni con i clienti.

1. Salva il tuo modello in modo che la configurazione del flusso di lavoro venga presa in considerazione nel modo corretto.
1. Carica un file di esempio dalla scheda **[!UICONTROL Properties]**. Il file caricato può contenere solo le colonne necessarie per le importazioni future o per i dati campione. I dati contenuti nel file di esempio consentono di verificare l’importazione semplificata, una volta definito il flusso di lavoro.

   ![](assets/import_template_sample.png)

   Questo file di esempio sarà quindi disponibile per gli utenti che utilizzano il modello per effettuare un’importazione. Gli utenti potranno quindi scaricarlo sul loro computer, ad esempio per riempirlo con i dati da importare. Assicurati di tenere presente questo aspetto durante l’aggiunta di un file di esempio.

1. Salva il modello. Il file di esempio viene ora preso in considerazione. Potrai scaricarlo nel computer in qualsiasi momento per controllarne il contenuto oppure modificarlo selezionando l’opzione **[!UICONTROL Drop a new sample file]**.

   ![](assets/simplified_import_model2.png)

1. Torna alla scheda **[!UICONTROL Workflow]** e apri l’attività **[!UICONTROL Load file]** per controllare e regolare la configurazione delle colonne del file di esempio caricato al passaggio precedente.
1. Esegui il test dell’importazione avviando il flusso di lavoro. Il file di esempio caricato al punto **5** deve contenere dei dati.

   I dati del file di esempio vengono quindi effettivamente importati. Assicurati che i dati utilizzati siano piccoli e fittizi, in modo da garantire che il database non venga compromesso.

1. Passa al registro di esecuzione del flusso di lavoro, disponibile nella barra delle azioni. Se riscontri un errore, controlla che le attività siano configurate correttamente.

   ![](assets/simplified_import_model3.png)

1. Nella scheda **[!UICONTROL Properties]**, imposta **[!UICONTROL Import template status]** su **[!UICONTROL Available]**, quindi salva il modello. Per interrompere l’utilizzo di questo modello, puoi impostare **[!UICONTROL Import template status]** su **[!UICONTROL Archived]**.

Il flusso di lavoro del modello può essere modificato caricando nuovamente il file di esempio e controllando la configurazione di **[!UICONTROL Load file]**.

Il modello di importazione è ora disponibile per gli utenti e può essere utilizzato per caricare i file.

**Argomenti correlati:**

* [Flussi di lavoro](../../automating/using/get-started-workflows.md)
* [Esempio: importare un modello di flusso di lavoro](../../automating/using/creating-import-workflow-templates.md)
