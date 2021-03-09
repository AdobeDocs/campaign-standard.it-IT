---
solution: Campaign Standard
product: campaign
title: Personalizzazione di campagne tramite gli attributi di Adobe Experience Platform
description: Scopri come personalizzare le campagne utilizzando gli attributi di Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 35d61efce8d752ea30b7eaad55e6c23d4debd853
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---


# Personalizzazione di campagne tramite gli attributi di Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta e potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.
>
>**** I canali  **in-** Appchannels push non sono ancora disponibili per la personalizzazione utilizzando dati contestuali provenienti da Adobe Experience Platform.

Una volta configurato il flusso di lavoro con un [pubblico Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md), puoi personalizzare i messaggi con gli attributi di profilo esistenti esclusivamente in Experience Data Model (XDM).

A questo scopo, devi aggiungere questi attributi all’attività **[!UICONTROL Read audience]** :

1. Apri l’attività **[!UICONTROL Read audience]** . Nella scheda **[!UICONTROL Additional data]** , fai clic sul pulsante **[!UICONTROL Create element]** .

   La scheda **[!UICONTROL Additional data]** è disponibile solo dopo che è stato selezionato un pubblico Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >I tipi di dati relativi a array e mappe non sono supportati in questa funzione. Inoltre, nel selettore verranno visualizzati solo i dati dello schema di unione.

1. Seleziona il campo XDM desiderato dall’elenco, quindi fai clic su **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Fai clic sul pulsante **[!UICONTROL Add]** per aggiungerlo all’elenco dei dati aggiuntivi.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Ripeti questi passaggi per ogni campo XDM che desideri aggiungere al flusso di lavoro.

   >[!NOTE]
   >
   >È possibile aggiungere un massimo di 20 campi XDM in un’attività **[!UICONTROL Read audience]**.

1. Una volta aggiunti tutti i campi, fai clic sul pulsante **[!UICONTROL Confirm]** per salvare le modifiche. Ora saranno disponibili per personalizzare le consegne.

Per ulteriori informazioni su come creare e personalizzare le consegne, consulta la documentazione di Campaign Standard:

* [Esplorazione dei canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Informazioni sulle attività dei canali](../../automating/using/about-channel-activities.md)
* [Personalizzazione delle consegne](../../designing/using/personalization.md)
