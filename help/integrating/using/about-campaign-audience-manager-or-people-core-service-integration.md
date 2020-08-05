---
title: Informazioni sull’integrazione di Campaign con Audience Manager o il servizio core People
description: Con l'integrazione del servizio di base  Audience Manager / Persone, potete condividere audience o segmenti all'interno delle diverse soluzioni Adobe Experience Cloud.
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
source-git-commit: 1e790f550f6eb84954f199caeda88a8fd90dfd85
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 3%

---


# Informazioni sull’integrazione di Campaign con Audience Manager o il servizio core People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>A seconda dei dati scambiati, l&#39;importazione di audience in  Adobe Campaign potrebbe essere soggetta a restrizioni legali.

 Adobe Campaign consente di scambiare e condividere audience/segmenti con le diverse applicazioni Adobe Experience Cloud. L’integrazione **Adobe Campaign** con il servizio **di base** Persone (noto anche come servizio **di base** Profili e pubblico) o Adobe Audience Manager consente di:

* Importa audience/segmenti da diverse soluzioni Adobe Experience Cloud in  Adobe Campaign. Le audience possono essere importate dal **[!UICONTROL Audiences]** menu in  Adobe Campaign.
* Esporta audience come audience/segmenti condivisi. Queste audience possono essere utilizzate nelle diverse soluzioni Adobe Experience Cloud che utilizzate. Le audience possono essere esportate dopo le attività di targeting in un flusso di lavoro, utilizzando l&#39; **[!UICONTROL Save audience]** attività.

L&#39;integrazione supporta due tipi di ID Adobe Experience Cloud:

* **ID**visitatore: questo tipo di ID consente di riconciliare i visitatori di Adobe Experience Cloud con  profili Adobe Campaign. Non appena una connessione viene abilitata tramite  Adobe IMS, viene attivato il servizio ID visitatori di Marketing Cloud, che sostituisce il cookie permanente utilizzato da  Adobe Campaign. Questo consente di identificare un visitatore e quindi di collegarlo a un profilo.
   <br>Un ID visitatore viene collegato a un profilo non appena il profilo fa clic in un messaggio e-mail inviato tramite  Adobe Campaign:
   * Se il profilo ha già un ID visitatore, i dati del browser del profilo consentono  Adobe Campaign di recuperare e collegare automaticamente il profilo all’ID visitatore.
   * Se non viene trovato alcun ID visitatore, viene creato un nuovo ID. Questo ID visitatore viene memorizzato nei registri di tracciamento del profilo.

   L’ID verrà quindi riconosciuto dalle altre applicazioni Adobe Marketing Cloud con lo stesso CNAME.

* **ID**dichiarato: questo tipo di ID consente di riconciliare qualsiasi tipo di dati con gli elementi del database Adobe Campaign . È rappresentata in  Adobe Campaign come chiave di riconciliazione predefinita. Durante lo scambio di dati, gli identificatori del database Adobe Campaign  vengono crittografati. Questi ID con hash vengono quindi confrontati con gli ID con hash del pubblico Adobe Marketing Cloud coinvolto nell&#39;importazione o nell&#39;esportazione.
   <br>Questa integrazione supporta ID dichiarati regolari, ID dichiarati con hash e ID dichiarati crittografati.

   >[!CAUTION]
   >
   >L&#39;ID dichiarato funzionerà solo con Adobe Audience Manager. L&#39;ID dichiarato non funzionerà senza di esso.

   La cifratura consente di condividere dati cifrati in origini dati (ad esempio PII) utilizzando l&#39;ID dichiarato specificando l&#39;algoritmo di cifratura.

   Ad esempio, con la possibilità di decrittografare indirizzi e-mail o numeri SMS crittografati, puoi anche inviare messaggi attivati agli utenti anche se il loro profilo non esiste nel database Adobe Campaign .

Nel diagramma seguente è illustrato il funzionamento di questa integrazione. Qui, AAM sta per Adobe Audience Manager et ACS per  Adobe Campaign Standard.

![](assets/aam_diagram.png)