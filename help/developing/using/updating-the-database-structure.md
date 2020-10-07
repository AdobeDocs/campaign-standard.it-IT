---
title: Aggiornamento della struttura del database
description: Scopri come aggiornare il database di Adobe Campaign.
page-status-flag: never-activated
uuid: 6c802f4f-d298-4ca4-acdb-09f2ad3865b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 2448b126-66b8-4608-aa6c-8028fb1902a4
context-tags: deploy,main;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 100%

---


# Aggiornamento della struttura del database{#updating-the-database-structure}

Per rendere effettive le modifiche al modello dati e poterle utilizzare, devi aggiornare la struttura del database.

>[!NOTE]
>
>Le risorse personalizzate vengono aggiornate automaticamente durante gli aggiornamenti automatici eseguiti da Adobe.

## Pubblicazione di una risorsa personalizzata {#publishing-a-custom-resource}

Per applicare le modifiche eseguite sulle risorse, devi eseguire un aggiornamento del database.

>[!NOTE]
>
>Se viene modificato o eliminato un campo di una risorsa personalizzata utilizzata all’interno di un evento, l’evento corrispondente viene automaticamente annullato. Consulta [Configurazione della messaggistica transazionale](../../administration/using/configuring-transactional-messaging.md).

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]**, quindi **[!UICONTROL Publishing]**.
1. Per impostazione predefinita, è selezionata l’opzione **[!UICONTROL Determine modifications since the last publication]**, il che significa che vengono applicate solo le modifiche eseguite dall’ultimo aggiornamento.

   >[!NOTE]
   >
   >Se la pubblicazione non è riuscita prima del completamento, **[!UICONTROL Repair database structure]** ristabilisce la configurazione corretta. Saranno eliminate eventuali modifiche eseguite direttamente nel database e non tramite l’utilizzo di risorse personalizzate.

   ![](assets/schema_extension_12.png)

1. Fai clic sul pulsante **[!UICONTROL Prepare publication]** per avviare l’analisi. Tieni presente che gli aggiornamenti cospicui delle tabelle devono essere eseguiti quando l’istanza non è completamente occupata dai flussi di lavoro.

   Per ulteriori informazioni sull’azione da eseguire nell’API Profiles &amp; Services API, consulta [Pubblicazione di una risorsa con estensione API](#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Una volta effettuata la pubblicazione, fai clic sul pulsante **[!UICONTROL Publish]** per applicare le nuove configurazioni.
1. Dopo la pubblicazione, il riquadro **[!UICONTROL Summary]** di ciascuna risorsa indica che adesso lo stato è **[!UICONTROL Published]** e specifica la data dell’ultima pubblicazione.

   >[!NOTE]
   >
   >Se apporti nuove modifiche a una risorsa, dovrai ripetere l’operazione per applicarle.

   Se prima della pubblicazione lo stato delle risorse è **[!UICONTROL Pending re-draft]**, verrà visualizzato un messaggio aggiuntivo che ti invita a controllare le azioni, poiché, dopo la pubblicazione, le modifiche saranno definitive (eliminazione di colonne, tabelle...). Per facilitare l’esecuzione di quest’ultima modifica, è disponibile una scheda **[!UICONTROL SQL Script]**. Tale scheda fornisce il comando SQL che verrà eseguito durante la pubblicazione.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >Per arrestare il processo di riprogettazione di una risorsa, fai clic sul pulsante **[!UICONTROL Cancel re-draft]**. Questa azione ripristina lo stato originale della risorsa.

1. Se la pubblicazione non è riuscita, puoi sempre tornare alla pubblicazione precedente facendo clic su **[!UICONTROL Back to latest successful publication]**.

   Se lasci la pubblicazione in uno stato di errore, non appena accedi all’istanza viene visualizzato un pop-up per ricordarti di correggere la pubblicazione. L’istanza non verrà aggiornata con le nuove versioni del prodotto finché la tua pubblicazione non sarà stata corretta.

   ![](assets/schema_extension_31.png)

## Pubblicazione di una risorsa con estensione API {#publishing-a-resource-with-api-extension}

Puoi creare l’API Profiles and Services nei seguenti casi:

* Quando estendi le risorse personalizzate **[!UICONTROL Profiles]** o **[!UICONTROL Services]**, puoi eseguire un aggiornamento dell’API Profiles and Services in modo da integrare i campi dichiarati nell’estensione delle risorse personalizzate.
* Quando definisci una risorsa personalizzata e crei un collegamento tra le risorse **[!UICONTROL Profiles]** o **[!UICONTROL Services]** e la risorsa personalizzata, puoi eseguire un aggiornamento per includere la nuova risorsa all’interno dell’API.

Puoi selezionare questa opzione nella schermata della pubblicazione.

* Se l’API non è ancora stata pubblicata, dunque non hai mai esteso la risorsa o se non hai ancora selezionato questa opzione per la risorsa in questione o per un’altra, puoi scegliere se crearla o meno.

   ![](assets/create-profile-and-services-api.png)

* Se l’API è già stata pubblicata, dunque hai già esteso la risorsa e hai già selezionato una volta questa opzione, viene forzato l’aggiornamento dell’API.

   Infatti, una volta creata, l’API viene automaticamente aggiornata a ogni nuova pubblicazione. In questo modo, si evita di interrompere la risorsa del profilo o del servizio di questa API, con conseguente danneggiamento dell’istanza.

Per impostazione predefinita, la risorsa personalizzata è integrata. Tuttavia, per un comportamento specifico, se non desideri pubblicare la risorsa, puoi selezionare l’opzione **[!UICONTROL Hide this resource from APIs]** disponibile nelle **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

Dopo il passaggio **[!UICONTROL Prepare Publication]**, Adobe Campaign visualizza nella scheda **[!UICONTROL Profiles & Services API Preview]** il delta tra la versione corrente dell’API e la versione futura successiva alla pubblicazione. Se estendi l’API per la prima volta, il delta confronta la definizione di risorsa personalizzata predefinita con l’estensione.

Le informazioni visualizzate nella scheda sono suddivise in tre sezioni: elementi aggiunti, eliminati e modificati.

![](assets/extendpandsapi_diff.png)

L’analisi del delta rappresenta un passaggio obbligatorio, poiché il passaggio della pubblicazione modificherà il comportamento dell’API e, molto probabilmente, influenzerà lo sviluppo circostante, in un effetto domino.

>[!NOTE]
>
>Questa pubblicazione aggiorna l’API **[!UICONTROL profilesAndServicesExt]**. L’API **[!UICONTROL profilesAndServices]** non è aggiornata.

Per ulteriori informazioni sull’API di Adobe Campaign, consulta la documentazione dedicata di Adobe Campaign su [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
