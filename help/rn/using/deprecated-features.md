---
title: Campaign Standard - Funzioni obsolete e rimosse
description: In questa pagina sono elencate le funzioni obsolete e rimosse di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 490908e5fe0810c0a07c73fef5040ddb42983019

---


# Funzioni obsolete e rimosse {#deprecated-and-removed-features}

Adobe valuta costantemente le funzionalità dei prodotti per identificare le funzioni meno recenti da sostituire con alternative più moderne, al fine di migliorare il valore complessivo dei clienti, sempre con un&#39;attenta considerazione della compatibilità con le versioni precedenti.

Per comunicare l&#39;imminente rimozione/sostituzione delle funzionalità di Campaign Standard, si applicano le regole seguenti:

* L&#39;annuncio della deprecazione viene prima. Le funzionalità obsolete possono essere ancora disponibili per gli utenti esistenti, ma non saranno ulteriormente migliorate né documentate.
* La rimozione di funzionalità obsolete verrà effettuata non prima nella versione successiva. La data di destinazione effettiva per la rimozione è annunciata in questa pagina.

Questo processo offre ai clienti almeno un ciclo di rilascio per adattare la loro implementazione a una nuova versione o successore di una funzionalità obsoleta, prima della rimozione effettiva.

>[!NOTE]
>Le versioni di Adobe Campaign Standard e le nuove funzionalità sono elencate nelle [note](../../rn/using/release-notes.md)sulla versione.


## Funzioni obsolete {#deprecated-features}

In questa sezione sono elencate le funzionalità contrassegnate come obsolete con le ultime versioni di Campaign Standard.

In genere, le funzioni pianificate per essere rimosse in una versione futura sono impostate per prime su obsoleta, con un&#39;alternativa fornita. Queste funzionalità non sono più disponibili per i nuovi clienti di Campaign Standard o non devono essere utilizzate per alcuna nuova implementazione. Vengono anche rimosse dalla documentazione del prodotto.

Si consiglia ai clienti di verificare se utilizzano la funzionalità o la funzionalità nella distribuzione corrente e di pianificare la modifica della propria implementazione per utilizzare l&#39;alternativa fornita. Fare riferimento alla data di rimozione della destinazione per pianificare l&#39;ambiente e gli aggiornamenti del progetto di conseguenza.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifiche push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione 20.1, SDK v4 è obsoleto. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Ulteriori</a>informazioni.</p><br/>
   <p>L’SDK <a href="https://aep-sdks.gitbook.io/docs/"></a> Adobe Experience Platform Mobile (in precedenza denominato v5) supporterà esclusivamente le funzionalità e le funzionalità di Adobe Experience Cloud in arrivo.</p></br>
     <p>Data di rimozione destinazione:30 settembre 2020</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK per Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK è stato disattivato. Di conseguenza, l'edizione dell'immagine fornita da Creative SDK nelle e-mail di Campaign Standard è obsoleta a partire dalla release 20.1.</p></br>
  <p> Data di rimozione destinazione:Marzo 2020 - Rilascio Campaign 20.2</p>
   </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Richieste sulla privacy - API e interfaccia della campagna</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partire dalla versione Campaign 19.4, l'utilizzo dell'API Campaign e dell'interfaccia per l'accesso e l'eliminazione delle richieste è obsoleto. Utilizzate il servizio <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">di base sulla privacy di</a>Adobe.</p></br>
   <p>Vedi anche Gestione della <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">privacy in Campaign Standard</a>.</p>
  <p> Data di rimozione destinazione:Luglio 2020 - Rilascio Campaign 20.5</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Progettazione e-mail - Editor e-mail legacy</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partire dalla versione di Campaign 19.0, l'editor e-mail legacy è diventato obsoleto. Utilizzate <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">il nuovo e-mail Designer</a> per creare e personalizzare il contenuto delle e-mail. </p></br>
   <p>Leggete <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">questa sezione</a> per apprendere come adattare i modelli delle e-mail per il nuovo editor.</p></br>
  <p> Data di rimozione destinazione:Ottobre 2020 - Rilascio Campaign 20.6</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Utenti e sicurezza - Unità geografiche</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partire dalla release 18.7, le unità geografiche sono obsolete. Le unità organizzative e geografiche sono costrutti identici in Campaign. Gli utenti devono utilizzare le sole unità aziendali per creare la propria gerarchia di autorizzazioni utente/accesso ai dati. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Ulteriori</a>informazioni. Le nuove istanze di Campaign Standard, così come le istanze esistenti senza unità geografiche create, non possono avere questa funzionalità implementata a partire dalla release 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>


## Fine della compatibilità {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign e Adobe Experience Cloud non supportano più Microsoft Internet Explorer 11 a partire dalla release Primavera 2019 e Campaign 19.2. Passate a Microsoft Edge o a un altro browser supportato. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Ulteriori</a>informazioni.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
