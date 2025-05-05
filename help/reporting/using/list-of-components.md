---
title: Elenco dei componenti
description: Qui trovi l’elenco di tutti i componenti disponibili in     Rapporti dinamici e relative definizioni.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '1308'
ht-degree: 0%

---

# Elenco dei componenti {#list-of-components}

Per ulteriori informazioni sulla compatibilità tra dimensioni e metriche, consulta questa [tabella](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se due componenti non sono compatibili, nella cella verrà visualizzato il valore **None**.

[![immagine](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=it)

## Dimensioni {#dimensions}

La tabella seguente fornisce l’elenco delle dimensioni utilizzate nei rapporti e le relative definizioni.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Browser<br /> </td> 
   <td> Browser da cui è stato aperto o su cui è stato fatto clic il messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campagna<br /> </td> 
   <td> Etichetta e ID della campagna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Città<br /> </td> 
   <td> Città registrata nel profilo del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Paese<br /> </td> 
   <td> Paese registrato nel profilo del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegna<br /> </td> 
   <td> Etichetta e ID della consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo da cui è stata aperta/visualizzata/su cui è stato fatto clic la notifica e-mail/SMS/push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo errore<br /> </td> 
   <td> Tipi di errori che hanno causato mancati recapiti per ogni consegna. Ad esempio, utente sconosciuto, dominio non valido o cassetta postale piena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Genere<br /> </td> 
   <td> Genere del destinatario, ad esempio maschile o femminile. Se il campo di genere è vuoto nel profilo del destinatario, il valore sarà nessuno.<br /> </td> 
  </tr> 
  <tr> 
   <td> Azioni messaggio in-app<br /> </td> 
   <td> Azioni sul messaggio in-app recapitato, ad esempio azioni sui pulsanti 1 o 2 o chiusure.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo di messaggio<br /> </td> 
   <td> Canale utilizzato per la consegna, ad esempio e-mail, SMS, notifica push o in-app.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nome app mobile<br /> </td> 
   <td> Nome dell'app mobile<br /> </td> 
  </tr> 
  <tr> 
   <td> Piattaforma<br /> </td> 
   <td> Piattaforma del dispositivo da cui è stato aperto/visualizzato/su cui è stato fatto clic il messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profilo<br /> </td> 
   <td> I campi di profilo predefiniti e personalizzati creati durante l'estensione della risorsa profilo sono raggruppati. Per ulteriori informazioni, consulta questa <a href="../../developing/using/key-steps-to-add-a-resource.md">pagina</a> o questo <a href="../../reporting/using/creating-a-custom-profile-dimension.md">esempio</a>.<br /> Si noti che i dati per questa dimensione vengono recuperati non appena viene pubblicata la risorsa personalizzata collegata al campo del profilo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Piattaforma push<br /> </td> 
   <td> Piattaforma del dispositivo da cui è stata aperta la notifica push, ad esempio iOS o Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio destinatario<br /> </td> 
   <td> Dominio utilizzato per aprire l'e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegna ricorrente<br /> </td> 
   <td> Etichetta e ID della consegna ricorrente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio mittente<br /> </td> 
   <td> Dominio utilizzato per inviare l'e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP mittente<br /> </td> 
   <td> IP utilizzato per inviare l'e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Stato<br /> </td> 
   <td> Stato registrato nel profilo del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL di tracciamento<br /> </td> 
   <td> URL su cui l'utente ha fatto clic dal messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tracciamento categoria URL<br /> </td> 
   <td> Categoria assegnata all'URL di tracciamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta URL di tracciamento<br /> </td> 
   <td> Etichetta fornita all'URL, ad esempio pagina mirror, contattaci o apri.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegna transazionale<br /> </td> 
   <td> Etichetta e ID della consegna transazionale.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante dell'e-mail in caso di test A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche {#metrics}

Le tabelle seguenti forniscono l’elenco delle metriche utilizzate nei rapporti e le relative definizioni a seconda del tipo di consegna.

### Metriche e-mail e SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrica<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Inserire nell'elenco Bloccati All'<br /> </td> 
   <td> Numero di destinatari che hanno dichiarato un'e-mail come posta indesiderata o posta indesiderata.<br /> </td> 
  </tr> 
  <tr> 
   <td> tasso di Inserisco nell'elenco Bloccati<br /> </td> 
   <td> Percentuale di consegne contrassegnate in base al inserisco nell'elenco Bloccati di.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancati recapiti + errori<br /> </td> 
   <td> Totale degli errori accumulati durante la consegna e l'elaborazione automatica della restituzione in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito + Percentuale di errori<br /> </td> 
   <td> Percentuale di messaggi e-mail non recapitati rispetto a quelli inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un contenuto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di click-through<br /> </td> 
   <td> Percentuale di clic in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di consegna<br /> </td> 
   <td> Percentuale di messaggi inviati correttamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito<br /> </td> 
   <td> Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale mancati recapiti permanenti<br /> </td> 
   <td> Percentuale di consegne non riuscite a causa di errori permanenti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pagina mirror<br /> </td> 
   <td> Numero di destinatari che hanno fatto clic sul collegamento della pagina mirror.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagine mirror<br /> </td> 
   <td> Percentuale di clic sul collegamento della pagina mirror rispetto al totale dei messaggi di consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic sull'offerta<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un'offerta in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di clic offerta<br /> </td> 
   <td> Percentuale di clic su un'offerta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> Numero di volte in cui un messaggio è stato aperto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale aperture<br /> </td> 
   <td> Percentuale di messaggi aperti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di invii per la consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantena<br /> </td> 
   <td> Numero di messaggi non recapitati che hanno portato alla quarantena dell'indirizzo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale quarantena<br /> </td> 
   <td> Percentuale di quarantena rispetto ai messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> Numero di messaggi classificati come spam dai server SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale rifiutata<br /> </td> 
   <td> Percentuale di messaggi contrassegnati come rifiutati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito non permanente<br /> </td> 
   <td> Numero totale di errori temporanei, ad esempio una casella in entrata completa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale mancati recapiti non permanenti<br /> </td> 
   <td> Percentuale di consegne non riuscite a causa di un motivo temporaneo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> Numero di destinatari che hanno fatto clic su un contenuto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> Numero di destinatari che hanno aperto la consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Annullamento iscrizione univoco<br /> </td> 
   <td> Numero di destinatari che hanno fatto clic sul collegamento di annullamento dell'abbonamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale annullamenti abbonamento<br /> </td> 
   <td> Numero di annullamenti di abbonamenti univoci rispetto ai messaggi consegnati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Annullamento sottoscrizione<br /> </td> 
   <td> Numero di clic sul collegamento di annullamento dell'abbonamento.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche delle notifiche push {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrica<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Mancati recapiti + errori<br /> </td> 
   <td> Totale degli errori accumulati durante la consegna in relazione al numero totale di messaggi inviati, ad esempio errori da MCPNS o dal provider.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mancato recapito + Percentuale di errori<br /> </td> 
   <td> Percentuale di notifiche push non recapitate rispetto alle notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> Numero di volte in cui una notifica push è stata recapitata al dispositivo e su cui l’utente ha fatto clic. L'utente desidera visualizzare la notifica, che verrà quindi spostata nel tracciamento Push Open, oppure ignorarla.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di click-through<br /> </td> 
   <td> Percentuale di utenti che hanno interagito con la notifica push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di consegna<br /> </td> 
   <td> Percentuale di notifiche push inviate correttamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression<br /> </td> 
   <td> Numero di volte in cui una notifica push è stata consegnata al dispositivo e lasciata intatta nel centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e inoltra tali informazioni al server.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> Numero totale di notifiche push inviate al dispositivo e su cui gli utenti hanno fatto clic, aprendo in tal modo l’app. È simile al clic push, tranne per il fatto che l'apertura push non verrà attivata se la notifica viene chiusa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale aperture<br /> </td> 
   <td> Percentuale di notifiche push aperte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
   <td> Numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio facendo clic sulla notifica o sul pulsante.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression univoche<br /> </td> 
   <td> Numero di impression per destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperture univoche<br /> </td> 
   <td> Numero di destinatari che hanno aperto la consegna.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche in-app {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metrica<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero totale di messaggi in-app recapitati al dispositivo dal provider di servizi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression<br /> </td> 
   <td> Totale dei messaggi in-app visualizzati dai destinatari a seconda che il criterio di attivazione sia stato soddisfatto.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app <br /> </td> 
   <td> Numero totale di destinatari che hanno fatto clic sul pulsante 1 o sul pulsante 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di click-through in-app<br /> </td> 
   <td> Percentuale di utenti che hanno fatto clic sul pulsante 1 o sul pulsante 2 rispetto agli utenti che hanno visualizzato il messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Chiusura in-app<br /> </td> 
   <td> Numero totale di messaggi che i destinatari hanno ignorato facendo clic sul pulsante Chiudi o Chiudi automaticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Percentuale di licenziamento in-app<br /> </td> 
   <td> Percentuale di messaggi in-app ignorati dai destinatari.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di messaggi in-app inviati da Adobe Campaign come parte del processo di consegna inviato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impression univoche<br /> </td> 
   <td> Numero di impression da parte di un destinatario univoco.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci in-app<br /> </td> 
   <td> Numero di volte in cui i destinatari hanno fatto clic sul pulsante 1 o sul pulsante 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Annullamenti in-app univoci<br /> </td> 
   <td> Numero di destinatari che hanno ignorato un messaggio in-app.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenti {#segments}

La tabella seguente fornisce l’elenco dei segmenti utilizzati nei rapporti e le relative definizioni.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Età: Boomers 1<br /> </td> 
   <td> Destinatari nati dal 1946 al 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Boomers 2<br /> </td> 
   <td> Destinatari nati dal 1955 al 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: da 18 a 25<br /> </td> 
   <td> Destinatari di età compresa tra 18 e 25 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: da 26 a 30<br /> </td> 
   <td> Destinatari di età compresa tra 26 e 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: da 31 a 40<br /> </td> 
   <td> Destinatari di età compresa tra 31 e 40 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: da 41 a 50<br /> </td> 
   <td> Destinatari di età compresa tra 41 e 50 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: generazione X<br /> </td> 
   <td> Destinatari nati dal 1966 al 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Generazione Y (Millennial)<br /> </td> 
   <td> Destinatari nati dal 1977 al 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: generazione Z<br /> </td> 
   <td> Destinatari nati dal 1995 a oggi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: maggiore di 50<br /> </td> 
   <td> Destinatari con età superiore a 50 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: meno di 25<br /> </td> 
   <td> Destinatari con età inferiore a 25 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: inferiore a 30<br /> </td> 
   <td> Destinatari con età inferiore a 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: inferiore a 40<br /> </td> 
   <td> Destinatari con età inferiore a 40 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: inferiore a 50<br /> </td> 
   <td> Destinatari con età inferiore a 50 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Generazione silenziosa<br /> </td> 
   <td> Destinatari nati nel 1945 o prima.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tutte le visite<br /> </td> 
   <td> Ogni destinatario<br /> </td> 
  </tr>
 </tbody> 
</table>
