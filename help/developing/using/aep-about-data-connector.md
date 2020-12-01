---
solution: Campaign Standard
product: campaign
title: Informazioni sul Connettore dati di Adobe Experience Platform
description: Gestire gli schemi XDM per rendere disponibili i dati Campaign Standard su Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 4%

---


# Informazioni sul Connettore dati di Adobe Experience Platform {#about-aep-data-connector}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in fase beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.

Adobe Experience Platform Data Connector aiuta i clienti esistenti a rendere disponibili i loro dati su Adobe Experience Platform mappando i dati XTK (dati acquisiti in Campaign) a dati XDM (Experience Data Model) su Adobe Experience Platform.

Il connettore è **unidirezionale** e invia i dati da  Adobe Campaign Standard ad Adobe Experience Platform. I dati non vengono mai inviati dall&#39;Adobe Experience Platform a  Adobe Campaign Standard.

Adobe Experience Platform Data Connector è destinato agli **sviluppatori di dati** che comprendono  risorse personalizzate Adobe Campaign Standard e hanno una conoscenza dello schema di dati complessivo del cliente all&#39;interno di Adobe Experience Platform.

Le sezioni seguenti descrivono i passaggi chiave per eseguire una mappatura dati tra Campaign Standard e Adobe Experience Platform. Questo inizia con la creazione di uno schema XDM e di un dataset.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

>[!NOTE]
>Una volta che Adobe Experience Platform Data Connector è configurato e i dati vengono correttamente inviati in Adobe Experience Platform, è necessario abilitare il dataset in modo che i dati siano inclusi nel profilo cliente in tempo reale.
>
>Questo può essere eseguito tramite le API o l&#39;interfaccia Adobe Experience Platform. Per maggiori informazioni, consulta la documentazione dedicata:
>
>* [Abilita un set di dati per il profilo cliente in tempo reale](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/datasets/dataset.html)
>* [Configurare un set di dati per il profilo cliente e il servizio identità in tempo reale mediante le API](https://docs.adobe.com/content/help/en/experience-platform/catalog/api/getting-started.html)


## Concetti chiave {#key-concepts}

* La mappatura casella è disponibile solo per i campi forniti in Campaign Standard per impostazione predefinita. Per acquisire tutti i campi e le risorse personalizzati, ogni cliente deve definire una propria mappatura.

* Adobe Experience Platform Data Connector invia i dati del profilo attraverso la piattaforma a intervalli regolari. &#x200B; La durata dell&#39;intervallo è di 15 minuti. Questo valore può essere modificato utilizzando le [API Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/ingestion/home.html).

* L&#39;ingegnere dei dati può pubblicare, modificare e mettere in pausa la mappatura da Campaign ad Adobe Experience Platform.

* È possibile mappare qualsiasi dimensione di targeting. La raccomandazione consiste nell&#39;avere un&#39;unica mappatura per tutti i campi in un&#39;unica dimensione di targeting.

* Tutti gli aggiornamenti di profilo, inclusi gli opt-in/opt-out di canale, fanno parte dell&#39;aggiornamento batch.

* Eventuali modifiche  schema Adobe Campaign Standard o XDM devono essere rimappate manualmente &#x200B;.

* I dati del registro di tracciamento e del registro di trasmissione vengono trasferiti automaticamente ad Adobe Experience Platform come eventi di esperienza. Questa assimilazione viene trasmessa in streaming ad Adobe Experience Platform in tempo reale.

*  Experience Cloud ID Service (ECID) è un identificatore dispositivo inviato per impostazione predefinita con Experience Events.

   Si tratta di un ID univoco e permanente assegnato a un visitatore, che può essere utilizzato dal servizio identità piattaforma per identificare lo stesso visitatore e i relativi dati in diverse soluzioni  Experience Cloud. Per ulteriori informazioni, consultare la [ Guida del servizio identità Experience Cloud](https://docs.adobe.com/content/help/en/id-service/using/home.html).

   >[!NOTE]
   >
   >Tenete presente che, se due o più profili condividono uno stesso dispositivo, l’ECID sarebbe lo stesso per questi due profili nel servizio Identità unificata.

## Limitazioni {#limitations}

* Il trasferimento out-of-the-box degli eventi di iscrizione non è supportato. Per trasferire gli eventi di iscrizione, puoi creare XDM e dataset corrispondenti in Adobe Experience Platform, quindi configurare una mappatura dati personalizzata per questi dati.

* Per quanto riguarda le richieste di privacy (entrambe le azioni di accesso ed eliminazione), i clienti devono effettuare richieste separate tramite il [Servizio di base sulla privacy](https://docs.adobe.com/content/help/en/experience-platform/privacy/home.html#how-to-use-privacy-service-to-manage-privacy-job-requests): uno per Campaign e uno per Adobe Experience Platform. Per ulteriori informazioni, vedere [Informazioni sulle richieste di privacy](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess) e [Gestione delle richieste di privacy](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests) in Campaign.

* Per ciascun campo XDM, l&#39;etichetta DULE deve essere eseguita in Adobe Experience Platform. Questa è responsabilità del cliente applicare etichette DULE.

* Le restrizioni sulle azioni di marketing diventano applicabili solo dopo l&#39;applicazione delle etichette DULE in Adobe Experience Platform. Prima di tale data, tutti i dati sono disponibili per tutti i tipi di azioni di marketing.

* Ogni 15 minuti, il processo batch è in esecuzione e identifica i record modificati dall&#39;ultimo batch. Se tutti i record cambiano allo stesso timestamp, potrebbe apparire un collo di bottiglia delle prestazioni per gestire l&#39;assimilazione di tutti i profili

## Video di esercitazione {#video}

Questo video fornisce una panoramica sul Connettore dati Adobe Experience Platform.

https://video.tv.adobe.com/v/27304?quality=12&amp;captions=ita

Ulteriori video relativi al Connettore dati Adobe Experience Platform sono disponibili [qui](https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html).
