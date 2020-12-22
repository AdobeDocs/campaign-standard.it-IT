---
solution: Campaign Standard
product: campaign
title: 'Progettazione di e-mail tramite  integrazioni Adobe Campaign '
description: Scoprite come progettare e-mail tramite  integrazioni Adobe Campaign in e-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 5758e5f0f6811a97f51e995fa3c378a7c7117ff5
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 5%

---


# Progettazione di e-mail con più soluzioni {#multi-solution-email-design}

 Adobe Campaign offre diverse opzioni di authoring delle e-mail. È possibile utilizzare soluzioni come Dreamweaver per modificare il contenuto delle e-mail e creare messaggi reattivi in Designer e-mail. Potete inoltre inviare contenuti e-mail con Adobe Experience Manager e utilizzarli nelle e-mail in  Adobe Campaign Standard.

## Modifica del contenuto in Dreamweaver {#editing-content-in-dreamweaver}

L&#39;integrazione Adobe Campaign Standard  con Dreamweaver consente di modificare il contenuto di un&#39;e-mail nell&#39;interfaccia Dreamweaver. Potete accedere alla potente interfaccia di Dreamweaver per progettare e sviluppare contenuti e-mail reattivi.

* **Sincronizzazione bidirezionale**

   Ogni volta che una modifica viene effettuata in un prodotto, viene aggiornata in tempo reale nell&#39;altro. Se desiderate modificare il colore del testo in Dreamweaver, non appena apportate la modifica, il colore del testo è live in Campaign. Inoltre, quando si seleziona il codice in Dreamweaver o Campaign, poiché i numeri di riga sono identici, la selezione rimane tra i due prodotti, il che è molto utile quando si cerca qualcosa di specifico nel codice.

* **Caricare immagini locali su Adobe Campaign tramite Dreamweaver**

   Quando create o modificate un’e-mail in Dreamweaver, potete semplicemente selezionare un’immagine dal desktop o dal computer locale. Anche se Dreamweaver vi ha sempre consentito di farlo, quando Dreamweaver e Campaign sono connessi, il file locale viene immediatamente caricato nel server Adobe Campaign : non è necessario caricare manualmente le immagini quando il contenuto cambia. Inoltre, garantisce che le immagini più recenti siano sempre live in Campaign.

* **Aggiunta di personalizzazione delle campagne in Dreamweaver**

   Per lo sviluppatore di e-mail non è più necessario aggiungere testo come `[[FIRSTNAME_PLACEHOLDER]]` né cercare la sintassi delle tabelle del modello dati. La barra degli strumenti Campagna di Dreamweaver si collega direttamente al modello dati dell&#39;istanza Campaign. Ciò significa che puoi inserire qualsiasi dato desideri per la personalizzazione da qualcosa come Nome all&#39;Indirizzo. Se hai creato blocchi di contenuto in Campaign, puoi anche estrarli direttamente in Dreamweaver.

Questa funzionalità è descritta in Documentazione Dreamweaver accessibile [qui](https://helpx.adobe.com/it/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

## Modifica del contenuto in  Experience Manager {#editing-content-in-experience-manager}

Il contenuto dell’e-mail può essere modificato in  Experience Manager e quindi utilizzato per uno o più messaggi e-mail in  Adobe Campaign Standard. Fare riferimento a [questo documento](../../integrating/using/integrating-with-experience-manager.md).

## Elenco prodotti {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Utilizzo delle inserzioni di prodotti"
>abstract="L&#39;elenco dei prodotti consente di fare riferimento a una raccolta di dati e di visualizzarla nel contenuto dell&#39;e-mail."

L&#39;elenco dei prodotti consente di fare riferimento a una o più raccolte di dati nel contenuto dell&#39;e-mail. Questi elenchi sono disponibili per le e-mail transazionali. Una sezione dedicata per questa funzione è disponibile [qui](../../designing/using/using-product-listings.md).

## Confronto delle opzioni di progettazione e-mail {#email-design-options-comparison}

 Adobe Campaign offre diverse opzioni di authoring delle e-mail. La tabella seguente mostra le principali possibilità, vantaggi e limitazioni per ciascuno di essi.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> E-mail Designer<br /> </th> 
   <th> Experience Manager <br /> </th> 
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
   <td> Solo all'interno di un componente HTML<br /> </td> 
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
   <td> Anteprima in AEM<br /> Prove in Campaign<br /> </td> 
   <td> Anteprima e prova in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Elenco prodotti</strong><br /> </td> 
   <td> Supportato nei messaggi di transazione per e-mail<br /> </td> 
   <td> Non supportato<br /> </td> 
   <td> Non supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Vantaggi</strong><br /> </td> 
   <td> 
     <p>- Facile creazione delle e-mail attraverso la funzione di trascinamento</p>
     <p>- Funzionalità simili all'editor di contenuti legacy</p>
     <p>- Contenuto riutilizzabile con frammenti</p>
  </td> 
   <td> 
     <p>- Riutilizzo di risorse da siti Web nelle e-mail</p>
     <p>- Sfruttare la potenza del  Experience Manager nei contenuti delle e-mail</p>
    </td> 
   <td> 
    <p>- Possibilità per uno sviluppatore di codificare direttamente un'e-mail</p>
    <p>- Sincronizzazione bidirezionale</p>
    <p>- Modifica offline in Dreamweaver e sincronizzazione in un secondo momento</p>
    <p>- Caricamento di immagini su  Adobe Campaign tramite Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitazioni</strong><br /> </td> 
   <td> 
     <p>- Nessun contenuto condizionale all'interno dei frammenti</p>
     <p>- Non è possibile utilizzare  frammenti di Experience Manager</p>
  </td> 
   <td> 
     <p>- Personalizzazione avanzata difficile da implementare</p>
     <p>- Invio di test in  Adobe Campaign</p>
  </td> 
   <td> Contenuto dinamico non supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Pubblico</strong><br /> </td> 
   <td> Esperti di marketing che desiderano mantenere la flessibilità di utilizzare componenti HTML in combinazione con funzioni di trascinamento della selezione<br /> </td> 
   <td> Gli addetti al marketing utilizzano già  Experience Manager che desiderano utilizzare modelli e-mail standard con poca personalizzazione<br /> </td> 
   <td> Sviluppatori che desiderano codificare i contenuti delle e-mail e integrarli direttamente con  Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Per saperne di più</strong><br /> </td> 
   <td> Vedere <a href="../../designing/using/designing-content-in-adobe-campaign.md">Informazioni su Email Designer</a>.<br /> </td> 
   <td> Vedere <a href="../../integrating/using/integrating-with-experience-manager.md">Integrazione con  Experience Manager</a>.<br /> </td> 
   <td> Vedere <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e Campaign</a> e guardare questo <a href="#video">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Video di esercitazione {#video}

In questo video viene illustrato come creare e modificare contenuti per  Adobe Campaign Standard utilizzando Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Ulteriori video dimostrativi sui Campaign Standard sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
