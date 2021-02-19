---
solution: Campaign Standard
product: campaign
title: Informazioni sull’importazione e sull’esportazione di dati
description: Scopri i diversi modi in cui importare ed esportare i dati con  Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%

---


# Informazioni sull’importazione e sull’esportazione di dati{#about-data-import-and-export}

A seconda delle esigenze aziendali, con  Adobe Campaign è possibile importare ed esportare i dati in diversi modi:

* **Pacchetti**: i pacchetti sono file XML che consentono di esportare e importare configurazioni e set di dati da un&#39;istanza di Adobe Campaign  a un&#39;altra. Gli aggiornamenti di sistema vengono eseguiti anche tramite le importazioni di pacchetti.
* **Elenchi**: è possibile configurare tutte le schermate elenco e esportare i dati visualizzati in un file separato.
* **Flussi** di lavoro: importare dati dai file e usarli per aggiornare il database o inviare e-mail. È inoltre possibile selezionare i dati da esportare nei file. I flussi di lavoro sono il modo migliore per automatizzare gli aggiornamenti regolari, come le importazioni di profili.

   * L’attività **[!UICONTROL Load file]** ti consente di importare i dati all’interno di un modulo strutturato, in modo da poterli utilizzare in Adobe Campaign. I dati vengono importati temporaneamente e occorre un’altra attività per integrarli definitivamente nel database di Adobe Campaign. Per ulteriori informazioni sull&#39;utilizzo di questa attività, vedere [questa sezione](../../automating/using/load-file.md).
   * L’attività **[!UICONTROL Transfer file]** ti consente di ricevere o inviare file, verificare se sono presenti o elencarli in Adobe Campaign. Puoi utilizzare questa attività prima di un **[!UICONTROL Load file]** nel caso sia necessario recuperare il file da un&#39;origine esterna. Per ulteriori informazioni sull&#39;utilizzo di questa attività, vedere [questa sezione](../../automating/using/transfer-file.md).

Durante la progettazione dei processi di importazione, è consigliabile utilizzare modelli di flusso di lavoro adattabili alle proprie esigenze. Per ulteriori informazioni su come impostare un modello di workflow per l&#39;importazione di dati, fare riferimento a [questo caso di utilizzo](../../automating/using/creating-import-workflow-templates.md).

 Adobe Campaign offre inoltre un modo semplificato per eseguire importazioni regolari, che consiste nella progettazione di **modelli di importazione**. I modelli di importazione sono modelli di flusso di lavoro specializzati disponibili tramite una schermata dedicata. Una volta progettato, l&#39;utente che esegue l&#39;importazione deve caricare solo il file da importare in una visualizzazione semplificata.

**Argomenti correlati**:

* [Importazione di dati con modelli di importazione](../../automating/using/importing-data-with-import-templates.md)
* [Definizione dei modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gestione dei pacchetti](../../automating/using/managing-packages.md)
