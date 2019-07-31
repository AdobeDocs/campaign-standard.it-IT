---
title: Gestione dei profili di prova e invio di prove
seo-title: Gestione dei profili di prova e invio di prove
description: Gestione dei profili di prova e invio di prove
seo-description: Scopri come gestire profili di test e prove.
page-status-flag: never-activated
uuid: eb 4 d 893 b -3724-4 b 15-9312-1 ec 74784368 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: preparazione-and-testing-messages
discoiquuid: 37320 ec 5-196 c -4260-8156-98932 da 3 e 4 a 5
context-tags: Seedmember, panoramica
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3cb698bc5025a59771128a8df493e7e126f00cab

---


# Managing test profiles and sending proofs{#managing-test-profiles-and-sending-proofs}

## About test profiles {#about-test-profiles}

I profili di prova consentono di eseguire il targeting di altri destinatari che non corrispondono ai criteri di targeting definiti. Vengono aggiunte al pubblico di un messaggio per rilevare qualsiasi uso fraudolento del database dei destinatari o per assicurarsi che le e-mail arrivino nelle inbox.

You can manage your test profiles from the advanced menu **[!UICONTROL Profiles & audiences > Test profiles]**.

Un profilo di prova contiene informazioni fittizie di contatto o informazioni di contatto controllate dal mittente, che possono quindi essere utilizzate in un messaggio nei seguenti contesti:

* For sending **Proofs**: the Proof is a specific message used to check the message before sending the finalized delivery to recipients. Un profilo Test prova è incaricato di controllare la consegna, in relazione al contenuto e al formato. See [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* For **Email rendering**: the Email rendering test profile is used to check the way in which a message is displayed according to the message inbox that receives it. Ad esempio, webmail, servizio messaggio, mobile, ecc. See [Email rendering](../../sending/using/email-rendering.md).

   The **Email rendering** use is read-only. I profili di test con questo utilizzo sono disponibili solo in Adobe Campaign.

* **Come abbondanza**: il messaggio viene inviato al profilo di prova esattamente come viene inviato alla destinazione principale, come mezzo per determinare se il file client è utilizzato in modo fraudolento.
* To **Preview** messages: a test profile can be selected when previewing a message to test the personalization elements.

![](assets/test_profile.png)

## Managing test profiles {#managing-test-profiles}

### Creating test profiles {#creating-test-profiles}

1. From the advanced menu, via the Adobe Campaign logo, select **Profiles &amp; audiences &gt; Test profiles** to access the list of test profiles.

   ![](assets/test_profile_creation_1.png)

1. From the **[!UICONTROL Test profiles]** dashboard, click **Create**.

   ![](assets/test_profile_creation_2.png)

1. Inserite i dati per questo profilo.

   ![](assets/test_profile_creation_3.png)

1. Selezionate l'utilizzo che intendete utilizzare per il profilo di prova.

   ![](assets/test_profile_creation_4.png)

1. Enter the contact channels **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, as well as the test profile address if necessary.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. Specificate un tipo di evento e i dati per questo evento se desiderate utilizzare questo profilo di prova per testare la personalizzazione di un messaggio di transazione.
1. Click **[!UICONTROL Create]** to save the test profile.

Il profilo di prova verrà quindi aggiunto all'elenco dei profili.

**Argomento correlato:**

[Creazione di un video profilo](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) di prova

### Editing test profiles {#editing-test-profiles}

Per modificare un profilo di prova e consultare i dati che vi sono collegati oppure per modificarli:

1. Selezionate il profilo di prova che desiderate modificare facendo clic sulla relativa immagine.
1. Consulta o modifica i campi.

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.

## Sending proofs {#sending-proofs}

Una prova è un messaggio specifico che consente di testare un messaggio prima di inviarlo alla destinazione principale.

I destinatari della prova possono approvare il messaggio (contenuto e modulo). They are defined in the **Test profiles**. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

Per inviare una prova, i profili di prova devono essere inclusi nell'audience del messaggio.

In un messaggio:

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. Selezionate il tipo di prova da utilizzare:

   * **[!UICONTROL Email rendering]**: Selezionate questa opzione per verificare il modo in cui il messaggio viene ricevuto in base alle inbox di destinazione. For more information, refer to [Email rendering](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: Selezionate questa opzione per testare il messaggio prima di inviarlo alla destinazione principale. I destinatari della prova hanno la responsabilità di approvare la consegna, controllando sia il contenuto che il formato.
   * **[!UICONTROL Proof + Email rendering]**: questa opzione combina le due opzioni precedenti.
   ![](assets/bat_select1.png)

1. Confermate la scelta.

   Le prove vengono inviate ai profili di prova.

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. Selezionate una prova per accedere al relativo riepilogo. For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. See [Email rendering](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

A seconda dei commenti delle persone che ricevono la prova, potrebbe essere necessario modificare il contenuto della consegna. Una volta apportate le modifiche, dovete riavviare la preparazione e-mail e inviare nuovamente una prova. Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

Devi inviare tutte le prove necessarie fino alla finalizzazione del contenuto della distribuzione. Una volta effettuata questa operazione, potete inviarla alla destinazione principale e chiudere il processo di approvazione.

**Argomento correlato:**

[Invio di un test, preparazione e invio di un](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) video e-mail

<!-- ## Sending proofs using additional data {#sending-proofs-using-additional-data}

This section describes how to send proofs using real customer data accessible via a workflow, as opposed to using fake test profile data. This allows you to check that the variables used in the workflow are accurate and to get a view of the message that your recipients will receive.

1. Create a test profile and enable **[!UICONTROL Proof]** and **[!UICONTROL Trap]** as the intended usage. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

    This test profile becomes part of the targeted audience.

   >[!NOTE]
   >
   >When using a test profile as a trap, for any enriched fields in a message, the corresponding additional data is randomly picked from a real targeted profile and assigned to the trap test profile.

1. Access the marketing activity list and create a test workflow.

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. Add additional data from a linked table. For more on this, see [Enriching data](../../automating/using/query.md#enriching-data).

1. Drag and drop an **Email delivery** activity into your workflow and open it.

   The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.

1. From the email message dashboard, select the test profile with trap usage that you created.

1. Add to your email content personalization fields using the additional data that you defined in the Query activity.

1. Save the email and start the workflow.

During message preparation, the target count includes the test profile that you selected.
Once the message is sent, additional data is replaced by data from a real profile.

>[!NOTE]
   >
   >Only additional data are replaced. No real profile data such as first name or last name will be used for the test profile. -->
