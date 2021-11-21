---
title: Informazioni sull’importazione e l’esportazione di dati
description: Scopri le diverse modalità di importazione ed esportazione dei dati con Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---

# Informazioni sull’importazione e l’esportazione di dati{#about-data-import-and-export}

A seconda delle esigenze aziendali, puoi importare ed esportare i dati con Adobe Campaign in diversi modi:

* **Pacchetti**: i pacchetti sono file XML che ti consentono di esportare e importare configurazioni e set di dati da un’istanza di Adobe Campaign a un’altra. Gli aggiornamenti di sistema vengono eseguiti anche tramite le importazioni di pacchetti.
* **Elenchi**: è possibile configurare tutte le schermate elenco e i dati visualizzati esportati in un file separato.
* **Flussi di lavoro**: importare dati da file e utilizzarli per aggiornare il database o inviare e-mail. Puoi anche selezionare i dati da esportare nei file. I flussi di lavoro sono il modo migliore per automatizzare gli aggiornamenti regolari, come le importazioni di profili.

   * L’attività **[!UICONTROL Load file]** ti consente di importare i dati all’interno di un modulo strutturato, in modo da poterli utilizzare in Adobe Campaign. I dati vengono importati temporaneamente e occorre un’altra attività per integrarli definitivamente nel database di Adobe Campaign. Per ulteriori informazioni su come utilizzare questa attività, consulta [questa sezione](../../automating/using/load-file.md).
   * L’attività **[!UICONTROL Transfer file]** ti consente di ricevere o inviare file, verificare se sono presenti o elencarli in Adobe Campaign. Puoi utilizzare questa attività prima di un **[!UICONTROL Load file]** nel caso sia necessario recuperare il file da un’origine esterna. Per ulteriori informazioni su come utilizzare questa attività, consulta [questa sezione](../../automating/using/transfer-file.md).

Durante la progettazione dei processi di importazione, è consigliabile utilizzare modelli di flusso di lavoro adattabili alle proprie esigenze. Per ulteriori informazioni su come impostare un modello di flusso di lavoro per importare i dati, consulta [questo caso d&#39;uso](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign offre anche un modo semplificato per eseguire importazioni regolari, che consiste nel progettare **modelli di importazione**. I modelli di importazione sono modelli di flusso di lavoro specializzati disponibili tramite una schermata dedicata. Una volta progettato, l’utente che esegue l’importazione deve caricare solo il file da importare in una visualizzazione semplificata.

**Argomenti correlati**:

* [Importazione di dati con modelli di importazione](../../automating/using/importing-data-with-import-templates.md)
* [Definizione dei modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gestione dei pacchetti](../../automating/using/managing-packages.md)
