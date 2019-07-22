---
title: Risoluzione dei problemi
seo-title: Risoluzione dei problemi
description: Risoluzione dei problemi
seo-description: Qui trovi domande comuni correlate alla generazione di rapporti dinamici.
page-status-flag: never-activated
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: beneat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: risoluzione dei problemi
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Troubleshooting{#troubleshooting}

In questa sezione potete trovare domande comuni correlate a rapporti dinamici.

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

Questo è un comportamento previsto.
Possiamo seguire questo esempio per spiegare questo comportamento.

Viene inviato un messaggio e-mail ai profili P 1 e P 2.

P 1 apre l'e-mail due volte il primo giorno e quindi la struttura ad albero il secondo giorno.

Mentre P 2 apre l'e-mail il primo giorno e non la riapre nei giorni seguenti.
Di seguito è riportata una rappresentazione visiva dell'interazione dei profili con l'e-mail inviata:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Giorno</strong><br /> </th> 
   <th align="center"> <strong>Aperture</strong><br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. Tuttavia, poiché l'e-mail è stata impostata come destinazione solo per 2 profili, la frequenza Open (Apri) dovrebbe mostrare 150%.

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. In questo caso, anche se P 1 ha aperto l'e-mail il Giorno 1 e il Giorno 2, la sua univoca apertura sarà ancora 1.

Ciò si tradurrà nella tabella seguente:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Giorno</strong><br /> </th> 
   <th align="center"> <strong>Aperture</strong><br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>I conteggi unici si basano su uno schizzo basato su HLL, che potrebbe causare lievi inesattezze a conteggio di grandi dimensioni.

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>Dato che i conteggi unici sono basati su uno schizzo basato su HLL, possono essere riscontrate lievi incoerenze tra i conteggi.

## Come vengono calcolati i calcoli periodici/transazionali?

Quando si utilizzano consegne ricorrenti e transazionali, i conteggi saranno attribuiti sia alle consegne principali che secondarie.

We can take the example of a recurring delivery named **R1** set to run every day on day 1 (RC1), day 2 (RC2) and day 3 (RC3).

Supponiamo che solo una persona abbia aperto più volte tutte le consegne secondarie. In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

Prima della versione standard di Adobe Campaign 19.2.1, i rapporti presentavano i seguenti elementi:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Consegna</strong><br /> </th> 
   <th align="center"> <strong>Inviato</strong><br /> </th> 
   <th align="center"> <strong>Consegnato</strong><br /> </th>
   <th align="center"> <strong>Aperture</strong><br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Dopo la versione standard di Adobe Campaign Standard 19.2.1, i rapporti sono:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Consegna</strong><br /> </th> 
   <th align="center"> <strong>Inviato</strong><br /> </th> 
   <th align="center"> <strong>Consegnato</strong><br /> </th>
   <th align="center"> <strong>Aperture</strong><br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## What is the colors' signification in my reports' table? {#reports-color-signification}

I colori visualizzati sui rapporti vengono randomizzati e non possono essere personalizzati. Rappresentano una barra di avanzamento e sono visualizzate per evidenziare meglio il valore massimo raggiunto nei rapporti.

Nell'esempio seguente, la cella ha lo stesso colore perché il suo valore è 100%.

![](assets/troubleshooting_1.png)

If you change the **Conditional formatting** to custom, when the value reaches the upper limit the cell will get greener. Tuttavia, se raggiunge il limite inferiore, viene redatta.

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)