---
title: Clic su
seo-title: Clic su
description: Clic su
seo-description: Con l'opzione Click (Sensibile), fai clic sul rapporto che hai selezionato per la distribuzione.
page-status-flag: never-activated
uuid: 7 ed 49 dd 3-d 7 ee -466 a -9 a 7 b-d 2 aa 16961667
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: list-of-reports
discoiquuid: ecbc 1 ade -63 d 9-4 ac 2-9828-380 a 1 aa 95094
context-tags: Deliveryhotclicksreport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Hot clicks{#hot-clicks}

This report can be accessed from the **[!UICONTROL Reports]** button in each delivery or transactional message.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ogni collegamento.

![](assets/delivery_reports_10.png)

Se avete creato contenuti dinamici per la distribuzione, potete visualizzare le percentuali per ogni condizione definita. For more on inserting conditional content in a delivery, see [Defining dynamic content](../../designing/using/defining-dynamic-content-in-a-landing-page.md).

Ad esempio, supponiamo che sia stata creata una distribuzione con le condizioni seguenti:

* Il collegamento sull'immagine principale è diverso se il destinatario è un uomo o una donna.
* Hai anche aggiunto un collegamento a un'offerta speciale che è visibile solo ai destinatari oltre il 25.

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

Per impostazione predefinita, non è selezionato alcun profilo. Solo i clic per i destinatari il cui genere è sconosciuto e per i destinatari che sono inferiori a 25 o la cui età è sconosciuta.

![](assets/delivery_reports_hot-clicks_1.png)

To display clicks for women, click the **[!UICONTROL Change profile]** button and select a female test profile. Per visualizzare i clic per gli utenti, procedete in modo simile e selezionate un profilo di test maschile.

![](assets/delivery_reports_hot-clicks_2.png)

To display clicks for recipients over 25, click the **[!UICONTROL Change profile]** button and select a test profile whose birth date is matching this condition.

For more on test profiles, see [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

>[!NOTE]
>
>Il numero di clic su un collegamento specifico è una percentuale del clic totale per tutti i contenuti condizionali in una consegna. Pertanto, se hai definito contenuto dinamico, il totale delle percentuali visualizzate per un profilo di test specifico potrebbe non corrispondere a 100.

Allo stesso modo, per le consegne ricorrenti e i messaggi transazionali, potete selezionare il profilo di prova corrispondente al contenuto dinamico che desiderate visualizzare, ma potete anche visualizzare le percentuali di clic in base alla distribuzione selezionata dell'esecuzione.

Una consegna dell'esecuzione è un messaggio tecnico non fruibile e non funzionante, creato nei casi seguenti:

* Ogni volta che viene eseguita o aggiornata una consegna periodica.

   Ad esempio, se il flusso di lavoro che gestisce la consegna viene eseguito una volta al mese, vi sarà una consegna di esecuzione al mese. Inoltre, ogni volta che il contenuto della consegna viene aggiornato, viene creata una distribuzione aggiuntiva dell'esecuzione.

   For more on recurring email deliveries, see [Email delivery](../../automating/using/email-delivery.md).

* Per impostazione predefinita, una volta al mese per i messaggi transazionali e ogni volta che un messaggio transazionale viene modificato e pubblicato di nuovo.

   For more on transactional messages, see [About transactional messaging](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>Poiché gli ID degli URL tracciati sono diversi per ogni esecuzione, i dati dei clic sensibili non possono essere aggregati per tutte le consegne di esecuzione di un dato messaggio. Può essere visualizzato solo per una consegna dell'esecuzione alla volta.

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

Per impostazione predefinita, è selezionata l'ultima consegna dell'esecuzione. Click the **[!UICONTROL Change execution delivery]** button to select another one.

![](assets/delivery_reports_hot-clicks_3.png)

Vengono visualizzate solo le percentuali di clic per l'esecuzione della consegna selezionata.
