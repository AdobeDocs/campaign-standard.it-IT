---
title: Progettazione di un messaggio e-mail per test A/B
description: Scopri la funzionalità di test A/B e segui questi passaggi per creare un’e-mail da un modello di test A/B in Adobe Campaign.
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
internal: n
snippet: y
translation-type: ht
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2
workflow-type: ht
source-wordcount: '832'
ht-degree: 100%

---


# Progettazione di un messaggio e-mail per test A/B{#designing-an-a-b-test-email}

La funzionalità di test A/B in Adobe Campaign ti consente di definire due o tre varianti di e-mail. Ogni variante viene inviata a campioni di popolazione per determinare quale ha il risultato migliore. Una volta determinata, la variante vincente viene quindi inviata alla popolazione rimanente.

Puoi scegliere di variare il contenuto, l’oggetto o il mittente dell’e-mail.

>[!NOTE]
>
>Non è possibile eseguire test A/B sulle e-mail create in Adobe Experience Manager.

## Creazione di un messaggio e-mail per test A/B {#creating-an-a-b-test-email}

È possibile creare un test A/B utilizzando la procedura guidata standard per la creazione di un’e-mail, alla quale viene aggiunto un passaggio di configurazione del test A/B. La creazione di un’e-mail standard è descritta nella sezione [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md).

Nel contesto specifico di un test A/B:

1. Crea una nuova e-mail da uno dei tre modelli specifici di test A/B, in base all’elemento che desideri variare:

   * Test A/B sul mittente
   * Test A/B sul contenuto
   * Test A/B sull’oggetto
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >I modelli di test A/B e di follow-up sono nascosti per impostazione predefinita. Per visualizzarli, seleziona la casella del test A/B sul lato sinistro (pannello laterale **[!UICONTROL Filter]**).

1. Definisci le proprietà generali e il pubblico target dell’e-mail, come per un’e-mail standard. Consulta la sezione [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).
1. Al quarto passaggio della procedura guidata di creazione, definisci i parametri del test A/B:

   * **[!UICONTROL Number of variants]**: puoi scegliere di utilizzare due o tre varianti. Se scegli tre varianti, questa scelta non può essere modificata dopo la conferma del passaggio nella procedura guidata.
   * **[!UICONTROL Winning strategy]**: seleziona il criterio da utilizzare per determinare la variante vincente.
   * **[!UICONTROL Target breakdown]**: scegli quale percentuale del target riceverà ogni variante. La percentuale rimanente riceverà la variante vincente una volta determinata. I profili di destinazione vengono selezionati in modo casuale.
   * **[!UICONTROL Winner sending method]**: scegli se desideri che la variante vincente sia inviata automaticamente una volta determinata o se desideri confermare manualmente l’invio alla popolazione rimanente.
   * **[!UICONTROL Test duration]**: specifica la durata del test. La variante vincente viene determinata automaticamente dopo tale durata. Puoi scegliere manualmente la variante vincente prima della fine del test dal dashboard e-mail.

      Il test deve essere di almeno un’ora affinché tutti i dati di tracciamento siano raccolti e presi in considerazione correttamente per selezionare la variante vincente.
   ![](assets/ab_parameters.png)

1. Una volta definiti i parametri del test A/B, passa al passaggio successivo nella procedura guidata e definisci il contenuto dell’e-mail. A seconda del modello scelto, puoi definire diversi oggetti, diversi nomi di mittenti o diversi contenuti differenti. Utilizza il carosello per navigare tra le diverse varianti dell’elemento. Per ulteriori informazioni, consulta la sezione [editor di contenuti](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/create_ab_testing2.png)

1. Conferma la creazione dell’e-mail. Verrà quindi visualizzato il dashboard e-mail.
1. Pianifica l’invio. La data definita indica l’inizio del test A/B.
1. Verifica i parametri del test A/B visualizzati nel blocco **[!UICONTROL A/B test parameters]**. Puoi modificarli fino a quando non confermi l’invio del test (passaggio 9) selezionando il blocco.

   ![](assets/create_ab_testing3.png)

1. Prepara l’invio dell’e-mail per analizzare il target e il numero di messaggi da inviare. Consulta la sezione [Preparazione dell’invio](../../sending/using/preparing-the-send.md).
1. Prima di inviare il test A/B, verifica l’e-mail inviando delle bozze.
1. Al termine della preparazione, conferma l’invio del test. Una volta confermati, i parametri del test A/B non possono essere modificati.

   Il test A/B viene avviato nella data definita nella **[!UICONTROL Schedule]**. Puoi tracciarne l’avanzamento utilizzando i blocchi **[!UICONTROL A/B test]** e **[!UICONTROL Deployment]**.

   Puoi selezionare manualmente la variante vincente in qualsiasi momento se desideri ridurre la durata del test.

   Al termine del test, nel blocco **[!UICONTROL A/B Test]** viene visualizzata una tabella di riepilogo che ti consente di visualizzare i vari indicatori per le diverse varianti testate.

1. Se hai selezionato **[!UICONTROL Send after confirmation]** come metodo di invio, devi selezionare manualmente la variante vincente per iniziare a inviarla alla popolazione rimanente. Se hai selezionato **[!UICONTROL Automatic]**, la variante vincente viene inviata automaticamente alla popolazione rimanente non appena è stata determinata dal sistema.

   >[!NOTE]
   >
   >Se si verifica un pareggio, la variante vincente deve essere selezionata manualmente. Puoi notificare chi ha creato e modificato l’e-mail che una variante è stata scelta o deve essere selezionata. Consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).

L’e-mail viene ora definita e inviata. Puoi accedere ai relativi log e report per misurare il successo della campagna.

**Argomento correlato**:

Video sulla [Creazione di un messaggio e-mail](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)

## Informazioni sugli indicatori del test A/B {#about-a-b-test-indicators}

Nel dashboard e-mail sono disponibili diversi indicatori che ti consentono di misurare il test A/B: numero di clic, aperture, mancate consegne e così via.

L’indicatore **[!UICONTROL Estimated recipient reactivity]** è un tasso che confronta il numero di destinatari che hanno fatto clic con il numero di destinatari che hanno aperto l’e-mail. Ad esempio, se 10 destinatari hanno aperto l’e-mail e 5 destinatari hanno fatto clic su di essa. Il tasso di reattività è del 50%.
