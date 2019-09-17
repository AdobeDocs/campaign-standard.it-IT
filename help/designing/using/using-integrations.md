---
title: 'Progettazione di e-mail tramite integrazioni Adobe Campaign '
seo-title: 'Progettazione di e-mail tramite integrazioni Adobe Campaign  '
description: 'Progettazione di e-mail tramite integrazioni Adobe Campaign '
seo-description: Scopri come progettare e-mail tramite le integrazioni Adobe Campaign in e-mail Designer.
page-status-flag: mai attivato
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: progettazione
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 195e8db45609b8f92f0ec60c987cf6eadfd463eb

---

# Progettazione di e-mail con più soluzioni {#multi-solution-email-design}

## Modifica del contenuto in Dreamweaver {#editing-content-in-dreamweaver}

L'integrazione di Adobe Campaign Standard con Dreamweaver consente di modificare il contenuto di un'e-mail nell'interfaccia di Dreamweaver. Potete accedere alla potente interfaccia di Dreamweaver per progettare e sviluppare contenuti e-mail reattivi.

* **Sincronizzazione bidirezionale**

   Ogni volta che una modifica viene effettuata in un prodotto, viene aggiornata in tempo reale nell'altro. Se desiderate modificare il colore del testo in Dreamweaver, non appena apportate la modifica, il colore del testo è live in Campaign. Inoltre, quando selezionate il codice in Dreamweaver o Campaign, poiché i numeri di riga sono identici, la selezione rimane tra i due prodotti, il che è molto utile quando cercate qualcosa di specifico nel codice.

* **Caricare immagini locali in Adobe Campaign tramite Dreamweaver**

   Quando create o modificate un'e-mail in Dreamweaver, potete semplicemente selezionare un'immagine dal desktop o dal computer locale. Dreamweaver vi ha sempre consentito di farlo, quando Dreamweaver e Campaign sono connessi, il file locale viene immediatamente caricato nel server di Adobe Campaign: non è necessario caricare manualmente le immagini quando il contenuto cambia. Inoltre, garantisce che le immagini più recenti siano sempre live in Campaign.

* **Aggiunta di personalizzazione delle campagne in Dreamweaver**

   Per lo sviluppatore di e-mail non è più necessario aggiungere testo come `[[FIRSTNAME_PLACEHOLDER]]` né cercare la sintassi delle tabelle del modello dati. La barra degli strumenti Campagna in Dreamweaver si collega direttamente al modello dati dell'istanza Campaign. Ciò significa che puoi inserire qualsiasi dato desideri per la personalizzazione da qualcosa come Nome all'Indirizzo. Se avete creato blocchi di contenuto in Campaign, potete anche estrarli direttamente in Dreamweaver.

Questa funzionalità è dettagliata nella documentazione di Dreamweaver accessibile [qui](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). È disponibile anche un [video](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) dimostrativo.

## Modifica del contenuto in Experience Manager {#editing-content-in-experience-manager}

Il contenuto dell'e-mail può essere modificato in Experience Manager e quindi utilizzato per uno o più messaggi e-mail in Adobe Campaign Standard. Fare riferimento a [questo documento](../../integrating/using/integrating-with-experience-manager.md).

## Confronto delle opzioni di progettazione e-mail {#email-design-options-comparison}

Adobe Campaign offre diverse opzioni di creazione e-mail. La tabella seguente mostra le principali possibilità, vantaggi e limitazioni per ciascuno di essi.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Designer e-mail<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Invia e-mail vuota</strong><br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Scrivi HTML</strong><br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Non supportato<br /> </td> 
   <td> Supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aggiorna HTML</strong><br /> </td> 
   <td> Solo all’interno di un componente HTML<br /> </td> 
   <td> Non supportato<br /> </td> 
   <td> Supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalizzazione di base</strong><br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalizzazione avanzata</strong><br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Non supportato<br /> </td> 
   <td> Non supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prova/Anteprima</strong><br /> </td> 
   <td> Supportato<br /> </td> 
   <td> Anteprima in AEM<br /> Proof in Campaign<br /> </td> 
   <td> Anteprima e prova in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Elenco prodotti</strong><br /> </td> 
   <td> Supportato nei messaggi transazionali e-mail<br /> </td> 
   <td> Non supportato<br /> </td> 
   <td> Non supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Vantaggi</strong><br /> </td> 
   <td> 
     - Semplice creazione di e-mail tramite trascinamento<br/>- Funzionalità simili all'editor<br/>di contenuti legacy - Contenuto riutilizzabile con frammenti
  </td> 
   <td> 
     - Riutilizzo delle risorse dal sito Web nelle e-mail<br/>- Utilizzo della potenza di Experience Manager nei contenuti delle e-mail
    </td> 
   <td> 
    - Possibilità per uno sviluppatore di codificare direttamente un'e-mail<br/>- Sincronizzazione<br/>bidirezionale - Modifica offline in Dreamweaver e sincronizzazione in un secondo momento<br/>- Caricamento delle immagini in Adobe Campaign tramite Dreamweaver
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitazioni</strong><br /> </td> 
   <td> 
     - Nessun contenuto condizionale nei frammenti<br/>- Non è possibile utilizzare i frammenti di Experience Manager
  </td> 
   <td> 
     - Personalizzazione avanzata difficile da implementare<br/>- Invio di test in Adobe Campaign
  </td> 
   <td> Contenuto dinamico non supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Pubblico</strong><br /> </td> 
   <td> Esperti di marketing che desiderano mantenere la flessibilità di utilizzare i componenti HTML in combinazione con le funzioni di trascinamento della selezione<br /> </td> 
   <td> Gli addetti al marketing utilizzano già Experience Manager e desiderano utilizzare modelli e-mail standard con poca personalizzazione<br /> </td> 
   <td> Sviluppatori che desiderano codificare i contenuti delle e-mail e integrarli direttamente con Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Per saperne di più</strong><br /> </td> 
   <td> Vedere <a href="../../designing/using/overview.md">Informazioni su Designer e-mail</a><br /> </td> 
   <td> Consultate <a href="../../integrating/using/integrating-with-experience-manager.md">Integrazione con Experience Manager</a><br /> </td> 
   <td> Guarda <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e Campaign</a> e guarda questo <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">video</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
