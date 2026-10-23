---
title: Attivazione delle mappature
description: Scopri come attivare la mappatura dei dati
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d7ca0de6-7f7b-4e31-877c-909d962c5f53
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Attivazione delle mappature {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Al termine della definizione della mappatura, puoi pubblicarla. Dopo la fase di distribuzione, la replica dei dati tra Campaign Standard e Adobe Experience Platform viene avviata automaticamente. In qualsiasi momento è possibile interrompere la replica facendo clic sul pulsante **[!UICONTROL Stop]**.

A seconda delle modifiche apportate alla mappatura, puoi scegliere di inviare nuovamente tutti i record a Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Dal riquadro di distribuzione, puoi accedere al registro di pubblicazione e ai registri di esportazione.

![](assets/aep_publog.png)

Nella scheda **[!UICONTROL Export jobs]** è possibile monitorare il processo di esportazione per la mappatura pubblicata.

![](assets/aep_jobstatus.png)

Per monitorare tutti i processi di esportazione dei dati, passare al menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**.

![](assets/aep_statusmapping.png)

Gli stati dei processi di acquisizione dati sono:

* **[!UICONTROL Created]**: viene creato un processo di acquisizione dati e l&#39;acquisizione dati è in corso.
* **[!UICONTROL Failed]**: un processo di acquisizione dati non è riuscito. Il campo del motivo descrive il motivo dell’errore. Il fallimento può essere transitorio o permanente. In caso di errori transitori, viene creato un nuovo processo di acquisizione dopo un intervallo configurato. Come primo passo per la risoluzione dei problemi, l’utente può controllare il campo del motivo dell’errore. Se il motivo reindirizza un utente all’interfaccia utente di Adobe Experience Platform, l’utente può accedere a Adobe Experience Platform e controllare lo stato del batch nel set di dati per determinare il motivo esatto dell’errore.
* **[!UICONTROL Uploaded]**: viene creato un batch in Adobe Experience Platform e i dati vengono quindi acquisiti nel batch. Il campo ID batch mostra l’ID del batch in Adobe Experience Platform. Adobe Experience Platform esegue anche una convalida post sul batch. Il batch viene inizialmente contrassegnato come caricato fino al completamento del passaggio di post-convalida da parte di Adobe Experience Platform. Dopo il caricamento, un processo mantiene il polling di Adobe Experience Platform per lo stato del batch. Una batch può essere impostata su Non riuscito o su Completato dopo la convalida in Adobe Experience Platform.
* **[!UICONTROL Success]**: dopo il caricamento di un batch in Adobe Experience Platform, lo stato del processo (post convalida in Platform) viene controllato dopo un intervallo configurato. Lo stato &quot;Success&quot; (Completato) ha identificato un’acquisizione corretta dei dati in Adobe Experience Platform.

In alcuni casi, quando pubblichi la mappatura, potresti ricevere l’errore di convalida indicato di seguito.

![](assets/aep_datamapping_ccpa.png)

Ciò si verifica quando lo schema XDM in uso non è stato aggiornato con il campo XDM più recente relativo alla gestione della privacy e contiene ancora il campo XDM &quot;ccpa&quot; obsoleto.

Per aggiornare lo schema XDM, effettua le seguenti operazioni:

1. Vai al set di dati su Adobe Experience Platform utilizzando il collegamento presente nella pagina di mappatura XDM.

1. Passa allo schema XDM.

1. Aggiungi il mixin **[!UICONTROL Profile Privacy]** allo schema.

   ![](assets/aep_datamapping_privacyfield.png)

1. Salva lo schema, quindi riprova a pubblicare il mapping. La pubblicazione dovrebbe ora passare.

   ![](assets/aep_save_mapping.png)
