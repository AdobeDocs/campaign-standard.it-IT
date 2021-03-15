---
solution: Campaign Standard
product: campaign
title: Hot click
description: Con il rapporto pronto all’uso sui clic, scopri dove il cliente ha fatto clic sulla consegna.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Generazione rapporti
role: Leader
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 1%

---


# Hot click{#hot-clicks}

Puoi accedere a questo rapporto dal pulsante **[!UICONTROL Reports]** in ogni consegna o messaggio transazionale.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ciascun collegamento.

![](assets/delivery_reports_10.png)

Se hai creato contenuto dinamico per la consegna, puoi visualizzare le percentuali per ogni condizione definita. Per ulteriori informazioni sull’inserimento di contenuto condizionale in una consegna, consulta [Definizione del contenuto dinamico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Ad esempio, immagina di creare una consegna con le seguenti condizioni:

* Il collegamento sull&#39;immagine principale è diverso se il destinatario è un uomo o una donna.
* Inoltre hai aggiunto un collegamento a un’offerta speciale visibile solo ai destinatari con più di 25 anni.

Una volta inviato il messaggio, seleziona **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** dal dashboard di consegna.

Per impostazione predefinita, non è selezionato alcun profilo. Vengono visualizzati solo i clic per i destinatari il cui genere è sconosciuto e per i destinatari la cui età è sconosciuta o inferiore ai 25 anni.

![](assets/delivery_reports_hot-clicks_1.png)

Per visualizzare i clic per le donne, fai clic sul pulsante **[!UICONTROL Change profile]** e seleziona un profilo di test femminile. Per visualizzare i clic per gli uomini, procedere in modo simile e selezionare un profilo di test maschile.

![](assets/delivery_reports_hot-clicks_2.png)

Per visualizzare i clic per i destinatari con più di 25 anni, fai clic sul pulsante **[!UICONTROL Change profile]** e seleziona un profilo di test la cui data di nascita corrisponde a questa condizione.

Per ulteriori informazioni sui profili di test, consulta [Informazioni sui profili di test](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>Il numero di clic su un collegamento specifico è una percentuale dei clic totali per tutto il contenuto condizionale di una consegna. Pertanto, se hai definito il contenuto dinamico, il totale delle percentuali visualizzate per un profilo di test specifico potrebbe non essere uguale a 100.

Analogamente, per le consegne ricorrenti e i messaggi transazionali, puoi selezionare il profilo di test corrispondente al contenuto dinamico che desideri visualizzare, ma puoi anche visualizzare le percentuali di clic in base alla consegna di esecuzione selezionata.

Una consegna di esecuzione è un messaggio tecnico non utilizzabile e non funzionale creato nei seguenti casi:

* Ogni volta che viene eseguita o aggiornata una consegna ricorrente.

   Ad esempio, se il flusso di lavoro che gestisce questa consegna viene eseguito una volta al mese, verrà eseguita una consegna di esecuzione al mese. Inoltre, ogni volta che il contenuto della consegna viene aggiornato, viene creata un’ulteriore consegna di esecuzione.

   Per ulteriori informazioni sulle consegne e-mail ricorrenti, consulta [Consegna e-mail](../../automating/using/email-delivery.md).

* Per impostazione predefinita, una volta al mese per i messaggi transazionali e ogni volta che un messaggio transazionale viene modificato e pubblicato di nuovo.

   Per ulteriori informazioni sui messaggi transazionali, consulta [Guida introduttiva alla messaggistica transazionale](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Poiché gli ID degli URL tracciati sono diversi per ogni esecuzione, i dati degli hot click non possono essere aggregati per tutte le consegne di esecuzione di un messaggio specifico. Può essere visualizzato solo per una consegna di esecuzione alla volta.

Una volta inviato il messaggio, seleziona **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** dal dashboard di consegna.

Per impostazione predefinita, è selezionata l’ultima consegna di esecuzione. Fai clic sul pulsante **[!UICONTROL Change execution delivery]** per selezionarne un altro.

![](assets/delivery_reports_hot-clicks_3.png)

Vengono visualizzate solo le percentuali di clic per l’esecuzione della consegna selezionata.
