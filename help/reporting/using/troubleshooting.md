---
solution: Campaign Standard
product: campaign
title: Risoluzione dei problemi
description: Qui trovi le domande comuni relative al reporting dinamico.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Generazione rapporti
role: Leader
level: Intermedio
translation-type: tm+mt
source-git-commit: d32bc25fe4e74605ac5cb78c162e242f790bdad5
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 5%

---


# Risoluzione dei problemi{#troubleshooting}

In questa sezione puoi trovare domande comuni relative al reporting dinamico.

## Per aperture univoche e clic univoci, il conteggio nella riga di aggregazione non corrisponde a quelli nelle singole righe {#unique-open-clicks-no-match}

Questo è un comportamento previsto.
Possiamo prendere l&#39;esempio seguente per spiegare questo comportamento.

Viene inviata un’e-mail ai profili P1 e P2.

P1 apre l’e-mail due volte il primo giorno e quindi tre volte il secondo giorno.

Al contrario, P2 apre l’e-mail una volta il primo giorno e non la riapre nei giorni successivi.
Ecco una rappresentazione visiva dell’interazione dei profili con l’e-mail inviata:

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

Per comprendere il numero complessivo di aperture univoche, è necessario sommare i conteggi delle righe di **[!UICONTROL Unique Opens]** che ci danno il valore 3. Ma poiché l’e-mail è stata destinata a soli 2 profili, il tasso di apertura dovrebbe mostrare il 150%.

Per non ottenere una percentuale superiore a 100, la definizione di **[!UICONTROL Unique Opens]** viene mantenuta come il numero di log di trasmissione univoci aperti. In questo caso, anche se P1 ha aperto l’e-mail il Giorno 1 e il Giorno 2, le sue aperture univoche saranno ancora 1.

Questo si tradurrà nella seguente tabella:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>Messaggi aperti</strong> <br /> </th> 
   <th align="center"> <strong>Aperture univoche</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6  </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr>
  <tr> 
   <td align="center"> Giorno 1<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Giorno 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>I conteggi univoci si basano su uno schizzo basato su HLL, il che può causare lievi inesattezze nei conteggi più grandi.

## I conteggi aperti non corrispondono al numero di database {#open-counts-no-match-database}

Questo può essere dovuto al fatto che, nel reporting dinamico, le euristiche vengono utilizzate per tracciare l’apertura anche quando non è possibile tenere traccia dell’azione **[!UICONTROL Open]**.

Ad esempio, se un utente ha disabilitato le immagini sul proprio client e fa clic su un collegamento nell’e-mail, il **[!UICONTROL Open]** potrebbe non essere tracciato dal database, ma il **[!UICONTROL Click]** lo farà.

Pertanto, i conteggi dei registri di tracciamento **[!UICONTROL Open]** potrebbero non avere lo stesso conteggio nel database.

Tali occorrenze vengono aggiunte come **&quot;un clic e-mail implica l&#39;apertura di un&#39;e-mail&quot;**.

>[!NOTE]
>
>Poiché i conteggi univoci si basano su uno schizzo basato su HLL, è possibile riscontrare incongruenze minori tra i conteggi.

## Come vengono calcolati i conteggi per consegne ricorrenti/transazionali? {#counts-recurring-deliveries}

Quando si lavora con consegne ricorrenti e transazionali, i conteggi vengono attribuiti alle consegne principali e secondarie.
Possiamo prendere l’esempio di una consegna ricorrente denominata **R1** impostata per essere eseguita ogni giorno il giorno 1 (RC1), il giorno 2 (RC2) e il giorno 3 (RC3).
Supponiamo che solo una singola persona abbia aperto tutte le consegne figlio più volte. In questo caso, le singole consegne figlie ricorrenti mostreranno il **[!UICONTROL Open]** conteggio come 1 per ciascuna.
Tuttavia, poiché la stessa persona ha fatto clic su tutte le consegne, anche la consegna ricorrente padre avrà **[!UICONTROL Unique open]** come 1.

I rapporti devono avere un aspetto simile al seguente:

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

I colori visualizzati nei rapporti vengono randomizzati e non possono essere personalizzati. Rappresentano una barra di avanzamento e vengono visualizzati per evidenziare meglio il valore massimo raggiunto nei rapporti.

Nell’esempio seguente, la cella è dello stesso colore in quanto il suo valore è 100%.

![](assets/troubleshooting_1.png)

Se cambi il valore **[!UICONTROL Conditional formatting]** su personalizzato, quando il valore raggiunge il limite superiore la cella diventerà più verde. Mentre, se raggiunge il limite inferiore, diventa più rosso.

Ad esempio, in questo caso, i valori **[!UICONTROL Upper limit]** vengono impostati su 500 e **[!UICONTROL Lower limit]** su 0.

![](assets/troubleshooting_2.png)

## Perché il valore N/D viene visualizzato nei miei rapporti?

![](assets/troubleshooting_3.png)

Il valore **N/A** può talvolta essere visualizzato nei rapporti dinamici. Questo può essere visualizzato per due motivi:

* La consegna è stata eliminata e viene visualizzata qui come **N/A** per non causare discrepanze nei risultati.
* Quando trascini e rilascia la dimensione **[!UICONTROL Transactional Delivery]** nei rapporti, il valore **N/A** potrebbe apparire come risultato. Questo accade perché il rapporto dinamico recupera ogni consegna anche se non è transazionale.
Questo può accadere anche quando trascini e rilascia la dimensione **[!UICONTROL Delivery]** nel rapporto, ma in questo caso il valore **N/A** rappresenta le consegne transazionali.
