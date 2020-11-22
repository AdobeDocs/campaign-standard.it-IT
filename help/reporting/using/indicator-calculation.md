---
solution: Campaign Standard
product: campaign
title: Calcolo indicatore
description: Comprendi i risultati dei tuoi report con un elenco della formula di ogni metrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 2%

---


# Calcolo indicatore{#indicator-calculation}

>[!NOTE]
>
>Per elaborare e gestire meglio volumi elevati e analisi in tempo reale, il reporting dinamico utilizza aggregati approssimativi per stime di conteggio distinte. Le aggregazioni approssimative offrono un utilizzo limitato della memoria e sono spesso più veloci dei calcoli esatti.

Le tabelle riportate di seguito forniscono l&#39;elenco degli indicatori utilizzati nei diversi rapporti e la relativa formula di calcolo in base al tipo di consegna.

## Email delivery {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong> <br /> </th> 
   <th> <strong>Nome campo</strong> <br /> </th> 
   <th> <strong>Formula di calcolo indicatore</strong> <br /> </th> 
   <th> <strong>Commenti</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Account disattivato<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Su elenco Bloccati<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> elenco Bloccati tasso<br /> </td> 
   <td> @rateBlacklist<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso è basato sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Punti + errori<br /> </td> 
   <td> @bounce<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo + Frequenza errori<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> @clic<br /> </td> 
   <td> count(@trackingUrlType=1, 10 o 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @UniqueClick/@consegnato<br /> </td> 
   <td> Denominatore per il calcolo del tasso è basato solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> @consegnato<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di consegna<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivery/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso è basato sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzi netti<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza rimbalzi netti<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso è basato sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio non valido<br /> </td> 
   <td> @InvalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cassetta postale completa<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Mirror, pagina<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> Denominatore per il calcolo del tasso è basato solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagina speculare<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@consegnato<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non connesso<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> @univocheApre<br /> </td> 
   <td> count(@trackingUrlType=2 + univoco(@trackingUrlType=1,2,3,6,10,11) - univoco(@trackingUrlType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso aperto<br /> </td> 
   <td> @rateOpen<br /> </td> 
   <td> @open/@consegnato<br /> </td> 
   <td> Denominatore per il calcolo del tasso è basato solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantina<br /> </td> 
   <td> @quarantena<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di quarantena<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantena/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso è basato sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr>
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> @rifiutato<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso rifiutato<br /> </td> 
   <td> @rateRejection<br /> </td> 
   <td> @rifiutato/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso è basato sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @consegnato + @bounce<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza rimbalzo morbida<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso è basato sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> Unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non Raggiungibile <br /> </td> 
   <td> @non raggiungibile<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Annulla sottoscrizione<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di annullamento sottoscrizione<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@consegnato<br /> </td> 
   <td> Denominatore per il calcolo del tasso è basato solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utente sconosciuto<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Consegna notifiche push {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong> <br /> </th> 
   <th> <strong>Nome campo</strong> <br /> </th> 
   <th> <strong>Formula di calcolo indicatore</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> @consegnato<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di consegna<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivery/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo + Frequenza errori<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivery/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso aperto<br /> </td> 
   <td> @rateOpen<br /> </td> 
   <td> (@open/@consegnato)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> Le aperture univoche vengono calcolate utilizzando i concetti di ThetaSketch di RecipientIds univoci. For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> @impression<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> @uniqueimpression<br /> </td> 
   <td> @univoche(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> @clic<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. For more on this, refer to this <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">example</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@consegnato)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## In-App delivery {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong> <br /> </th> 
   <th> <strong>Nome campo</strong> <br /> </th> 
   <th> <strong>Formula di calcolo indicatore</strong> <br /> </th> 
   <th> <strong>Commenti</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> @consegnato<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
   <td> consegnato=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> @impression<br /> </td> 
   <td> @count(status=view) o @count(status=pulsante 1 clic + pulsante 2 clic + chiusure)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> @uniqueimpression<br /> </td> 
   <td> @univoche(@count(status=view))<br /> </td> 
   <td> Per gli utenti di <span class="uicontrol">Target in base al modello di profilo Campaign (inAppProfile)</span> , utente = ID destinatario.<br /> Per <span class="uicontrol">Target tutti gli utenti di un'app mobile (inAppBroadcast)</span> e di utenti <span class="uicontrol">Target basati sui modelli del loro profilo mobile (inApp)</span> , utente = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app <br /> </td> 
   <td> @inappClick<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app univoci<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @univoche(@count (status=clic)<br /> </td> 
   <td> Per gli utenti di <span class="uicontrol">Target in base al modello di profilo Campaign (inAppProfile)</span> , utente = ID destinatario.<br /> Per <span class="uicontrol">Target tutti gli utenti di un'app mobile (inAppBroadcast)</span> e di utenti <span class="uicontrol">Target basati sui modelli del loro profilo mobile (inApp)</span> , utente = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di click-through in-app<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Clic totale sul pulsante 1 o sul pulsante 2/impression totale*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Licenza in-app<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Licenze univoche in-app<br /> </td> 
   <td> @unicedismissal<br /> </td> 
   <td> @univoche(@count (status=close))<br /> </td> 
   <td> Per gli utenti di <span class="uicontrol">Target in base al modello di profilo Campaign (inAppProfile)</span> , utente = ID destinatario.<br /> Per <span class="uicontrol">Target tutti gli utenti di un'app mobile (inAppBroadcast)</span> e di utenti <span class="uicontrol">Target basati sui modelli del loro profilo mobile (inApp)</span> , utente = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di licenziamento in-app<br /> </td> 
   <td> @dismissalate<br /> </td> 
   <td> Totale impression/totale* 100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

