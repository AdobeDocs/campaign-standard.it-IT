---
title: Progettazione di un'e-mail di test A/B
seo-title: Progettazione di un'e-mail di test A/B
description: Progettazione di un'e-mail di test A/B
seo-description: Scopri la funzionalità di test A/B ed effettua questi passaggi per creare un'e-mail da un modello di test A/B in Adobe Campaign.
page-status-flag: never-activated
uuid: 104 f 6973-68 a 7-4692-a 90 a-a 5570 a 980 ec 7
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: email-messages
discoiquuid: e 249 ba 70-90 d 0-43 f 2-868 c-ce 9 fdc 7 e 642 d
context-tags: delivery, abtest, back; Deliverycreation, wizard; distribuzione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Designing an A/B test email{#designing-an-a-b-test-email}

La funzionalità di test A/B in Adobe Campaign consente di definire due varianti e-mail. Ogni variante viene inviata agli esempi di popolazione per determinare il risultato migliore. Una volta determinata, la variante vincente viene inviata alla popolazione rimanente.

Potete scegliere di variare il contenuto, l'oggetto o il mittente dell'e-mail.

>[!NOTE]
>
>I test A/B sulle e-mail create in Adobe Experience Manager non sono possibili.

## Creating an A/B test email {#creating-an-a-b-test-email}

Un test A/B può essere creato utilizzando la procedura guidata di creazione e-mail standard, a cui viene aggiunto un passaggio di configurazione A/B. Creating a standard email is detailed in the [Creating an email](../../channels/using/creating-an-email.md) section.

Nel contesto specifico di un test A/B:

1. Create un nuovo messaggio e-mail da uno dei tre modelli A/B, in base all'elemento che desiderate variare:

   * Test A/B sul mittente
   * Test A/B sul contenuto
   * Test A/B sull'oggetto
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >I modelli di test A/B sono nascosti per impostazione predefinita. Check the A/B test box on the left side ( **[!UICONTROL Filter]** lateral panel) to display them.

1. Definite le proprietà generali e il pubblico di destinazione dell'e-mail, esattamente come per un'e-mail standard. Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. Al quarto passaggio della procedura guidata Creazione, definite i parametri di test A/B:

   * **[!UICONTROL Number of variants]**: È possibile scegliere di utilizzare due o tre varianti. Se scegliete tre varianti, questa scelta non può essere modificata dopo che questo passaggio è stato confermato nella procedura guidata.
   * **[!UICONTROL Winning strategy]**: Selezionate il criterio da utilizzare per determinare la variante vincente.
   * **[!UICONTROL Target breakdown]**: Scegliete quale percentuale della destinazione riceverà ogni variante. La percentuale rimanente riceverà la variante vincente una volta determinata. I profili di destinazione sono selezionati in modo casuale.
   * **[!UICONTROL Winner sending method]**: Scegliete se la variante vincente deve essere inviata automaticamente una volta determinata o se desiderate confermare manualmente l'invio alla popolazione rimanente.
   * **[!UICONTROL Test duration]**: Specificate la durata del test. La variante vincente viene determinata automaticamente dopo tale durata. Potete scegliere manualmente la variante vincente prima della fine del test dal dashboard e-mail.

      Il test deve essere almeno un'ora affinché tutti i dati di tracciamento siano raccolti e presi in considerazione correttamente per selezionare la variante vincente.
   ![](assets/ab_parameters.png)

1. Una volta definiti i parametri di test A/B, passate al passaggio successivo nella procedura guidata e definite il contenuto dell'e-mail. A seconda del modello scelto, potete definire diversi argomenti, vari nomi di mittente o diversi contenuti. Utilizzare il carosello per spostarsi tra le diverse varianti dell'elemento. For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/create_ab_testing2.png)

1. Confermate la creazione dell'e-mail. Il pannello e-mail verrà quindi visualizzato.
1. Pianificate l'invio. La data definita indica l'inizio del test A/B.
1. Check the A/B test parameters displayed in the **[!UICONTROL A/B test parameters]** block. Potete modificarle fino a quando non confermate l'invio del test (passaggio 9) selezionando il blocco.

   ![](assets/create_ab_testing3.png)

1. Preparate l'invio e-mail per analizzare la destinazione e il numero di messaggi da inviare. Consult the [Preparing the send](../../sending/using/preparing-the-send.md) section.
1. Prima di inviare il test A/B, controllate l'e-mail inviando le prove.
1. Una volta completata la preparazione, confermate l'invio del test. Una volta confermato, i parametri di test A/B non possono essere modificati.

   The A/B test starts on the date defined in the **[!UICONTROL Schedule]**.You can track its progress using the **[!UICONTROL A/B test]** and **[!UICONTROL Deployment]** blocks.

   Potete selezionare manualmente la variante vincente in qualsiasi momento se desiderate tagliare la durata del test.

   Once testing has finished, a summary table is displayed in the **[!UICONTROL A/B Test]** block and this allows you to view the various indicators for the different variants that were tested.

1. If you have selected **[!UICONTROL Send after confirmation]** as the sending method, you have to manually select the winning variant to start sending it to the remaining population. If you have selected **[!UICONTROL Automatic]**, the winning variant is automatically sent to the remaining population as soon as it has been determined by the system.

   >[!NOTE]
   >
   >In caso di collegamento, la variante vincente deve essere selezionata manualmente. Potete avvisare l'autore e i modificatori dell'e-mail che è stata scelta o meno una variante. See [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

L'e-mail ora è definita e inviata. Potete accedere ai suoi registri e ai rapporti per misurare il successo della campagna.

**Argomento** correlato:

[Creazione di](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-email-from-homepage-feature-video-use.html) un video e-mail

## About A/B test indicators {#about-a-b-test-indicators}

Nel dashboard e-mail, sono disponibili diversi indicatori per misurare il test A/B: numero di clic, aperture, rimbalzi e così via.

Note that the **[!UICONTROL Estimated recipient reactivity]** indicator is a rate comparing the number of recipients who clicked against the number of recipients who opened the email. Ad esempio, se 10 destinatari hanno aperto l'e-mail e l'utente ha fatto clic su 5 destinatari. Il tasso di attività è 50%.
