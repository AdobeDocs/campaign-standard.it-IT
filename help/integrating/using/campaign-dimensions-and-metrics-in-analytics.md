---
title: Dimensioni e metriche di Campaign in Analytics
description: Scopri le diverse dimensioni che puoi trovare in Adobe Analytics per iniziare a monitorare le consegne delle e-mail da Adobe Campaign.
page-status-flag: mai attivato
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: lavorare con campagne e analisi
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Dimensioni e metriche di Campaign in Analytics{#campaign-dimensions-and-metrics-in-analytics}

L'integrazione di Adobe Campaign e Adobe Analytics consente di tenere traccia del successo delle comunicazioni e-mail direttamente in Adobe Analytics.

La campagna **[!UICONTROL dimensions]** trovata in Analytics è elencata di seguito:

<table> 
 <thead> 
  <tr> 
   <th> Dimensione<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID campagna<br /> </td> 
   <td> Nome interno della campagna come mostrato in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta campagna<br /> </td> 
   <td> Etichetta della campagna come visualizzata in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID consegna<br /> </td> 
   <td> Nome interno della consegna, come mostrato in Campaign.<br /> Ad esempio, DM1 è una consegna periodica pianificata per inviare consegne figlio ogni settimana. DM2, DM3 e DM4 vengono inviati nelle prime tre settimane. La dimensione ID consegna visualizzerà quindi i risultati per ogni consegna, vale a dire da DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta consegna<br /> </td> 
   <td> Etichetta di consegna come visualizzata in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID consegna eseguito<br /> </td> 
   <td> Nome interno della consegna, come mostrato in Campaign. Riguarda solo la consegna in esecuzione in Campaign.<br /> Ad esempio, DM1 è una consegna periodica pianificata per inviare consegne figlio ogni settimana. DM2, DM3 e DM4 vengono inviati nelle prime tre settimane. La dimensione ID consegna eseguita visualizzerà quindi i risultati per le consegne eseguite, ovvero le consegne figlio DM2, DM3 e DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta consegna eseguita<br /> </td> 
   <td> Etichetta di consegna come mostrato in Campaign. Riguarda solo la consegna in esecuzione in Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La campagna **[!UICONTROL metrics]** trovata in Analytics è elencata di seguito:

<table> 
 <thead> 
  <tr> 
   <th> Metrica<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clic<br /> </td> 
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
   <td> Totale importi<br /> </td> 
   <td> Totale degli errori cumulati durante l'elaborazione del recapito e del ritorno automatico in relazione al numero totale di messaggi inviati.<br /> </td> 
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
   <td> Annulla sottoscrizione<br /> </td> 
   <td> Numero di clic sul collegamento di annullamento della sottoscrizione.<br /> </td> 
  </tr> 
 </tbody> 
</table>

