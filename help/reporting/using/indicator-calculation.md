---
solution: Campaign Standard
product: campaign
title: Calcolo indicatore
description: Comprendi i risultati dei tuoi rapporti con un elenco della formula di ogni metrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 2%

---


# Calcolo indicatore{#indicator-calculation}

>[!NOTE]
>
>Per elaborare e gestire meglio volumi elevati e analisi in tempo reale, il reporting dinamico utilizza aggregazioni approssimative per stime di conteggio distinte. Le aggregazioni approssimative offrono un utilizzo limitato della memoria e sono spesso più veloci dei calcoli esatti.

Le tabelle seguenti forniscono l’elenco degli indicatori utilizzati nei diversi rapporti e la relativa formula di calcolo a seconda del tipo di consegna.

## Email delivery {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong> <br /> </th> 
   <th> <strong>Nome campo</strong> <br /> </th> 
   <th> <strong>Formula di calcolo dell'indicatore</strong> <br /> </th> 
   <th> <strong>Commenti</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Account disabilitato<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failedReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Al elenco Bloccati<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failedReason=8, @failedType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di Elenco Bloccati<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzi + errori<br /> </td> 
   <td> @bounces<br /> </td> 
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
   <td> @click<br /> </td> 
   <td> count(@trackingUrlType=1 o 10 o 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @univeclicks/@delivery<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> @delivery<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Velocità consegna<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivery/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzi netti<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failedType=2 AND @failedReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza rimbalzi netti<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio non valido<br /> </td> 
   <td> @validDomain<br /> </td> 
   <td> count(@failedReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cassetta postale piena<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failedReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Pagina speculare<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagina speculare<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivery<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non connesso<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failedReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> @univoche<br /> </td> 
   <td> count(@trackingUrlType=2 + univoco(@trackingUrlType=1,2,3,6,10,11) - univoco(@trackingUrlType=2)))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Velocità aperta<br /> </td> 
   <td> @rateAperture<br /> </td> 
   <td> @open/@delivery<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantena<br /> </td> 
   <td> @quarantena<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di quarantena<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantena/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr>
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> @rifiutato<br /> </td> 
   <td> count(@failedReason=20, @failedType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso rifiutato<br /> </td> 
   <td> @rateReject<br /> </td> 
   <td> @rifiutato/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivery + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failedType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di rimbalzo morbida<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoco<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. Per ulteriori informazioni, consulta questo <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non raggiungibile <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failedReason=3)<br /> </td> 
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
   <td> Il denominatore per il calcolo del tasso si basa solo su Delivered.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utente sconosciuto<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failedReason=1)<br /> </td> 
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
   <th> <strong>Formula di calcolo dell'indicatore</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> @delivery<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocità consegna<br /> </td> 
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
   <td> @open<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocità aperta<br /> </td> 
   <td> @rateAperture<br /> </td> 
   <td> (@open/@delivery)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> Le aperture univoche vengono calcolate utilizzando i concetti ThetaSketch di RecipientIds univoci. Per ulteriori informazioni, consulta questo <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression<br /> </td> 
   <td> @impression<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> @uniqueimpression<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> @click<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoco<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. Per ulteriori informazioni, consulta questo <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
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
   <th> <strong>Formula di calcolo dell'indicatore</strong> <br /> </th> 
   <th> <strong>Commenti</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=delivery<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> @delivery<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
   <td> delivery=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression<br /> </td> 
   <td> @impression<br /> </td> 
   <td> @count(status=view) o @count(status=pulsante 1 clic + pulsante 2 clic + cancellazioni)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> @uniqueimpression<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Per <span class="uicontrol">Eseguire il targeting degli utenti in base al loro modello di profilo Campaign (inAppProfile)</span>, utente = ID destinatario.<br /> Per  <span class="uicontrol">Target tutti gli utenti di un’app mobile (inAppBroadcast)</span> e  <span class="uicontrol">Target utenti in base ai loro modelli di profilo mobile (inApp)</span> , utente = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app <br /> </td> 
   <td> @inappclick<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app univoci<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=click))<br /> </td> 
   <td> Per <span class="uicontrol">Eseguire il targeting degli utenti in base al loro modello di profilo Campaign (inAppProfile)</span>, utente = ID destinatario.<br /> Per  <span class="uicontrol">Target tutti gli utenti di un’app mobile (inAppBroadcast)</span> e  <span class="uicontrol">Target utenti in base ai loro modelli di profilo mobile (inApp)</span> , utente = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di click-through in-app<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Clic totale sul pulsante 1 o sul pulsante 2/impressioni totali*100<br /> </td> 
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
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Per <span class="uicontrol">Eseguire il targeting degli utenti in base al loro modello di profilo Campaign (inAppProfile)</span>, utente = ID destinatario.<br /> Per  <span class="uicontrol">Target tutti gli utenti di un’app mobile (inAppBroadcast)</span> e  <span class="uicontrol">Target utenti in base ai loro modelli di profilo mobile (inApp)</span> , utente = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di licenziamento in-app<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Totale impression finali/totali*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

