---
title: Aggiunta di un blocco di contenuto
seo-title: Aggiunta di un blocco di contenuto
description: Aggiunta di un blocco di contenuto
seo-description: Scopri i diversi blocchi di contenuto dinamici forniti da te per personalizzare i messaggi e imparare a creare blocchi di contenuto personalizzati.
page-status-flag: never-activated
uuid: 08153 ea 0-42 fb -4 c 0 b -8 d 4 b -9407540748 d 6
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: personalizzazione del contenuto
discoiquuid: 3 ffda 143-f 42 a -4 cf 9-b 43 c-e 53 d 24549025
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Adding a content block{#adding-a-content-block}

Adobe Campaign offre un elenco di blocchi di contenuto preconfigurati. Questi blocchi di contenuto sono dinamici, personalizzati e hanno un rendering specifico. Ad esempio, potete aggiungere un saluto o un collegamento alla pagina speculare.

>[!NOTE]
>
>The images below show how to insert a content block using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) for an email.

Per aggiungere un blocco di contenuto:

1. Click inside a text block, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert content block]**. For more on the Email Designer interface, see [this section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Selezionare il blocco di contenuto da inserire. I blocchi disponibili variano a seconda del contesto (e-mail o pagina di destinazione).

   ![](assets/email_content_block_2.png)

1. Click **[!UICONTROL Save]**.

Il nome del blocco di contenuto viene visualizzato nell'editor ed è evidenziato in giallo. Si adatta automaticamente al profilo quando viene generata la personalizzazione.

![](assets/email_content_block_3.png)

I blocchi di contenuto forniti sono:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**: Questo blocco di contenuto può essere utilizzato solo in una **pagina di destinazione**.
* **[!UICONTROL Default sender name (DefaultSenderName)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**: Questo blocco di contenuto può essere utilizzato solo in **una consegna**.
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

## Creating custom content blocks {#creating-custom-content-blocks}

Puoi definire nuovi blocchi di contenuto che verranno inseriti in un messaggio o in una pagina di destinazione.

Per creare un blocco di contenuto, effettuate le seguenti operazioni:

1. Click **[!UICONTROL Resources > Content blocks]** from the advanced menu to access the list of content blocks.
1. Click the **[!UICONTROL Create]** button or duplicate a pre-existing content block.

   ![](assets/content_bloc_01.png)

1. Immettete un'etichetta.
1. Select the block's **[!UICONTROL Content type]**. Sono disponibili tre opzioni:

   * **[!UICONTROL Shared]**: Il blocco di contenuto può essere utilizzato in una consegna o in una pagina di destinazione.
   * **[!UICONTROL Delivery]**: Il blocco di contenuto può essere utilizzato solo in una consegna.
   * **[!UICONTROL Landing page]**: Il blocco di contenuto può essere utilizzato solo in una pagina di destinazione.
   ![](assets/content_bloc_02.png)

1. You can select a **[!UICONTROL Targeting dimension]**. For more on this, see [About targeting dimension](../../designing/using/adding-a-content-block.md#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. You can select the **[!UICONTROL Depends on format]** option to define two different blocks: one for HTML emails, and one for emails in text format. Verranno quindi visualizzate due schede nell'editor (HTML e Testo) per definire i contenuti corrispondenti.

   ![](assets/content_bloc_03.png)

1. Enter the content of the content block(s), and click the **[!UICONTROL Create]** button.

Adesso, il blocco di contenuto può essere usato nell'editor del contenuto di un messaggio o di una pagina di destinazione.

## About targeting dimension {#about-targeting-dimension}

La dimensione di targeting consente di definire in quale tipo di messaggio è possibile utilizzare il blocco di contenuto. Ciò serve a evitare l'uso di blocchi inadeguati in un messaggio, il che potrebbe causare errori.

In realtà, quando si modifica un messaggio, è possibile selezionare solo blocchi di contenuto con una dimensione di targeting compatibile con la dimensione di targeting di quel messaggio.

For example, the **[!UICONTROL Unsubscription link]** block's targeting dimension is **[!UICONTROL Profiles]** because it contains personalization fields specific to the **[!UICONTROL Profiles]** resource. Therefore, you cannot use an **[!UICONTROL Unsubscription link]** block in an [event transactional message](../../channels/using/event-transactional-messages.md), because the targeting dimension of that type of message is **[!UICONTROL Real-time events]**. However, you can use the **Unsubscription link** block in a [profile transactional message](../../channels/using/profile-transactional-messages.md), because the targeting dimension of that type of message is **Profiles**. Finally, the **[!UICONTROL Link to mirror page]** block does not have a targeting dimension, so you can use it in any message.

Se lasciate vuoto questo campo, il blocco di contenuto sarà compatibile con tutti i messaggi, indipendentemente dalla dimensione di targeting. Se imposti una dimensione di targeting, tale blocco sarà compatibile solo con i messaggi con la stessa dimensione di targeting.

For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
