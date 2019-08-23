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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Creazione di una notifica push multilingue{#creating-a-multilingual-push-notification}

## Informazioni sulla notifica push multilingue {#about-multilingual-push-notification}

Personalizza i contenuti delle notifiche push inviando messaggi basati sulle lingue e sulle aree preferite degli utenti. Puoi importare direttamente varianti di contenuto push in più lingue nell'editor di contenuto e inviare una notifica push multilingue in una singola consegna.

Questa funzione si basa su lingue preferite specificate nei profili dei destinatari o nelle preferenze della lingua del sistema per gli abbonati a app mobili, a seconda del modello di consegna utilizzato per la notifica push. Se la preferenza lingua non viene compilata per un particolare utente, il sistema utilizzerà la variante predefinita definita durante la creazione di una notifica push multilingue. Per ulteriori informazioni su come gestire i profili e gli abbonati, consulta questa [guida](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Per utilizzare varianti di contenuto multilingue per la distribuzione di notifiche push, procedere come segue:

* [Passaggio 1: Carica variante di contenuto multilingue](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [Passaggio 2: Visualizzare in anteprima e finalizzare una notifica push utilizzando varianti di contenuto in più lingue](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Passaggio 3: Inviare e analizzare la consegna di notifiche push in più lingue](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Passaggio 1: Carica variante di contenuto multilingue {#step-1--upload-multilingual-content-variant}

Prima di personalizzare la notifica push multilingue, occorre innanzitutto caricare le varianti di contenuto in un modello di consegna multilingue e creare la distribuzione.

>[!NOTE]
>
>Potete inoltre saltare questo passaggio se desiderate creare manualmente una variante per ogni variante lingua.

1. In **[!UICONTROL Marketing activities]**, fate clic sul **[!UICONTROL Create]** pulsante e quindi selezionate **[!UICONTROL Push notification]**.
1. Selezionate il modello **[!UICONTROL Send multilingual push to Campaign profiles]** se desiderate eseguire il targeting dei profili di Adobe Campaign che hanno sottoscritto l'applicazione mobile o il modello **[!UICONTROL Send multilingual push to app subscriber]** per inviare una notifica push a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall'applicazione mobile.

   ![](assets/multivariant_push_2.png)

1. Immetti le proprietà di notifica push e seleziona la tua app mobile nel **[!UICONTROL Associate a Mobile App to a delivery]** campo.

   Tieni presente che il menu a discesa visualizzerà le applicazioni SDK per SDK v 4 e Adobe Experience Platform.

1. Nelle **[!UICONTROL Audiences]** finestre, trascina e rilascia query per perfezionare il pubblico.

   Le query aggiunte dipendono dal modello scelto: se scegliete il **[!UICONTROL Send multilingual push to Campaign profiles]** modello, potete interrogare i destinatari noti dell'applicazione mobile. Se hai scelto il **[!UICONTROL Send multilingual push to app subscriber]** modello, puoi interrogare tutti gli abbonati di una particolare app che ha acconsentito.

   ![](assets/push_notif_audience.png)

1. Nella **[!UICONTROL Manage Content Variants]** finestra, trascinate il file o selezionate un file dal computer.

   Il file deve essere codificato in UTF 8 e deve avere un layout specifico che si trova facendo clic sull **[!UICONTROL Download the sample file]** 'opzione. È inoltre necessario utilizzare la sintassi corretta per i valori delle impostazioni internazionali. Per ulteriori informazioni sul formato di file e sulle impostazioni internazionali supportate, fare riferimento a questa [nota tecnica](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Dopo aver caricato il file, le varianti della lingua vengono popolate automaticamente nella **[!UICONTROL Variants]** scheda. Se per l'utente di destinazione non viene specificata alcuna lingua preferita, puoi fornire un **[!UICONTROL Default variant]** contenuto nel file che sarà la variante di contenuto predefinita.

   ![](assets/multivariant_push_5.png)

1. La **[!UICONTROL Variant selection]** scheda fornirà uno script per determinare quale lingua adottare in base al modello di consegna. Si tratta di uno script out-of-the-box che non richiede modifiche.
1. Se si desidera aggiungere ulteriori varianti non presenti nel file importato, fare clic sul **[!UICONTROL Add an element]** pulsante e aggiungere tutte le nuove varianti di lingua necessarie.

   Aggiungendo varianti diverse da quelle caricate dal file, nessun contenuto verrà collegato a questa lingua. Dovrete modificare il contenuto direttamente nel dashboard di distribuzione.

   ![](assets/multivariant_push_6.png)

1. Fate clic **[!UICONTROL Create]** al termine della configurazione. Potete sempre tornare alla **[!UICONTROL Content variant]** finestra e apportare alcune modifiche dal dashboard di distribuzione.

   ![](assets/multivariant_push_8.png)

Ora puoi iniziare a personalizzare la notifica push multilingue.

## Passaggio 2: Visualizzare in anteprima e finalizzare una notifica push utilizzando varianti di contenuto in più lingue {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Dopo aver caricato il file contenente varianti di contenuto, ora potete visualizzare l'anteprima delle diverse varianti dalla distribuzione push.

È inoltre possibile creare e modificare più varianti oltre a quelle caricate dal file.

1. Nella **[!UICONTROL Content]** finestra dal dashboard di distribuzione, l'elenco a discesa consente di visualizzare l'anteprima del contenuto di notifica push in base alla lingua selezionata.

   ![](assets/multivariant_push_7.png)

1. Se non viene specificata una variante di contenuto per una particolare lingua, fate clic sull'icona della campana sotto l'anteprima per iniziare ad aggiungere contenuto a questa variante della lingua.

   Facendo clic sulla **[!UICONTROL Content]** finestra, la notifica push rappresenta il contenuto della lingua selezionata nel menu a discesa. Le modifiche apportate in questa finestra hanno effetto solo su una lingua.

1. Potete anche fare clic su una variante di contenuto per personalizzarla ulteriormente ad esempio con i campi di personalizzazione.

   Per ulteriori informazioni su come personalizzare la notifica push, consulta questa [sezione](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Fare clic sulla **[!UICONTROL Content variant]** finestra per aggiungere o eliminare varianti di lingua.

   Nota: è necessario aggiungere manualmente il contenuto alla notifica push collegata al linguaggio aggiunto.

   ![](assets/multivariant_push_10.png)

La distribuzione delle notifiche push in più lingue è ora pronta per l'invio.

## Passaggio 3: Inviare e analizzare la consegna di notifiche push in più lingue {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Le notifiche push di varianti di contenuto multilingue ora sono pronte per essere inviate ai tuoi utenti.

1. Per iniziare a preparare l'invio, fate clic sul **[!UICONTROL Prepare]** pulsante.
1. Quando la preparazione è terminata senza avvertenze, potete fare clic sul **[!UICONTROL Confirm]** pulsante per iniziare a inviare il push multilingue.

   ![](assets/multivariant_push_12.png)

1. Dopo aver inviato la notifica push, fate clic sull **[!UICONTROL Reports]** 'icona e **[!UICONTROL Dynamic reports]** quindi per analizzare il successo della distribuzione.

   ![](assets/multivariant_push_13.png)

1. Seleziona **[!UICONTROL Push notification report]**.
1. Trascina la **[!UICONTROL Variant]** dimensione nel pannello per avviare il filtro dei dati.

   ![](assets/multivariant_push_11.png)

Ora puoi misurare l'impatto della consegna di notifiche push multilingue sui destinatari.

**Argomenti correlati:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all'interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)
* [Raggiungere audience in più lingue mediante un unico flusso di lavoro](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
