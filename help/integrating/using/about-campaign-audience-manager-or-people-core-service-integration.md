---
title: Informazioni sull’integrazione di Campaign con Audience Manager o il servizio core People
description: Con l’integrazione del servizio di base Audience Manager/People, puoi condividere audience o segmenti all’interno delle diverse soluzioni Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 18%

---

# Informazioni sull’integrazione di Campaign con Audience Manager o il servizio core People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>A seconda dei dati scambiati, l’importazione di tipi di pubblico in Adobe Campaign può essere soggetta a restrizioni legali.

Adobe Campaign consente di scambiare e condividere tipi di pubblico/segmenti con diverse applicazioni Adobe Experience Cloud. L&#39;integrazione di **Adobe Campaign** con il servizio core **People** (noto anche come servizio core **Profiles &amp; Audiences**) o Adobe Audience Manager consente di:

* Importa tipi di pubblico/segmenti da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. I tipi di pubblico possono essere importati dal menu **[!UICONTROL Audiences]** in Adobe Campaign.
* Esporta i tipi di pubblico come tipi di pubblico/segmenti condivisi. Questi tipi di pubblico possono essere utilizzati nelle diverse soluzioni Adobe Experience Cloud che utilizzi. I tipi di pubblico possono essere esportati dopo le attività di targeting in un flusso di lavoro, utilizzando l&#39;attività **[!UICONTROL Save audience]**.

L&#39;integrazione supporta due tipi di ID Adobe Experience Cloud:

* **ID visitatore**: questo tipo di ID consente di riconciliare i visitatori di Adobe Experience Cloud con i profili Adobe Campaign. Non appena viene abilitata una connessione tramite Adobe IMS, viene attivato il servizio ID visitatore del Marketing Cloud, che sostituisce il cookie permanente utilizzato da Adobe Campaign. Questo consente di identificare un visitatore e quindi collegarlo a un profilo.
  <br>Un ID visitatore viene collegato a un profilo non appena quest&#39;ultimo fa clic in un&#39;e-mail inviata tramite Adobe Campaign:
   * Se il profilo dispone già di un ID visitatore, i dati del browser del profilo consentono ad Adobe Campaign di recuperare e collegare automaticamente il profilo all’ID visitatore.
   * Se non viene trovato alcun ID visitatore, viene creato un nuovo ID. Questo ID visitatore viene memorizzato nei registri di tracciamento del profilo.

  L’ID verrà quindi riconosciuto dalle altre applicazioni Adobe Marketing Cloud con lo stesso CNAME.

* **ID dichiarato**: questo tipo di ID consente di riconciliare qualsiasi tipo di dati con gli elementi del database di Adobe Campaign. In Adobe Campaign è rappresentato come chiave di riconciliazione predefinita. Quando si scambiano dati, agli identificatori del database di Adobe Campaign viene applicato l’hash. Questi ID con hash vengono quindi confrontati con gli ID con hash del pubblico Adobe Marketing Cloud coinvolto nell’importazione o esportazione.
  <br>Questa integrazione supporta gli ID dichiarati regolari, gli ID dichiarati con hash e gli ID dichiarati crittografati.

  >[!NOTE]
  >
  >L’origine dati ID dichiarato ora piò essere utilizzata anche con l’integrazione del servizio core People.
  >
  >Se utilizzi l’integrazione con il servizio core People e desideri aggiungere l’integrazione con Audience Manager, ti servirà l’aiuto di un consulente Adobe Audience Manager per evitare di perdere tutte le sincronizzazioni ID raccolte durante la transizione all’utilizzo dell’origine dati ID dichiarato in un contesto Adobe Audience Manager.


  La crittografia consente di condividere dati crittografati in origini dati (ad esempio PII) utilizzando l’ID dichiarato specificando l’algoritmo di crittografia.

  Ad esempio, con la possibilità di decrittografare indirizzi e-mail o numeri SMS crittografati, puoi anche inviare messaggi attivati ai tuoi utenti anche se il loro profilo non esiste nel database di Adobe Campaign.

Il diagramma seguente illustra il funzionamento di questa integrazione. Qui AAM sta per Adobe Audience Manager e ACS per Adobe Campaign Standard.

![](assets/aam_diagram.png)
