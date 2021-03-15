---
solution: Campaign Standard
product: campaign
title: Informazioni sull’integrazione di Campaign con Audience Manager o il servizio core People
description: Con l’integrazione del servizio core Audience Manager / Persone, puoi condividere tipi di pubblico o segmenti all’interno delle diverse soluzioni Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---


# Informazioni sull’integrazione di Campaign con Audience Manager o il servizio core People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>A seconda dei dati scambiati, l’importazione di tipi di pubblico in Adobe Campaign può essere soggetta a restrizioni legali.

Adobe Campaign consente di scambiare e condividere audience/segmenti con le diverse applicazioni Adobe Experience Cloud. L&#39;integrazione di **Adobe Campaign** con **il servizio core People** (noto anche come **Servizio di base Profili e pubblico**) o Adobe Audience Manager consente di:

* Importa tipi di pubblico/segmenti da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. I tipi di pubblico possono essere importati dal menu **[!UICONTROL Audiences]** in Adobe Campaign.
* Esporta i tipi di pubblico come tipi di pubblico/segmenti condivisi. Questi tipi di pubblico possono essere utilizzati nelle diverse soluzioni Adobe Experience Cloud che utilizzi. I tipi di pubblico possono essere esportati dopo le attività di targeting in un flusso di lavoro, utilizzando l’attività **[!UICONTROL Save audience]** .

L&#39;integrazione supporta due tipi di ID Adobe Experience Cloud:

* **ID** visitatore: questo tipo di ID consente di riconciliare i visitatori di Adobe Experience Cloud con i profili Adobe Campaign. Non appena una connessione viene abilitata tramite Adobe IMS, viene attivato il servizio ID visitatore di Marketing Cloud, che sostituisce il cookie permanente utilizzato da Adobe Campaign. Questo ti consente di identificare un visitatore e quindi collegarlo a un profilo.
   <br>Un ID visitatore viene collegato a un profilo non appena il profilo fa clic in un’e-mail inviata tramite Adobe Campaign:
   * Se il profilo ha già un ID visitatore, i dati del browser del profilo consentono ad Adobe Campaign di recuperare e collegare automaticamente il profilo all’ID visitatore.
   * Se non viene trovato alcun ID visitatore, viene creato un nuovo ID. Questo ID visitatore viene memorizzato nei registri di tracciamento del profilo.

   L&#39;ID verrà quindi riconosciuto dalle altre applicazioni Adobe Marketing Cloud con lo stesso CNAME.

* **ID** dichiarato: questo tipo di ID consente di riconciliare qualsiasi tipo di dati con gli elementi del database Adobe Campaign. È rappresentato in Adobe Campaign come chiave di riconciliazione predefinita. Durante lo scambio di dati, gli identificatori del database Adobe Campaign vengono crittografati. Questi ID con hash vengono quindi confrontati con gli ID con hash del pubblico Adobe Marketing Cloud coinvolto nell’importazione o nell’esportazione.
   <br>Questa integrazione supporta gli ID dichiarati regolari, gli ID dichiarati con hash e gli ID dichiarati crittografati.

   >[!CAUTION]
   >
   >L&#39;ID dichiarato funziona solo con Adobe Audience Manager. L&#39;ID dichiarato non funzionerà senza di esso.

   La cifratura consente di condividere i dati cifrati nelle origini dati (ad esempio PII) utilizzando l’ID dichiarato specificando l’algoritmo di cifratura.

   Ad esempio, con la possibilità di decrittografare indirizzi e-mail o numeri SMS crittografati, puoi anche inviare messaggi attivati agli utenti anche se il loro profilo non esiste nel database di Adobe Campaign.

Il diagramma seguente illustra il funzionamento di questa integrazione. Qui, AAM sta per Adobe Audience Manager e ACS per Adobe Campaign Standard.

![](assets/aam_diagram.png)