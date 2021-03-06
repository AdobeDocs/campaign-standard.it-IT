---
title: Estensione degli abbonamenti a una risorsa dell’applicazione
description: Scopri come estendere l’abbonamento a una risorsa dell’applicazione
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 24%

---

# Estensione degli abbonamenti a una risorsa dell’applicazione{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, i dati degli attributi del profilo mobile inviati da dispositivi mobili sono memorizzati nella risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** che ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni. Per ulteriori informazioni sulle risorse personalizzate, consulta [questa pagina](../../developing/using/key-steps-to-add-a-resource.md).

Questa risorsa può essere estesa per raccogliere i dati che intendi inviare dal dispositivo mobile ad Adobe Campaign.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]**, quindi **[!UICONTROL Custom resources]**.
1. Fai clic su **[!UICONTROL Create]** e scegli la **[!UICONTROL Extend an existing resource]** opzione .
1. Seleziona la **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** fai clic su **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. In **[!UICONTROL Fields]** categoria **[!UICONTROL Data structure]** definisci i dati cliente che desideri recuperare dall’app mobile facendo clic sul pulsante **[!UICONTROL Add field]** pulsante .

   >[!NOTE]
   >
   >Se gestisci diverse applicazioni mobili, devono essere elencati tutti i campi utilizzati da tutte le applicazioni. La chiamata PII per la raccolta di iOS o Android definisce quali campi vengono acquisiti da ogni applicazione.

   ![](assets/in_app_personal_data.png)

1. Aggiungi un **[!UICONTROL Label]** e **[!UICONTROL ID]** al nuovo campo. Seleziona il campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. In **[!UICONTROL Link to profiles]** configura la chiave di riconciliazione utilizzata per collegare i profili dal database Adobe Campaign agli abbonati delle tue applicazioni, ad esempio l’e-mail.

   Per i messaggi in-app puoi definire una sola chiave di riconciliazione per tutte le tue app mobili.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e pubblica la risorsa personalizzata. Per ulteriori informazioni sulla pubblicazione di risorse personalizzate, consulta questo [page](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
