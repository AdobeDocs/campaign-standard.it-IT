---
title: Creazione di una posta diretta
seo-title: Creazione di una posta diretta
description: Creazione di una posta diretta
seo-description: Segui questi passaggi per creare una consegna diretta in Adobe Campaign.
page-status-flag: never-activated
uuid: 3 b 1365 c 4-4 ea 1-4434-818 b -05 ff 0 c 9 b 42 c 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: direct-mail
discoiquuid: 5 b 02227 f -9438-4001-bc 2 f -3 d 8661 d 173 b 3
context-tags: delivery, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Creating the direct mail{#creating-the-direct-mail}

La creazione di una consegna diretta è molto simile alla creazione di un messaggio e-mail regolare. Nei passaggi seguenti viene descritta la configurazione specifica di questo canale. Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

1. Create una nuova consegna diretta. You can create one from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in a [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >Potete anche aggiungere un'attività posta diretta in un flusso di lavoro. For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Choose either the out-of-the-box **[!UICONTROL Direct mail]** template or one of your own templates. For more information on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

   ![](assets/direct_mail_2.png)

1. Immettete le proprietà generali della distribuzione.

   ![](assets/direct_mail_3.png)

1. Definite l'audience che desiderate includere nel file di estrazione nonché i profili di test e abbondanza. See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La definizione dell'audience è molto simile alla definizione di un normale pubblico. See [Creating audiences](../../audiences/using/creating-audiences.md).

1. Modificate il contenuto del file: colonne da includere per ciascun profilo, struttura file, intestazione e piè di pagina. See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Click on the **[!UICONTROL Schedule]** section of the delivery dashboard to define the contact date. Per la posta diretta, la data di contatto è obbligatoria. For more information, refer to [Scheduling the send](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. If you added test profiles (refer to [Adding test and trap profiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), you can test your delivery before preparing the final file. Consente di creare un file di esempio contenente solo i profili di prova selezionati.

   Click on **[!UICONTROL Test]** to generate the sample file. Click on **[!UICONTROL Summary]**, in the top left corner, then select **[!UICONTROL Proofs]**. On the left part of the screen, select the proof and click on **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >**[!UICONTROL Export]** Il ruolo è necessario per consentire ad Adobe Campaign di esportare il file e renderlo disponibile per il download. Contattate l'amministratore.

   ![](assets/direct_mail_19.png)

1. Once you have defined your delivery content, audience and contact date, click on the **[!UICONTROL Prepare]** button, on the delivery dashboard.

   ![](assets/direct_mail_16.png)

   Sono applicate regole per tipologie. Ad esempio, tutti gli indirizzi postali non specificati sono esclusi dalla destinazione. This is why you need to make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information (see [Recommendations](../../channels/using/about-direct-mail.md#recommendations)). If you have defined a **[!UICONTROL Maximum volume of message]** in the direct mail properties or at the template level, it will also be applied here.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Potete impostare regole globali di affaticamento cross-channel che escluderanno automaticamente i profili superflui dalle campagne. See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Click on **[!UICONTROL Explore file]** to preview the first 100 lines of the file.

   ![](assets/direct_mail_18.png)

   Il file completo è accessibile per il download locale nella parte sinistra della schermata. Downloading the file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

   >[!NOTE]
   >
   >**[!UICONTROL Export]** Il ruolo è necessario per consentire ad Adobe Campaign di esportare il file e renderlo disponibile per il download. Contattate l'amministratore.

   If you need to change the delivery content, you only have to click on the **[!UICONTROL Regenerate file]** button to take the change into account. senza dover ripetere la preparazione.

   ![](assets/direct_mail_21.png)

1. To confirm that the file is final, click on **[!UICONTROL Confirm]** in the delivery dashboard.

   ![](assets/direct_mail_20.png)

Siete ora pronti per inviare il file di estrazione al provider di posta diretta. A questo scopo, sono disponibili diverse opzioni:

* Inviatela tramite un messaggio e-mail regolare, con il file allegato
* Send it via Campaign: perform your direct mail within a campaign [workflow](../../automating/using/direct-mail-delivery.md) and add a **[!UICONTROL Transfer file]** to send the file via FTP for example. See [Transfer file](../../automating/using/transfer-file.md).

Il fornitore recupera l'elenco di indirizzi errati e invia queste informazioni ad Adobe Campaign, che elenca automaticamente gli indirizzi errati. See [Return to sender](../../channels/using/return-to-sender.md).
