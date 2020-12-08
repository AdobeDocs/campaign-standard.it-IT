---
solution: Campaign Standard
product: campaign
title: 'Elenco dei componenti '
description: Consulta l’elenco di tutti i componenti disponibili in     Rapporti dinamici e relative definizioni.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 6fffc6a3574c71c01f1e07ff4e6e6aa194479079
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 1%

---


# Elenco dei componenti {#list-of-components}

Per ulteriori informazioni sulla compatibilità tra dimensioni e metriche, consultare la [tabella](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Se due componenti non sono compatibili, nella cella verrà visualizzato il valore **None**.

[![immagine](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension {#dimensions}

Nella tabella seguente è riportato l’elenco delle dimensioni utilizzate nei rapporti e le relative definizioni.

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
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
   <td> Paese/regione<br /> </td> 
   <td> Paese registrato nel profilo del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegna<br /> </td> 
   <td> Etichetta e ID della consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Device<br /> </td> 
   <td> Dispositivo da cui è stata aperta/visualizzata/su cui è stato fatto clic la notifica e-mail/SMS/push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo errore<br /> </td> 
   <td> Tipi di errori che hanno causato rimbalzi per ogni consegna, ad esempio utente sconosciuto, dominio non valido o cassetta postale piena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Genere<br /> </td> 
   <td> Genere del destinatario, ad esempio maschio o femmina. Se il campo di genere è vuoto nel profilo del destinatario, il valore sarà none.<br /> </td> 
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
   <td> Nome dell'applicazione mobile<br /> </td> 
  </tr> 
  <tr> 
   <td> Platform<br /> </td> 
   <td> Piattaforma del dispositivo da cui è stato aperto/visualizzato/fatto clic sul messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profilo<br /> </td> 
   <td> Esegui il backup dei campi out-of-the-box e dei profili personalizzati creati durante l'estensione della risorsa del profilo. Per ulteriori informazioni, fare riferimento a <a href="../../developing/using/key-steps-to-add-a-resource.md">page</a> o a questo <a href="../../reporting/using/creating-a-custom-profile-dimension.md">esempio</a>.<br /> I dati per questa dimensione vengono recuperati non appena viene pubblicata la risorsa personalizzata collegata al campo del profilo.<br /> </td> 
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
   <td> Mittente IP<br /> </td> 
   <td> IP utilizzato per inviare l'e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> State<br /> </td> 
   <td> Stato registrato nel profilo del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL tracciamento<br /> </td> 
   <td> URL su cui l'utente ha fatto clic dal messaggio.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria URL tracciamento<br /> </td> 
   <td> Categoria assegnata all'URL di tracciamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Etichetta URL tracciamento<br /> </td> 
   <td> Etichetta data all'URL, ad esempio pagina mirror, contattateci o aprite.<br /> </td> 
  </tr> 
  <tr> 
   <td> Distribuzione transazionale<br /> </td> 
   <td> Etichetta e ID della consegna transazionale.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variant<br /> </td> 
   <td> Variante dell'e-mail in caso di test A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Metriche {#metrics}

Le tabelle riportate di seguito forniscono l&#39;elenco delle metriche utilizzate nei report e le relative definizioni in base al tipo di consegna.

### Metriche e-mail e SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Al elenco Bloccati<br /> </td> 
   <td> Numero di destinatari che hanno dichiarato un'e-mail come spam o posta indesiderata.<br /> </td> 
  </tr> 
  <tr> 
   <td> elenco Bloccati tasso di <br /> </td> 
   <td> Percentuale di consegne contrassegnate al elenco Bloccati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Punti + errori<br /> </td> 
   <td> Totale degli errori cumulati durante la consegna e l'elaborazione automatica del ritorno in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rimbalzo + Frequenza errori<br /> </td> 
   <td> Percentuale di messaggi e-mail rimbalzati rispetto a quelli inviati tramite e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Fai clic su<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un contenuto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> Percentuale di clic in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di messaggi inviati correttamente, in relazione al numero totale di messaggi inviati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocità di consegna<br /> </td> 
   <td> Percentuale di messaggi inviati correttamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> rimbalzo rigido<br /> </td> 
   <td> Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza rimbalzo rigido<br /> </td> 
   <td> Percentuale di consegne non riuscite a causa di errori permanenti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mirror page<br /> </td> 
   <td> Numero di destinatari che hanno fatto clic sul collegamento della pagina mirror.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza pagina speculare<br /> </td> 
   <td> Percentuale di clic sul collegamento della pagina mirror rispetto al totale dei messaggi di consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic sull'offerta<br /> </td> 
   <td> Numero di volte in cui è stato fatto clic su un'offerta in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasso di clic offerta<br /> </td> 
   <td> Percentuale di clic su un'offerta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> Numero di volte in cui un messaggio è stato aperto in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> Percentuale di messaggi aperti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di invii per la consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quarantena<br /> </td> 
   <td> Numero di messaggi rimbalzati e risultati nella quarantena dell'indirizzo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocità di quarantena<br /> </td> 
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
   <td> Soft bounce rate<br /> </td> 
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
   <td> Annulla sottoscrizione<br /> </td> 
   <td> Percentuale di annullamento sottoscrizioni per destinatario rispetto ai messaggi consegnati.<br /> </td> 
  </tr> 
  <tr> 
   <td> Annulla sottoscrizione<br /> </td> 
   <td> Numero di clic sul collegamento di annullamento della sottoscrizione.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Metriche delle notifiche push {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
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
   <td> Fai clic su<br /> </td> 
   <td> Numero di volte in cui una notifica push viene inviata al dispositivo e su cui l'utente fa clic. L'utente desidera visualizzare la notifica, che verrà quindi spostata nel tracciamento di apertura push, oppure chiuderla.<br /> </td> 
  </tr> 
  <tr> 
   <td> Click through rate<br /> </td> 
   <td> Percentuale di utenti che hanno interagito con la notifica push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero di notifiche push inviate correttamente, in relazione al numero totale di notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocità di consegna<br /> </td> 
   <td> Percentuale di notifiche push inviate correttamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> Numero di volte in cui una notifica push viene inviata al dispositivo e lasciata inalterata nel Centro notifiche. Nella maggior parte dei casi, il numero di impression deve essere simile al numero consegnato. In questo modo il dispositivo riceve il messaggio e le ritorna al server.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di notifiche push inviate.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open<br /> </td> 
   <td> Numero totale di notifiche push inviate al dispositivo e fate clic su di esse dagli utenti per aprire l'app. Questo è simile al clic push, tranne per il fatto che l'apertura push non viene attivata se la notifica è stata chiusa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Open rate<br /> </td> 
   <td> Percentuale delle notifiche push aperte.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci<br /> </td> 
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
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Consegnato<br /> </td> 
   <td> Numero totale di messaggi in-app inviati al dispositivo dal provider di servizi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni<br /> </td> 
   <td> Totale dei messaggi in-app visualizzati dai destinatari a seconda che il criterio di attivazione sia stato soddisfatto.<br /> </td> 
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
   <td> Numero totale di messaggi che i destinatari hanno chiuso facendo clic sul pulsante di chiusura o di chiusura automatica.<br /> </td> 
  </tr> 
  <tr> 
   <td> Frequenza di licenziamento in-app<br /> </td> 
   <td> Percentuale di messaggi in-app che i destinatari hanno chiuso.<br /> </td> 
  </tr> 
  <tr> 
   <td> Elaborato/inviato<br /> </td> 
   <td> Numero totale di messaggi in-app inviati da  Adobe Campaign nell'ambito del processo di consegna inviata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impressioni univoche<br /> </td> 
   <td> Numero di impression per un destinatario univoco.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic univoci in-app<br /> </td> 
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
>Per impostazione predefinita, il segmento **[!UICONTROL Exclude proof]** è già selezionato per filtrare i rapporti, ma può essere modificato se necessario.

Nella tabella seguente sono elencati i segmenti utilizzati nei report e le relative definizioni.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br /> </th> 
   <th> Definition<br /> </th> 
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
   <td> Destinatari da 18 a 25 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Da 26 a 30<br /> </td> 
   <td> Destinatari da 26 a 30 anni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Da 31 a 40<br /> </td> 
   <td> Destinatari da 31 a 40 anni.<br /> </td> 
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
   <td> Destinatari nati dal 1995 a oggi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Età: Maggiore di 50<br /> </td> 
   <td> Destinatari la cui età è superiore a 50.<br /> </td> 
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
   <td> Età: Generazione invisibile<br /> </td> 
   <td> Destinatari nati nel 1945 o prima.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tutte le visite<br /> </td> 
   <td> Ogni destinatario<br /> </td> 
  </tr> 
    <tr> 
   <td> Escludi prova<br /> </td> 
   <td> Escludi prove di stampa dai report<br /> </td> 
  </tr> 
 </tbody> 
</table>

