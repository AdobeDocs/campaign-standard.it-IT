---
title: Definizione del contenuto di posta diretta
seo-title: Definizione del contenuto di posta diretta
description: Definizione del contenuto di posta diretta
seo-description: Scoprite come definire il contenuto per la distribuzione diretta del messaggio.
page-status-flag: never-activated
uuid: c 1234 c 06-4 d 22-46 d 7-ad 1 b -3 c 88660 f 9 b 06
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: direct-mail
discoiquuid: 9 e 73 d 6 b 5-41 b 4-474 b-a 880-a 0 cd 5999 c 2 d 1
context-tags: delivery, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail content{#defining-the-direct-mail-content}

You can either define the content in the last screen of the creation wizard or by clicking on the **Content** section of the delivery dashboard.

![](assets/direct_mail_6.png)

The **[!UICONTROL Content]** definition screen is specific to the direct mail channel. It is divided into four tabs: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** and **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Defining the extraction {#defining-the-extraction}

1. Iniziate definendo il nome del file di estrazione. Click on the button to the right of the **[!UICONTROL Output file]** field and enter the desired label. You can use personalization fields, content blocks and dynamic text (see [Defining content](../../designing/using/example--email-personalization.md)). Ad esempio, puoi completare l'etichetta con l'ID di consegna o la data di estrazione.

   ![](assets/direct_mail_12.png)

1. Click the **[!UICONTROL +]** or **[!UICONTROL Add an element]** button to add an output column. The **[!UICONTROL Output columns]** let you define the profile information (columns) to be exported into the output file.

   >[!CAUTION]
   >
   >Accertatevi che i profili includano un indirizzo postale in quanto queste informazioni sono essenziali per il provider di posta diretta. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Create tutte le colonne necessarie. Potete modificare le colonne facendo clic sulle relative espressioni ed etichette.

>[!NOTE]
>
>For more information on output column definition, refer to the [Extract file](../../automating/using/extract-file.md) workflow activity section.

## Defining the file structure {#defining-the-file-structure}

The **File structure** tab allows you to configure the output, date, and number formats for the file that will be exported.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>The available options are detailed in the [Extract file](../../automating/using/extract-file.md) workflow activity sections.

## Defining the header and footer {#defining-the-header-and-footer}

A volte potrebbe essere necessario aggiungere informazioni all'inizio o alla fine del file di estrazione. For this, use the **[!UICONTROL Header]** and **[!UICONTROL Footer]** tabs of the **[!UICONTROL Content]** configuration screen.

![](assets/direct_mail_7.png)

Ad esempio, potrebbe essere utile includere, per il provider di posta diretta, le informazioni del mittente nell'intestazione del file. È possibile personalizzare il piè di pagina e l'intestazione con le informazioni disponibili nel contesto della distribuzione. See [Defining content](../../designing/using/example--email-personalization.md).

The sender address is defined in the **[!UICONTROL Send]** section of the direct mail properties or at the template level.

![](assets/direct_mail_24.png)

