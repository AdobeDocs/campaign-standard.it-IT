---
title: Informazioni sul Connettore dati di Adobe Experience Platform
description: Gestisci gli schemi XDM per rendere i dati Campaign Standard disponibili su Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: f4fcf256-e030-4d7b-b4b7-2448acc2ae1c
hide: true
hidefromtoc: true
source-git-commit: 376f00576ca1d0dfb536b29dbf25d88f7c93b9a8
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 4%

---

# Informazioni sul Connettore dati di Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>Connettore dati Adobe Experience Platform è ora obsoleto. Le funzionalità obsolete sono ancora disponibili, ma non vengono ulteriormente migliorate né supportate. Per ulteriori informazioni, consulta [questa pagina](../../rn/using/deprecated-features.md)

Il connettore dati di Adobe Experience Platform aiuta i clienti esistenti a rendere i propri dati disponibili su Adobe Experience Platform mappando i dati XTK (dati acquisiti in Campaign) su Experience Data Model (XDM) in Adobe Experience Platform.

Il connettore è **unidirezionale** e invia i dati da Adobe Campaign Standard a Adobe Experience Platform. I dati non vengono mai inviati da Adobe Experience Platform ad Adobe Campaign Standard.

Connettore dati Adobe Experience Platform è destinato a **data engineer** che conoscono le risorse personalizzate di Adobe Campaign Standard e sanno come lo schema generale dei dati del cliente deve trovarsi all’interno di Adobe Experience Platform.

Le sezioni seguenti descrivono i passaggi chiave per eseguire una mappatura dei dati tra Campaign Standard e Adobe Experience Platform. Ciò inizia con la creazione di uno schema XDM e un set di dati.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

>[!NOTE]
>Dopo aver configurato il connettore dati di Adobe Experience Platform e aver acquisito correttamente i dati in Adobe Experience Platform, devi abilitare il set di dati in modo che vengano inclusi nel profilo cliente in tempo reale.
>
>Questa operazione può essere eseguita tramite le API o l’interfaccia di Adobe Experience Platform. Per ulteriori informazioni, consulta la documentazioni dedicata:
>
>* [Abilitare un set di dati per Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurare un set di dati per Real-time Customer Profile e Identity Service tramite API](https://experienceleague.adobe.com/docs/experience-platform/catalog/api/getting-started.html)

## Concetti chiave {#key-concepts}

* La mappatura out-of-the-box è disponibile solo per i campi forniti in Campaign Standard per impostazione predefinita. Per acquisire tutti i campi e le risorse personalizzati, ogni cliente deve definire la propria mappatura.

* Adobe Experience Platform Data Connector invia i dati del profilo tramite la piattaforma a intervalli regolari. &#x200B; La durata dell’intervallo è di 15 minuti. Questo valore può essere modificato tramite [API di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html).

* L’ingegnere dati può pubblicare, modificare e mettere in pausa la mappatura da Campaign a Adobe Experience Platform.

* È possibile mappare qualsiasi dimensione di targeting. Si consiglia di avere un’unica mappatura per tutti i campi in un’unica dimensione di targeting.

* Tutti gli aggiornamenti del profilo, inclusi i consensi/rinunce per il canale, fanno parte dell’aggiornamento batch.

* Qualsiasi modifica allo schema Adobe Campaign Standard o XDM deve essere rimappata manualmente. &#x200B;

* I dati del registro di tracciamento e del Broadlog vengono acquisiti automaticamente in Adobe Experience Platform come eventi di esperienza. Questa acquisizione viene trasmessa in streaming e in tempo reale a Adobe Experience Platform.

* Experience Cloud ID Service (ECID) è un identificatore di dispositivo che viene inviato per impostazione predefinita con Experience Events.

  Si tratta di un ID univoco e permanente assegnato a un visitatore, che può essere utilizzato dal servizio Platform Identity per identificare lo stesso visitatore e i relativi dati in diverse soluzioni di Experience Cloud. Per ulteriori informazioni, consulta [Guida del servizio Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).

  >[!NOTE]
  >
  >Tieni presente che, se due o più profili condividono lo stesso dispositivo, l’ECID sarebbe lo stesso per questi due profili nel servizio Unified Identity.

## Limitazioni {#limitations}

* Il trasferimento predefinito degli eventi di abbonamento non è supportato. Per trasferire gli eventi di abbonamento, puoi creare l’XDM e il set di dati corrispondenti in Adobe Experience Platform, quindi configurare una mappatura dei dati personalizzata per tali dati.

* Per quanto riguarda le richieste di privacy (sia le azioni di accesso che quelle di eliminazione), i clienti devono effettuare richieste separate tramite [Servizio core per la privacy](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): uno per Campaign e uno per Adobe Experience Platform. Per ulteriori informazioni, consulta [Informazioni sulle richieste di accesso a dati personali](https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=it#getting-started) e [Gestione delle richieste di accesso a dati personali](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) in Campaign.

* Per ogni campo XDM, l’etichettatura DULE deve essere eseguita in Adobe Experience Platform. È responsabilità del cliente applicare le etichette DULE.

* Le restrizioni sulle azioni di marketing diventano applicabili solo dopo l’applicazione delle etichette DULE in Adobe Experience Platform. In precedenza, tutti i dati erano disponibili per tutti i tipi di azioni di marketing.

* Ogni 15 minuti viene eseguito il processo batch che identifica i record modificati dall&#39;ultimo batch. Se tutti i record cambiano contemporaneamente, potrebbe apparire un collo di bottiglia delle prestazioni che gestirà l’acquisizione di tutti i profili

## Video tutorial {#video}

Questo video offre una panoramica del connettore dati di Adobe Experience Platform.

>[!VIDEO](https://video.tv.adobe.com/v/27304?quality=12&captions=eng)

Sono disponibili altri video relativi al Connettore dati di Adobe Experience Platform [qui](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
