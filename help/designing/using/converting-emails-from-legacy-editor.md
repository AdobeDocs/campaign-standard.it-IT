---
solution: Campaign Standard
product: campaign
title: 'Conversione di e-mail dell’Editor Legacy in E-mail Designer '
description: Scopri come utilizzare le e-mail create nell’editor legacy e-mail per e-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Progettazione e-mail
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 8%

---


# Conversione del contenuto e-mail dell’editor legacy {#converting-an-html-content}

Inizia a utilizzare E-mail Designer e crea modelli e frammenti riutilizzabili dal codice HTML dell’e-mail creato nell’editor legacy.

Questo caso d’uso consente di creare un modello E-mail Designer utilizzando un’e-mail HTML e di suddividerlo nei componenti HTML in E-mail Designer.

>[!NOTE]
>
>Come la modalità di compatibilità, un componente HTML è modificabile con opzioni limitate: è possibile eseguire solo edizioni sul posto.

>[!IMPORTANT]
>
>Questa sezione è destinata agli utenti avanzati che hanno dimestichezza con il codice HTML.

## Preparazione del contenuto dell’e-mail

1. Seleziona un messaggio e-mail HTML.
1. Identifica le sezioni per dividere l’e-mail HTML.
1. Taglia i diversi blocchi dal tuo HTML.

## Creare la struttura delle e-mail

1. Apri **[!UICONTROL Email Designer]** per creare un contenuto e-mail vuoto.
1. Imposta gli attributi del livello del corpo: colori di sfondo, larghezza, ecc. Per ulteriori informazioni, consulta [Modifica degli stili delle e-mail](../../designing/using/styles.md).
1. Aggiungi tutti i componenti struttura disponibili. Per ulteriori informazioni, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

## Aggiungi contenuto HTML

1. Aggiungi un componente HTML a ciascun componente struttura. Per ulteriori informazioni, consulta [Aggiunta di frammenti e componenti](../../designing/using/designing-from-scratch.md#defining-the-email-structure).
1. Copia e incolla il codice HTML in ogni componente.

## Gestione dello stile dell’e-mail {#manage-the-style-of-your-email}

1. Passa a **[!UICONTROL Mobile view]**. Per ulteriori informazioni, consulta [questa sezione](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

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

## Caso d’uso

Proviamo a convertire questa e-mail, creata nell’editor legacy, in un modello **[!UICONTROL Email Designer]**.

### Identifica la sezione dell’e-mail

Possiamo identificare 11 sezioni in questo messaggio e-mail.

![](assets/html-dce-view-mail.png)

Per identificare quale elemento è la sezione dell’HTML, puoi selezionarla.

![](assets/breadcrumbs.png)

Per visualizzare la versione HTML dell’e-mail, fai clic su **[!UICONTROL Show source]**.

### Creare il modello e-mail e la relativa struttura

1. Trascina **[!UICONTROL Structure components]** per rispecchiare il layout della nostra e-mail.

1. Ripeti il numero di volte necessario. Dobbiamo creare 11 componenti della struttura.

   ![](assets/structure-components-migration.png)

### Inserimento di componenti di contenuto HTML

1. Inserisci un **[!UICONTROL HTML component]** in ogni **[!UICONTROL Structure component]** .

   ![](assets/html-components.png)

1. Per ciascuna sezione, fai clic su **[!UICONTROL Show source code]** .

   ![](assets/show-source-code.png)

1. Inserisci la sezione HTML.

1. Fai clic su **[!UICONTROL Save]**.

Ora puoi controllare il rendering della tua e-mail.

![](assets/migrated-email-result.png)

### Gestione degli stili per adattarli alla visualizzazione mobile

1. Inserisci elementi CSS per assicurarti che l’e-mail sia adatta alla visualizzazione mobile.

1. Passa al codice sorgente e copia e incolla la sezione stile in una nuova sezione stile.

Per ulteriori informazioni, consulta [Gestire lo stile dell’e-mail](#manage-the-style-of-your-email).

L’e-mail legacy è ora disponibile in E-mail Designer.