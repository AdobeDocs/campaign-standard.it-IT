---
title: Risoluzione dei problemi
description: Qui troverai le domande più frequenti relative al reporting dinamico.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a894e72bb02fbecb86d43c6d2a13adf7ab10f73e
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 5%

---


# Risoluzione dei problemi{#troubleshooting}

In questa sezione potete trovare domande comuni relative al reporting dinamico.

## Per le aperture univoche e i clic univoci, il conteggio nella riga aggregata non corrisponde a quelli in singole righe {#unique-open-clicks-no-match}

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

Per capire il numero complessivo di aperture univoche, dobbiamo riassumere i conteggi delle righe **[!UICONTROL Unique Opens]** che ci danno il valore 3. Tuttavia, dal momento che l&#39;e-mail è stata indirizzata solo a 2 profili, la percentuale di apertura dovrebbe essere del 150%.

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

## I conteggi aperti non corrispondono al conteggio del database {#open-counts-no-match-database}

Ciò può essere dovuto al fatto che, nel reporting dinamico, le euristica vengono utilizzate per tenere traccia delle aperture anche quando non è possibile monitorare l&#39; **[!UICONTROL Open]** azione.

Ad esempio, se un utente ha disattivato le immagini sul proprio client e fa clic su un collegamento presente nell’e-mail, il database potrebbe non **[!UICONTROL Open]** tenerne traccia, ma **[!UICONTROL Click]** lo farà.

Pertanto, i conteggi dei registri di **[!UICONTROL Open]** tracciamento potrebbero non avere lo stesso conteggio nel database.

Tali occorrenze vengono aggiunte come **&quot;un clic e-mail implica l’apertura di un’e-mail&quot;**.

>[!NOTE]
>
>Poiché i conteggi univoci si basano su uno schizzo basato su HLL, è possibile riscontrare piccole incongruenze tra i conteggi.

## Come vengono calcolati i conteggi delle consegne ricorrenti/transazionali? {#counts-recurring-deliveries}

Quando si lavora con consegne ricorrenti e transazionali, i conteggi vengono attribuiti sia alle consegne principali che a quelle secondarie.
Possiamo prendere l&#39;esempio di una consegna ricorrente denominata **R1** impostata per essere eseguita ogni giorno al giorno 1 (RC1), al giorno 2 (RC2) e al giorno 3 (RC3).
Supponiamo che solo una singola persona abbia aperto tutte le consegne di bambini più volte. In questo caso, le singole consegne figlio ricorrenti visualizzeranno il **[!UICONTROL Open]** conteggio come 1 per ciascuna.
Tuttavia, poiché la stessa persona ha fatto clic su tutte le consegne, anche la consegna ricorrente padre avrà **[!UICONTROL Unique open]** come 1.

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

Se si modifica il valore **[!UICONTROL Conditional formatting]** in personalizzato, quando il valore raggiunge il limite superiore la cella diventa più verde. Invece, se raggiunge il limite inferiore, diventa più rosso.

Ad esempio, in questo caso, impostate il valore **[!UICONTROL Upper limit]** su 500 e **[!UICONTROL Lower limit]** su 0.

![](assets/troubleshooting_2.png)

## Perché il valore N/D viene visualizzato nei miei rapporti?

![](assets/troubleshooting_3.png)

Il valore **N/D** può talvolta essere visualizzato nei rapporti dinamici. Questo può essere visualizzato per due motivi:

* La consegna è stata eliminata ed è visualizzata qui come **N/D** per non causare discrepanze nei risultati.
* Quando trascinate e rilasciate la **[!UICONTROL Transactional Delivery]** dimensione nei rapporti, il valore **N/D** potrebbe comparire come risultato. Ciò accade perché il report dinamico recupera ogni consegna anche se non sono transazionali.
Questo può accadere anche quando trascina e rilascia la **[!UICONTROL Delivery]** dimensione nel report, ma in questo caso il valore **N/D** rappresenterà le consegne transazionali.
