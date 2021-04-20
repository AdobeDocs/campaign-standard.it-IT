---
solution: Campaign Standard
product: campaign
title: 'Progettazione di e-mail con contenuto esistente '
description: Scopri come progettare e-mail utilizzando il contenuto esistente di e-mail in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 5%

---

# Progettazione con contenuto esistente {#designing-using-existing-content}

## Selezione di un contenuto esistente{#selecting-an-existing-content}

Adobe Campaign viene fornito con un set di contenuti predefiniti per aiutarti a iniziare. Puoi utilizzare uno di questi o, se il contenuto del messaggio da inviare è in preparazione all’esterno di Adobe Campaign, puoi importarlo dal computer o da un URL.

Quando crei un’e-mail o una pagina di destinazione, puoi scegliere di caricare un contenuto esistente da un’altra origine.

>[!NOTE]
>
>Le immagini seguenti mostrano come caricare un contenuto esistente utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Dopo aver creato l’e-mail o la pagina di destinazione, apri il relativo contenuto.
1. Fai clic sull’icona Home per accedere alla home page di **[!UICONTROL Email Designer]** .

   ![](assets/des_loading_1.png)

1. Seleziona l’origine del contenuto da caricare:

   * [Modelli](../../designing/using/using-reusable-content.md#content-templates) di contenuto: fai clic sulla  **[!UICONTROL Templates]** scheda .
   * [Contenuto da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), per iniziare da nuovo: fai clic sul  **[!UICONTROL Create]** pulsante .
   * [Contenuto del computer come file](#importing-content-from-a-file) ZIP o HTML: fai clic sul  **[!UICONTROL Upload]** pulsante .
   * [Contenuto da un URL](#importing-content-from-a-url)  esistente (solo per e-mail): fai clic sul  **[!UICONTROL Import from URL]** pulsante .

   ![](assets/des_loading_2.png)

1. Carica il contenuto. Il contenuto selezionato sostituisce il contenuto corrente.

   Una volta importato, il contenuto può essere modificato e personalizzato.

   >[!NOTE]
   >
   >L’ [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) utilizza tag specifici. Il contenuto HTML standard caricato in Campaign deve corrispondere all’assegnazione tag prevista per essere completamente compatibile e modificabile da E-mail Designer. Se non corrisponde, il contenuto viene caricato in [modalità di compatibilità](#compatibility-mode). Per rendere i contenuti esistenti compatibili, consulta [questa sezione](#editing-existing-contents-with-the-email-designer).

**Argomenti correlati:**

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Gestione delle pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md)

## Modifica di contenuti esistenti con E-mail Designer{#editing-existing-contents-with-the-email-designer}

Per sfruttare appieno le possibilità di modifica di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md), il codice HTML caricato deve contenere tag specifici che lo rendono conforme all’editor WYSIWYG.

Se per tutto o in parte l’HTML non è presente questo tag, il contenuto viene caricato in &#39; [modalità di compatibilità](#compatibility-mode)&#39;.

Per rendere un contenuto esterno esistente completamente modificabile all’interno di E-mail Designer, consulta la sezione [Progettazione di un’e-mail utilizzando contenuti esistenti](../../designing/using/using-existing-content.md) .

## Importazione di un contenuto e-mail esistente {#importing}

### Importazione di contenuto da un file {#importing-content-from-a-file}

Dalla home page di E-mail Designer, fai clic sul pulsante **[!UICONTROL Upload]** per caricare un file dal computer, quindi conferma.

Non ci sono vincoli alla struttura del file zip. Tuttavia, il riferimento ai file HTML deve essere relativo e rispettare la struttura ad albero della cartella zip.

L’importazione supporta i seguenti formati:

* Un file HTML con un foglio di stile incorporato
* Una cartella .zip contenente il file HTML, il foglio di stile (.CSS) e le immagini

>[!NOTE]
>
>Per il contenuto dell’e-mail, è consigliabile importare singoli file HTML con un foglio di stile incorporato.

#### Importazione di contenuto da un URL {#importing-content-from-a-url}

Prima di importare il contenuto da un URL, accertati che soddisfi i seguenti requisiti:

* Il contenuto deve essere disponibile al pubblico tramite questo URL.
* Per motivi di sicurezza, sono consentiti solo gli URL che iniziano con **[!UICONTROL https]** .
* Assicurati che tutte le risorse (immagini, CSS) siano impostate in collegamenti assoluti e in HTTPS. In caso contrario, dopo l’invio dell’e-mail, la pagina speculare verrebbe visualizzata senza le relative risorse. Ecco un esempio di definizione assoluta di collegamento:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>Il caricamento del contenuto da un URL è disponibile solo per il canale e-mail.

Per recuperare il contenuto esistente da un URL, segui la procedura seguente:

1. Dalla home page di E-mail Designer, selezionare il pulsante **[!UICONTROL Import from URL]** .

   ![](assets/email_designer_importfromurl.png)

1. Definisci l’URL da cui verrà recuperato il contenuto.
1. Fai clic su **[!UICONTROL Confirm]**.

Scopri questa funzione nel video.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Sono disponibili ulteriori video dimostrativi su Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).

### Recupero automatico del contenuto da un URL al momento della preparazione {#retrieving-content-from-a-url-automatically-at-preparation-time}

L’importazione di contenuto da un URL durante la preparazione dei messaggi consente di recuperare il contenuto HTML più recente ogni volta che l’e-mail viene preparata. In questo modo, il contenuto delle e-mail ricorrenti è sempre aggiornato al momento dell’invio. Questa funzione ti consente inoltre di creare un messaggio pianificato in una data specifica, anche se il contenuto non è ancora pronto.

Per recuperare il contenuto in fase di preparazione, segui i passaggi seguenti:

1. Selezionare l&#39;opzione **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. Il contenuto dell’URL viene visualizzato nell’editor come di sola lettura.

   >[!CAUTION]
   >
   >A questo punto, la visualizzazione HTML nell’editor di contenuti non deve essere presa in considerazione. Sarà recuperato nella fase di preparazione.

1. Per visualizzare in anteprima il contenuto dell’URL recuperato, apri il messaggio una volta creato, quindi fai clic sul pulsante **[!UICONTROL Preview]** .

È possibile personalizzare l’URL remoto da cui verrà recuperato il contenuto. Per farlo, segui la procedura indicata di seguito:

1. Fai clic sull’etichetta e-mail nella parte superiore dello schermo per accedere alla scheda E-mail Designer **[!UICONTROL Properties]** .
1. Trova il campo **[!UICONTROL Remote URL]** .

   ![](assets/email_designer_importfromurl4.png)

1. Inserisci il campo di personalizzazione, il blocco di contenuto o il testo dinamico desiderato.

   Il blocco di contenuto **[!UICONTROL Current date - YYYYMMDD]**, ad esempio, consente di inserire la data del giorno.

   >[!NOTE]
   >
   >I campi di personalizzazione disponibili sono collegati solo agli attributi **Delivery** (data di creazione e-mail, stato, etichetta della campagna...).

### Modalità di compatibilità {#compatibility-mode}

Quando carichi un contenuto, questo deve contenere tag specifici per essere completamente conformi e modificabili con l’editor WYSIWYG di E-mail Designer.

Se tutto o parte dell’HTML caricato non è conforme ai tag previsti, il contenuto viene caricato in &quot;modalità di compatibilità&quot;, che limita le possibilità di modifica attraverso l’interfaccia utente.

Quando un contenuto viene caricato in modalità di compatibilità, è comunque possibile eseguire le seguenti modifiche tramite l’interfaccia (le azioni non disponibili sono nascoste):

* Modifica del testo o modifica di un’immagine
* Inserimento di collegamenti e campi di personalizzazione
* Modifica alcune opzioni di stile sul blocco HTML selezionato
* Definizione del contenuto condizionale

![](assets/email_designer_compatibility.png)

Altre modifiche, come l’aggiunta di nuove sezioni all’e-mail o lo stile avanzato, devono essere effettuate direttamente nel codice sorgente dell’e-mail tramite la modalità HTML.

Per ulteriori informazioni sulla conversione di un’e-mail esistente in un messaggio e-mail compatibile con E-mail Designer, consulta [questa sezione](../../designing/using/using-existing-content.md).

**Argomento correlato**:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Video introduttivo su E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Conversione del contenuto HTML {#converting-an-html-content}

Se desideri creare un framework di modelli e frammenti modulari che possano essere combinati per riutilizzare in più e-mail, considera la possibilità di convertire il codice HTML dell’e-mail in un modello di E-mail Designer.

Questo caso d’uso offre un modo rapido per convertire le e-mail HTML in componenti di E-mail Designer.

>[!CAUTION]
>
>Questa sezione è destinata agli utenti avanzati che hanno dimestichezza con il codice HTML.

>[!NOTE]
>
>Come la modalità di compatibilità, un componente HTML è modificabile con opzioni limitate: è possibile eseguire solo edizioni sul posto.

Al di fuori di E-mail Designer, accertati che l’HTML originale sia diviso in sezioni riutilizzabili.

In caso contrario, ritaglia i diversi blocchi dal tuo HTML. Ad esempio:

```
<!-- 3 COLUMN w/CTA (SCALED) -->
<table width="100%" align="center" cellspacing="0" cellpadding="0" border="0" role="presentation" style="max-width:680px;">
<tbody>
<tr>
<td class="padh10" align="center" valign="top" style="padding:0 5px 20px 5px;">
<table width="100%" cellspacing="0" cellpadding="0" border="0" role="presentation">
<tbody>
<tr>
...
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<!-- //3 COLUMN w/CTA (SCALED) -->
```

Dopo aver identificato tutti i blocchi, in E-mail Designer ripeti la seguente procedura per ogni sezione dell’e-mail esistente:

1. Apri E-mail Designer per creare un contenuto e-mail vuoto.
1. Imposta gli attributi del livello del corpo: colori di sfondo, larghezza, ecc. Per ulteriori informazioni, consulta [Modifica degli stili delle e-mail](../../designing/using/styles.md).
1. Aggiungi un componente struttura. Per ulteriori informazioni, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Aggiungi un componente HTML. Per ulteriori informazioni, consulta [Aggiunta di frammenti e componenti](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copia e incolla il codice HTML in quel componente.
1. Passa alla visualizzazione mobile. Per ulteriori informazioni, consulta [questa sezione](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   La visualizzazione reattiva non funziona perché manca il CSS.

1. Per risolvere il problema, passa alla modalità codice sorgente e copia-incolla la sezione stile in una nuova sezione stile. Ad esempio:

   ```
   <style type="text/css">
   a {text-decoration:none;}
   body {min-width:100% !important; margin:0 auto !important; padding:0 !important;}
   img {line-height:100%; text-decoration:none; -ms-interpolation-mode:bicubic;}
   ...
   </style>
   ```

   >[!NOTE]
   >
   >Assicurati di aggiungere lo stile dopo questo in un altro tag di stile personalizzato.
   >
   >Non modificare il CSS generato da E-mail Designer:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`


1. Torna alla visualizzazione mobile per verificare che il contenuto sia visualizzato correttamente e salvare le modifiche.
