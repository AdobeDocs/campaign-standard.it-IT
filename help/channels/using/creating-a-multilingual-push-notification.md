---
title: Creazione di una notifica push multilingue
description: Create notifiche push multilingue per indirizzare gli utenti nelle rispettive lingue e aree geografiche preferite.
page-status-flag: never-activated
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---


# Creazione di una notifica push multilingue{#creating-a-multilingual-push-notification}

## Informazioni sulla notifica push multilingue {#about-multilingual-push-notification}

Personalizza il contenuto delle notifiche push inviando messaggi in base alle lingue e alle aree preferite dagli utenti. Potete importare direttamente varianti di contenuto per le notifiche push multilingue nell&#39;editor dei contenuti e inviare una notifica push multilingue in un&#39;unica consegna.

Questa funzione utilizza le lingue preferite specificate nei profili dei destinatari o le preferenze della lingua del sistema per gli utenti iscritti alle app mobili, a seconda del modello di consegna utilizzato per la notifica push. Se le preferenze della lingua non vengono popolate per un particolare utente, il sistema utilizzerà la variante predefinita definita durante la creazione di una notifica push multilingue. Per ulteriori informazioni su come gestire i profili e gli utenti iscritti, consulta questa [guida](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Per utilizzare varianti di contenuto multilingue per la distribuzione delle notifiche push, effettuate le seguenti operazioni:

* [Passaggio 1: Caricare una variante di contenuto multilingue](#step-1--upload-multilingual-content-variant)
* [Passaggio 2: Visualizzare in anteprima e finalizzare una notifica push utilizzando varianti di contenuto multilingue](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Passaggio 3: Inviare e analizzare la consegna di notifiche push in più lingue](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Passaggio 1: Caricare una variante di contenuto multilingue {#step-1--upload-multilingual-content-variant}

Prima di personalizzare la notifica push multilingue, è necessario caricare le varianti di contenuto in un modello di consegna multilingue e creare la consegna.

>[!NOTE]
>
>Potete inoltre saltare questo passaggio se desiderate creare manualmente una variante per ogni variante della lingua.

1. In **[!UICONTROL Marketing activities]**, fare clic sul **[!UICONTROL Create]** pulsante e selezionare **[!UICONTROL Push notification]**.
1. Selezionate il modello **[!UICONTROL Send multilingual push to Campaign profiles]** se desiderate eseguire il targeting dei profili Adobe Campaign  che hanno effettuato l&#39;iscrizione all&#39;applicazione mobile o al modello **[!UICONTROL Send multilingual push to app subscriber]** per inviare una notifica push a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall&#39;applicazione mobile.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Il menu a discesa mostrerà le applicazioni SDK SDK V4 e Adobe Experience Platform.

1. Nelle **[!UICONTROL Audiences]** finestre, trascinate le query per ottimizzare il pubblico.

   Le query aggiunte dipendono dal modello scelto: se avete scelto il **[!UICONTROL Send multilingual push to Campaign profiles]** modello, potete eseguire query ai destinatari noti dell’applicazione mobile. Se invece avete scelto il **[!UICONTROL Send multilingual push to app subscriber]** modello, potete eseguire una query a tutti gli abbonati di una particolare app che hanno acconsentito.
   >[!NOTE]
   >
   >Se eseguite il targeting di audience con lingue specifiche, dovete elencare tutte le lingue di destinazione nel file CSV.

   ![](assets/push_notif_audience.png)

1. Nella **[!UICONTROL Manage Content Variants]** finestra, trascinare il file o selezionare un file dal computer.

   Il file deve essere codificato in UTF8 e deve avere un layout specifico che può essere trovato facendo clic sull&#39; **[!UICONTROL Download the sample file]** opzione. È inoltre necessario utilizzare la sintassi corretta per i valori delle impostazioni internazionali. Per ulteriori informazioni sul formato del file e sulle impostazioni internazionali supportate, consultare questa [nota tecnica](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Dopo aver caricato il file, le varianti di lingua vengono popolate automaticamente nella **[!UICONTROL Variants]** scheda. È possibile includere nel file una **[!UICONTROL Default variant]** variante di contenuto predefinita, se non viene specificata alcuna lingua preferita per l&#39;utente di destinazione.

   ![](assets/multivariant_push_5.png)

1. La **[!UICONTROL Variant selection]** scheda fornirà uno script per determinare quale preferenza di lingua tenere conto in base al modello di consegna. Si tratta di uno script out-of-the-box che non richiede alcuna modifica.
1. Per aggiungere altre varianti non presenti nel file importato, fare clic sul **[!UICONTROL Add an element]** pulsante e aggiungere tutte le nuove varianti di lingua necessarie.

   Aggiungendo varianti diverse da quelle caricate dal file, nessun contenuto verrà collegato a questa lingua. Dovrete modificare il contenuto direttamente nel dashboard di distribuzione.

   ![](assets/multivariant_push_6.png)

1. Fate clic **[!UICONTROL Create]** al termine della configurazione. Puoi sempre tornare alla **[!UICONTROL Content variant]** finestra e apportare alcune modifiche dal dashboard di distribuzione.

   ![](assets/multivariant_push_8.png)

Ora puoi iniziare a personalizzare la notifica push multilingue.

## Passaggio 2: Visualizzare in anteprima e finalizzare una notifica push utilizzando varianti di contenuto multilingue {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Dopo aver caricato il file contenente varianti di contenuto, ora potete visualizzare in anteprima le diverse varianti dalla distribuzione delle notifiche push.

È inoltre possibile creare e modificare più varianti oltre a quelle caricate dal file.

1. Nella **[!UICONTROL Content]** finestra del dashboard di distribuzione, l&#39;elenco a discesa consente di visualizzare l&#39;anteprima del contenuto delle notifiche push in base alla lingua scelta.

   ![](assets/multivariant_push_7.png)

1. Se non è specificata una variante di contenuto per una lingua particolare, fate clic sull&#39;icona a forma di campana sotto l&#39;anteprima per iniziare ad aggiungere contenuto a questa variante di lingua.

   Facendo clic sulla **[!UICONTROL Content]** finestra, la notifica push rappresenta il contenuto della lingua selezionata nell&#39;elenco a discesa. Le modifiche apportate in questa finestra influiscono solo su una lingua.

1. Potete anche fare clic su una variante di contenuto per personalizzarla ulteriormente, ad esempio con i campi di personalizzazione.

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Fare clic sulla **[!UICONTROL Content variant]** finestra se si desidera aggiungere o eliminare varianti di lingua.

   Tenete presente che aggiungendo una nuova lingua, dovrete aggiungere manualmente il contenuto alla notifica push collegata alla lingua aggiunta.

   ![](assets/multivariant_push_10.png)

È ora possibile inviare la notifica push in più lingue.

## Passaggio 3: Inviare e analizzare la consegna di notifiche push in più lingue {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Le notifiche push delle varianti di contenuto multilingue sono ora pronte per essere inviate agli utenti.

1. Per iniziare a preparare l&#39;invio, fare clic sul **[!UICONTROL Prepare]** pulsante.
1. Quando la preparazione è finita senza avvertenze, potete fare clic sul **[!UICONTROL Confirm]** pulsante per iniziare a inviare la vostra notifica multilingue.

   ![](assets/multivariant_push_12.png)

1. Dopo aver inviato correttamente la notifica push, fate clic sull&#39; **[!UICONTROL Reports]** icona, quindi **[!UICONTROL Dynamic reports]** per analizzare il successo della distribuzione.

   ![](assets/multivariant_push_13.png)

1. Seleziona **[!UICONTROL Push notification report]**.
1. Trascina la **[!UICONTROL Variant]** dimensione nel pannello per iniziare a filtrare i dati.

   ![](assets/multivariant_push_11.png)

Ora puoi misurare l&#39;impatto della consegna di notifiche push in più lingue sui destinatari.

**Argomenti correlati:**

* [Report notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all’interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)
* [Raggiungere audience in più lingue con un unico flusso di lavoro](https://helpx.adobe.com/it/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
