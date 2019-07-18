---
title: Importazione di contenuto da un URL
seo-title: Importazione di contenuto da un URL
description: Importazione di contenuto da un URL
seo-description: Scoprite come caricare contenuti da un URL esistente quando create un'e-mail.
page-status-flag: never-activated
uuid: 7 db 6 c 20 f -7004-4 fb 8-add 9-362 eab 3 d 2795
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: caricamento del contenuto
discoiquuid: 738 b 7 c 8 a -88 eb -491 c-a 4 d 0-078 b 973 b 0959
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Importing content from a URL{#importing-content-from-a-url}

Prima di importare il contenuto da un URL, accertatevi che sia conforme ai requisiti seguenti:

* Il contenuto deve essere pubblicamente disponibile tramite questo URL.
* For security reasons, only URLs beginning with **[!UICONTROL https]** are allowed.
* Accertatevi che tutte le risorse (immagini, CSS) siano impostate in collegamenti assoluti e in HTTPS. In caso contrario, dopo l'invio dell'e-mail, la pagina speculare veniva visualizzata senza le relative risorse. Esempio di definizione collegamento assoluto:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>Il caricamento del contenuto da un URL è disponibile solo per il canale e-mail.

Per recuperare un contenuto esistente, effettuate le operazioni seguenti:

1. From the Email Designer home page, select the **[!UICONTROL Import from URL]** button.

   ![](assets/email_designer_importfromurl.png)

1. Definite l'URL da cui verrà recuperato il contenuto.
1. Click **[!UICONTROL Confirm]**.

**Argomento correlato:**

[Importazione di contenuto da](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) un video URL

## Retrieving content from a URL automatically at preparation time {#retrieving-content-from-a-url-automatically-at-preparation-time}

L'importazione di contenuto da un URL durante la preparazione dei messaggi consente di recuperare il contenuto HTML più recente ogni volta che l'e-mail è preparata. In questo modo, il contenuto delle e-mail ricorrenti è sempre aggiornato al momento dell'invio. Questa funzione consente anche di creare un messaggio pianificato a una data specifica, anche se il contenuto non è ancora pronto.

Per recuperare il contenuto in fase di preparazione, effettuate le operazioni seguenti:

1. Select the **[!UICONTROL Content imported during preparation]** option.

   ![](assets/email_designer_importfromurl2.png)

1. Il contenuto dell'URL viene visualizzato nell'editor come sola lettura.

   >[!CAUTION]
   >
   >A questo passaggio, la visualizzazione HTML nell'editor di contenuto non deve essere considerata. Sarà recuperata nella fase di preparazione.

1. To preview the URL content that has been retrieved, open the message once it is created then click the **[!UICONTROL Preview]** button.

È possibile personalizzare l'URL remoto da cui verrà recuperato il contenuto. A tal fine, attenetevi alla procedura seguente:

1. Click the email label on top of the screen to acces the Email Designer **[!UICONTROL Properties]** tab.
1. Find the **[!UICONTROL Remote URL]** field.

   ![](assets/email_designer_importfromurl4.png)

1. Inserisci il campo personalizzato di personalizzazione, il blocco di contenuto o il testo dinamico.

   The **[!UICONTROL Current date - YYYYMMDD]** content block, for example, enables you to insert the date of the day.

   >[!NOTE]
   >
   >The available personalization fields are linked to **Delivery** attributes only (email creation date, status, campaign label...).

