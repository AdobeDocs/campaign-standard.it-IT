---
title: Calcolo indicatore
description: Comprendi i risultati dei rapporti con un elenco della formula di ogni metrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 1%

---

# Calcolo indicatore{#indicator-calculation}

>[!NOTE]
>
>Per elaborare e gestire in modo migliore volumi elevati e analisi in tempo reale, il reporting dinamico utilizza aggregazioni approssimative per le stime dei conteggi distinti. Le aggregazioni approssimative offrono un utilizzo limitato della memoria e sono spesso più veloci dei calcoli esatti.

Le tabelle seguenti forniscono l’elenco degli indicatori utilizzati nei diversi rapporti e la relativa formula di calcolo a seconda del tipo di consegna.

## Consegna e-mail {#email-delivery}

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
   <td> Account disabilitato<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Inserire nell'elenco Bloccati All'<br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> tasso di Inserisco nell'elenco Bloccati<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (recapitati + non recapitati).<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancati recapiti + errori<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito + Percentuale di errori<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 o 10 o 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di consegna<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (recapitati + non recapitati).<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancati recapiti permanenti<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 E @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale mancati recapiti permanenti<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (recapitati + non recapitati).<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio non valido<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cassetta postale piena<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Pagina mirror<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagine mirror<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
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
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale aperture<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@delivered<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantena<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale quarantena<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (recapitati + non recapitati).<br /> </td> 
  </tr>
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale rifiutata<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (recapitati + non recapitati).<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito non permanente<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Percentuale mancati recapiti non permanenti<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa sul conteggio dei messaggi inviati (recapitati + non recapitati).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. Per ulteriori informazioni, consulta questo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> univoco(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non raggiungibile <br /> </td> 
   <td> @unreachable<br /> </td> 
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
   <td> Percentuale annullamenti abbonamento<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> Il denominatore per il calcolo del tasso si basa solo su Consegnato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utente sconosciuto<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Consegna notifica push {#push-notification-delivery}

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
   <td> @count(stato=inviato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(stato=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di consegna<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito + Percentuale di errori<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale aperture<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> Aperture univoche viene calcolato utilizzando i concetti ThetaSketch di RecipientIds univoci. Per ulteriori informazioni, consulta questo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(stato=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression univoche<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch. Per ulteriori informazioni, consulta questo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">esempio</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Consegna in-app {#in-app-delivery}

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
   <td> @count(stato=inviato)<br /> </td> 
   <td> sent=delivered<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(stato=consegnato)<br /> </td> 
   <td> delivery=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) o @count(status=button 1 click + button 2 click + dismissals)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impression univoche<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Per <span class="uicontrol">utenti Target in base al modello del profilo Campaign (inAppProfile)</span>, user = Recipient Id.<br /> Per <span class="uicontrol">Eseguire il targeting di tutti gli utenti di un'app mobile (inAppBroadcast)</span> e <span class="uicontrol">Eseguire il targeting degli utenti in base ai modelli del loro profilo mobile (inApp)</span>, user = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (stato=clic)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci in-app<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (stato=clic))<br /> </td> 
   <td> Per <span class="uicontrol">utenti Target in base al modello del profilo Campaign (inAppProfile)</span>, user = Recipient Id.<br /> Per <span class="uicontrol">Eseguire il targeting di tutti gli utenti di un'app mobile (inAppBroadcast)</span> e <span class="uicontrol">Eseguire il targeting degli utenti in base ai modelli del loro profilo mobile (inApp)</span>, user = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di click-through in-app<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Clic totali sul pulsante 1 o sul pulsante 2/impression totali*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Chiusura in-app<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Annullamenti in-app univoci<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (stato=chiusura))<br /> </td> 
   <td> Per <span class="uicontrol">utenti Target in base al modello del profilo Campaign (inAppProfile)</span>, user = Recipient Id.<br /> Per <span class="uicontrol">Eseguire il targeting di tutti gli utenti di un'app mobile (inAppBroadcast)</span> e <span class="uicontrol">Eseguire il targeting degli utenti in base ai modelli del loro profilo mobile (inApp)</span>, user = MC Id o equivalente che rappresenta una combinazione univoca di utente, app mobile e dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di licenziamento in-app<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Totale impression chiusura/totale*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
