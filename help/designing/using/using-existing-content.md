---
title: Progettazione di e-mail con contenuto esistente
description: Scopri come progettare e-mail utilizzando il contenuto esistente del contenuto e-mail in E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: 3bda4227-2a6e-4813-a288-93a4388a9787
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1277'
ht-degree: 3%

---

# Progettazione con contenuto esistente {#designing-using-existing-content}

## Selezione di un contenuto esistente{#selecting-an-existing-content}

Adobe Campaign viene fornito con un set di contenuti predefiniti per aiutarti a iniziare. Puoi utilizzare uno di questi o, se il contenuto del messaggio da inviare è in preparazione al di fuori di Adobe Campaign, puoi importarlo dal computer o da un URL.

Quando crei un’e-mail o una pagina di destinazione, puoi scegliere di caricare un contenuto esistente da un’altra origine.

>[!NOTE]
>
>Le immagini seguenti mostrano come caricare un contenuto esistente utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md).

1. Dopo aver creato l’e-mail o la pagina di destinazione, apri il relativo contenuto.
1. Fare clic sull&#39;icona Home per accedere alla home page di **[!UICONTROL Email Designer]**.

   ![](assets/des_loading_1.png)

1. Seleziona l’origine del contenuto da caricare:

   * [Modelli di contenuto](../../designing/using/using-reusable-content.md#content-templates): fare clic sulla scheda **[!UICONTROL Templates]**.
   * [Contenuto da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch), per ricominciare: fare clic sul pulsante **[!UICONTROL Create]**.
   * [Contenuto del computer come file ZIP o HTML](#importing-content-from-a-file): fare clic sul pulsante **[!UICONTROL Upload]**.
   * [Contenuto da un URL esistente](#importing-content-from-a-url) (solo per e-mail): fai clic sul pulsante **[!UICONTROL Import from URL]**.

   ![](assets/des_loading_2.png)

1. Carica il contenuto. Il contenuto selezionato sostituisce il contenuto corrente.

   Una volta importato, il contenuto può essere modificato e personalizzato.

   >[!NOTE]
   >
   >[E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) utilizza tag specifici. I contenuti standard di HTML caricati in Campaign devono corrispondere ai tag previsti per essere completamente compatibili e modificabili da E-mail Designer. Se non corrisponde, il contenuto viene caricato in [modalità di compatibilità](#compatibility-mode). Per rendere compatibili i contenuti esistenti, vedere [questa sezione](#editing-existing-contents-with-the-email-designer).

**Argomenti correlati:**

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Gestione delle pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md)

## Modifica dei contenuti esistenti con E-mail Designer{#editing-existing-contents-with-the-email-designer}

Per sfruttare appieno le possibilità di modifica di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md), il HTML caricato deve contenere tag specifici che lo rendano conforme all&#39;editor WYSIWYG.

Se questo tag non è presente in tutto o in parte nel HTML, il contenuto verrà caricato in &#39; [modalità di compatibilità](#compatibility-mode)&#39;.

Per rendere completamente modificabile un contenuto esterno esistente all&#39;interno di E-mail Designer, consulta la sezione [Progettazione di un messaggio e-mail con contenuti esistenti](../../designing/using/using-existing-content.md).

## Importazione di un contenuto e-mail esistente {#importing}

### Importazione di contenuto da un file {#importing-content-from-a-file}

Dalla home page di E-mail Designer, fare clic sul pulsante **[!UICONTROL Upload]** per caricare un file dal computer, quindi confermare.

Non ci sono vincoli sulla struttura del file zip. Tuttavia, il riferimento ai file HTML deve essere relativo e rispettare la struttura ad albero della cartella zip.

Sono supportati i seguenti formati per l’importazione:

* Un file HTML con un foglio di stile incorporato
* Una cartella .zip contenente il file HTML, il foglio di stile (CSS) e le immagini

>[!NOTE]
>
>Per il contenuto delle e-mail, si consiglia di importare file HTML singoli con un foglio di stile incorporato.

#### Importazione di contenuto da un URL {#importing-content-from-a-url}

Prima di importare contenuti da un URL, accertati che siano soddisfatti i seguenti requisiti:

* Il contenuto deve essere disponibile pubblicamente tramite questo URL.
* Per motivi di sicurezza, sono consentiti solo gli URL che iniziano con **[!UICONTROL https]**.
* Assicurati che tutte le risorse (immagini, CSS) siano impostate nei collegamenti assoluti e in HTTPS. In caso contrario, dopo l’invio dell’e-mail, la pagina speculare verrebbe visualizzata senza le relative risorse. Di seguito è riportato un esempio di definizione di collegamento assoluto:

  ```
  <a href="https://www.mywebsite.com/images/myimage.png">
  ```

>[!NOTE]
>
>Il caricamento di contenuto da un URL è disponibile solo per il canale e-mail.

Per recuperare il contenuto esistente da un URL, effettua le seguenti operazioni:

1. Dalla home page di E-mail Designer, selezionare il pulsante **[!UICONTROL Import from URL]**.

   ![](assets/email_designer_importfromurl.png)

1. Definisci l’URL da cui verrà recuperato il contenuto.
1. Fai clic su **[!UICONTROL Confirm]**.

Scopri questa funzione nel video.

>[!VIDEO](https://video.tv.adobe.com/v/25926?quality=12)

Sono disponibili altri video dimostrativi di Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).

### Recupero automatico del contenuto da un URL in fase di preparazione {#retrieving-content-from-a-url-automatically-at-preparation-time}

L’importazione di contenuto da un URL durante la preparazione del messaggio consente di recuperare il contenuto HTML più recente ogni volta che l’e-mail viene preparata. In questo modo, il contenuto delle e-mail ricorrenti è sempre aggiornato al momento dell’invio. Questa funzione consente inoltre di creare un messaggio pianificato in una data specifica, anche se il contenuto non è ancora pronto.

Per recuperare il contenuto al momento della preparazione, effettua le seguenti operazioni:

1. Selezionare l&#39;opzione **[!UICONTROL Content imported during preparation]**.

   ![](assets/email_designer_importfromurl2.png)

1. Il contenuto dell’URL viene visualizzato nell’editor in sola lettura.

   >[!CAUTION]
   >
   >In questo passaggio, la visualizzazione HTML nell’editor dei contenuti non deve essere presa in considerazione. Verrà recuperato nella fase di preparazione.

1. Per visualizzare in anteprima il contenuto dell&#39;URL recuperato, aprire il messaggio dopo averlo creato e fare clic sul pulsante **[!UICONTROL Preview]**.

È possibile personalizzare l’URL remoto da cui verrà recuperato il contenuto. A questo scopo, segui la procedura indicata di seguito:

1. Fare clic sull&#39;etichetta e-mail nella parte superiore dello schermo per accedere alla scheda E-mail Designer **[!UICONTROL Properties]**.
1. Trova il campo **[!UICONTROL Remote URL]**.

   ![](assets/email_designer_importfromurl4.png)

1. Inserisci il campo di personalizzazione, il blocco di contenuto o il testo dinamico desiderato.

   Il blocco di contenuto **[!UICONTROL Current date - YYYYMMDD]**, ad esempio, consente di inserire la data del giorno.

   >[!NOTE]
   >
   >I campi di personalizzazione disponibili sono collegati solo agli attributi **Delivery** (data di creazione e-mail, stato, etichetta della campagna...).

Se il download del contenuto non riesce al primo tentativo, è possibile riprovare due volte:

1. Il secondo tentativo inizia 50 ms dopo il primo.
1. Il terzo tentativo inizia 100 ms dopo il secondo tentativo.

Questi nuovi tentativi sono utili in questi casi:

* Errore di servizio di breve durata su un server remoto
* Un errore del server in un cluster, nel qual caso è più probabile che i nuovi tentativi abbiano esito positivo grazie al bilanciamento del carico in un server funzionante

### Modalità di compatibilità {#compatibility-mode}

Quando carichi un contenuto, questo deve contenere tag specifici affinché sia completamente conforme e modificabile con l’editor WYSIWYG di E-mail Designer.

Se il HTML caricato non è conforme, in tutto o in parte, all’assegnazione tag prevista, il contenuto viene quindi caricato in &quot;modalità di compatibilità&quot;, che limita le possibilità di modifica tramite l’interfaccia utente.

Quando un contenuto viene caricato in modalità di compatibilità, è comunque possibile eseguire le seguenti modifiche tramite l’interfaccia (le azioni non disponibili sono nascoste):

* Modifica del testo o dell&#39;immagine
* Inserimento di collegamenti e campi di personalizzazione
* Modifica alcune opzioni di stile sul blocco HTML selezionato
* Definizione del contenuto condizionale

![](assets/email_designer_compatibility.png)

Altre modifiche, come l’aggiunta di nuove sezioni all’e-mail o lo stile avanzato, devono essere effettuate direttamente nel codice sorgente dell’e-mail tramite la modalità HTML.

Per ulteriori informazioni sulla conversione di un messaggio e-mail esistente in un messaggio e-mail compatibile con Designer, consulta [questa sezione](../../designing/using/using-existing-content.md).

**Argomento correlato**:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Video introduttivo all’E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md#video)
* [Progettazione di contenuti e-mail da zero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch)

## Conversione di contenuti HTML {#converting-an-html-content}

Se desideri creare un framework di modelli modulari e frammenti che possano essere combinati per essere riutilizzati in più e-mail, dovresti considerare la possibilità di convertire il tuo HTML e-mail in un modello di Designer e-mail.

Questo caso d’uso offre un modo rapido per convertire i messaggi e-mail di HTML in componenti di E-mail Designer.

>[!CAUTION]
>
>Questa sezione è destinata agli utenti avanzati che hanno familiarità con il codice HTML.

>[!NOTE]
>
>Analogamente alla modalità di compatibilità, un componente HTML può essere modificato con opzioni limitate: è possibile eseguire solo l’edizione sul posto.

Al di fuori di E-mail Designer, accertati che il HTML originale sia diviso in sezioni riutilizzabili.

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

Una volta identificati tutti i blocchi, nel Designer e-mail, ripeti la seguente procedura per ogni sezione dell’e-mail esistente:

1. Apri E-mail Designer per creare un contenuto e-mail vuoto.
1. Imposta gli attributi del livello del corpo: colori di sfondo, larghezza, ecc. Per ulteriori informazioni, consulta [Modifica degli stili delle e-mail](../../designing/using/styles.md).
1. Aggiungi un componente struttura. Per ulteriori informazioni, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Aggiungi un componente HTML. Per ulteriori informazioni, consulta [Aggiunta di frammenti e componenti](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copia e incolla il HTML in quel componente.
1. Passa alla visualizzazione per dispositivi mobili. Per ulteriori informazioni, consulta [questa sezione](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

   La visualizzazione reattiva è interrotta perché manca il file CSS.

1. Per risolvere questo problema, passa alla modalità codice sorgente e copia e incolla la sezione di stile in una nuova sezione di stile. Ad esempio:

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
   >Assicurati di aggiungere il tuo stile dopo in un altro tag di stile personalizzato.
   >
   >Non modificare il CSS generato da E-mail Designer:
   >
   >* `<style data-name="default" type="text/css">(##)</style>`
   >* `<style data-name="supportIOS10" type="text/css">(##)</style>`
   >* `<style data-name="mediaIOS8" type="text/css">(##)</style>`
   >* `<style data-name="media-default-max-width-500px" type="text/css">(##)</style>`
   >* `<style data-name="media-default--webkit-min-device-pixel-ratio-0" type="text/css">(##)</style>`

1. Torna alla visualizzazione per dispositivi mobili per verificare che il contenuto sia visualizzato correttamente e salvare le modifiche.
