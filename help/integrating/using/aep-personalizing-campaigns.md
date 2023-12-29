---
title: Personalizzazione di campagne tramite gli attributi di Adobe Experience Platform
description: Scopri come personalizzare le campagne utilizzando gli attributi di Adobe Experience Platform.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 4d4e7e58-e161-4e5a-898a-b5c29ffb20e0
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 6%

---

# Personalizzazione di campagne tramite gli attributi di Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta, e potrebbe essere soggetto ad aggiornamenti frequenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Contatta l’Assistenza clienti di Adobe se desideri accedervi.
>
>**Push** e **In-app** i canali non sono ancora disponibili per la personalizzazione utilizzando i dati contestuali di Adobe Experience Platform.

Una volta configurato il flusso di lavoro con [Pubblico Adobe Experience Platform](../../integrating/using/aep-about-audience-destinations-service.md), puoi personalizzare i messaggi con gli attributi del profilo presenti esclusivamente nel Experience Data Model (XDM).

A questo scopo, devi aggiungere questi attributi al **[!UICONTROL Read audience]** attività:

1. Apri **[!UICONTROL Read audience]** attività. In **[!UICONTROL Additional data]** , fare clic sulla scheda **[!UICONTROL Create element]** pulsante.

   Tieni presente che **[!UICONTROL Additional data]** è disponibile solo dopo la selezione di un pubblico di Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >I tipi di dati array e mappa non sono supportati in questa funzione. Inoltre, nel selettore verranno visualizzati solo i dati dello schema di unione.

1. Seleziona il campo XDM desiderato dall’elenco, quindi fai clic su **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Fai clic su **[!UICONTROL Add]** per aggiungerlo all’elenco dei dati aggiuntivi.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Ripeti questi passaggi per ogni campo XDM da aggiungere al flusso di lavoro.

   >[!NOTE]
   >
   >È possibile aggiungere un massimo di 20 campi XDM in una **[!UICONTROL Read audience]** attività.

1. Una volta aggiunti tutti i campi, fai clic sul pulsante **[!UICONTROL Confirm]** per salvare le modifiche. Ora saranno disponibili per personalizzare le consegne.

Per ulteriori informazioni su come creare e personalizzare le consegne, consulta la documentazione di Campaign Standard:

* [Esplorazione dei canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Informazioni sulle attività del canale](../../automating/using/about-channel-activities.md)
* [Personalizzazione delle consegne](../../designing/using/personalization.md)
