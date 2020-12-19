---
solution: Campaign Standard
product: campaign
title: Risoluzione dei problemi
description: Qui troverai le domande più frequenti relative al reporting dinamico.
audience: reporting
content-type: reference
topic-tags: troubleshooting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 5%

---


# Risoluzione dei problemi{#troubleshooting}

In questa sezione potete trovare domande comuni relative al reporting dinamico.

## Per le aperture univoche e i clic univoci, il conteggio nella riga aggregata non corrisponde a quelli nelle singole righe {#unique-open-clicks-no-match}

Questo è un comportamento previsto.
Per spiegare questo comportamento, possiamo prendere l&#39;esempio seguente.

Viene inviata un&#39;e-mail ai profili P1 e P2.

P1 apre l&#39;e-mail due volte il primo giorno e tre volte il secondo giorno.

P2 apre invece l’e-mail una volta il primo giorno e non la riapre nei giorni successivi.
Di seguito è riportata una rappresentazione visiva dell&#39;interazione dei profili con l&#39;e-mail inviata:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Messaggi aperti</strong> <br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Giorno 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Giorno 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Per capire il numero complessivo di aperture univoche, è necessario riassumere il numero di righe di **[!UICONTROL Unique Opens]** che ci dà il valore 3. Tuttavia, dal momento che l&#39;e-mail è stata indirizzata solo a 2 profili, la percentuale di apertura dovrebbe essere del 150%.

Per non ottenere una percentuale superiore a 100, la definizione di **[!UICONTROL Unique Opens]** viene mantenuta come il numero di log univoci aperti. In questo caso anche se P1 ha aperto l&#39;e-mail il Giorno 1 e il Giorno 2, le sue aperture univoche saranno ancora 1.

Questo si tradurrà nella seguente tabella:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Messaggi aperti</strong> <br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Giorno 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Giorno 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>I conteggi univoci si basano su uno schizzo basato su HLL. Ciò potrebbe causare lievi inesattezze nei conteggi più grandi.

## I conteggi aperti non corrispondono al numero di database {#open-counts-no-match-database}

Ciò può essere dovuto al fatto che, nel reporting dinamico, le euristica vengono utilizzate per tenere traccia delle aperture anche quando non è possibile tracciare l&#39;azione **[!UICONTROL Open]**.

Ad esempio, se un utente ha disabilitato le immagini sul proprio client e fa clic su un collegamento nell&#39;e-mail, il **[!UICONTROL Open]** potrebbe non essere monitorato dal database, ma il **[!UICONTROL Click]** lo sarà.

Di conseguenza, i conteggi dei registri di monitoraggio **[!UICONTROL Open]** potrebbero non avere lo stesso conteggio nel database.

Tali occorrenze vengono aggiunte come **&quot;un clic e-mail implica l&#39;apertura di un&#39;e-mail&quot;**.

>[!NOTE]
>
>Poiché i conteggi univoci si basano su uno schizzo basato su HLL, è possibile riscontrare piccole incongruenze tra i conteggi.

## Come vengono calcolati i conteggi delle consegne ricorrenti/transazionali? {#counts-recurring-deliveries}

Quando si lavora con consegne ricorrenti e transazionali, i conteggi vengono attribuiti sia alle consegne principali che a quelle secondarie.
Possiamo prendere l&#39;esempio di una consegna ricorrente denominata **R1** impostata per essere eseguita ogni giorno al giorno 1 (RC1), al giorno 2 (RC2) e al giorno 3 (RC3).
Supponiamo che solo una singola persona abbia aperto tutte le consegne di bambini più volte. In questo caso, le singole consegne figlio ricorrenti mostreranno il numero **[!UICONTROL Open]** come 1 per ciascuna consegna.
Tuttavia, poiché la stessa persona ha fatto clic su tutte le consegne, la consegna ricorrente padre avrà anche **[!UICONTROL Unique open]** come 1.

I rapporti devono essere simili ai seguenti:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Consegna</strong> <br /> </th> 
   <th align="center"> <strong>Inviato</strong> <br /> </th> 
   <th align="center"> <strong>Consegnato</strong> <br /> </th>
   <th align="center"> <strong>Messaggi aperti</strong> <br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong> <br /> </th>
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

## Qual è il significato dei colori nella tabella dei miei rapporti? {#reports-color-signification}

I colori visualizzati nei rapporti sono randomizzati e non possono essere personalizzati. Rappresentano una barra di avanzamento e vengono visualizzati per evidenziare meglio il valore massimo raggiunto nei rapporti.

Nell&#39;esempio seguente, la cella ha lo stesso colore, poiché il suo valore è 100%.

![](assets/troubleshooting_1.png)

Se si modifica il valore **[!UICONTROL Conditional formatting]** su personalizzato, quando il valore raggiunge il limite superiore la cella diventa più verde. Invece, se raggiunge il limite inferiore, diventa più rosso.

Ad esempio, in questo caso, il valore **[!UICONTROL Upper limit]** viene impostato su 500 e il valore **[!UICONTROL Lower limit]** su 0.

![](assets/troubleshooting_2.png)

## Perché il valore N/D viene visualizzato nei miei rapporti?

![](assets/troubleshooting_3.png)

Il valore **N/A** può talvolta essere visualizzato nei rapporti dinamici. Questo può essere visualizzato per due motivi:

* La consegna è stata eliminata ed è indicata qui come **N/A** per non causare discrepanze nei risultati.
* Quando si trascina e si rilascia la dimensione **[!UICONTROL Transactional Delivery]** nei report, è possibile che venga visualizzato il valore **N/A**. Ciò accade perché il report dinamico recupera ogni consegna anche se non sono transazionali.
Ciò può accadere anche quando si trascina e si rilascia la dimensione **[!UICONTROL Delivery]** nel report, ma in questo caso il valore **N/A** rappresenterà le consegne transazionali.
