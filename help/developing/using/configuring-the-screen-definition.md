---
title: Configurazione della definizione dello schermo
seo-title: Configurazione della definizione dello schermo
description: Configurazione della definizione dello schermo
seo-description: Scopri come definire le nuove schermate di Adobe Campaign in base alla struttura dei dati delle risorse.
page-status-flag: never-activated
uuid: 40848197-b 1 a 0-4018-bfc 3-7 df 64 fb 83307
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: sviluppo
content-type: riferimento
topic-tags: adding-or-extending-a-resource
discoiquuid: 9 dabb 328-ac 0 c -49 fd -8996-8 d 56341 ee 7 ac
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b3291f7c0cbede6a3180ad4a4ab8a365720f5031

---


# Configuring the screen definition{#configuring-the-screen-definition}

Quando si crea una risorsa o si aggiungono nuovi campi a una risorsa esistente, è possibile definire la modalità di visualizzazione nell'interfaccia.

Questo passaggio non è obbligatorio in quanto sarà ancora in grado di compilare la risorsa e di accedere ai dati tramite flussi di lavoro, audience e REST API.

In the **[!UICONTROL Screen definition]** tab, you can:

* Aggiunta di accesso alla risorsa personalizzata nel riquadro di navigazione
* Personalizzare il modo in cui viene presentato l'elenco degli elementi che compongono la risorsa
* Definire il modo in cui visualizzare la visualizzazione dettagli di ogni elemento della risorsa

## Enabling access from the navigation menu {#enabling-access-from-the-navigation-menu}

Se desiderate che la risorsa abbia una schermata dedicata, potete renderla disponibile dal menu di navigazione.

1. From the **[!UICONTROL Screen definition]** tab of the resource, unfold the **[!UICONTROL Navigation]** section.
1. Check the **[!UICONTROL Add an entry in the 'Client data' section]** box to allow access to this resource from the navigation pane.

   ![](assets/schema_extension_19.png)

The resource will appear as a sub-entry within the **[!UICONTROL Client data]** section.

## Defining the default list configuration {#defining-the-default-list-configuration}

The **[!UICONTROL List configuration]** section of the screen definition lets you define the columns and information that will be displayed by default in the overview of a resource.

1. Check the **[!UICONTROL Customize the list configuration]** box to define the way the columns of the resource are displayed.
1. Use the **[!UICONTROL Create element]** button to select a field from those that you have created.
1. Il campo creato viene visualizzato nell'elenco. Potete modificarne l'etichetta e la larghezza.

   ![](assets/schema_extension_20.png)

1. In the **[!UICONTROL Simple search]** section, check the **[!UICONTROL Specify the fields to be taken into account in the search]** to define which fields will be included in the search.

   >[!CAUTION]
   >
   >Questa configurazione sostituisce i campi utilizzati nella ricerca predefinita.

1. In the **[!UICONTROL Advanced filtering]** section, check the **[!UICONTROL Add search fields]** box to add additional fields beyond the simple search field. Ad esempio, se si seleziona il campo "data" dai campi creati, l'utente sarà in grado di eseguire una ricerca che fa riferimento solo alla data.
1. È possibile modificare l'ordine dei campi per i due tipi di ricerca.
1. Per una ricerca avanzata, potete aggiungere campi che collegino a una risorsa collegata. These filters appear in the **[!UICONTROL Search]** menu of the generated screen.

La schermata panoramica della risorsa è ora definita.

## Defining the detail screen configuration {#defining-the-detail-screen-configuration}

The **[!UICONTROL Detail screen configuration]** section of the screen definition lets you define the columns and information that will be displayed in the detail screen of each element of the resource.

1. Unfold the **[!UICONTROL Detail screen configuration]** section and check the **[!UICONTROL Define a detail screen]** to configure the screen that corresponds to each element of the resource. Se non selezionate questa casella, la visualizzazione dettagli degli elementi di questa risorsa non sarà accessibile.
1. Puoi aggiungere tutti i campi dalla risorsa personalizzata con un solo clic. To do this, click the ![](assets/addallfieldsicon.png) icon or use the **[!UICONTROL Add an element]** button.
1. Selezionate un elemento da quelli creati per questa risorsa e specificate un tipo di campo:

   * **[!UICONTROL Input field]**: è un campo modificabile.
   * **[!UICONTROL Value]**: è un campo di sola lettura.
   * **[!UICONTROL List]**: è una tabella.
   * **[!UICONTROL Separator]**: divide gli elementi in categorie.
   ![](assets/schema_extension_23.png)

1. L'elemento aggiunto viene visualizzato nell'elenco. È possibile modificare l'etichetta.

   ![](assets/schema_extension_22.png)

1. Add as many **[!UICONTROL Separator]** as needed to split your elements into different categories.

   Questo consente di visualizzare il separatore in modo da organizzare meglio le finestre.

   ![](assets/schema_extension_25.png)

La schermata dei dettagli della risorsa è ora configurata.

## Actions on data section {#actions-on-data-section}

Queste impostazioni consentono di visualizzare una barra di controllo nella schermata delle risorse personalizzate. Sono disponibili tre opzioni:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: questa opzione consente di attivare la creazione di elementi della risorsa. L'utente può quindi aggiungere record aggiuntivi.

   >[!NOTE]
   >
   >È prima necessario attivare la schermata dei dettagli collegata alla risorsa per rendere disponibile questa opzione.

* **[!UICONTROL Authorize duplicating]**: questa opzione consente di attivare la duplicazione dei record collegati alla risorsa personalizzata.
* **[!UICONTROL Authorize deleting]**: questa opzione consente di attivare l'eliminazione di record collegati alla risorsa personalizzata.

