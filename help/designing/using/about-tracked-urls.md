---
title: Gli URL tracciati
seo-title: Gli URL tracciati
description: Gli URL tracciati
seo-description: Scoprite come gestire tutti gli URL del contenuto che verrà tracciato.
page-status-flag: never-activated
uuid: dfe 5146 b -5256-431 c -87 b 3-3 c 54817 eba 36
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: progettazione
content-type: riferimento
topic-tags: managing-links
discoiquuid: d 9 b 0 b 3 c 2-874 b -4 cb 4-bce 9-c 0194 a 19 f 25 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About tracked URLs{#about-tracked-urls}

Adobe Campaign consente di tenere traccia del comportamento dei destinatari quando fanno clic su un URL incluso in un messaggio e-mail. For more on tracking, see [this section](../../sending/using/tracking-messages.md#about-tracking).

The **[!UICONTROL Links]** icon in the action bar automatically displays the list of all the URLs of your content that will be tracked.

![](assets/des_links.png)

>[!NOTE]
>
>Il tracciamento è attivato per impostazione predefinita. Questa funzionalità è disponibile solo per le e-mail, se in Adobe Campaign è stato attivato il tracciamento. For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

L'URL, la categoria, l'etichetta e il tipo di tracciamento di ciascun collegamento possono essere modificati da questo elenco. Per modificare un collegamento, fate clic sulla corrispondente icona matita.

![](assets/des_links_tracking.png)

Per ogni URL tracciato, potete impostare la modalità di tracciamento su uno di questi valori:

* **Tracciamento**: attiva il tracciamento su questo URL.
* **Pagina speculare**: considera l'URL come URL di pagina speculare.
* **Mai**: non attiva mai il tracciamento dell'URL. Queste informazioni vengono salvate: se l'URL viene nuovamente visualizzato in un messaggio futuro, il tracciamento viene disattivato automaticamente.
* **Rinuncia**: considera questo URL come URL di annullamento o annullamento della sottoscrizione.

![](assets/des_link_tracking_type.png)

Potete anche disattivare o attivare il tracciamento per ogni URL.

>[!NOTE]
>
>By default in Adobe Campaign, all content URLs are tracked except **Mirror page URL** and **Unsubscription** link.

You can regroup your URLs by editing the **[!UICONTROL Category]** field, depending on the URLs used in the message. These categories can be displayed reports, as for example in [URLs and click streams](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

When building a report, from the **[!UICONTROL Components]** tab, select **[!UICONTROL Dimension]** and scroll down the list to access the tracking components. For example, drag and drop **[!UICONTROL Tracking URL Category]** into the workspace to display results according to the tracking category of each clicked URL.

![](assets/des_link_tracking_report.png)

For more on building customized reports, see [this section](../../reporting/using/about-dynamic-reports.md).
