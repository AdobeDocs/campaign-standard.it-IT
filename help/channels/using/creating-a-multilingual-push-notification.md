---
solution: Campaign Standard
product: campaign
title: Creazione di una notifica push multilingue
description: Crea notifiche push multilingue per eseguire il targeting degli utenti nelle loro lingue e aree geografiche preferite.
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '921'
ht-degree: 3%

---

# Creazione di una notifica push multilingue{#creating-a-multilingual-push-notification}

## Informazioni sulla notifica push multilingue {#about-multilingual-push-notification}

Personalizza il contenuto delle notifiche push inviando messaggi in base alle lingue e alle aree geografiche preferite dagli utenti. Puoi importare direttamente varianti di contenuto di notifiche push multilingue nell’editor dei contenuti e inviare una notifica push multilingue in un’unica consegna.

Questa funzione sfrutta le lingue preferite specificate nei profili dei destinatari o la preferenza relativa alla lingua del sistema per gli abbonati alle app mobili in base al modello di consegna utilizzato per le notifiche push. Se la preferenza per la lingua non viene compilata per un particolare utente, il sistema utilizza la variante predefinita definita durante la creazione di una notifica push multilingue. Per ulteriori informazioni su come gestire profili e abbonati, consulta questa [guida](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Per utilizzare varianti di contenuto multilingue per la consegna delle notifiche push, effettua le seguenti operazioni:

* [Passaggio 1: Carica variante di contenuto multilingue](#step-1--upload-multilingual-content-variant)
* [Passaggio 2: Anteprima e finalizzazione di una notifica push utilizzando varianti di contenuto multilingue](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Passaggio 3: Inviare e analizzare la consegna delle notifiche push multilingue](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Passaggio 1: Carica variante di contenuto multilingue {#step-1--upload-multilingual-content-variant}

Prima di personalizzare la notifica push multilingue, è necessario caricare le varianti di contenuto in un modello di consegna multilingue e creare la consegna.

>[!NOTE]
>
>Puoi anche saltare questo passaggio se desideri creare manualmente una variante per ogni variante della lingua.

1. In **[!UICONTROL Marketing activities]**, fai clic sul pulsante **[!UICONTROL Create]** , quindi seleziona **[!UICONTROL Push notification]**.
1. Seleziona il modello **[!UICONTROL Send multilingual push to Campaign profiles]** se desideri eseguire il targeting dei profili Adobe Campaign abbonati alla tua app mobile o al modello **[!UICONTROL Send multilingual push to app subscriber]** per inviare una notifica push a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dalla tua app mobile.

   ![](assets/multivariant_push_2.png)

1. Immetti le proprietà di notifica push e seleziona la tua app mobile nel campo **[!UICONTROL Associate a Mobile App to a delivery]** .

   Il menu a discesa visualizza le applicazioni SDK V4 e Adobe Experience Platform.

1. Nelle finestre **[!UICONTROL Audiences]** , trascina e rilascia le query per ottimizzare il pubblico.

   Le query aggiunte dipendono dal modello scelto: se hai scelto il modello **[!UICONTROL Send multilingual push to Campaign profiles]**, puoi eseguire query sui destinatari noti della tua app mobile. Se invece hai scelto il modello **[!UICONTROL Send multilingual push to app subscriber]**, puoi eseguire una query su tutti gli abbonati di una particolare app che hanno acconsentito.
   >[!NOTE]
   >
   >Se esegui il targeting di tipi di pubblico con lingue specifiche, devi elencare tutte le lingue di destinazione nel file CSV.

   ![](assets/push_notif_audience.png)

1. Nella finestra **[!UICONTROL Manage Content Variants]**, trascina e rilascia il file o seleziona un file dal computer.

   Il file deve essere codificato in UTF8 e deve avere un layout specifico che può essere trovato facendo clic sull&#39;opzione **[!UICONTROL Download the sample file]**. È inoltre necessario utilizzare la sintassi corretta per i valori delle impostazioni internazionali. Per ulteriori informazioni sul formato del file e sulle impostazioni internazionali supportate, consulta questa [nota tecnica](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Dopo aver caricato il file, le varianti di lingua vengono popolate automaticamente nella scheda **[!UICONTROL Variants]** . Tieni presente che nel file puoi specificare una **[!UICONTROL Default variant]** che sarà la variante di contenuto predefinita se non è specificata alcuna lingua preferita per l’utente di destinazione.

   ![](assets/multivariant_push_5.png)

1. La scheda **[!UICONTROL Variant selection]** fornirà uno script per determinare quale preferenza di lingua tenere conto in base al modello di consegna. Si tratta di uno script preconfigurato che non richiede l’esecuzione di modifiche.
1. Per aggiungere altre varianti non presenti nel file importato, fai clic sul pulsante **[!UICONTROL Add an element]** e aggiungi tutte le nuove varianti di lingua necessarie.

   Aggiungendo varianti diverse da quelle caricate dal file, nessun contenuto verrà collegato a questa lingua. Dovrai modificare il contenuto direttamente nel dashboard di consegna.

   ![](assets/multivariant_push_6.png)

1. Al termine della configurazione, fai clic su **[!UICONTROL Create]** . Puoi sempre tornare alla finestra **[!UICONTROL Content variant]** e apportare alcune modifiche dal dashboard di consegna.

   ![](assets/multivariant_push_8.png)

Ora puoi iniziare a personalizzare la notifica push multilingue.

## Passaggio 2: Anteprima e finalizzazione di una notifica push utilizzando varianti di contenuto multilingue {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Dopo aver caricato il file contenente varianti di contenuto, ora puoi visualizzare in anteprima le diverse varianti dalla consegna delle notifiche push.

È anche possibile creare e modificare più varianti oltre a quelle caricate dal file .

1. Nella finestra **[!UICONTROL Content]** del dashboard di consegna, l’elenco a discesa ti consente di visualizzare in anteprima il contenuto delle notifiche push in base alla lingua scelta.

   ![](assets/multivariant_push_7.png)

1. Se non è specificata una variante di contenuto per una lingua specifica, fai clic sull’icona a forma di campana sotto l’anteprima per iniziare ad aggiungere contenuto a questa variante di lingua.

   Facendo clic sulla finestra **[!UICONTROL Content]** , la notifica push rappresenta il contenuto della lingua selezionata nel menu a discesa. Le modifiche apportate in questa finestra avranno un impatto solo su una lingua.

1. Puoi anche fare clic su una variante di contenuto per personalizzarla ulteriormente, ad esempio con i campi di personalizzazione.

   Per ulteriori informazioni su come personalizzare la notifica push, consulta questa [sezione](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Fare clic sulla finestra **[!UICONTROL Content variant]** per aggiungere o eliminare varianti di lingua.

   Aggiungi una nuova lingua per aggiungere manualmente contenuti alla notifica push collegata alla lingua aggiunta.

   ![](assets/multivariant_push_10.png)

La consegna delle notifiche push multilingue è ora pronta per essere inviata.

## Passaggio 3: Inviare e analizzare la consegna delle notifiche push multilingue {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Le notifiche push con varianti di contenuto multilingue sono ora pronte per essere inviate agli utenti.

1. Per iniziare a preparare l’invio, fai clic sul pulsante **[!UICONTROL Prepare]** .
1. Una volta completata la preparazione senza avvisi, puoi fare clic sul pulsante **[!UICONTROL Confirm]** per iniziare a inviare il push multilingue.

   ![](assets/multivariant_push_12.png)

1. Dopo aver inviato correttamente la notifica push, fai clic sull’icona **[!UICONTROL Reports]** e quindi **[!UICONTROL Dynamic reports]** per analizzare il successo della consegna.

   ![](assets/multivariant_push_13.png)

1. Seleziona **[!UICONTROL Push notification report]**.
1. Trascina e rilascia la dimensione **[!UICONTROL Variant]** nel pannello per iniziare a filtrare i dati.

   ![](assets/multivariant_push_11.png)

Ora puoi misurare l’impatto della consegna di notifiche push multilingue sui destinatari.

**Argomenti correlati:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all’interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)
* [Raggiungere un pubblico multilingue tramite un unico flusso di lavoro](https://helpx.adobe.com/it/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
