---
solution: Campaign Standard
product: campaign
title: Estensione degli abbonamenti a una risorsa dell’applicazione
description: null
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 25%

---


# Estensione degli abbonamenti a una risorsa dell’applicazione{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, i dati degli attributi del profilo mobile inviati da dispositivi mobili sono memorizzati nella risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** che ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni. Per ulteriori informazioni sulle risorse personalizzate, consultare [questa pagina](../../developing/using/key-steps-to-add-a-resource.md).

Questa risorsa può essere estesa per raccogliere i dati che si intende inviare dal dispositivo mobile a  Adobe Campaign.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]**, quindi **[!UICONTROL Custom resources]**.
1. Fare clic su **[!UICONTROL Create]** e scegliere l&#39;opzione **[!UICONTROL Extend an existing resource]**.
1. Selezionate la risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** e fate clic su **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Nella categoria **[!UICONTROL Fields]** della scheda **[!UICONTROL Data structure]**, definire i dati del cliente che si desidera recuperare dall&#39;applicazione mobile facendo clic sul pulsante **[!UICONTROL Add field]**.

   >[!NOTE]
   >
   >Se gestite diverse applicazioni mobili, devono essere elencati tutti i campi utilizzati da tutte le applicazioni. La chiamata PII per la raccolta di iOS o Android definisce i campi acquisiti da ciascuna applicazione.

   ![](assets/in_app_personal_data.png)

1. Aggiungete un **[!UICONTROL Label]** e un **[!UICONTROL ID]** al nuovo campo. Selezionare il campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. Nella categoria **[!UICONTROL Link to profiles]**, configurate la chiave di riconciliazione utilizzata per collegare i profili dal database Adobe Campaign  agli abbonati delle applicazioni, ad esempio l&#39;e-mail.

   Per i messaggi in-app puoi definire una sola chiave di riconciliazione per tutte le applicazioni mobili.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e pubblicate la risorsa personalizzata. Per ulteriori informazioni sulla pubblicazione di risorse personalizzate, fare riferimento a questa [pagina](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

