---
title: Funzioni obsolete e rimosse di Campaign Standard
description: In questa pagina sono elencate le funzioni obsolete e rimosse di Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 67%

---

# Funzioni obsolete e rimosse {#deprecated-and-removed-features}

Adobe valuta costantemente le funzionalità dei prodotti per identificare le funzioni meno recenti da sostituire con alternative più moderne, al fine di migliorare il valore complessivo per il cliente, sempre con un’attenta considerazione della compatibilità con le versioni precedenti.

Per comunicare l’imminente rimozione/sostituzione delle funzionalità di Campaign Standard, si applicano le seguenti regole:

* Per prima cosa viene annunciato che una data funzione diventerà obsoleta. Le funzionalità obsolete rimarranno disponibili per gli utenti esistenti, ma non saranno ulteriormente migliorate né documentate.
* La rimozione delle funzionalità obsolete viene effettuata non prima della versione successiva. La data effettiva di rimozione viene annunciata su questa pagina.

Questo processo offre ai clienti almeno un ciclo di pubblicazione per adattare la loro implementazione a una nuova versione o alla funzionalità che sostituirà quella obsoleta, prima della rimozione effettiva.

>[!NOTE]
>Le versioni e le nuove funzionalità di Adobe Campaign Standard sono elencate nelle [Note sulla versione](../../rn/using/release-notes.md).


## Funzioni obsolete {#deprecated-features}

In questa sezione sono elencate le funzioni e funzionalità contrassegnate come obsolete con le ultime versioni di Campaign Standard.

In genere, le funzioni che si prevede di rimuovere in una versione futura vengono inizialmente catalogate come obsolete e ne viene fornita un’alternativa. Queste funzioni e funzionalità non sono più disponibili per i nuovi clienti di Campaign Standard o non devono essere utilizzate nelle nuove implementazioni. Vengono inoltre rimosse dalla documentazione del prodotto.

I clienti sono invitati a verificare se utilizzano la funzione/funzionalità nella distribuzione corrente e a pianificare la modifica della loro implementazione in modo da utilizzare l’alternativa fornita. Consulta la versione effettiva di rimozione per pianificare di conseguenza gli aggiornamenti di ambiente e progetto.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con il servizio Audience Destinations</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione 21.3 di Campaign Standard, l’integrazione con il servizio Audience Destinations è diventata obsoleta. </p>
   <p>Per una nuova implementazione, non puoi più integrare il servizio Audience Destinations con Adobe Campaign Standard. Puoi comunque integrare Campaign e Adobe Experience Platform tramite Origini e Destinazioni. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">Ulteriori informazioni</a>.</p>
     <em>Data prevista di rimozione: 2022</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con il connettore dati Adobe Experience Platform</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione 21.3 di Campaign Standard, l’integrazione con Adobe Experience Platform Data Connector è obsoleta. </p>
   <p>Per una nuova implementazione, non puoi più integrare Adobe Experience Platform Data Connector con Adobe Campaign Standard. Puoi comunque integrare Campaign e Adobe Experience Platform tramite Origini e Destinazioni. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=en">Ulteriori informazioni</a>.</p>
     <em>Data prevista di rimozione: 2022</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>


<table> 
 <thead> 
  <tr> 
   <th> <strong>Progettazione delle e-mail - Editor e-mail legacy</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partire dalla versione di Campaign 19.0, l’editor e-mail legacy diventa obsoleto. Utilizza <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Campaign Email Designer</a> per creare e personalizzare il contenuto delle e-mail. </p></br>
   <p>Leggi <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">questa sezione</a> per scoprire come adattare i modelli e-mail per il nuovo editor.</p></br>
  <p> 
  <em>Data prevista di rimozione: 2022</em></p>
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
   <td> <p>A partire dalla versione 18.7 di Campaign, le unità geografiche sono diventate obsolete. Le unità organizzative e geografiche sono costrutti identici in Campaign. Gli utenti devono utilizzare solo le unità organizzative per creare la propria gerarchia di autorizzazioni utente/accesso ai dati. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=it#administrating">Ulteriori informazioni</a>. Ricorda che, a partire dalla versione 18.7, questa funzionalità non può essere implementata nelle nuove istanze di Campaign Standard né in quelle esistenti senza unità geografiche create.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Funzioni rimosse {#removed-features}

In questa sezione sono elencate le funzionalità rimosse da Campaign Standard.



<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifiche push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione Campaign 20.1, l’SDK v4 è diventato obsoleto. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Ulteriori informazioni</a>.</p><br/>
   <p>L’ <a href="https://aep-sdks.gitbook.io/docs/">SDK di Adobe Experience Platform Mobile</a> (precedentemente denominato v5) ora supporta esclusivamente le prossime funzioni e funzionalità di Adobe Experience Cloud.</p>
   <p>Dopo il 31 agosto 2021 i clienti potranno continuare a scaricare e utilizzare gli SDK versione 4, ma non saranno più disponibili né l’assistenza clienti né l’accesso ai forum.</p>
   <p>Scopri come migrare da SDK v4 a Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">in questa pagina</a>.</p></br>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Richieste di accesso a dati personali - API e interfaccia di Campaign</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partire dalla versione 21.2 di Campaign, l’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione diventerà obsoleto. L’eliminazione del profilo in due fasi non sarà disponibile. Utilizza il <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">servizio core per la privacy di Adobe</a>.</p></br>
   <p>Consulta anche <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=it">Gestione delle richieste di accesso a dati personali</a>.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Linea oggetto predittivo</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire da aprile 2021, la funzionalità Predictive Subject Line è disattivata.</p><br/>
   <p>Ti consigliamo di sfruttare le funzionalità e-mail basate sull’intelligenza artificiale per analizzare e prevedere i tassi di apertura, i tempi di invio ottimali e la probabilità di abbandono in base a metriche di coinvolgimento storiche. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">Ulteriori informazioni</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Punteggio tendenza con trigger di Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il <b>punteggio tendenza</b> è stato disattivato dai trigger di Adobe Experience Cloud. Di conseguenza, questa opzione è stata rimossa da Adobe Campaign Standard. Per evitare eventuali valori obsoleti del punteggio tendenza negli schemi di arricchimento, si consiglia di aggiornare gli schemi per recuperare le modifiche più recenti e ripubblicare i trigger esistenti. Per ulteriori informazioni, consulta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html">Pubblicazione di un trigger in Campaign</a>.
</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK Creative per Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>[!DNL Adobe Creative SDK] è stato ritirato. Di conseguenza, l’edizione dell’immagine fornita da [!DNL Creative SDK] nelle e-mail in Campaign Standard non è più disponibile a partire dalla versione 20.2 di Campaign.</p></br>
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
   <td> <p> Adobe Campaign e Adobe Experience Cloud non supportano più Microsoft Internet Explorer 11 a partire dalla primavera 2019 e dalla versione 19.2 di Campaign. Passa a Microsoft Edge o a un altro browser supportato. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Ulteriori informazioni</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
