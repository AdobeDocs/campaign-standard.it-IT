---
title: Informazioni sull’importazione e sull’esportazione di dati
description: Scopri le diverse modalità di importazione ed esportazione dei dati con Adobe Campaign.
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0deabe17442b679a340a4497945837b83b4c9207
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 6%

---


# Informazioni sull’importazione e sull’esportazione di dati{#about-data-import-and-export}

A seconda delle esigenze aziendali, con Adobe Campaign puoi importare ed esportare i dati in diversi modi:

* **Pacchetti**: i pacchetti sono file XML che consentono di esportare e importare configurazioni e set di dati da un&#39;istanza di Adobe Campaign a un&#39;altra. Gli aggiornamenti di sistema vengono eseguiti anche tramite le importazioni di pacchetti.
* **Elenchi**: è possibile configurare tutte le schermate elenco e esportare i dati visualizzati in un file separato.
* **Flussi** di lavoro: importare dati dai file e usarli per aggiornare il database o inviare e-mail. È inoltre possibile selezionare i dati da esportare nei file. I flussi di lavoro sono il modo migliore per automatizzare gli aggiornamenti regolari, come le importazioni di profili.

   * L&#39; **[!UICONTROL Load file]** attività consente di importare i dati in un modulo strutturato per utilizzarli in Adobe Campaign. I dati vengono importati temporaneamente e un&#39;altra attività è necessaria per integrarli definitivamente nel database di Adobe Campaign. Per ulteriori informazioni sull&#39;utilizzo di questa attività, consultate [questa sezione](../../automating/using/load-file.md).
   * L&#39; **[!UICONTROL Transfer file]** attività consente di ricevere o inviare file, verificare se sono presenti file o elencare file in Adobe Campaign. Potete utilizzare questa attività prima di un **[!UICONTROL Load file]** caso in cui sia necessario recuperare il file da un&#39;origine esterna. Per ulteriori informazioni sull&#39;utilizzo di questa attività, consultate [questa sezione](../../automating/using/transfer-file.md).

Durante la progettazione dei processi di importazione, è consigliabile utilizzare modelli di flusso di lavoro adattabili alle proprie esigenze. Per ulteriori informazioni su come impostare un modello di flusso di lavoro per l’importazione di dati, consulta [questo caso](../../automating/using/creating-import-workflow-templates.md)di utilizzo.

Adobe Campaign offre inoltre un modo semplificato per effettuare importazioni regolari, che consiste nella progettazione di modelli **di** importazione. I modelli di importazione sono modelli di flusso di lavoro specializzati disponibili tramite una schermata dedicata. Una volta progettato, l&#39;utente che esegue l&#39;importazione deve caricare solo il file da importare in una visualizzazione semplificata.

**Argomenti** correlati:

* [Importazione di dati con modelli di importazione](../../automating/using/importing-data-with-import-templates.md)
* [Definizione dei modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Gestione dei pacchetti](../../automating/using/managing-packages.md)
