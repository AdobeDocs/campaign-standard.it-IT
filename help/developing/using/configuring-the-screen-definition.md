---
title: Configurazione della definizione della schermata
description: Scopri come definire nuove schermate di Adobe Campaign basate sulla struttura dei dati delle risorse.
page-status-flag: never-activated
uuid: 40848197-b1a0-4018-bfc3-7df64fb83307
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 9dabb328-ac0c-49fd-8996-8d56341ee7ac
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8852adb5edeb42eba1acf2911c988071104f1401

---


# Configurazione della definizione della schermata{#configuring-the-screen-definition}

Quando create una risorsa o aggiungete nuovi campi a una risorsa esistente, potete definire la modalità di visualizzazione nell’interfaccia.

Questo passaggio non è obbligatorio in quanto potrai comunque compilare la risorsa e accedere ai suoi dati tramite flussi di lavoro, audience e REST API.

Nella **[!UICONTROL Screen definition]** scheda è possibile:

* Aggiungere l&#39;accesso alla risorsa personalizzata nel riquadro di navigazione
* Personalizzare il modo in cui viene presentato l&#39;elenco degli elementi che compongono la risorsa
* Definire la modalità di visualizzazione dei dettagli di ciascun elemento della risorsa

## Abilitazione dell&#39;accesso dal menu di navigazione {#enabling-access-from-the-navigation-menu}

Se desiderate che la risorsa disponga di una schermata dedicata, potete renderla disponibile dal menu di navigazione.

1. Dalla **[!UICONTROL Screen definition]** scheda della risorsa, aprite la **[!UICONTROL Navigation]** sezione.
1. Selezionare la **[!UICONTROL Add an entry in the 'Client data' section]** casella per consentire l&#39;accesso a questa risorsa dal riquadro di navigazione.

   ![](assets/schema_extension_19.png)

La risorsa verrà visualizzata come una voce secondaria all&#39;interno della **[!UICONTROL Client data]** sezione.

## Definizione della configurazione di elenco predefinita {#defining-the-default-list-configuration}

La **[!UICONTROL List configuration]** sezione della definizione dello schermo consente di definire le colonne e le informazioni che verranno visualizzate per impostazione predefinita nella panoramica di una risorsa.

1. Selezionare la **[!UICONTROL Customize the list configuration]** casella per definire il modo in cui vengono visualizzate le colonne della risorsa.
1. Utilizzare il **[!UICONTROL Create element]** pulsante per selezionare un campo tra quelli creati.
1. Il campo creato viene visualizzato nell’elenco. Potete modificarne l’etichetta e la larghezza.

   ![](assets/schema_extension_20.png)

1. Nella **[!UICONTROL Simple search]** sezione, selezionare **[!UICONTROL Specify the fields to be taken into account in the search]** per definire i campi da includere nella ricerca.

   >[!IMPORTANT]
   >
   >Questa configurazione sostituisce i campi utilizzati nella ricerca predefinita.

1. Nella **[!UICONTROL Advanced filtering]** sezione, selezionare la **[!UICONTROL Add search fields]** casella per aggiungere altri campi oltre il campo di ricerca semplice. Ad esempio, se si seleziona il campo &quot;data&quot; dai campi creati, l&#39;utente sarà in grado di eseguire una ricerca che si riferisce solo alla data.
1. È possibile modificare l&#39;ordine dei campi per i due tipi di ricerca.
1. Per una ricerca avanzata, potete aggiungere campi che si collegano a una risorsa collegata. Questi filtri vengono visualizzati nel **[!UICONTROL Search]** menu dello schermo generato.

La schermata di panoramica della risorsa è ora definita.

## Definizione della configurazione della schermata di dettaglio {#defining-the-detail-screen-configuration}

La **[!UICONTROL Detail screen configuration]** sezione della definizione dello schermo consente di definire le colonne e le informazioni che verranno visualizzate nella schermata di dettaglio di ciascun elemento della risorsa.

1. Aprite la **[!UICONTROL Detail screen configuration]** sezione e verificate il **[!UICONTROL Define a detail screen]** pulsante per configurare la schermata corrispondente a ciascun elemento della risorsa. Se non selezionate questa casella, la visualizzazione dettagliata degli elementi di questa risorsa non sarà accessibile.
1. Puoi aggiungere tutti i campi dalla risorsa personalizzata con un solo clic. A tale scopo, fare clic sull&#39; ![](assets/addallfieldsicon.png) icona o utilizzare il **[!UICONTROL Add an element]** pulsante.
1. Selezionate un elemento da quelli creati per la risorsa e specificate un tipo di campo:

   * **[!UICONTROL Input field]**: è un campo modificabile.
   * **[!UICONTROL Value]**: è un campo di sola lettura.
   * **[!UICONTROL List]**: è un tavolo.
   * **[!UICONTROL Separator]**: divide gli elementi in categorie.
   ![](assets/schema_extension_23.png)

1. L’elemento aggiunto viene visualizzato nell’elenco. Potete modificarne l’etichetta.

   ![](assets/schema_extension_22.png)

1. Aggiungete il numero **[!UICONTROL Separator]** necessario per suddividere gli elementi in diverse categorie.

   Questo consente di visualizzare un separatore per organizzare meglio le finestre.

   ![](assets/schema_extension_25.png)

La schermata di dettaglio della risorsa è ora configurata.

## Azioni sulla sezione dei dati {#actions-on-data-section}

Queste impostazioni consentono di visualizzare una barra di controllo nella schermata delle risorse personalizzate. Sono disponibili tre opzioni:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: questa opzione consente di attivare la creazione di elementi della risorsa. L&#39;utente può quindi aggiungere altri record.

   >[!NOTE]
   >
   >Per rendere disponibile questa opzione, è innanzitutto necessario attivare la schermata dei dettagli collegata alla risorsa.

* **[!UICONTROL Authorize duplicating]**: questa opzione consente di attivare i record duplicati collegati alla risorsa personalizzata.
* **[!UICONTROL Authorize deleting]**: questa opzione consente di attivare l&#39;eliminazione di record collegati alla risorsa personalizzata.
