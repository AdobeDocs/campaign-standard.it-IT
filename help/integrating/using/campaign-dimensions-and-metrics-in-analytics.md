---
title: Dimensioni e metriche di Campaign in Analytics
description: Scopri le diverse dimensioni che puoi trovare in Adobe Analytics per iniziare a tracciare le consegne e-mail da Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 3%

---

# Dimensioni e metriche di Campaign in Analytics{#campaign-dimensions-and-metrics-in-analytics}

L’integrazione tra Adobe Campaign e Adobe Analytics consente di monitorare il successo delle consegne di e-mail direttamente in Adobe Analytics.

Campagna **[!UICONTROL dimensions]** trovati in Analytics sono elencati di seguito:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID campagna<br /> </td> 
   <td> Nome interno della campagna visualizzato in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta della campagna<br /> </td> 
   <td> Etichetta della campagna come visualizzata in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID consegna<br /> </td> 
   <td> Nome interno della consegna, come visualizzato in Campaign.<br /> Ad esempio, DM1 è una consegna ricorrente programmata per inviare consegne secondarie ogni settimana. DM2, DM3 e DM4 vengono inviati per le prime tre settimane. La dimensione ID consegna visualizzerà quindi i risultati per ogni consegna, ovvero da DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta di consegna<br /> </td> 
   <td> Etichetta della consegna come visualizzata in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID consegna eseguita<br /> </td> 
   <td> Nome interno della consegna, come visualizzato in Campaign. Questo riguarda solo la consegna in esecuzione in Campaign.<br /> Ad esempio, DM1 è una consegna ricorrente programmata per inviare consegne secondarie ogni settimana. DM2, DM3 e DM4 vengono inviati per le prime tre settimane. La dimensione ID consegna eseguita visualizza quindi i risultati per le consegne eseguite, ovvero le consegne figlie DM2, DM3 e DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta consegna eseguita<br /> </td> 
   <td> Etichetta della consegna come visualizzata in Campaign. Questo riguarda solo la consegna in esecuzione in Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campagna **[!UICONTROL metrics]** trovati in Analytics sono elencati di seguito:

<table> 
 <thead> 
  <tr> 
   <th> Metrica<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clic effettuato<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un contenuto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperto<br /> </td> 
   <td> Numero di volte in cui un messaggio è stato aperto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Inviato<br /> </td> 
   <td> Numero totale di invii per la consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzi totali<br /> </td> 
   <td> Totale degli errori accumulati durante la consegna e l’elaborazione automatica della restituzione in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura univoca<br /> </td> 
   <td> Numero di destinatari che hanno aperto la consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoco<br /> </td> 
   <td> Numero di destinatari che hanno fatto clic su un contenuto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Annullamento iscrizione<br /> </td> 
   <td> Numero di clic sul collegamento di annullamento dell’abbonamento.<br /> </td> 
  </tr> 
 </tbody> 
</table>
