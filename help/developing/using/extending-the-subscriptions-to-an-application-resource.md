---
title: Estensione delle sottoscrizioni a una risorsa dell’applicazione
description: null
page-status-flag: mai attivato
uuid: 8879b427-b31b-4311-bf54-258a91b1fb78
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: development
content-type: reference
topic-tags: casi di utilizzo—estensione delle risorse
discoiquuid: 59faa74e-86fc-42d3-90da-f48580b5ec13
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Estensione delle sottoscrizioni a una risorsa dell’applicazione{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers. Per ulteriori informazioni sulle risorse personalizzate, consultate questa [pagina](../../developing/using/key-steps-to-add-a-resource.md).

Questa risorsa può essere estesa per raccogliere i dati che si intende inviare dal dispositivo mobile ad Adobe Campaign.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, quindi **[!UICONTROL Custom resources]**.
1. Fate clic **[!UICONTROL Create]** e scegliete l’ **[!UICONTROL Extend an existing resource]** opzione.
1. Selezionate la **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** risorsa e fate clic su **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Nella **[!UICONTROL Fields]** categoria della **[!UICONTROL Data structure]** scheda, definite i dati cliente che desiderate recuperare dall'applicazione mobile facendo clic sul **[!UICONTROL Add field]** pulsante.

   >[!NOTE]
   >
   >Se gestite diverse applicazioni mobili, devono essere elencati tutti i campi utilizzati da tutte le applicazioni. La chiamata PII per la raccolta di iOS o Android definisce i campi acquisiti da ciascuna applicazione.

   ![](assets/in_app_personal_data.png)

1. Aggiungere un **[!UICONTROL Label]** e un **[!UICONTROL ID]** campo al nuovo campo. Seleziona il campo **[!UICONTROL Type]**.

   ![](assets/schema_extension_uc9.png)

1. Nella **[!UICONTROL Link to profiles]** categoria, configura la chiave di riconciliazione utilizzata per collegare i profili dal database di Adobe Campaign agli abbonati delle tue applicazioni, come l'e-mail.

   Per i messaggi in-app puoi definire una sola chiave di riconciliazione per tutte le applicazioni mobili.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e pubblicate la risorsa personalizzata. Per ulteriori informazioni sulla pubblicazione di risorse personalizzate, consultate questa [pagina](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

