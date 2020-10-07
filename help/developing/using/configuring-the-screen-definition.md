---
title: Configurazione della definizione della schermata
description: Scopri come definire nuove schermate di Adobe Campaign in base alla struttura dati delle risorse.
page-status-flag: never-activated
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 100%

---


# Configurazione della definizione della schermata{#configuring-the-screen-definition}

Quando crei una risorsa o aggiungi nuovi campi a una risorsa esistente, puoi definirne la modalità di visualizzazione nell’interfaccia.

Questo passaggio non è obbligatorio in quanto puoi comunque popolare la risorsa e accedere ai relativi dati tramite flussi di lavoro, tipi di pubblico e API REST.

Nella scheda **[!UICONTROL Screen definition]**, puoi:

* Aggiungere l’accesso alla risorsa personalizzata nel riquadro di navigazione
* Personalizzare il modo in cui viene presentato l’elenco degli elementi che compongono la risorsa
* Definire la modalità di visualizzazione dei dettagli di ciascun elemento della risorsa

## Abilitazione dell’accesso dal menu di navigazione {#enabling-access-from-the-navigation-menu}

Se desideri che la risorsa disponga di una schermata dedicata, puoi renderla disponibile dal menu di navigazione.

1. Dalla scheda **[!UICONTROL Screen definition]** della risorsa, apri la sezione **[!UICONTROL Navigation]**.
1. Seleziona la casella **[!UICONTROL Add an entry in the 'Client data' section]** per consentire l’accesso a questa risorsa dal riquadro di navigazione.

   ![](assets/schema_extension_19.png)

La risorsa verrà visualizzata come una voce secondaria all’interno della sezione **[!UICONTROL Client data]**.

## Definizione della configurazione di elenco predefinita {#defining-the-default-list-configuration}

La sezione **[!UICONTROL List configuration]** della definizione della schermata consente di definire le colonne e le informazioni che vengono visualizzate per impostazione predefinita nella panoramica di una risorsa.

1. Seleziona la casella **[!UICONTROL Customize the list configuration]** per definire la modalità di visualizzazione delle colonne della risorsa.
1. Utilizza il pulsante **[!UICONTROL Create element]** per selezionare un campo tra quelli creati.
1. Il campo creato viene visualizzato nell’elenco. Puoi modificarne l’etichetta e la larghezza.

   ![](assets/schema_extension_20.png)

1. Nella sezione **[!UICONTROL Simple search]**, seleziona **[!UICONTROL Specify the fields to be taken into account in the search]** per definire quali campi saranno inclusi nella ricerca.

   >[!IMPORTANT]
   >
   >Questa configurazione sostituisce i campi utilizzati nella ricerca predefinita.

1. Nella sezione **[!UICONTROL Advanced filtering]**, seleziona la casella **[!UICONTROL Add search fields]** per aggiungere campi aggiuntivi oltre al campo di ricerca semplice. Ad esempio, se selezioni il campo &quot;data&quot; dai campi creati, l’utente sarà in grado di eseguire una ricerca che si riferisce solo alla data.
1. Puoi modificare l’ordine dei campi per i due tipi di ricerca.
1. Per una ricerca avanzata, puoi aggiungere campi che si collegano a una risorsa collegata. Questi filtri vengono visualizzati nel menu **[!UICONTROL Search]** della schermata generata.

La schermata di panoramica della risorsa è ora definita.

## Definizione della configurazione della schermata di dettaglio {#defining-the-detail-screen-configuration}

La sezione **[!UICONTROL Detail screen configuration]** della definizione della schermata ti consente di definire le colonne e le informazioni che verranno visualizzate nella schermata di dettaglio di ciascun elemento della risorsa.

1. Apri la sezione **[!UICONTROL Detail screen configuration]** e seleziona **[!UICONTROL Define a detail screen]** per configurare la schermata corrispondente a ciascun elemento della risorsa. Se non selezioni questa casella, la visualizzazione dei dettagli degli elementi di questa risorsa non sarà accessibile.
1. Puoi aggiungere tutti i campi dalla risorsa personalizzata con un solo clic. A tale scopo, fai clic sull’icona ![](assets/addallfieldsicon.png) o utilizza il pulsante **[!UICONTROL Add an element]**.
1. Seleziona un elemento da quelli creati per la risorsa e specifica un tipo di campo:

   * **[!UICONTROL Input field]**: è un campo modificabile.
   * **[!UICONTROL Value]**: è un campo di sola lettura.
   * **[!UICONTROL List]**: è una tabella.
   * **[!UICONTROL Separator]**: divide gli elementi in categorie.

   ![](assets/schema_extension_23.png)

1. L’elemento aggiunto viene visualizzato nell’elenco. Puoi modificarne l’etichetta.

   ![](assets/schema_extension_22.png)

1. Aggiungi il numero necessario di **[!UICONTROL Separator]** per suddividere gli elementi in diverse categorie.

   Ciò consente di visualizzare un separatore per una migliore organizzazione delle finestre.

   ![](assets/schema_extension_25.png)

La schermata di dettaglio della risorsa è ora configurata.

## Azioni sulla sezione dati {#actions-on-data-section}

Queste impostazioni consentono di visualizzare una barra di controllo nella schermata delle risorse personalizzate. Sono disponibili tre opzioni:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: questa opzione consente di attivare la creazione di elementi della risorsa. L’utente può quindi aggiungere altri record.

   >[!NOTE]
   >
   >Per rendere disponibile questa opzione, devi innanzitutto attivare la schermata di dettaglio collegata alla risorsa.

* **[!UICONTROL Authorize duplicating]**: questa opzione consente di attivare la duplicazione dei record collegati alla risorsa personalizzata.
* **[!UICONTROL Authorize deleting]**: questa opzione consente di attivare l’eliminazione dei record collegati alla risorsa personalizzata.
