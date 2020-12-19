---
solution: Campaign Standard
product: campaign
title: Hot click
description: Con il rapporto "Hot Click out-of-the-box", scopri dove il cliente ha fatto clic sulla tua consegna.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Hot click{#hot-clicks}

È possibile accedere a questo report dal pulsante **[!UICONTROL Reports]** in ogni consegna o messaggio transazionale.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ciascun collegamento.

![](assets/delivery_reports_10.png)

Se avete creato contenuto dinamico per la distribuzione, potete visualizzare le percentuali per ogni condizione definita. Per ulteriori informazioni sull&#39;inserimento di contenuto condizionale in una distribuzione, vedere [Definizione di contenuto dinamico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Ad esempio, supponiamo di aver creato una consegna con le seguenti condizioni:

* Il collegamento sull&#39;immagine principale è diverso se il destinatario è un uomo o una donna.
* È stato aggiunto anche un collegamento a un&#39;offerta speciale visibile solo ai destinatari con più di 25 anni.

Una volta inviato il messaggio, seleziona **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** dal dashboard di distribuzione.

Per impostazione predefinita, non è selezionato alcun profilo. Vengono visualizzati solo i clic per i destinatari il cui genere è sconosciuto e per i destinatari con meno di 25 anni o la cui età è sconosciuta.

![](assets/delivery_reports_hot-clicks_1.png)

Per visualizzare i clic per le donne, fate clic sul pulsante **[!UICONTROL Change profile]** e selezionate un profilo di test femminile. Per visualizzare i clic per gli uomini, procedere in modo simile e selezionare un profilo di test maschile.

![](assets/delivery_reports_hot-clicks_2.png)

Per visualizzare i clic per i destinatari con più di 25 anni, fare clic sul pulsante **[!UICONTROL Change profile]** e selezionare un profilo di prova la cui data di nascita corrisponda a questa condizione.

Per ulteriori informazioni sui profili di test, vedere [Informazioni sui profili di test](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>Il numero di clic su un collegamento specifico è una percentuale dei clic totali per tutto il contenuto condizionale in una consegna. Pertanto, se avete definito il contenuto dinamico, il totale delle percentuali visualizzate per un profilo di test specifico potrebbe non essere uguale a 100.

Allo stesso modo, per le consegne ricorrenti e i messaggi transazionali, potete selezionare il profilo di test corrispondente al contenuto dinamico che desiderate visualizzare, ma potete anche visualizzare le percentuali di clic in base alla consegna di esecuzione selezionata.

Una consegna di esecuzione è un messaggio tecnico non utilizzabile e non funzionale creato nei seguenti casi:

* Ogni volta che viene eseguita o aggiornata una consegna ricorrente.

   Ad esempio, se il flusso di lavoro che gestisce la consegna viene eseguito una volta al mese, verrà eseguito un recapito di esecuzione al mese. Inoltre, ogni volta che il contenuto della consegna viene aggiornato, viene creata una consegna di esecuzione aggiuntiva.

   Per ulteriori informazioni sulle consegne ricorrenti di e-mail, vedere [Distribuzione di e-mail](../../automating/using/email-delivery.md).

* Per impostazione predefinita, una volta al mese per i messaggi transazionali e ogni volta che un messaggio transazionale viene modificato e pubblicato di nuovo.

   Per ulteriori informazioni sui messaggi transazionali, vedere [Guida introduttiva ai messaggi transazionali](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Poiché gli ID degli URL tracciati sono diversi per ogni esecuzione, i dati dei clic attivi non possono essere aggregati per tutte le consegne di esecuzione di un dato messaggio. Può essere visualizzato solo per una consegna di esecuzione alla volta.

Una volta inviato il messaggio, seleziona **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** dal dashboard di distribuzione.

Per impostazione predefinita, è selezionato l&#39;ultimo recapito di esecuzione. Fare clic sul pulsante **[!UICONTROL Change execution delivery]** per selezionarne un altro.

![](assets/delivery_reports_hot-clicks_3.png)

Vengono visualizzate solo le percentuali di clic per l&#39;esecuzione della consegna selezionata.
