---
title: Informazioni su Adobe Experience Platform Data Connector
description: Gestisci schemi XDM per rendere disponibili i dati di Campaign Standard su Adobe Experience Platform.
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 327d0e4f862b39c60fb3943d1128f4f42828bc0d

---


# Informazioni su Adobe Experience Platform Data Connector {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta l&#39;Assistenza clienti Adobe.

Adobe Experience Platform Data Connector aiuta i clienti esistenti a rendere disponibili i loro dati su Adobe Experience Platform mappando i dati XTK (i dati acquisiti in Campaign) su dati XDM (Experience Data Model) in Adobe Experience Platform.

Il connettore è **unidirezionale** e invia i dati da Adobe Campaign Standard ad Adobe Experience Platform. I dati non vengono mai inviati da Adobe Experience Platform ad Adobe Campaign Standard.

Adobe Experience Platform Data Connector è destinato agli ingegneri **di** dati che conoscono le risorse personalizzate di Adobe Campaign Standard e che hanno un&#39;idea di come lo schema di dati complessivo del cliente dovrebbe essere all&#39;interno di Adobe Experience Platform.

Le sezioni seguenti descrivono i passaggi chiave per eseguire una mappatura dei dati tra Campaign Standard e Adobe Experience Platform. Questo inizia con la creazione di uno schema XDM e di un dataset.

I video dimostrativi sono disponibili anche in [questa pagina](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).

>[!NOTE]
>Una volta che Adobe Experience Platform Data Connector è configurato e i dati vengono correttamente assimilati in Adobe Experience Platform, è necessario abilitare il dataset in modo che i dati vengano inclusi nel profilo cliente in tempo reale.
>
>Questa operazione può essere eseguita tramite le API o l&#39;interfaccia di Adobe Experience Platform. Per maggiori informazioni, consulta la documentazione dedicata:
>
>* [Abilita un set di dati per il profilo cliente in tempo reale](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurare un set di dati per il profilo cliente e il servizio identità in tempo reale mediante le API](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Concetti chiave {#key-concepts}

* La mappatura della casella è disponibile solo per i campi forniti in Campaign Standard per impostazione predefinita. Per acquisire tutti i campi e le risorse personalizzati, ogni cliente deve definire una propria mappatura.

* Adobe Experience Platform Data Connector invia i dati del profilo attraverso la piattaforma a intervalli regolari &#x200B;. La durata dell&#39;intervallo è di 15 minuti. Questo valore può essere modificato utilizzando le API [](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html)Adobe Experience Platform.

* Il tecnico dei dati può pubblicare, modificare e mettere in pausa la mappatura da Campaign ad Adobe Experience Platform.

* È possibile mappare qualsiasi dimensione di targeting. La raccomandazione consiste nell&#39;avere un&#39;unica mappatura per tutti i campi in un&#39;unica dimensione di targeting.

* Tutti gli aggiornamenti di profilo, inclusi gli opt-in/opt-out di canale, fanno parte dell&#39;aggiornamento batch.

* Qualsiasi modifica allo schema di Adobe Campaign Standard o XDM deve essere rimappata manualmente. &#x200B;

* I dati del registro di tracciamento e del registro di trasmissione vengono trasferiti automaticamente in Adobe Experience Platform come Eventi esperienza. Questa assimilazione viene trasmessa in streaming in tempo reale ad Adobe Experience Platform.

* Experience Cloud ID Service (ECID) è un identificatore dispositivo inviato per impostazione predefinita con Experience Events.

   Si tratta di un ID univoco e costante assegnato a un visitatore, che può essere utilizzato dal servizio Identità piattaforma per identificare lo stesso visitatore e i relativi dati in diverse soluzioni Experience Cloud. Per ulteriori informazioni, consulta l’Aiuto [del servizio](https://docs.adobe.com/content/help/en/id-service/using/home.html)Experience Cloud ID.

   >[!NOTE]
   >
   >Tenete presente che, se due o più profili condividono uno stesso dispositivo, l’ECID sarebbe lo stesso per questi due profili nel servizio Identità unificata.

## Limitazioni {#limitations}

* Il trasferimento out-of-the-box degli eventi di iscrizione non è supportato. Per trasferire gli eventi di iscrizione, puoi creare XDM e dataset corrispondenti in Adobe Experience Platform, quindi configurare una mappatura dati personalizzata per questi dati.

* Per quanto riguarda le richieste di privacy, i clienti devono effettuare richieste separate per il servizio di privacy di base di Campaign e per Adobe Experience Platform per poter accedere ed eliminare le azioni.

* Per ciascun campo XDM, l&#39;etichettatura DULE deve essere realizzata in Adobe Experience Platform. Questa è responsabilità del cliente applicare etichette DULE.

* Le restrizioni sulle azioni di marketing diventano applicabili solo dopo l&#39;applicazione delle etichette DULE in Adobe Experience Platform. Prima di tale data, tutti i dati sono disponibili per tutti i tipi di azioni di marketing.

* Ogni 15 minuti, il processo batch è in esecuzione e identifica i record modificati dall&#39;ultimo batch. Se tutti i record cambiano allo stesso timestamp, potrebbe apparire un collo di bottiglia delle prestazioni per gestire l&#39;assimilazione di tutti i profili
