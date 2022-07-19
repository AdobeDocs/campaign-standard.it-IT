---
title: Informazioni sul Connettore dati di Adobe Experience Platform
description: Gestisci gli schemi XDM per rendere disponibili i dati di Campaign Standard in Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 4%

---

# Informazioni sul Connettore dati di Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Adobe Experience Platform Data Connector aiuta i clienti esistenti a rendere i loro dati disponibili su Adobe Experience Platform mappando i dati XTK (dati acquisiti in Campaign) su Experience Data Model (XDM) su Adobe Experience Platform.

Il connettore è **unidirezionale** e invia i dati da Adobe Campaign Standard ad Adobe Experience Platform. I dati non vengono mai inviati da Adobe Experience Platform ad Adobe Campaign Standard.

Connettore dati Adobe Experience Platform è destinato a **data engineer** che conoscono le risorse personalizzate di Adobe Campaign Standard e conoscono lo schema generale dei dati del cliente all’interno di Adobe Experience Platform.

Le sezioni seguenti descrivono i passaggi chiave per eseguire una mappatura dei dati tra Campaign Standard e Adobe Experience Platform. Questo inizia con la creazione di uno schema XDM e un set di dati.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

>[!NOTE]
>Una volta configurato Adobe Experience Platform Data Connector e acquisito correttamente i dati in Adobe Experience Platform, devi abilitare il set di dati in modo che i dati siano inclusi nel Profilo cliente in tempo reale.
>
>Questa operazione può essere eseguita tramite le API o l’interfaccia di Adobe Experience Platform. Per ulteriori informazioni, consulta la documentazione dedicata:
>
>* [Abilitare un set di dati per il profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurare un set di dati per il profilo cliente in tempo reale e il servizio Identity utilizzando le API](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)


## Concetti chiave {#key-concepts}

* La funzione Mappatura casella è disponibile solo per i campi forniti in Campaign Standard per impostazione predefinita. Per acquisire tutti i campi e le risorse personalizzati, ogni cliente deve definire una propria mappatura.

* Adobe Experience Platform Data Connector invierà i dati del profilo attraverso la piattaforma a intervalli regolari. &#x200B; La durata dell&#39;intervallo è di 15 minuti. Questo valore può essere modificato utilizzando [API di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* L’ingegnere dei dati può pubblicare, modificare e mettere in pausa la mappatura da Campaign a Adobe Experience Platform.

* È possibile mappare qualsiasi dimensione di targeting. Si consiglia di avere una singola mappatura per tutti i campi in un’unica dimensione di targeting.

* Tutti gli aggiornamenti di profilo, incluse le rinunce e le Rinunce al canale, fanno parte dell&#39;aggiornamento batch.

* Eventuali modifiche allo schema Adobe Campaign Standard o XDM devono essere rimappate manualmente. &#x200B;

* I dati del registro di tracciamento e del registro di trasmissione vengono acquisiti automaticamente in Adobe Experience Platform come eventi di esperienza. Questa acquisizione viene trasmessa in tempo reale a Adobe Experience Platform.

* Il servizio Experience Cloud ID (ECID) è un identificatore del dispositivo inviato per impostazione predefinita con Eventi esperienza.

   Si tratta di un ID univoco e costante assegnato a un visitatore, che può essere utilizzato dal servizio Platform Identity per identificare lo stesso visitatore e i relativi dati in diverse soluzioni di Experience Cloud. Per ulteriori informazioni, consulta la sezione [Guida del servizio Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).

   >[!NOTE]
   >
   >Se due o più profili condividono uno stesso dispositivo, l’ECID sarà lo stesso per questi due profili nel servizio Unified Identity.

## Limitazioni {#limitations}

* Il trasferimento predefinito degli eventi di abbonamento non è supportato. Per trasferire gli eventi di abbonamento, puoi creare XDM e set di dati corrispondenti in Adobe Experience Platform, quindi configurare una mappatura dati personalizzata per questi dati.

* Per quanto riguarda le richieste di privacy (entrambe le azioni di accesso ed eliminazione), i clienti devono inserire richieste separate tramite la [Servizio core Privacy](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): uno per Campaign e uno per Adobe Experience Platform. Per ulteriori informazioni, consulta [Informazioni sulle richieste di privacy](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=it#getting-started) e [Gestione delle richieste di privacy](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) in Campaign.

* Per ogni campo XDM, l’etichettatura DULE deve essere eseguita in Adobe Experience Platform. È responsabilità del cliente applicare le etichette DULE.

* Le restrizioni alle azioni di marketing diventano applicabili solo dopo l’applicazione delle etichette DULE in Adobe Experience Platform. Prima di questo passaggio, tutti i dati sono disponibili per tutti i tipi di azioni di marketing.

* Ogni 15 minuti, il processo batch è in esecuzione e identifica i record che sono cambiati dall&#39;ultimo batch. Se tutti i record cambiano allo stesso timestamp, potrebbe apparire un collo di bottiglia delle prestazioni per gestire l’acquisizione di tutti i profili

## Video tutorial {#video}

Questo video fornisce una panoramica su Adobe Experience Platform Data Connector.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Sono disponibili altri video relativi al Connettore dati di Adobe Experience Platform [qui](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
