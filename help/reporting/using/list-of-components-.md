---
title: 'Elenco dei componenti '
description: Consulta l’elenco di tutti i componenti disponibili nei report dinamici e le relative definizioni.
page-status-flag: never-activated
uuid: a2403806-8df4-4bb1-bac2-2689dc584ae0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 17cf126a-7ce1-4e11-bb5e-2bdce01cfded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f78e101b8abea3640ad93db6ff53243a42e07086

---


# Elenco dei componenti {#list-of-components}

Per ulteriori informazioni sulla compatibilità tra dimensioni e metriche, consulta questa [tabella](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se due componenti non sono compatibili, nella cella viene visualizzato il valore **Nessuno**.

![](assets/dynamic_report_compatibility.png)

## Dimensioni {#dimensions}

Nella tabella seguente è riportato l’elenco delle dimensioni utilizzate nei rapporti e le relative definizioni.

<table> 
 <thead> 
  <tr> 
   <th> Dimensione<br /> </th> 
   <th> Definizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Browser<br /> </td> 
   <td> Browser da cui è stato aperto il messaggio o su cui è stato fatto clic.<br /> </td> 
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
   <td> Paese/regione<br /> </td> 
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
   <td> Tipi di errori che causavano errori per ogni consegna, ad esempio un utente sconosciuto, un dominio o una cassetta postale non valida.<br /> </td> 
  </tr> 
  <tr> 
   <td> Genere<br /> </td> 
   <td> Genere del destinatario, ad esempio maschio o femmina. Se il campo genere è vuoto nel profilo del destinatario, il valore sarà none.<br /> </td> 
  </tr> 
  <tr> 
   <td> Azioni messaggio in-app<br /> </td> 
   <td> Azioni sul messaggio in-app inviato, ad esempio azioni sul pulsante 1 o 2 o licenziamenti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo di messaggio<br /> </td> 
   <td> Canale utilizzato per la consegna, ad esempio e-mail, SMS, notifica push o In-App.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nome app mobile<br /> </td> 
   <td> Nome dell’applicazione mobile<br /> </td> 
  </tr> 
  <tr> 
   <td> Piattaforma<br /> </td> 
   <td> Piattaforma del dispositivo da cui è stato aperto/visualizzato/fatto clic sul messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profili<br /> </td> 
   <td> Esegui il backup dei campi out-of-the-box e dei profili personalizzati creati durante l'estensione della risorsa del profilo. Per ulteriori informazioni, fare riferimento a questa <a href="../../developing/using/key-steps-to-add-a-resource.md">pagina</a> o a questo <a href="../../reporting/using/creating-a-custom-profile-dimension.md">esempio</a>.<br /> I dati per questa dimensione vengono recuperati non appena viene pubblicata la risorsa personalizzata collegata al campo del profilo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Piattaforma push<br /> </td> 
   <td> Piattaforma del dispositivo da cui è stata aperta la notifica push, ad esempio iOS o Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio destinatario<br /> </td> 
   <td> Dominio utilizzato per aprire l’e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegna ricorrente<br /> </td> 
   <td> Etichetta e ID della consegna ricorrente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio mittente<br /> </td> 
   <td> Dominio utilizzato per inviare l’e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP mittente<br /> </td> 
   <td> IP utilizzato per inviare l’e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Stato<br /> </td> 
   <td> Stato registrato nel profilo del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL tracciamento<br /> </td> 
   <td> URL su cui l’utente ha fatto clic dal messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria URL tracciamento<br /> </td> 
   <td> Categoria assegnata all’URL di tracciamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta URL tracciamento<br /> </td> 
   <td> Etichetta data all’URL, ad esempio pagina mirror, contattateci o aprite.<br /> </td> 
  </tr> 
  <tr> 
   <td> Distribuzione transazionale<br /> </td> 
   <td> Etichetta e ID della consegna transazionale.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante del messaggio e-mail in caso di test A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche {#metrics}

Le tabelle riportate di seguito forniscono l'elenco delle metriche utilizzate nei report e le relative definizioni in base al tipo di consegna.

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
   <td> Blacklist<br /> </td> 
   <td> Numero di destinatari che hanno dichiarato un'e-mail come spam o posta indesiderata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tariffa Blacklist<br /> </td> 
   <td> Percentuale di consegne contrassegnate come in lista nera.<br /> </td> 
  </tr> 
  <tr> 
   <td> Punti + errori<br /> </td> 
   <td> Totale degli errori cumulati durante l'elaborazione del recapito e del ritorno automatico in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo + Frequenza errori<br /> </td> 
   <td> Percentuale di e-mail rimbalzate rispetto a quelle inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un contenuto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di click-through<br /> </td> 
   <td> Percentuale di clic in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di consegna<br /> </td> 
   <td> Percentuale di messaggi inviati correttamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo duro<br /> </td> 
   <td> Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocità limite<br /> </td> 
   <td> Percentuale di consegne non riuscite a causa di errori permanenti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror, pagina<br /> </td> 
   <td> Numero di destinatari che hanno fatto clic sul collegamento della pagina mirror.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagina speculare<br /> </td> 
   <td> Percentuale di clic sul collegamento della pagina mirror rispetto al totale dei messaggi di consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic offerta<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un'offerta in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di clic offerta<br /> </td> 
   <td> Percentuale di clic su un'offerta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> Numero di volte in cui un messaggio è stato aperto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso aperto<br /> </td> 
   <td> Percentuale di messaggi aperti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di invii per la consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantina<br /> </td> 
   <td> Numero di messaggi rimbalzati e risultati nella quarantena dell'indirizzo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di quarantena<br /> </td> 
   <td> Percentuale di quarantena rispetto ai messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rifiutato<br /> </td> 
   <td> Numero di messaggi classificati come spam dai server SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso rifiutato<br /> </td> 
   <td> Percentuale di messaggi contrassegnati come rifiutati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Soft bounce<br /> </td> 
   <td> Numero totale di errori temporanei, ad esempio una casella in entrata completa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza rimbalzo morbida<br /> </td> 
   <td> Percentuale di consegne non riuscite a causa di motivi temporanei.<br /> </td> 
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
   <td> Tasso di annullamento sottoscrizione<br /> </td> 
   <td> Percentuale di annullamento delle sottoscrizioni per destinatario rispetto ai messaggi consegnati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Annulla sottoscrizione<br /> </td> 
   <td>  Numero di clic sul collegamento di annullamento della sottoscrizione.<br /> </td> 
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
   <td> Punti + errori<br /> </td> 
   <td> Totale degli errori cumulati durante la consegna in relazione al numero totale di messaggi inviati, ad esempio errori da MCPNS o provider.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo + Frequenza errori<br /> </td> 
   <td> Percentuale di notifiche push rimbalzate rispetto alle notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic<br /> </td> 
   <td> Numero di volte in cui una notifica push viene inviata al dispositivo e su cui l'utente fa clic. L'utente desidera visualizzare la notifica, che verrà quindi spostata nel tracciamento dell'apertura push, o chiusa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di click-through<br /> </td> 
   <td> Percentuale di utenti che hanno interagito con la notifica push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di consegna<br /> </td> 
   <td> Percentuale delle notifiche push inviate correttamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> Numero di volte in cui una notifica push viene inviata al dispositivo e lasciata inalterata nel Centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e ritorna al server.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apri<br /> </td> 
   <td> Numero totale di notifiche push inviate al dispositivo e fate clic su di esse dagli utenti per aprire l'app. Questo è simile al clic push, tranne per il fatto che l'apertura push non viene attivata se la notifica è stata chiusa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso aperto<br /> </td> 
   <td> Percentuale delle notifiche push aperte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoco<br /> </td> 
   <td> Numero di volte in cui un utente univoco interagisce con la notifica push, ad esempio facendo clic sulla notifica o sul pulsante.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
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
   <td> Numero totale di messaggi in-app inviati al dispositivo dal provider di servizi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> Totale dei messaggi in-app visualizzati dai destinatari a seconda del rispetto o meno del criterio di attivazione.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app <br /> </td> 
   <td> Numero totale di destinatari che hanno fatto clic sul pulsante 1 o sul pulsante 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di click-through in-app<br /> </td> 
   <td> Percentuale di utenti che hanno fatto clic sul pulsante 1 o sul pulsante 2 rispetto agli utenti che hanno visto il messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Licenza in-app<br /> </td> 
   <td> Numero totale di messaggi che i destinatari hanno chiuso facendo clic sul pulsante Chiudi o chiudendo automaticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di licenziamento in-app<br /> </td> 
   <td> Percentuale di messaggi in-app che i destinatari hanno chiuso.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di messaggi in-app inviati da Adobe Campaign nell'ambito del processo di consegna inviata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> Numero di impression per un destinatario univoco.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic in-app univoci<br /> </td> 
   <td> Numero di volte in cui i destinatari hanno fatto clic sul pulsante 1 o sul pulsante 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Licenze univoche in-app<br /> </td> 
   <td> Numero di volte in cui i destinatari hanno chiuso un messaggio in-app.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmenti {#segments}

>[!NOTE]
>
>Per impostazione predefinita, il **[!UICONTROL Exclude proof]** segmento è già selezionato per filtrare i rapporti, ma può essere modificato se necessario.

Nella tabella seguente sono elencati i segmenti utilizzati nei report e le relative definizioni.

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
   <td> Età: Da 18 a 25<br /> </td> 
   <td> Destinatari dai 18 ai 25 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Da 26 a 30<br /> </td> 
   <td> Destinatari dai 26 ai 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Da 31 a 40<br /> </td> 
   <td> Destinatari dai 31 ai 40 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Da 41 a 50<br /> </td> 
   <td> Destinatari da 41 a 50 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Generazione X<br /> </td> 
   <td> Destinatari nati dal 1966 al 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Generazione Y (millenni)<br /> </td> 
   <td> Destinatari nati dal 1977 al 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Generazione Z<br /> </td> 
   <td> Destinatari nati dal 1995 ad oggi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Maggiore di 50<br /> </td> 
   <td> Destinatari con età maggiore di 50 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Inferiore a 25<br /> </td> 
   <td> Destinatari con età inferiore a 25 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Inferiore a 30<br /> </td> 
   <td> Destinatari con età inferiore a 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Inferiore a 40<br /> </td> 
   <td> Destinatari con età inferiore a 40 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Inferiore a 50<br /> </td> 
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
    <tr> 
   <td> Escludi prova<br /> </td> 
   <td> Escludere le prove di stampa dai report<br /> </td> 
  </tr> 
 </tbody> 
</table>

