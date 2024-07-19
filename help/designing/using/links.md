---
title: Aggiunta di collegamenti
description: Scopri come gestire i collegamenti con E-mail Designer.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d1714101-bad0-40c1-8d60-90469d033197
source-git-commit: 146dfea38bd456a5d9200b0632d4aa279b10a7b9
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 4%

---

# Aggiunta di collegamenti {#links}

## Inserimento di un collegamento {#inserting-a-link}

L’editor ti consente di personalizzare un’e-mail o una pagina di destinazione inserendo collegamenti negli elementi di contenuto HTML.

Puoi inserire un collegamento in qualsiasi elemento della pagina: immagine, parola, gruppo di parole, blocco di testo, ecc.

>[!NOTE]
>
>Nelle immagini seguenti viene illustrato come inserire un collegamento utilizzando [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md) in un messaggio e-mail.

1. Selezionare un elemento e fare clic su **[!UICONTROL Insert link]** nella barra degli strumenti contestuale.

   ![](assets/des_insert_link.png)

1. Scegli il tipo di collegamento da creare:

   * **Collegamento esterno**: inserire un collegamento a un URL esterno.

     Puoi definire la personalizzazione per i tuoi URL. Consulta [Personalizzazione degli URL](personalization.md#personalizing-urls).

   * **Pagina di destinazione**: consente di accedere a una pagina di destinazione di Adobe Campaign.
   * **Collegamento di abbonamento**: inserisci un collegamento per effettuare l&#39;abbonamento a un servizio Adobe Campaign.
   * **Collegamento per annullare l&#39;abbonamento**: inserisci un collegamento per annullare l&#39;abbonamento a un servizio Adobe Campaign.
   * **Collegamento che definisce un&#39;azione**: definisce un&#39;azione quando si fa clic su un elemento nella pagina di destinazione.

     >[!NOTE]
     >
     >Questo tipo di collegamento è disponibile solo per le pagine di destinazione.

1. Puoi modificare il testo visualizzato al destinatario.
1. Puoi impostare il comportamento del browser quando l’utente fa clic sul collegamento (ad esempio, per aprire una nuova finestra).

   >[!NOTE]
   >
   >La definizione del comportamento del browser si applica solo alle pagine di destinazione.

1. Salva le modifiche.

Una volta creato il collegamento, puoi comunque modificarlo dal riquadro Impostazioni. Fai clic sull’icona della matita per modificarne i parametri.

![](assets/des_link_edit.png)

Quando modifichi un&#39;e-mail con [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md), puoi facilmente accedere e modificare i collegamenti creati dalla tabella in cui sono elencati tutti gli URL inclusi nell&#39;e-mail. Questo elenco ti consente di avere una vista centralizzata e di individuare ogni URL nel contenuto dell’e-mail. Per accedervi, vedi [Informazioni sugli URL tracciati](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>Gli URL personalizzati come **URL pagina mirror** o **collegamento per annullare l&#39;abbonamento** non possono essere modificati da questo elenco. Tutti gli altri collegamenti sono modificabili.

**Argomenti correlati**:

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di blocchi di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione del contenuto dinamico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Informazioni sugli URL tracciati {#about-tracked-urls}

Adobe Campaign consente di tenere traccia del comportamento dei destinatari che fanno clic su un URL incluso in un’e-mail. Per ulteriori informazioni sul tracciamento, consulta [questa sezione](../../sending/using/tracking-messages.md#about-tracking).

L&#39;icona **[!UICONTROL Links]** nella barra delle azioni visualizza automaticamente l&#39;elenco di tutti gli URL del contenuto che verranno tracciati.

![](assets/des_links.png)

>[!NOTE]
>
>Il tracciamento è attivato per impostazione predefinita. Questa funzionalità è disponibile solo per le e-mail, se il tracciamento è stato attivato in Adobe Campaign. Per ulteriori informazioni sui parametri di tracciamento, consulta [questa sezione](../../administration/using/configuring-email-channel.md#tracking-parameters).

L’URL, la categoria, l’etichetta e il tipo di tracciamento di ciascun collegamento possono essere modificati da questo elenco. Per modificare un collegamento, fai clic sull’icona a forma di matita corrispondente.

![](assets/des_links_tracking.png)

Per ogni URL tracciato, puoi impostare la modalità di tracciamento su uno dei seguenti valori:

* **Tracciato**: attiva il tracciamento su questo URL.
* **Pagina mirror**: considera questo URL come un URL di pagina mirror.
* **Mai**: non attiva mai il tracciamento di questo URL. Queste informazioni vengono salvate: se l’URL viene nuovamente visualizzato in un messaggio futuro, il suo tracciamento viene disattivato automaticamente.
* **Rinuncia**: considera questo URL come URL di rinuncia o di annullamento dell&#39;abbonamento.

![](assets/des_link_tracking_type.png)

Puoi anche disattivare o attivare il tracciamento per ogni URL.

>[!NOTE]
>
>Per impostazione predefinita, in Adobe Campaign, tutti gli URL di contenuto vengono tracciati tranne **URL pagina mirror** e **collegamento di annullamento sottoscrizione**.

È possibile raggruppare gli URL modificando il campo **[!UICONTROL Category]**, a seconda degli URL utilizzati nel messaggio. Queste categorie possono essere visualizzate nei rapporti, ad esempio in [URL e flussi di clic](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

Durante la creazione di un report, dalla scheda **[!UICONTROL Components]**, selezionare **[!UICONTROL Dimension]** e scorrere l&#39;elenco per accedere ai componenti di tracciamento. Ad esempio, trascina **[!UICONTROL Tracking URL Category]** nell&#39;area di lavoro per visualizzare i risultati in base alla categoria di tracciamento di ciascun URL su cui hai fatto clic.

![](assets/des_link_tracking_report.png)

Per ulteriori informazioni sulla creazione di report personalizzati, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).
