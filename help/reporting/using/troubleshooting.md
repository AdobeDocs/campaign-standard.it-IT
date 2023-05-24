---
title: Risoluzione dei problemi di reporting dinamico
description: Qui trovi le domande comuni relative al reporting dinamico.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 5%

---

# Risoluzione dei problemi{#troubleshooting}

In questa sezione trovi le domande comuni relative al reporting dinamico.

## Per aperture univoche e clic univoci, il conteggio nella riga aggregata non corrisponde a quelli nelle singole righe {#unique-open-clicks-no-match}

Si tratta di un comportamento previsto.
Per spiegare questo comportamento, prendiamo l’esempio seguente.

Viene inviata un’e-mail ai profili P1 e P2.

P1 apre l’e-mail due volte il primo giorno e poi tre volte il secondo giorno.

Invece, P2 apre l’e-mail una volta il primo giorno e non la riapre nei giorni successivi.
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

Per comprendere il numero complessivo di aperture univoche, è necessario sommare i conteggi delle righe di **[!UICONTROL Unique Opens]** che ci dà il valore 3. Tuttavia, poiché l’e-mail era destinata solo a 2 profili, il tasso di apertura dovrebbe mostrare il 150%.

Per non ottenere una percentuale superiore a 100, la definizione di **[!UICONTROL Unique Opens]** viene mantenuto per essere il numero di broadLog univoci aperti. In questo caso, anche se P1 ha aperto l’e-mail il Giorno 1 e il Giorno 2, l’apertura univoca sarà comunque 1.

Questo determina la seguente tabella:

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
   <td align="center"> <strong> 6 </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
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
>I conteggi univoci si basano su uno schizzo basato su HLL, che può causare lievi imprecisioni in conteggi elevati.

## I conteggi aperti non corrispondono al conteggio del database {#open-counts-no-match-database}

Questo può essere dovuto al fatto che, nel reporting dinamico, l’euristica viene utilizzata per tenere traccia delle aperture anche quando non è possibile tenere traccia di **[!UICONTROL Open]** azione.

Ad esempio, se un utente ha disabilitato le immagini sul proprio client e fa clic su un collegamento nell’e-mail, il **[!UICONTROL Open]** non possono essere tracciati dal database, ma **[!UICONTROL Click]** Will.

Pertanto, la **[!UICONTROL Open]** i conteggi dei registri di tracciamento potrebbero non avere lo stesso conteggio nel database.

Tali occorrenze vengono aggiunte come **&quot;un clic e-mail implica l’apertura di un’e-mail&quot;**.

>[!NOTE]
>
>Poiché i conteggi univoci si basano su uno schizzo basato su HLL, è possibile riscontrare incoerenze minori tra i conteggi.

## Come vengono calcolati i conteggi per le consegne ricorrenti/transazionali? {#counts-recurring-deliveries}

Quando si utilizzano consegne ricorrenti e transazionali, i conteggi vengono attribuiti sia alle consegne padre che a quelle figlio.
Ad esempio, una consegna ricorrente denominata **R1** impostato per essere eseguito ogni giorno il giorno 1 (RC1), il giorno 2 (RC2) e il giorno 3 (RC3).
Supponiamo che solo una singola persona abbia aperto tutte le consegne dei bambini più volte. In questo caso, le singole consegne secondarie ricorrenti mostreranno **[!UICONTROL Open]** contare come 1 per ciascuno di essi.
Tuttavia, poiché la stessa persona ha fatto clic su tutte le consegne, anche la consegna ricorrente principale avrà **[!UICONTROL Unique open]** as 1.

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
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
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

## Qual è il significato dei colori nella tabella dei rapporti? {#reports-color-signification}

I colori visualizzati nei rapporti sono randomizzati e non possono essere personalizzati. Rappresentano una barra di avanzamento e vengono visualizzati per aiutarti a evidenziare meglio il valore massimo raggiunto nei rapporti.

Nell&#39;esempio seguente, la cella è dello stesso colore poiché il relativo valore è 100%.

![](assets/troubleshooting_1.png)

Se si modifica il **[!UICONTROL Conditional formatting]** per personalizzare, quando il valore raggiunge il limite superiore la cella diventa più verde. Mentre, se raggiunge il limite inferiore, diventa più rosso.

Ad esempio, in questo caso, impostiamo il **[!UICONTROL Upper limit]** a 500 e **[!UICONTROL Lower limit]** a 0.

![](assets/troubleshooting_2.png)

## Perché il valore N/D viene visualizzato nei rapporti?

![](assets/troubleshooting_3.png)

Il valore **N/D** possono a volte essere visualizzate nei rapporti dinamici. Questo può essere visualizzato per tre motivi:

* La consegna è stata eliminata ed è visualizzata qui come **N/D** per non causare discrepanze nei risultati.
* Quando si trascina **[!UICONTROL Transactional Delivery]** ai rapporti, il valore **N/D** potrebbe apparire come risultato. Questo accade perché il rapporto dinamico recupera ogni consegna anche se non è transazionale. Ciò può verificarsi anche quando si trascina **[!UICONTROL Delivery]** nel rapporto, ma in questo caso, il **N/D** Il valore rappresenta le consegne transazionali.
* Quando una dimensione viene utilizzata con una metrica non correlata alla dimensione. Nell’esempio seguente, viene aggiunta una suddivisione con il **[!UICONTROL Tracking URL]** anche se il **[!UICONTROL Click]** il conteggio è impostato su 0 in questa consegna.

   ![](assets/troubleshooting_4.png)

## I rapporti delle consegne mostrano dati incompleti quando si utilizza la mappatura Target personalizzata

Se utilizzi mappature di destinazione personalizzate importate nelle consegne e nei diversi rapporti non vengono visualizzati dati, potrebbe significare che gli arricchimenti dei rapporti non sono stati creati per tali mappature di destinazione.

Per risolvere il problema:

* Dopo aver importato la mappatura di Target da un XML, dovrai importare anche l’arricchimento per reporting.

* Invece di importare la mappatura di Target, puoi crearla direttamente in Adobe Campaign Standard, creando automaticamente l’arricchimento per i rapporti.
