---
title: Funzioni Campaign Standard obsolete e rimosse
description: In questa pagina sono elencate le funzioni obsolete e rimosse di  Adobe Campaign Standard.
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
source-git-commit: 5b99fb9fbf8bdac506aeb8a35f30a7ef33aaa7e6
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 17%

---


# Funzioni obsolete e rimosse {#deprecated-and-removed-features}

Adobe valuta costantemente le funzionalità dei prodotti per identificare le funzioni meno recenti da sostituire con alternative più moderne, al fine di migliorare il valore complessivo per il cliente, sempre con un’attenta considerazione della compatibilità con le versioni precedenti.

Per comunicare l&#39;imminente rimozione/sostituzione delle funzionalità Campaign Standard, si applicano le regole seguenti:

* Per prima cosa viene annunciato che una data funzione diventerà obsoleta. Le funzionalità obsolete possono essere ancora disponibili per gli utenti esistenti, ma non saranno ulteriormente migliorate né documentate.
* La rimozione delle funzionalità obsolete viene effettuata non prima della versione successiva. La data effettiva di rimozione viene annunciata su questa pagina.

Questo processo offre ai clienti almeno un ciclo di pubblicazione per adattare la loro implementazione a una nuova versione o alla funzionalità che sostituirà quella obsoleta, prima della rimozione effettiva.

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## Funzioni obsolete {#deprecated-features}

In questa sezione sono elencate le funzionalità contrassegnate come obsolete con le ultime versioni di Campaign Standard.

In genere, le funzioni pianificate per essere rimosse in una versione futura sono impostate per prime su obsoleta, con un&#39;alternativa fornita. Queste funzionalità non sono più disponibili per i nuovi clienti Campaign Standard o non devono essere utilizzate per alcuna nuova implementazione. Vengono inoltre rimosse dalla documentazione del prodotto.

Si consiglia ai clienti di verificare se utilizzano la funzionalità o la funzionalità nella distribuzione corrente e di pianificare la modifica della propria implementazione per utilizzare l&#39;alternativa fornita. Fare riferimento alla versione di rimozione di destinazione per pianificare l&#39;ambiente e gli aggiornamenti del progetto di conseguenza.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifiche push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione 20.1, SDK v4 è obsoleto. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Ulteriori informazioni</a>.</p><br/>
   <p>L’SDK <a href="https://aep-sdks.gitbook.io/docs/"></a> Adobe Experience Platform Mobile (in precedenza denominato v5) supporterà esclusivamente le funzionalità e le funzionalità imminenti di Adobe Experience Cloud.</p></br>
     <p>
     <em>Data di rimozione destinazione: 30 settembre 2020</em></p>
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
   <td> <p>A partire dalla versione Campaign 19.4, l'utilizzo dell'API Campaign e dell'interfaccia per l'accesso e l'eliminazione delle richieste è obsoleto. L'eliminazione del profilo in due fasi non sarà disponibile. Utilizzate <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Vedi anche Gestione della <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">privacy in Campaign Standard</a>.</p>
  <p> 
  <em>Data effettiva di rimozione: 2021</em></p>
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
  <p> 
  <em>Data effettiva di rimozione: 2021</em></p>
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
   <td> <p>A partire dalla release 18.7, le unità geografiche sono obsolete. Le unità organizzative e geografiche sono costrutti identici in Campaign. Gli utenti devono utilizzare le sole unità aziendali per creare la propria gerarchia di autorizzazioni utente/accesso ai dati. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Ulteriori informazioni</a>. Le nuove istanze di Campaign Standard, così come quelle esistenti senza unità geografiche create, non possono avere questa funzionalità implementata a partire dalla release 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

In questa sezione sono elencate le funzionalità rimosse dai Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Punteggio tendenza con attivatori  Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il punteggio <b>tendenza</b> è stato disattivato da Adobe Experience Cloud Triggers. Di conseguenza, questa opzione è stata rimossa da  Adobe Campaign Standard. Per evitare eventuali valori obsoleti di Propensity score (Punteggio tendenza) negli schemi di arricchimento, si consiglia di aggiornare gli schemi per recuperare le modifiche più recenti e ripubblicare gli Attivatori esistenti. Per ulteriori informazioni, consulta <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html#publishing-trigger-in-campaign"> Pubblicazione di un trigger in Campaign </a>.
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK for Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL  Adobe Creative SDK] è stato disattivato. Di conseguenza, l'edizione dell'immagine fornita da [!DNL Creative SDK] nelle e-mail in Campaign Standard non è più disponibile a partire dalla release Campaign 20.2.</p></br>
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
   <td> <p> Adobe Campaign e Adobe Experience Cloud non supportano più Microsoft Internet Explorer 11 a partire dalla release Primavera 2019 e Campaign 19.2. Passate a Microsoft Edge o a un altro browser supportato. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">Ulteriori informazioni</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
