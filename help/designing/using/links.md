---
title: Gestione dei collegamenti
seo-title: Gestione dei collegamenti
description: 'Gestione dei collegamenti '
seo-description: Scoprite come gestire i collegamenti con e-mail Designer.
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
source-git-commit: 1ccea1d142f0b1550c8891b2f31233af8c9d4e29

---


# Collegamenti {#links}

## Inserimento di un collegamento {#inserting-a-link}

L'editor consente di personalizzare un'e-mail o una pagina di destinazione inserendo collegamenti negli elementi di contenuto HTML.

Puoi inserire un collegamento in qualsiasi elemento di pagina: immagine, parola, gruppo di parole, blocco di testo, ecc.

>[!NOTE]
>
>Le immagini seguenti mostrano come inserire un collegamento tramite [Email Designer](../../designing/using/overview.md) in un messaggio e-mail.

1. Selezionate un elemento e fate clic **[!UICONTROL Insert link]** sulla barra degli strumenti contestuale.

   ![](assets/des_insert_link.png)

1. Scegliete il tipo di collegamento che desiderate creare:

   * **Collegamento** esterno: inserite un collegamento a un URL esterno.

      Puoi definire la personalizzazione per i tuoi URL. Consultate [Personalizzazione degli URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Pagina** di destinazione: consente di accedere a una pagina di destinazione di Adobe Campaign.
   * **Collegamento** iscrizione: inserite un collegamento per iscrivervi a un servizio Adobe Campaign.
   * **Collegamento** di annullamento sottoscrizione: inserite un collegamento per annullare l'iscrizione a un servizio Adobe Campaign.
   * **Collegamento che definisce un’azione**: definire un'azione quando si fa clic su un elemento nella pagina di destinazione.

      >[!NOTE]
      >
      >Questo tipo di collegamento è disponibile solo per le pagine di destinazione.

1. È possibile modificare il testo visualizzato al destinatario.
1. Potete impostare il comportamento del browser quando l'utente fa clic sul collegamento (ad esempio, apri una nuova finestra).

   >[!NOTE]
   >
   >La definizione del comportamento del browser si applica solo alle pagine di destinazione.

1. Salvare le modifiche.

Una volta creato il collegamento, puoi comunque modificarlo dal riquadro Impostazioni. Fate clic sull’icona matita per modificarne i parametri.

![](assets/des_link_edit.png)

Quando si modifica un'e-mail con [Email Designer](../../designing/using/overview.md), è possibile accedere e modificare facilmente i collegamenti creati dalla tabella, elencando tutti gli URL inclusi nell'e-mail. Questo elenco consente di avere una vista centralizzata e di individuare ogni URL nel contenuto dell’e-mail. Per accedervi, consultate [Informazioni sugli URL](#about-tracked-urls)tracciati.

![](assets/des_link_list.png)

>[!NOTE]
>
>Impossibile modificare da questo elenco gli URL personalizzati, ad esempio URL **di pagina** Mirror o collegamento **Annulla iscrizione** . Tutti gli altri collegamenti sono modificabili.

**Argomenti** correlati:

* [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Aggiunta di blocchi di contenuto](../../designing/using/personalization.md#adding-a-content-block)
* [Definizione del contenuto dinamico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Informazioni sugli URL tracciati {#about-tracked-urls}

Adobe Campaign consente di monitorare il comportamento dei destinatari quando fanno clic su un URL incluso in un messaggio e-mail. Per ulteriori informazioni sul tracciamento, consulta [questa sezione](../../sending/using/tracking-messages.md#about-tracking).

L' **[!UICONTROL Links]** icona nella barra delle azioni visualizza automaticamente l'elenco di tutti gli URL del contenuto che verranno tracciati.

![](assets/des_links.png)

>[!NOTE]
>
>Il tracciamento è attivato per impostazione predefinita. Questa funzionalità è disponibile solo per le e-mail, se il tracciamento è stato attivato in Adobe Campaign. Per ulteriori informazioni sui parametri di tracciamento, consulta [questa sezione](../../administration/using/configuring-email-channel.md#tracking-parameters).

L'URL, la categoria, l'etichetta e il tipo di tracciamento di ciascun collegamento possono essere modificati da questo elenco. Per modificare un collegamento, fai clic sull’icona matita corrispondente.

![](assets/des_links_tracking.png)

Per ciascun URL tracciato, potete impostare la modalità di tracciamento su uno dei seguenti valori:

* **Tracciato**: attiva il tracciamento su questo URL.
* **Mirror page**: considera questo URL come un URL della pagina mirror.
* **Mai**: non attiva mai il tracciamento di questo URL. Queste informazioni vengono salvate: se l’URL viene nuovamente visualizzato in un messaggio futuro, il tracciamento viene disattivato automaticamente.
* **Rifiuto**: considera questo URL come un URL di rinuncia o di annullamento dell’iscrizione.

![](assets/des_link_tracking_type.png)

Potete inoltre disattivare o attivare il tracciamento per ogni URL.

>[!NOTE]
>
>Per impostazione predefinita in Adobe Campaign, tutti gli URL del contenuto vengono tracciati, ad eccezione dell'URL **della pagina** Mirror e del collegamento **Annulla sottoscrizione** .

Potete raggruppare gli URL modificando il **[!UICONTROL Category]** campo, a seconda degli URL utilizzati nel messaggio. Queste categorie possono essere visualizzate come rapporti, ad esempio negli [URL e nei flussi](../../reporting/using/urls-and-click-streams.md)di clic.

![](assets/des_link_tracking_category.png)

Durante la creazione di un rapporto, dalla **[!UICONTROL Components]** scheda selezionare **[!UICONTROL Dimension]** e scorrere l'elenco verso il basso per accedere ai componenti di tracciamento. Ad esempio, trascinate **[!UICONTROL Tracking URL Category]** nell’area di lavoro per visualizzare i risultati in base alla categoria di tracciamento di ciascun URL su cui avete fatto clic.

![](assets/des_link_tracking_report.png)

Per ulteriori informazioni sulla creazione di rapporti personalizzati, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).
