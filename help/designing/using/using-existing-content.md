---
title: Progettazione di e-mail con contenuto esistente
description: Scopri come progettare e-mail utilizzando il contenuto esistente di e-mail in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 0d645de54106d49452a846ee650335607dbf21d3
workflow-type: tm+mt
source-wordcount: '1282'
ht-degree: 6%

---

# Progettazione con contenuto esistente {#designing-using-existing-content}

## Selezione di un contenuto esistente{#selecting-an-existing-content}

Adobe Campaign viene fornito con un set di contenuti predefiniti per aiutarti a iniziare. Puoi utilizzare uno di questi o, se il contenuto del messaggio da inviare è in preparazione all’esterno di Adobe Campaign, puoi importarlo dal computer o da un URL.

Quando crei un’e-mail o una pagina di destinazione, puoi scegliere di caricare un contenuto esistente da un’altra origine.

>[!NOTE]
>
>Le immagini seguenti mostrano come caricare un contenuto esistente utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Dopo aver creato l’e-mail o la pagina di destinazione, apri il relativo contenuto.
1. Fai clic sull’icona Home per accedere al **[!UICONTROL Email Designer]** home page.

   ![](assets/des_loading_1.png)

1. Seleziona l’origine del contenuto da caricare:

   * [Modelli di contenuto](../../designing/using/using-reusable-content.md#content-templates): fai clic su **[!UICONTROL Templates]** scheda .
   * [Contenuto da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), per iniziare di nuovo: fai clic su **[!UICONTROL Create]** pulsante .
   * [Contenuto del computer come file ZIP o HTML](#importing-content-from-a-file): fai clic su **[!UICONTROL Upload]** pulsante .
   * [Contenuto da un URL esistente](#importing-content-from-a-url) (solo per le e-mail): fai clic su **[!UICONTROL Import from URL]** pulsante .

   ![](assets/des_loading_2.png)

1. Carica il contenuto. Il contenuto selezionato sostituisce il contenuto corrente.

   Una volta importato, il contenuto può essere modificato e personalizzato.

   >[!NOTE]
   >
   >La [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) utilizza tag specifici. Il contenuto HTML standard caricato in Campaign deve corrispondere all’assegnazione tag prevista per essere completamente compatibile e modificabile da E-mail Designer. Se non corrisponde, il contenuto viene caricato in [modalità di compatibilità](#compatibility-mode). Per rendere i contenuti esistenti compatibili, vedi [questa sezione](#editing-existing-contents-with-the-email-designer).

**Argomenti correlati:**

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Gestione delle pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md)

## Modifica di contenuti esistenti con E-mail Designer{#editing-existing-contents-with-the-email-designer}

Per sfruttare appieno le possibilità di edizione del [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md), il HTML caricato deve contenere tag specifici che lo rendono conforme all’editor WYSIWYG.

Se questa assegnazione tag non è presente in tutto o in parte in HTML, il contenuto viene quindi caricato in &quot; [modalità di compatibilità](#compatibility-mode)&quot;.

Per rendere un contenuto esterno esistente completamente modificabile all’interno di E-mail Designer, consulta [Progettazione di un’e-mail con contenuti esistenti](../../designing/using/using-existing-content.md) sezione .

## Importazione di un contenuto e-mail esistente {#importing}

### Importazione di contenuto da un file {#importing-content-from-a-file}

Dalla home page di E-mail Designer, fai clic sul pulsante **[!UICONTROL Upload]** per caricare un file dal computer, quindi confermare.

Non ci sono vincoli alla struttura del file zip. Tuttavia, il riferimento ai file HTML deve essere relativo e rispettare la struttura ad albero della cartella zip.

L’importazione supporta i seguenti formati:

* Un file HTML con un foglio di stile incorporato
* Una cartella .zip contenente il file HTML, il foglio di stile (.CSS) e le immagini

>[!NOTE]
>
>Per il contenuto dell’e-mail, è consigliabile importare file HTML singoli con un foglio di stile incorporato.

#### Importazione di contenuto da un URL {#importing-content-from-a-url}

Prima di importare il contenuto da un URL, accertati che soddisfi i seguenti requisiti:

* Il contenuto deve essere disponibile al pubblico tramite questo URL.
* Per motivi di sicurezza, solo gli URL che iniziano con **[!UICONTROL https]** sono ammessi.
* Assicurati che tutte le risorse (immagini, CSS) siano impostate in collegamenti assoluti e in HTTPS. In caso contrario, dopo l’invio dell’e-mail, la pagina speculare verrebbe visualizzata senza le relative risorse. Ecco un esempio di definizione assoluta di collegamento:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>Il caricamento del contenuto da un URL è disponibile solo per il canale e-mail.

Per recuperare il contenuto esistente da un URL, segui la procedura seguente:

1. Dalla home page di E-mail Designer, seleziona la **[!UICONTROL Import from URL]** pulsante .

   ![](assets/email_designer_importfromurl.png)

1. Definisci l’URL da cui verrà recuperato il contenuto.
1. Fai clic su **[!UICONTROL Confirm]**.

Scopri questa funzione nel video.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Sono disponibili ulteriori video dimostrativi su Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).

### Recupero automatico del contenuto da un URL al momento della preparazione {#retrieving-content-from-a-url-automatically-at-preparation-time}

L’importazione di contenuto da un URL durante la preparazione dei messaggi consente di recuperare il contenuto HTML più recente ogni volta che l’e-mail viene preparata. In questo modo, il contenuto delle e-mail ricorrenti è sempre aggiornato al momento dell’invio. Questa funzione ti consente inoltre di creare un messaggio pianificato in una data specifica, anche se il contenuto non è ancora pronto.

Per recuperare il contenuto in fase di preparazione, segui i passaggi seguenti:

1. Seleziona la **[!UICONTROL Content imported during preparation]** opzione .

   ![](assets/email_designer_importfromurl2.png)

1. Il contenuto dell’URL viene visualizzato nell’editor come di sola lettura.

   >[!CAUTION]
   >
   >A questo punto, la visualizzazione di HTML nell’editor di contenuti non deve essere presa in considerazione. Sarà recuperato nella fase di preparazione.

1. Per visualizzare l’anteprima del contenuto dell’URL recuperato, apri il messaggio una volta creato, quindi fai clic sul pulsante **[!UICONTROL Preview]** pulsante .

È possibile personalizzare l’URL remoto da cui verrà recuperato il contenuto. A tale scopo, segui la procedura indicata di seguito:

1. Fai clic sull’etichetta e-mail nella parte superiore dello schermo per accedere a E-mail Designer **[!UICONTROL Properties]** scheda .
1. Trova il **[!UICONTROL Remote URL]** campo .

   ![](assets/email_designer_importfromurl4.png)

1. Inserisci il campo di personalizzazione, il blocco di contenuto o il testo dinamico desiderato.

   La **[!UICONTROL Current date - YYYYMMDD]** il blocco di contenuto, ad esempio, consente di inserire la data del giorno.

   >[!NOTE]
   >
   >I campi di personalizzazione disponibili sono collegati a **Consegna** solo attributi (data di creazione e-mail, stato, etichetta della campagna..).

Se il download del contenuto non riesce al primo tentativo, può essere ritentato due volte:

1. Il secondo tentativo inizia 50 ms dopo il primo tentativo.
1. Il terzo tentativo inizia 100 ms dopo il secondo tentativo.

Questi tentativi sono utili nei casi seguenti:

* Errore di servizio di breve durata su un server remoto
* Un errore del server su un cluster, nel qual caso i tentativi hanno maggiori probabilità di successo grazie al bilanciamento del carico su un server di lavoro

### Modalità di compatibilità {#compatibility-mode}

Quando carichi un contenuto, questo deve contenere tag specifici per essere completamente conformi e modificabili con l’editor WYSIWYG di E-mail Designer.

Se in tutto o in parte HTML caricato non è conforme ai tag previsti, il contenuto viene caricato in &quot;modalità compatibilità&quot;, che limita le possibilità di modifica attraverso l’interfaccia utente.

Quando un contenuto viene caricato in modalità di compatibilità, è comunque possibile eseguire le seguenti modifiche tramite l’interfaccia (le azioni non disponibili sono nascoste):

* Modifica del testo o modifica di un’immagine
* Inserimento di collegamenti e campi di personalizzazione
* Modifica alcune opzioni di stile sul blocco di HTML selezionato
* Definizione del contenuto condizionale

![](assets/email_designer_compatibility.png)

Altre modifiche, ad esempio l’aggiunta di nuove sezioni all’e-mail o allo stile avanzato, devono essere eseguite direttamente nel codice sorgente dell’e-mail tramite la modalità HTML.

Per ulteriori informazioni sulla conversione di un’e-mail esistente in un’e-mail compatibile con E-mail Designer, consulta [questa sezione](../../designing/using/using-existing-content.md).

**Argomento correlato**:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Video introduttivo su E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Conversione del contenuto HTML {#converting-an-html-content}

Se desideri creare un framework di modelli e frammenti modulari che possano essere combinati per riutilizzare in più e-mail, considera la possibilità di convertire il tuo HTML e-mail in un modello di E-mail Designer.

Questo caso d’uso offre un modo rapido per convertire e-mail HTML in componenti di E-mail Designer.

>[!CAUTION]
>
>Questa sezione è destinata agli utenti avanzati che hanno dimestichezza con il codice HTML.

>[!NOTE]
>
>Come la modalità di compatibilità, un componente HTML è modificabile con opzioni limitate: è possibile eseguire solo edizioni sul posto.

Al di fuori di E-mail Designer, assicurarsi che il HTML originale sia diviso in sezioni riutilizzabili.

In caso contrario, ritagliare i diversi blocchi dal HTML. Ad esempio:

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
1. Copia e incolla il tuo HTML in quel componente.
1. Passa alla vista per dispositivi mobili. Per ulteriori informazioni, consulta [questa sezione](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

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
