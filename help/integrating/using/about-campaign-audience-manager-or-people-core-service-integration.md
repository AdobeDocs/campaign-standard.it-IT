---
title: Informazioni sull'integrazione di Campaign-Audience Manager o di servizi di base
seo-title: Informazioni sull'integrazione di Campaign-Audience Manager o di servizi di base
description: Informazioni sull'integrazione di Campaign-Audience Manager o di servizi di base
seo-description: Con l'integrazione di Audience Manager/Persone, puoi condividere tipi di pubblico o segmenti all'interno delle diverse soluzioni Adobe Experience Cloud.
page-status-flag: never-activated
uuid: 39 e 3 c 78 e-cccd -4823-afe 9-abc 7 f 8 aef 034
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf 718329-f 181-46 f 7-80 a 2-b 525 a 8 dee 46 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Audience Manager or People core service integration{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign consente di scambiare e condividere tipi di pubblico/segmenti con le diverse applicazioni Adobe Experience Cloud. Integrating **Adobe Campaign** with **People core service** (also known as **Profiles &amp; Audiences core service**) or Adobe Audience Manager allows you to:

* Importa tipi di pubblico/segmenti da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. Audiences can be imported from the **[!UICONTROL Audiences]** menu in Adobe Campaign.
* Esportare audience come tipi di pubblico/segmenti condivisi. Queste audience possono essere utilizzate nelle diverse soluzioni Adobe Experience Cloud che utilizzi. Audiences can be exported after targeting activities in a workflow, using the **[!UICONTROL Save audience]** activity.

L'integrazione supporta due tipi di ID di Adobe Experience Cloud:

* **ID visitatore**: questo tipo di ID consente di riconciliare i visitatori di Adobe Experience Cloud con i profili Adobe Campaign.
* **ID dichiarato**: questo tipo di ID consente di riconciliare qualsiasi tipo di dati con profili nel database Adobe Campaign. Questa integrazione supporta ID regolari dichiarati, ID dichiarati con hash e ID dichiarati crittografati.

   La crittografia consente di condividere dati cifrati in origini dati (ad esempio PII) utilizzando l'ID dichiarato specificando l'algoritmo di cifratura.

   Ad esempio, con la possibilità di decifrare indirizzi e-mail o numeri SMS crittografati, puoi anche inviare messaggi attivati ai tuoi utenti anche se il loro profilo non esiste nel database Adobe Campaign.

>[!CAUTION]
>
>A seconda dei dati scambiati, l'importazione di audience in Adobe Campaign può essere soggetta a restrizioni legali

