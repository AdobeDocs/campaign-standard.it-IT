---
title: Dimensioni e metriche della campagna in Analytics
seo-title: Dimensioni e metriche della campagna in Analytics
description: Dimensioni e metriche della campagna in Analytics
seo-description: Scopri le diverse dimensioni che puoi trovare in Adobe Analytics per iniziare a tracciare le tue consegne e-mail da Adobe Campaign.
page-status-flag: never-activated
uuid: effa 1028-66 b 2-4 bef-b 5 e 4-7319 dbb 23 d 5 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb 3639 f 5-7246-46 c 4-8 ddb-da 9413 b 40 c 32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Campaign dimensions and metrics in Analytics{#campaign-dimensions-and-metrics-in-analytics}

L'integrazione di Adobe Campaign e Adobe Analytics consente di tenere traccia del successo delle comunicazioni e-mail direttamente in Adobe Analytics.

Campaign **[!UICONTROL dimensions]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campaign ID<br /> </td> 
   <td> Campaign's internal name as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign label<br /> </td> 
   <td> Campaign's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery ID<br /> </td> 
   <td> Nome interno della distribuzione, come mostrato in Campaign.<br /> Ad esempio, DM 1 è una consegna ricorrente pianificata per inviare consegne secondarie ogni settimana. DM 2, DM 3 e DM 4 vengono inviate per le prime tre settimane. The Delivery ID dimension will then display the results for every delivery, namely DM1 to DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery label<br /> </td> 
   <td> Delivery's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery ID<br /> </td> 
   <td> Nome interno della distribuzione, come mostrato in Campaign. Questo riguarda solo la consegna nell'esecuzione in Campaign.<br /> Ad esempio, DM 1 è una consegna ricorrente pianificata per inviare consegne secondarie ogni settimana. DM 2, DM 3 e DM 4 vengono inviate per le prime tre settimane. The Executed delivery ID dimension will then display the results for the executed deliveries, namely the child deliveries DM2, DM3 and DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery label<br /> </td> 
   <td> Etichetta della distribuzione come mostrato in Campaign. This only concerns delivery in execution in Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clicked<br /> </td> 
   <td> Number of times a content was clicked in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> Number of messages successfully sent, in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Opened<br /> </td> 
   <td> Number of times a message was opened in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> Total number of sends for the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total Bounces<br /> </td> 
   <td> Total of errors cumulated during delivery and automatic return processing in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Open<br /> </td> 
   <td> Number of recipients who opened the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Click<br /> </td> 
   <td> Number of recipients who clicked on a content in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribed<br /> </td> 
   <td> Number of clicks on the unsubscription link.<br /> </td> 
  </tr> 
 </tbody> 
</table>

