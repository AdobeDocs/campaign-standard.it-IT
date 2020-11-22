---
solution: Campaign Standard
product: campaign
title: Personalizzazione di campagne tramite gli attributi di Adobe Experience Platform
description: Scopri come personalizzare le campagne utilizzando  attributi della piattaforma di esperienza Adobe.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 8%

---


# Personalizzazione di campagne tramite gli attributi di Adobe Experience Platform {#personalizing-campaigns-using-aep-attributes}

>[!IMPORTANT]
>
>Il servizio Destinazioni audience è attualmente in versione beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.
>
>**I canali push** e **in-app** non sono ancora disponibili per la personalizzazione utilizzando dati contestuali di Adobe Experience Platform.

Una volta configurato il flusso di lavoro con un pubblico [](../../audiences/using/aep-about-audience-destinations-service.md)Adobe Experience Platform, puoi personalizzare i messaggi con gli attributi di profilo disponibili esclusivamente in Experience Data Model (XDM).

A tal fine, è necessario aggiungere questi attributi all&#39; **[!UICONTROL Read audience]** attività:

1. Aprite l&#39; **[!UICONTROL Read audience]** attività. In the **[!UICONTROL Additional data]** tab, click the **[!UICONTROL Create element]** button.

   La **[!UICONTROL Additional data]** scheda è disponibile solo dopo che è stato selezionato un pubblico Adobe Experience Platform.

   ![](assets/aep_wkf_readaudience_attributes.png)

   >[!NOTE]
   >
   >I tipi di dati relativi a array e mappe non sono supportati in questa funzione. Inoltre, nel selettore verranno visualizzati solo i dati dello schema di unione.

1. Selezionare il campo XDM desiderato dall&#39;elenco, quindi fare clic su **[!UICONTROL Confirm]**.

   ![](assets/aep_wkf_readaudience_perso1.png)

1. Fare clic sul **[!UICONTROL Add]** pulsante per aggiungerlo all&#39;elenco di dati aggiuntivi.

   ![](assets/aep_wkf_readaudience_perso3.png)

1. Ripetete questi passaggi per ogni campo XDM che desiderate aggiungere al flusso di lavoro.

   >[!NOTE]
   >
   >Potete aggiungere un massimo di 20 campi XDM in un&#39; **[!UICONTROL Read audience]** attività.

1. Una volta aggiunti tutti i campi, fate clic sul **[!UICONTROL Confirm]** pulsante per salvare le modifiche. Ora saranno disponibili per personalizzare le consegne.

Per ulteriori informazioni su come creare e personalizzare le consegne, consulta la documentazione Campaign Standard:

* [Esplorazione dei canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Informazioni sulle attività dei canali](../../automating/using/about-channel-activities.md)
* [Personalizzazione delle consegne](../../designing/using/personalization.md)
