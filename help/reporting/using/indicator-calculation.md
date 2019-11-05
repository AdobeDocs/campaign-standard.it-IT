---
title: Calcolo indicatore
description: Comprendi i risultati dei tuoi report con un elenco della formula di ogni metrica.
page-status-flag: mai attivato
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec733
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: informazioni sui rapporti
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Calcolo indicatore{#indicator-calculation}

Le tabelle riportate di seguito forniscono l'elenco degli indicatori utilizzati nei diversi rapporti e la relativa formula di calcolo in base al tipo di consegna.

## Recapito e-mail {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong><br /> </th> 
   <th> <strong>Nome</strong> campo <br /> </th> 
   <th> <strong>Formula</strong> di calcolo dell'indicatore <br /> </th> 
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
   <td> Blacklist<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tariffa Blacklist<br /> </td> 
   <td> @rateBlacklist<br /> </td> 
   <td> @blacklist/@sent<br /> </td> 
   <td> Denominatore per il calcolo del tasso si basa sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
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
   <td> Clic<br /> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
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
   <td> @opens<br /> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> @rifiutato<br /> </td> 
   <td> count(@failureReason=20)<br /> </td> 
   <td> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
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
   <td> Denominatore per il calcolo del tasso si basa sul conteggio inviato (Consegnato + Bounces).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> Unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Non raggiungibile <br /> </td> 
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

## Recapito notifiche push {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong><br /> </th> 
   <th> <strong>Nome</strong> campo <br /> </th> 
   <th> <strong>Formula</strong> di calcolo dell'indicatore <br /> </th> 
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
   <td> Le aperture univoche vengono calcolate utilizzando i concetti di ThetaSketch di RecipientIds univoci.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> @impression<br /> </td> 
   <td> @count(status=consegnato)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> @uniqueimpression<br /> </td> 
   <td> @Unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic<br /> </td> 
   <td> @clic<br /> </td> 
   <td> @count(status=interact)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> @univeclicks<br /> </td> 
   <td> I clic univoci vengono calcolati utilizzando i concetti di ThetaSketch.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di click-through<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@consegnato)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Distribuzione in-app {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etichetta</strong><br /> </th> 
   <th> <strong>Nome</strong> campo <br /> </th> 
   <th> <strong>Formula</strong> di calcolo dell'indicatore <br /> </th> 
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
   <td> @Unique(@count(status=view))<br /> </td> 
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

