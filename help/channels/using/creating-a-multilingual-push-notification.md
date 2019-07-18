---
title: Creazione di una notifica push multilingue
seo-title: Creazione di una notifica push multilingue
description: Creazione di una notifica push multilingue
seo-description: Potete creare notifiche push in più lingue per indirizzare gli utenti alle lingue e alle aree preferite.
page-status-flag: never-activated
uuid: d 4 aff 741-e 969-47 c 6-bae 8-787 c 6 c 673191
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: notifiche push
discoiquuid: f 9 bb 2235-d 388-4025-9 ace -734 beb 0 c 1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Creating a multilingual push notification{#creating-a-multilingual-push-notification}

## About multilingual push notification {#about-multilingual-push-notification}

Personalizza i contenuti delle notifiche push inviando messaggi basati sulle lingue e sulle aree preferite degli utenti. Puoi importare direttamente varianti di contenuto push in più lingue nell'editor di contenuto e inviare una notifica push multilingue in una singola consegna.

Questa funzione si basa su lingue preferite specificate nei profili dei destinatari o nelle preferenze della lingua del sistema per gli abbonati a app mobili, a seconda del modello di consegna utilizzato per la notifica push. Se la preferenza lingua non viene compilata per un particolare utente, il sistema utilizzerà la variante predefinita definita durante la creazione di una notifica push multilingue. For more information on how to manage your profiles and subscribers, refer to this [guide](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Per utilizzare varianti di contenuto multilingue per la distribuzione di notifiche push, procedere come segue:

* [Passaggio 1: Carica variante di contenuto multilingue](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [Passaggio 2: Visualizzare in anteprima e finalizzare una notifica push utilizzando varianti di contenuto in più lingue](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Passaggio 3: Inviare e analizzare la consegna di notifiche push in più lingue](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Step 1: Upload multilingual content variant {#step-1--upload-multilingual-content-variant}

Prima di personalizzare la notifica push multilingue, occorre innanzitutto caricare le varianti di contenuto in un modello di consegna multilingue e creare la distribuzione.

>[!NOTE]
>
>Potete inoltre saltare questo passaggio se desiderate creare manualmente una variante per ogni variante lingua.

1. In the **[!UICONTROL Marketing activities]**, click the **[!UICONTROL Create]** button then select **[!UICONTROL Push notification]**.
1. Select the template **[!UICONTROL Send multilingual push to Campaign profiles]** if you want to target the Adobe Campaign profiles who have subscribed to your mobile application or the template **[!UICONTROL Send multilingual push to app subscriber]** to send a push notification to all users who have opted in to receive notifications from your mobile application.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tieni presente che il menu a discesa visualizzerà le applicazioni SDK per SDK v 4 e Adobe Experience Platform.

1. In the **[!UICONTROL Audiences]** windows, drag and drop queries to fine tune your audience.

   The queries added depend on the chosen template: if you chose the **[!UICONTROL Send multilingual push to Campaign profiles]** template you can query known recipients of your mobile application. Whereas if you chose the **[!UICONTROL Send multilingual push to app subscriber]** template, you can query all subscribers of a particular app who have opted in.

   ![](assets/push_notif_audience.png)

1. In the **[!UICONTROL Manage Content Variants]** window, drag and drop your file or select a file from your computer.

   The file has to be UTF8 encoded and must have a specific layout which can be found by clicking the **[!UICONTROL Download the sample file]** option. È inoltre necessario utilizzare la sintassi corretta per i valori delle impostazioni internazionali. For more information regarding the file format and the supported locales, refer to this [technote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. After uploading your file, the language variants are automatically populated in the **[!UICONTROL Variants]** tab. Note that you can provide a **[!UICONTROL Default variant]** in the file which will be your default content variant if no preferred language is specified for the targeted user.

   ![](assets/multivariant_push_5.png)

1. The **[!UICONTROL Variant selection]** tab will provide a script to determine which language preference to take into account depending on the delivery template. Si tratta di uno script out-of-the-box che non richiede modifiche.
1. If you want to add more variants not present in the imported file, you can do so by clicking the **[!UICONTROL Add an element]** button and add as many new language variants as needed.

   Aggiungendo varianti diverse da quelle caricate dal file, nessun contenuto verrà collegato a questa lingua. Dovrete modificare il contenuto direttamente nel dashboard di distribuzione.

   ![](assets/multivariant_push_6.png)

1. Click **[!UICONTROL Create]** when the configuration is done. You can always come back to the **[!UICONTROL Content variant]** window and make some changes from your delivery dashboard.

   ![](assets/multivariant_push_8.png)

Ora puoi iniziare a personalizzare la notifica push multilingue.

## Step 2: Preview and finalize a push notification using multilingual content variants {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Dopo aver caricato il file contenente varianti di contenuto, ora potete visualizzare l'anteprima delle diverse varianti dalla distribuzione push.

È inoltre possibile creare e modificare più varianti oltre a quelle caricate dal file.

1. In the **[!UICONTROL Content]** window from the delivery dashboard, the drop-down allows you to preview your push notification content depending on the chosen language.

   ![](assets/multivariant_push_7.png)

1. Se non viene specificata una variante di contenuto per una particolare lingua, fate clic sull'icona della campana sotto l'anteprima per iniziare ad aggiungere contenuto a questa variante della lingua.

   By clicking the **[!UICONTROL Content]** window, the push notification represents the content from the language selected in the drop down. Le modifiche apportate in questa finestra hanno effetto solo su una lingua.

1. Potete anche fare clic su una variante di contenuto per personalizzarla ulteriormente ad esempio con i campi di personalizzazione.

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Click the **[!UICONTROL Content variant]** window if you want to add or delete language variants.

   Nota: è necessario aggiungere manualmente il contenuto alla notifica push collegata al linguaggio aggiunto.

   ![](assets/multivariant_push_10.png)

La distribuzione delle notifiche push in più lingue è ora pronta per l'invio.

## Step 3: Send and analyze multilingual push notification delivery {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Le notifiche push di varianti di contenuto multilingue ora sono pronte per essere inviate ai tuoi utenti.

1. To start preparing the send, click the **[!UICONTROL Prepare]** button.
1. When the preparation is finished with no warnings, you can click the **[!UICONTROL Confirm]** button to start sending your multilingual push.

   ![](assets/multivariant_push_12.png)

1. After successfully sending your push notification, click the **[!UICONTROL Reports]** icon then **[!UICONTROL Dynamic reports]** to analyze the success of your delivery.

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. Drag and drop the **[!UICONTROL Variant]** dimension to your panel to start filtering your data.

   ![](assets/multivariant_push_11.png)

Ora puoi misurare l'impatto della consegna di notifiche push multilingue sui destinatari.

**Argomenti correlati:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all'interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)

