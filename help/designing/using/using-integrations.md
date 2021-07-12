---
solution: Campaign Standard
product: campaign
title: 'Progettazione di e-mail tramite integrazioni Adobe Campaign '
description: Scopri come progettare e-mail tramite integrazioni Adobe Campaign in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Progettazione e-mail
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 5%

---

# Progettazione di e-mail con più soluzioni {#multi-solution-email-design}

Adobe Campaign offre diverse opzioni di authoring delle e-mail. È possibile utilizzare soluzioni quali Dreamweaver per modificare il contenuto delle e-mail e creare messaggi reattivi in E-mail Designer. Puoi anche inviare contenuti e-mail con Adobe Experience Manager e utilizzarli nelle e-mail in Adobe Campaign Standard.

## Modifica del contenuto in Dreamweaver {#editing-content-in-dreamweaver}

L’integrazione di Adobe Campaign Standard con Dreamweaver consente di modificare il contenuto di un’e-mail nell’interfaccia di Dreamweaver. Puoi accedere alla potente interfaccia di Dreamweaver per progettare e sviluppare contenuti e-mail reattivi.

* **Sincronizzazione bidirezionale**

   Ogni volta che una modifica viene effettuata in un prodotto, viene aggiornata in tempo reale nell’altro. Se desideri modificare il colore del testo in Dreamweaver, non appena apporti tale modifica, il colore del testo è attivo in Campaign. Inoltre, quando selezioni il codice in Dreamweaver o Campaign, poiché i numeri di riga sono gli stessi, la selezione rimane tra i due prodotti, il che è molto utile quando cerchi qualcosa di specifico nel codice.

* **Caricare immagini locali su Adobe Campaign tramite Dreamweaver**

   Quando crei o modifichi un’e-mail in Dreamweaver, puoi semplicemente selezionare un’immagine dal desktop o dal computer locale. Dreamweaver ti ha sempre consentito di farlo, quando Dreamweaver e Campaign sono connessi, il file locale viene immediatamente caricato sul server Adobe Campaign: non è necessario caricare manualmente le immagini quando il contenuto cambia. Inoltre, garantisce che le immagini più recenti siano sempre live in Campaign.

* **Aggiungere la personalizzazione di Campaign in Dreamweaver**

   Per lo sviluppatore di e-mail non è più necessario aggiungere testo come `[[FIRSTNAME_PLACEHOLDER]]` né cercare la sintassi delle tabelle del modello di dati. La barra degli strumenti Campaign in Dreamweaver si connette direttamente al modello dati dell’istanza Campaign. Ciò significa che puoi inserire tutti i dati che desideri per la personalizzazione da un elemento come Nome a Indirizzo. Se hai creato blocchi di contenuto all’interno di Campaign, puoi anche estrarli direttamente in Dreamweaver.

Questa funzionalità è descritta in Documentazione Dreamweaver accessibile [qui](https://helpx.adobe.com/it/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

## Modifica del contenuto in un Experience Manager {#editing-content-in-experience-manager}

Il contenuto dell’e-mail può essere modificato in Experience Manager e quindi utilizzato per uno o più messaggi e-mail in Adobe Campaign Standard. Fare riferimento a [questo documento](../../integrating/using/integrating-with-experience-manager.md).

## Elenco prodotti {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Utilizzo degli elenchi di prodotti"
>abstract="Gli elenchi dei prodotti ti consentono di fare riferimento a una raccolta di dati e di visualizzarli nel contenuto dell’e-mail."

Gli elenchi dei prodotti ti consentono di fare riferimento a una o più raccolte di dati nel contenuto dell’e-mail. Questi elenchi sono disponibili per le e-mail transazionali. Una sezione dedicata a questa funzione è disponibile [qui](../../designing/using/using-product-listings.md).

## Confronto delle opzioni di progettazione e-mail {#email-design-options-comparison}

Adobe Campaign offre diverse opzioni di authoring delle e-mail. La tabella seguente mostra le principali possibilità, vantaggi e limitazioni per ciascuno di essi.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> E-mail Designer<br /> </th> 
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
   <td> Anteprima in AEM<br /> Prova in Campaign<br /> </td> 
   <td> Anteprima e bozza in Campaign<br /> </td> 
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
     <p>- Facile creazione di e-mail tramite trascinamento della selezione</p>
     <p>- Funzionalità simili all’editor di contenuti legacy</p>
     <p>- Contenuto riutilizzabile con frammenti</p>
  </td> 
   <td> 
     <p>- Riutilizzo delle risorse dal sito web nelle e-mail</p>
     <p>- Sfruttare la potenza dell’Experience Manager nei contenuti delle e-mail</p>
    </td> 
   <td> 
    <p>- Possibilità per uno sviluppatore di codificare direttamente un’e-mail</p>
    <p>- Sincronizzazione bidirezionale</p>
    <p>- Modifica offline in Dreamweaver e sincronizzazione in un secondo momento</p>
    <p>- Caricamento di immagini in Adobe Campaign tramite Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitazioni</strong><br /> </td> 
   <td> 
     <p>- Nessun contenuto condizionale nei frammenti</p>
     <p>- Non è possibile utilizzare frammenti di Experience Manager</p>
  </td> 
   <td> 
     <p>- Personalizzazione avanzata difficile da implementare</p>
     <p>- Necessità di inviare test in Adobe Campaign</p>
  </td> 
   <td> Contenuto dinamico non supportato<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Pubblico</strong><br /> </td> 
   <td> Esperti di marketing che desiderano mantenere la flessibilità di utilizzare i componenti HTML in combinazione con funzioni di trascinamento della selezione<br /> </td> 
   <td> Esperti di marketing che utilizzano già un Experience Manager per utilizzare modelli e-mail standard con poca personalizzazione<br /> </td> 
   <td> Sviluppatori che desiderano codificare i contenuti delle e-mail e integrarli direttamente con Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Per saperne di più</strong><br /> </td> 
   <td> Vedere <a href="../../designing/using/designing-content-in-adobe-campaign.md">Informazioni su E-mail Designer</a>.<br /> </td> 
   <td> Vedere <a href="../../integrating/using/integrating-with-experience-manager.md">Integrazione con Experience Manager</a>.<br /> </td> 
   <td> Consulta <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver e Campaign</a> e guarda questo <a href="#video">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Video tutorial {#video}

Questo video mostra come creare e modificare contenuti per Adobe Campaign Standard utilizzando Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Sono disponibili ulteriori video dimostrativi su Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
