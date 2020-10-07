---
title: Hot click
description: Con il rapporto "Hot Click out-of-the-box", scopri dove il cliente ha fatto clic sulla tua consegna.
page-status-flag: never-activated
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---


# Hot click{#hot-clicks}

È possibile accedere a questo rapporto dal **[!UICONTROL Reports]** pulsante in ogni consegna o messaggio transazionale.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ciascun collegamento.

![](assets/delivery_reports_10.png)

Se avete creato contenuto dinamico per la distribuzione, potete visualizzare le percentuali per ogni condizione definita. Per ulteriori informazioni sull&#39;inserimento di contenuto condizionale in una consegna, consultate [Definizione del contenuto](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)dinamico.

Ad esempio, supponiamo di aver creato una consegna con le seguenti condizioni:

* Il collegamento sull&#39;immagine principale è diverso se il destinatario è un uomo o una donna.
* È stato aggiunto anche un collegamento a un&#39;offerta speciale visibile solo ai destinatari con più di 25 anni.

Una volta inviato il messaggio, seleziona **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** dal dashboard di distribuzione.

Per impostazione predefinita, non è selezionato alcun profilo. Vengono visualizzati solo i clic per i destinatari il cui genere è sconosciuto e per i destinatari con meno di 25 anni o la cui età è sconosciuta.

![](assets/delivery_reports_hot-clicks_1.png)

Per visualizzare i clic per le donne, fate clic sul **[!UICONTROL Change profile]** pulsante e selezionate un profilo di test femminile. Per visualizzare i clic per gli uomini, procedere in modo simile e selezionare un profilo di test maschile.

![](assets/delivery_reports_hot-clicks_2.png)

Per visualizzare i clic per i destinatari con più di 25 anni, fare clic sul **[!UICONTROL Change profile]** pulsante e selezionare un profilo di test la cui data di nascita corrisponda a questa condizione.

Per ulteriori informazioni sui profili di test, consultate [Informazioni sui profili](../../audiences/using/managing-test-profiles.md)di test.

>[!NOTE]
>
>Il numero di clic su un collegamento specifico è una percentuale dei clic totali per tutto il contenuto condizionale in una consegna. Pertanto, se avete definito il contenuto dinamico, il totale delle percentuali visualizzate per un profilo di test specifico potrebbe non essere uguale a 100.

Allo stesso modo, per le consegne ricorrenti e i messaggi transazionali, potete selezionare il profilo di test corrispondente al contenuto dinamico che desiderate visualizzare, ma potete anche visualizzare le percentuali di clic in base alla consegna di esecuzione selezionata.

Una consegna di esecuzione è un messaggio tecnico non utilizzabile e non funzionale creato nei seguenti casi:

* Ogni volta che viene eseguita o aggiornata una consegna ricorrente.

   Ad esempio, se il flusso di lavoro che gestisce la consegna viene eseguito una volta al mese, verrà eseguito un recapito di esecuzione al mese. Inoltre, ogni volta che il contenuto della consegna viene aggiornato, viene creata una consegna di esecuzione aggiuntiva.

   Per ulteriori informazioni sulle consegne e-mail ricorrenti, consulta [Invio](../../automating/using/email-delivery.md)e-mail.

* Per impostazione predefinita, una volta al mese per i messaggi transazionali e ogni volta che un messaggio transazionale viene modificato e pubblicato di nuovo.

   Per ulteriori informazioni sui messaggi transazionali, consulta [Guida introduttiva ai messaggi](../../channels/using/getting-started-with-transactional-msg.md)transazionali.

>[!NOTE]
>
>Poiché gli ID degli URL tracciati sono diversi per ogni esecuzione, i dati dei clic attivi non possono essere aggregati per tutte le consegne di esecuzione di un dato messaggio. Può essere visualizzato solo per una consegna di esecuzione alla volta.

Una volta inviato il messaggio, seleziona **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** dal dashboard di distribuzione.

Per impostazione predefinita, è selezionato l&#39;ultimo recapito di esecuzione. Fate clic sul **[!UICONTROL Change execution delivery]** pulsante per selezionarne un altro.

![](assets/delivery_reports_hot-clicks_3.png)

Vengono visualizzate solo le percentuali di clic per l&#39;esecuzione della consegna selezionata.
