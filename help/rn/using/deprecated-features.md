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
source-git-commit: 6ffbf03a7eb4fc1b5bfbd523c0c5342d41cfd211

---


# Campaign Standard - Funzioni obsolete e rimosse {#deprecated-and-removed-features}

Adobe valuta costantemente le funzionalità dei prodotti per identificare le funzioni meno recenti da sostituire con alternative più moderne, al fine di migliorare il valore complessivo dei clienti, sempre con un&#39;attenta considerazione della compatibilità con le versioni precedenti.

Per comunicare l&#39;imminente rimozione/sostituzione delle funzionalità di Campaign Standard, si applicano le regole seguenti:

* L&#39;annuncio della deprecazione viene prima. Le funzionalità obsolete possono essere ancora disponibili per gli utenti esistenti, ma non saranno ulteriormente migliorate né documentate.
* La rimozione di funzionalità obsolete verrà effettuata non prima nella versione successiva. La data di destinazione effettiva per la rimozione è annunciata in questa pagina.

Questo processo offre ai clienti almeno un ciclo di rilascio per adattare la loro implementazione a una nuova versione o successore di una funzionalità obsoleta, prima della rimozione effettiva.

>[!NOTE]
>Le versioni di Adobe Campaign Standard e le nuove funzionalità sono elencate nelle [note](../../rn/using/release-notes.md)sulla versione.


## Funzioni obsolete {#deprecated-features}

In questa sezione sono elencate le funzionalità contrassegnate come obsolete con le ultime versioni di Campaign Standard. In genere, le funzioni pianificate per essere rimosse in una versione futura sono impostate per prime su obsoleta, con un&#39;alternativa fornita. Queste funzionalità non sono più disponibili per i nuovi clienti di Campaign Standard o non devono essere utilizzate per alcuna nuova implementazione. Vengono anche rimosse dalla documentazione del prodotto.

Si consiglia ai clienti di verificare se utilizzano la funzionalità o la funzionalità nella distribuzione corrente e di pianificare la modifica della propria implementazione per utilizzare l&#39;alternativa fornita. Fare riferimento alla data di rimozione della destinazione per pianificare l&#39;ambiente e gli aggiornamenti del progetto di conseguenza.

<table> 
 <thead> 
  <tr> 
   <th> Release<br /> </th> 
   <th> Caratteristiche<br /> </th> 
   <th> Sostituzione<br /> </th> 
    <th> Data di rimozione destinazione<br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Push Notifications<br /> </td> 
    <td> L’SDK <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq"></a> Adobe Experience Platform Mobile (in precedenza denominato v5) supporterà esclusivamente le funzionalità e le funzionalità di Adobe Experience Cloud in arrivo. <br /> </td> 
    <td> 30 settembre 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Creative SDK per Campaign Standard<br /> </td> 
  <td> Adobe Creative SDK è stato disattivato. Di conseguenza, l'edizione dell'immagine fornita da Creative SDK nelle e-mail di Campaign Standard è ora obsoleta.<br /> </td>
  <td> Marzo 2020 - Rilascio Campaign 20.2<br /> </td> 
  </tr> 
  <tr> 
   <td> 19.4<br /> </td> 
   <td> Richieste sulla privacy - API e interfaccia della campagna<br /> </td>
    <td> L'utilizzo dell'API e dell'interfaccia di Campaign per le richieste di accesso ed eliminazione è obsoleto. Utilizzate il servizio di base sulla privacy. <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Ulteriori</a>informazioni. Vedi anche Gestione della <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">privacy in Campaign Standard</a>.<br /> </td>
    <td> Luglio 2020 - Rilascio Campaign 20.5<br /> </td> 
  </tr>
  <tr> 
   <td> 19.0<br /> </td> 
   <td> Progettazione e-mail - Editor e-mail legacy<br /> </td>
    <td> L'editor e-mail legacy ora è obsoleto. Il nuovo e-mail Designer consente di creare e personalizzare il contenuto delle e-mail. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Ulteriori</a>informazioni. Leggete <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">questa sezione</a> per apprendere come adattare i modelli delle e-mail per il nuovo editor.<br /> </td>
    <td> Ottobre 2020 - Rilascio Campaign 20.6<br /> </td> 
  </tr>
  <tr> 
   <td> 18.7<br /> </td> 
   <td> Utenti e sicurezza - Unità geografiche<br /> </td>
    <td> Le unità organizzative e geografiche sono costrutti identici in Campaign. Gli utenti devono utilizzare le sole unità aziendali per creare la propria gerarchia di autorizzazioni utente/accesso ai dati. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Ulteriori</a>informazioni. Le nuove istanze di Campaign Standard, così come le istanze esistenti senza unità geografiche create, non possono avere questa funzionalità implementata a partire dalla release 18.7.<br /> </td>
    <td> N/D<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Fine della compatibilità {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> Release<br /> </th> 
   <th> Caratteristiche<br /> </th> 
   <th> Sostituzione<br /> </th> 
 </tr> 
 </thead> 
 <tbody>
<tr> 
   <td> 19.2<br /> </td> 
   <td> Richieste sulla privacy - API e interfaccia della campagna<br /> </td>
    <td> Adobe Campaign e Adobe Experience Cloud non supportano più Microsoft Internet Explorer 11 a partire dalla release Primavera 2019 e Campaign 19.2. Passate a Microsoft Edge o a un altro browser supportato.  <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Ulteriori</a>informazioni.<br /> </td>
    <td><br /> </td> 
  </tr>
  </tbody> 
</table>
