---
title: Funzioni obsolete e rimosse di Campaign Standard
description: In questa pagina sono elencate le funzioni obsolete e rimosse di Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
TQID: https://experienceleague.adobe.com/S430SyqHAam2JE4LQppJUy3xuEdS6lw1qGQE9viVCS8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b631758a-142d-425f-b9aa-f756d85cb979
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1045
ht-degree: 50%

---

# Funzioni obsolete e rimosse {#deprecated-and-removed-features}

Adobe valuta costantemente le funzionalità dei prodotti per identificare le funzioni meno recenti da sostituire con alternative più moderne, al fine di migliorare il valore complessivo per il cliente, sempre con un’attenta considerazione della compatibilità con le versioni precedenti.

Per comunicare l’imminente rimozione/sostituzione delle funzionalità di Campaign Standard, si applicano le seguenti regole:

* Per prima cosa viene annunciato che una data funzione diventerà obsoleta. Le funzionalità obsolete rimarranno disponibili per gli utenti esistenti, ma non saranno ulteriormente migliorate né documentate.
* La rimozione delle funzionalità obsolete viene effettuata non prima della versione successiva. La data prevista di rimozione viene annunciata su questa pagina.

Questo processo offre ai clienti almeno un ciclo di pubblicazione per adattare la loro implementazione a una nuova versione o alla funzionalità che sostituirà quella obsoleta, prima della rimozione effettiva.

>[!NOTE]
>Le versioni e le nuove funzionalità di Adobe Campaign Standard sono elencate nelle [Note sulla versione](../../rn/using/release-notes.md).


## Funzioni obsolete {#deprecated-features}

In questa sezione sono elencate le funzioni e funzionalità contrassegnate come obsolete con le ultime versioni di Campaign Standard.

In genere, le funzioni che si prevede di rimuovere in una versione futura vengono inizialmente catalogate come obsolete e ne viene fornita un’alternativa. Queste funzioni e funzionalità non sono più disponibili per i nuovi clienti di Campaign Standard o non devono essere utilizzate nelle nuove implementazioni. Vengono inoltre rimosse dalla documentazione del prodotto.

I clienti sono invitati a verificare se utilizzano la funzione/funzionalità nella distribuzione corrente e a pianificare la modifica della loro implementazione in modo da utilizzare l’alternativa fornita. Fai riferimento alla versione effettiva in cui avverrà la rimozione per pianificare di conseguenza gli aggiornamenti di ambiente e progetto.



<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK V4 per applicazioni mobili</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il supporto per gli SDK Adobe Experience Platform Mobile versione 4 è terminato il 31 agosto 2021. Se utilizzi ancora questa versione legacy di SDK in Adobe Campaign Standard, devi aggiornare l'implementazione con Adobe Experience Platform SDK <strong>prima della fine di giugno 2024</strong>. </p></br>
   <p>Consulta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">questo articolo</a> per scoprire come adattare la tua implementazione e passare alla versione più recente di Experience Platform SDK.</p></br>
   <p><strong>Attenzione</strong>: SDK V4 non sarà più supportato in Campaign Standard a partire dalla fine di giugno 2024.</p>
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
   <td> <p>A partire dalla versione di Campaign 19.0, l’editor e-mail legacy diventa obsoleto. Utilizza <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">E-mail campagna Designer</a> per creare e personalizzare il contenuto delle e-mail. </p></br>
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
   <td> <p> A partire dalla versione 21.3 di Campaign Standard, l’integrazione con il servizio Audience Destinations è diventata obsoleta.  Ora è stato rimosso.</p>
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
   <td> <p> A partire dalla versione 21.3 di Campaign Standard, l’integrazione con il connettore dati di Adobe Experience Platform è diventata obsoleta.  Ora è stato rimosso.</p>
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
   <td> <p> A partire dalla versione 20.1 di Campaign, SDK v4 è diventato obsoleto. Ora è stato rimosso. <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=it">Ulteriori informazioni</a>.</p><br/>
   <p><a href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform Mobile SDK</a> (in precedenza denominato v5) ora supporta esclusivamente le nuove funzionalità di Adobe Experience Cloud.</p>
   <p>Dopo il 31 agosto 2021 i clienti potranno continuare a scaricare e utilizzare gli SDK versione 4, ma non saranno più disponibili né il supporto dell’Assistenza clienti né l’accesso ai forum.</p>
   <p>Scopri come effettuare la migrazione da SDK v4 a Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html">in questa pagina</a>.</p></br>
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
   <td> <p>A partire dalla versione 21.2 di Campaign, l’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione diventerà obsoleto. L’eliminazione del profilo in due fasi non è più disponibile. Utilizza <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Adobe Privacy Core Service</a>.</p></br>
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
   <td> <p>[!DNL Adobe Creative SDK] è stato disattivato. Di conseguenza, l’edizione dell’immagine fornita da [!DNL Creative SDK] nelle e-mail di Campaign Standard non è più disponibile a partire dalla versione 20.2 di Campaign.</p></br>
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
   <td> <p>Adobe Campaign e Adobe Experience Cloud non supportano più Microsoft Internet Explorer 11 a partire dalla primavera 2019 e dalla versione 19.2 di Campaign. Passa a Microsoft Edge o a un altro browser supportato. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html">Ulteriori informazioni</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
