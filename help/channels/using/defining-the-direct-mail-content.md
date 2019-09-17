---
title: Definizione del contenuto della posta diretta
seo-title: Definizione del contenuto della posta diretta
description: Definizione del contenuto della posta diretta
seo-description: Scoprite come definire il contenuto per la distribuzione diretta della posta.
page-status-flag: mai attivato
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# Definizione del contenuto della posta diretta{#defining-the-direct-mail-content}

Potete definire il contenuto nell’ultima schermata della creazione guidata oppure facendo clic sulla sezione **Contenuto** del dashboard di distribuzione.

![](assets/direct_mail_6.png)

La schermata di **[!UICONTROL Content]** definizione è specifica per il canale di posta diretta. È diviso in quattro schede: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** e **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definizione dell'estrazione {#defining-the-extraction}

1. Iniziate definendo il nome del file di estrazione. Fare clic sul pulsante a destra del **[!UICONTROL Output file]** campo e immettere l'etichetta desiderata. Potete utilizzare campi di personalizzazione, blocchi di contenuto e testo dinamico (consultate [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization)). Ad esempio, puoi completare l’etichetta con l’ID di consegna o la data di estrazione.

   ![](assets/direct_mail_12.png)

1. Fate clic sul **[!UICONTROL +]** pulsante o **[!UICONTROL Add an element]** per aggiungere una colonna di output. Consente di **[!UICONTROL Output columns]** definire le informazioni di profilo (colonne) da esportare nel file di output.

   >[!CAUTION]
   >
   >Accertatevi che i vostri profili includano un indirizzo postale, in quanto queste informazioni sono essenziali per il fornitore di posta diretta. Inoltre accertatevi di aver selezionato la **[!UICONTROL Address specified]** casella nelle informazioni del profilo. Vedete [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Create tutte le colonne necessarie. Per modificare le colonne, fare clic sulle relative espressioni ed etichette.

>[!NOTE]
>
>Per ulteriori informazioni sulla definizione della colonna di output, consultate la sezione Attività flusso di lavoro del file [](../../automating/using/extract-file.md) Extract.

## Definizione della struttura del file {#defining-the-file-structure}

La scheda Struttura **** file consente di configurare i formati di output, data e numero per il file da esportare.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>Le opzioni disponibili sono dettagliate nelle sezioni dell'attività del flusso di lavoro del file [](../../automating/using/extract-file.md) Extract.

## Definizione dell’intestazione e del piè di pagina {#defining-the-header-and-footer}

A volte può essere necessario aggiungere informazioni all'inizio o alla fine del file di estrazione. A questo scopo, utilizzate le schede **[!UICONTROL Header]** e **[!UICONTROL Footer]** della schermata di **[!UICONTROL Content]** configurazione.

![](assets/direct_mail_7.png)

Ad esempio, potrebbe essere utile includere, per il provider di posta diretta, le informazioni sul mittente nell'intestazione del file. È possibile personalizzare il piè di pagina e l’intestazione con le informazioni disponibili nel contesto della distribuzione. Consultate [Definizione del contenuto](../../designing/using/personalization.md#example-email-personalization).

L'indirizzo del mittente è definito nella **[!UICONTROL Send]** sezione delle proprietà della posta diretta o a livello di modello.

![](assets/direct_mail_24.png)

