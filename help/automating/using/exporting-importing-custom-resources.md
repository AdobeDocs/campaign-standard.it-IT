---
title: Esportazione/importazione di risorse personalizzate
description: Questa esercitazione spiega come esportare e importare un pacchetto di risorse personalizzate.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 71ee939b6ef256be8c693ec6e15d9609c7e80677

---


# Esportazione/importazione di risorse personalizzate {#exporting-importing-custom-resources}

Questa esercitazione spiega come esportare e importare un pacchetto di risorse personalizzate da un ambiente di sviluppo a un ambiente di produzione.

Questo esempio è destinato agli amministratori funzionali collegati ad Adobe Campaign.

I prerequisiti sono:

* **Una o più risorse** personalizzate disponibili e pubblicate.

   Inoltre, è necessario aver definito una chiave univoca per queste risorse perché le chiavi primarie automatiche non vengono esportate nei pacchetti. La risorsa può quindi avere una chiave primaria e una chiave univoca aggiuntiva per garantire l'univocità dei record.
* **I diritti** necessari per creare ed esportare un pacchetto.

Risorse aggiuntive:

* [Gestione dei pacchetti](../../automating/using/managing-packages.md)
* [Distribuzione di pacchetti:Principio di funzionamento](../../developing/using/data-model-concepts.md)
* [Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)

## Passaggio 1: Esportazione della struttura {#exporting-the-structure}

In questa sezione verrà eseguita un'esportazione del primo pacchetto con informazioni dettagliate sulla struttura fisica dei dati delle risorse personalizzate.

Questo esempio include due risorse personalizzate: **Prodotti** e **ordini**.

1. Vai al **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package exports]** menu.

   Stiamo per creare un nuovo pacchetto per esportare il **[!UICONTROL Custom resource (cusResource)]** filtro con le due risorse personalizzate, "Products" e "Orders".

1. Nella **[!UICONTROL Package exports]** pagina, fate clic **[!UICONTROL Create]** per creare un nuovo pacchetto.
1. Completare l’etichetta e fare clic **[!UICONTROL Create element]**.

   ![](assets/cusresources_export1.png)

1. Cercare e selezionare il **[!UICONTROL Custom resource (cusResource)]**.

   ![](assets/cusresources_export2.png)

1. Configurate i dettagli del filtro **[!UICONTROL Custom resource]** selezionando le due risorse, **Prodotti** e **Ordini**, nelle condizioni di filtraggio.

   Assicurarsi di non dimenticare di modificare l'operatore logico. Il valore deve essere impostato su **OR** in modo che la struttura della risorsa prodotti e la risorsa ordini siano integrate nel pacchetto.

   ![](assets/cusresources_export3.png)

1. Confermate e salvate la definizione del pacchetto.

Ora potete fare clic **[!UICONTROL Start export]**.

![](assets/cusresources_export4.png)

Il pacchetto generato è disponibile nella cartella Download. Il nome del file zip viene generato in modo casuale. Potete rinominarlo.

## Esportazione dei dati {#exporting-the-data}

Questa seconda esportazione ci consentirà di esportare i dati dalle risorse personalizzate **Prodotti** e **Ordini** .

In base allo stesso tipo di esportazione dell'esportazione della struttura, verrà creato un secondo pacchetto contenente i dati.

1. Nella **[!UICONTROL Package exports]** pagina, fate clic **[!UICONTROL Create]** per creare un nuovo pacchetto.
1. Completare l'etichetta con **[!UICONTROL Export data of my resources]** quindi fare clic **[!UICONTROL Create element]** nella **[!UICONTROL Export content]** scheda.
1. Cercare e selezionare la risorsa **Prodotti** .

   ![](assets/cusresources_exportdata1.png)

1. Configurate una condizione **di** filtro avanzata con **@Label IS NOT NULL**.

   ![](assets/cusresources_exportdata2.png)

1. Controlla il numero.

   ![](assets/cusresources_exportdata3.png)

1. Ripetere la stessa operazione per la risorsa personalizzata **Ordini** .

   ![](assets/cusresources_exportdata4.png)

1. Confermate e salvate la definizione del pacchetto.

Ora potete fare clic **[!UICONTROL Start export]**.

![](assets/cusresources_exportdata5.png)

Il pacchetto generato è disponibile nella cartella Download. Il nome del file zip viene generato in modo casuale. Potete rinominarlo.

## Importazione della struttura {#importing-the-structure}

### Importazione del pacchetto {#importing-the-structure-package}

1. Connettetevi all'istanza **di** destinazione in cui desiderate importare i pacchetti appena creati.
1. Andate al **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** menu per creare un nuovo pacchetto per importare il file dalla prima esportazione.
1. Trascinate e rilasciate il file **di** struttura nella zona fornita a tal fine. I formati accettati sono ZIP o XML.

   ![](assets/cusresources_import2.png)

1. Modificate l'etichetta, ad esempio struttura **** Importa, quindi fate clic su **[!UICONTROL Save]**.
1. Click **[!UICONTROL Start import]**.

   ![](assets/cusresources_import3.png)

### Publish {#publish-structure}

1. Vai al **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** menu.
1. Fate clic **[!UICONTROL Prepare publication]** quindi **[!UICONTROL Publish]** per aggiornare l'istanza con i dati delle nuove risorse personalizzate.
1. Le voci di menu corrispondenti al pacchetto installato verranno inserite nel **[!UICONTROL Client data]** menu.

   ![](assets/cusresources_import1.png)

## Importazione dei dati {#importing-the-data}

In questa sezione verranno **importati i dati** collegati al pacchetto installato nell'istanza nel passaggio precedente.

Allo stesso modo del passo precedente, è diviso in due parti: importare il pacchetto e pubblicare.

### Importazione del pacchetto {#importing-the-data-package}

1. Andate al **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** menu per creare un nuovo pacchetto per importare il file contenente i dati.
1. Trascinare e rilasciare il file di dati nella zona fornita a tal fine. I formati accettati sono ZIP o XML.
1. Modificate l'etichetta, ad esempio "Importa dati", quindi fate clic **[!UICONTROL Save]**.
1. Click **[!UICONTROL Start import]**.

   ![](assets/cusresources_importdata.png)

### Publish {#publish-data}

1. Vai al **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** menu.
1. Fate clic **[!UICONTROL Prepare publication]** quindi **[!UICONTROL Publish]** per aggiornare l'istanza con i dati delle risorse personalizzate.
