---
title: Funzioni obsolete e rimosse di Campaign Standard
description: In questa pagina sono elencate le funzioni obsolete e rimosse di Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 58%

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
   <th> <strong>SDK V4 per applicazioni mobili</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il supporto per gli SDK Adobe Experience Platform Mobile versione 4 è terminato il 31 agosto 2021. Se utilizzi ancora questa versione legacy dell’SDK in Adobe Campaign Standard, devi aggiornare la tua implementazione con Adobe Experience Platform SDK <strong>prima della fine di giugno 2024</strong>. </p></br>
   <p>Leggete <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">questo articolo</a> per scoprire come adattare la tua implementazione e passare all’SDK di Experience Platform più recente.</p></br>
   <p><strong>Attenzione</strong>: l’SDK V4 non sarà più supportato in Campaign Standard a partire dalla fine di giugno 2024.</p>
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
   <td> <p>A partire dalla versione di Campaign 19.0, l’editor e-mail legacy diventa obsoleto. Utilizzare <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">E-mail Designer di Campaign</a> per creare e personalizzare il contenuto delle e-mail. </p></br>
   <p>Leggi <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">questa sezione</a> per scoprire come adattare i modelli e-mail per il nuovo editor.</p></br>
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
   <td> <p>A partire dalla versione 18.7 di Campaign, le unità geografiche diventeranno obsolete. Le unità organizzative e geografiche sono costrutti identici in Campaign. Gli utenti devono utilizzare solo le unità organizzative per creare la propria gerarchia di autorizzazioni utente/accesso ai dati. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=it#administrating">Ulteriori informazioni</a>. Ricorda che, a partire dalla versione 18.7, questa funzionalità non può essere implementata nelle nuove istanze di Campaign Standard né in quelle esistenti senza unità geografiche create.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Funzioni rimosse {#removed-features}

In questa sezione sono elencate le funzionalità rimosse da Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con il servizio Audience Destinations</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione di Campaign Standard 21.3, l’integrazione con il servizio Audience Destinations è diventata obsoleta.  Ora è stato rimosso.</p>
   <p>Per la nuova implementazione, non è più possibile integrare il servizio Audience Destinations con Adobe Campaign Standard. Tuttavia, puoi integrare Campaign e Adobe Experience Platform tramite Origini e Destinazioni. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">Ulteriori informazioni</a>.</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con Adobe Experience Platform Data Connector</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione di Campaign Standard 21.3, l’integrazione con Adobe Experience Platform Data Connector è diventata obsoleta.  Ora è stato rimosso.</p>
   <p>Per la nuova implementazione, non è più possibile integrare Connettore dati di Adobe Experience Platform con Adobe Campaign Standard. Tuttavia, puoi integrare Campaign e Adobe Experience Platform tramite Origini e Destinazioni. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html">Ulteriori informazioni</a>.</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notifiche push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire dalla versione 20.1 di Campaign, SDK v4 è diventato obsoleto. Ora è stato rimosso. <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html">Ulteriori informazioni</a>.</p><br/>
   <p>Il <a href="https://developer.adobe.com/client-sdks/documentation/">SDK di Adobe Experience Platform Mobile</a> (in precedenza denominato v5) ora supporta esclusivamente le nuove funzioni e funzionalità di Adobe Experience Cloud.</p>
   <p>Dopo il 31 agosto 2021 i clienti potranno continuare a scaricare e utilizzare gli SDK versione 4, ma non saranno più disponibili né il supporto dell’Assistenza clienti né l’accesso ai forum.</p>
   <p>Scopri come migrare dall’SDK v4 a Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">in questa pagina</a>.</p></br>
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
   <td> <p>A partire dalla versione 21.2 di Campaign, l’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione diventerà obsoleto. L’eliminazione del profilo in due fasi non è più disponibile. Utilizzare <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Servizio core per la privacy Adobe</a>.</p></br>
   <p>Consulta anche <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html">Gestione delle richieste di accesso a dati personali</a>.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Oggetto predittivo</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partire da aprile 2021, la funzionalità Predictive Subject Line verrà disattivata.</p><br/>
   <p>Consigliamo di sfruttare le funzionalità e-mail basate sull’intelligenza artificiale per analizzare e prevedere i tassi di apertura, i tempi di invio ottimali e i tassi di abbandono probabili in base a metriche di coinvolgimento storiche. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html">Ulteriori informazioni</a></p></br>
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
   <td> <p>[!DNL Adobe Creative SDK] è stato disattivato. Di conseguenza, l’edizione dell’immagine è basata su [!DNL Creative SDK] nelle e-mail Campaign Standard non è più disponibile a partire dalla versione 20.2 di Campaign.</p></br>
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
