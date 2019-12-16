---
title: Informazioni sull’integrazione di Campaign-Audience Manager o del servizio di base Persone
description: Con l'integrazione dei servizi di base Audience Manager/Persone, puoi condividere audience o segmenti all'interno delle diverse soluzioni Adobe Experience Cloud.
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0062079addfbcd577faa1b16096f4588a05a8f78

---


# Informazioni sull’integrazione di Campaign-Audience Manager o del servizio di base Persone{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign consente di scambiare e condividere audience/segmenti con le diverse applicazioni Adobe Experience Cloud. L'integrazione di **Adobe Campaign** con il servizio **di base** Persone (noto anche come servizio **di base** Profili e pubblico) o Adobe Audience Manager consente di:

* Importa audience/segmenti da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. Le audience possono essere importate dal **[!UICONTROL Audiences]** menu in Adobe Campaign.
* Esporta audience come audience/segmenti condivisi. Queste audience possono essere utilizzate nelle diverse soluzioni Adobe Experience Cloud che utilizzi. Le audience possono essere esportate dopo attività di targeting in un flusso di lavoro, utilizzando l' **[!UICONTROL Save audience]** attività.

L'integrazione supporta due tipi di Adobe Experience Cloud ID:

* **ID** visitatore: questo tipo di ID consente di riconciliare i visitatori di Adobe Experience Cloud con i profili di Adobe Campaign.
* **ID** dichiarato: questo tipo di ID consente di riconciliare qualsiasi tipo di dati con i profili presenti nel database Adobe Campaign. Questa integrazione supporta ID dichiarati regolari, ID dichiarati con hash e ID dichiarati crittografati.

   La cifratura consente di condividere dati cifrati in origini dati (ad esempio PII) utilizzando l'ID dichiarato specificando l'algoritmo di cifratura.

   Ad esempio, con la capacità di decrittografare indirizzi e-mail o numeri SMS crittografati, puoi anche inviare messaggi attivati agli utenti anche se il loro profilo non esiste nel database di Adobe Campaign.

>[!CAUTION]
>
>A seconda dei dati scambiati, l'importazione di audience in Adobe Campaign potrebbe essere soggetta a restrizioni legali

