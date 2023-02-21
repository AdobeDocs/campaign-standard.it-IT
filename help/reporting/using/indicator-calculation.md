---
title: Calcolo indicatore
description: Comprendi i risultati dei tuoi rapporti con un elenco della formula di ogni metrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 6%

---

# Calcolo indicatore{#indicator-calculation}

>[!NOTE]
>
>Per elaborare e gestire meglio volumi elevati e analisi in tempo reale, il reporting dinamico utilizza aggregazioni approssimative per stime di conteggio distinte. Le aggregazioni approssimative offrono un utilizzo limitato della memoria e sono spesso più veloci dei calcoli esatti.

Le tabelle seguenti forniscono l’elenco degli indicatori utilizzati nei diversi rapporti e la relativa formula di calcolo a seconda del tipo di consegna.

## Attività Email delivery {#email-delivery}

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
   <td> A elenco Bloccati<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failedReason=8, @failedType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Elenco Bloccati tasso di <br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzi + errori<br /> </td> 
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
   <td> @click<br /> </td> 
   <td> count(@trackingUrlType=1 o 10 o 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @univeclicks/@delivery<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancati recapiti permanenti<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failedType=2 AND @failedReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza rimbalzi netti<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
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
   <td> Pagina mirror<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagina speculare<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivery<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non connessi<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failedReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> @univocheAperture<br /> </td> 
   <td> count(@trackingUrlType=2 + univoco(@trackingUrlType=1,2,3,6,10,11) - univoco(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso aperto<br /> </td> 
   <td> @rateAperture<br /> </td> 
   <td> @open/@delivery<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr>
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> @rigettato<br /> </td> 
   <td> count(@failedReason=20, @failedType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso rifiutato<br /> </td> 
   <td> @rateRejects<br /> </td> 
   <td> @failed/@sent<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivery + @bounce<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo morbido<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failedType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di rimbalzo morbida<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (Consegnati + Rimbalzi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoco<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. Per ulteriori informazioni, consulta questo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
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
   <td> @irraggiungibile<br /> </td> 
   <td> count(@failedReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Annulla iscrizione<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasso di annullamento sottoscrizione<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivery<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utente sconosciuto<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failedReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Attività Push notification delivery {#push-notification-delivery}

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
   <td> @rateAperture<br /> </td> 
   <td> (@open/@consegna)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> Le aperture univoche vengono calcolate utilizzando i concetti ThetaSketch di RecipientIds univoci. Per ulteriori informazioni, consulta questo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
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
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. Per ulteriori informazioni, consulta questo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@consegnato)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Attività In-App delivery {#in-app-delivery}

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
   <td> Consegnato<br /> </td> 
   <td> @consegnato<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
   <td> delivery=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> @impression<br /> </td> 
   <td> @count(status=view) o @count(status=pulsante 1 clic + pulsante 2 clic + cancellazioni)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> @uniqueimpression<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Per <span class="uicontrol">Eseguire il targeting degli utenti in base al loro profilo Campaign (inAppProfile)</span> template, user = Recipient Id.<br /> Per <span class="uicontrol">Esegui il targeting per tutti gli utenti di un’app mobile (inAppBroadcast)</span> e <span class="uicontrol">Eseguire il targeting degli utenti in base al loro profilo mobile (inApp)</span> modelli, utente = ID MC o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
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
   <td> Per <span class="uicontrol">Eseguire il targeting degli utenti in base al loro profilo Campaign (inAppProfile)</span> template, user = Recipient Id.<br /> Per <span class="uicontrol">Esegui il targeting per tutti gli utenti di un’app mobile (inAppBroadcast)</span> e <span class="uicontrol">Eseguire il targeting degli utenti in base al loro profilo mobile (inApp)</span> modelli, utente = ID MC o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
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
   <td> Per <span class="uicontrol">Eseguire il targeting degli utenti in base al loro profilo Campaign (inAppProfile)</span> template, user = Recipient Id.<br /> Per <span class="uicontrol">Esegui il targeting per tutti gli utenti di un’app mobile (inAppBroadcast)</span> e <span class="uicontrol">Eseguire il targeting degli utenti in base al loro profilo mobile (inApp)</span> modelli, utente = ID MC o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di licenziamento in-app<br /> </td> 
   <td> @dismissalate<br /> </td> 
   <td> Totale impression finali/totali*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
