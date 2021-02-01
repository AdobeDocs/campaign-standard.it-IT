---
solution: Campaign Standard
product: campaign
title: Attivazione mappature
description: Scopri come attivare la mappatura dei dati
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---


# Attivazione mappature {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in fase beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.

Al termine della definizione di mappatura, potete pubblicare la mappatura. Dopo il passaggio di distribuzione, la replica dei dati tra Campaign Standard e Adobe Experience Platform viene avviata automaticamente. In qualsiasi momento, è possibile interrompere la replica facendo clic sul pulsante **[!UICONTROL Stop]**.

A seconda delle modifiche apportate alla mappatura, puoi scegliere di inviare nuovamente tutti i record ad Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Dal riquadro di distribuzione potete accedere al registro delle pubblicazioni ed esportare i registri.

![](assets/aep_publog.png)

Nella scheda **[!UICONTROL Export jobs]** è possibile monitorare il processo di esportazione per la mappatura pubblicata.

![](assets/aep_jobstatus.png)

Per monitorare tutti i processi di esportazione dei dati, scegliere **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** >  > **[!UICONTROL Status of data export to platform]**.

![](assets/aep_statusmapping.png)

Gli stati del processo di assimilazione dei dati sono:

* **[!UICONTROL Created]**: Viene creato un processo di assimilazione dei dati e l’assimilazione dei dati è in corso.
* **[!UICONTROL Failed]**: Un processo di inserimento dei dati non è riuscito. Il campo reason descrive il motivo dell&#39;errore. Il fallimento può essere transitorio o permanente. In caso di errori temporanei, viene creato un nuovo processo di assimilazione dopo un intervallo configurato. Come primo passo per la risoluzione dei problemi, l&#39;utente può controllare il campo del motivo dell&#39;errore. Se il motivo del reindirizzamento di un utente all&#39;interfaccia utente di Adobe Experience Platform, l&#39;utente può accedere ad Adobe Experience Platform e controllare lo stato del batch nel dataset per determinare il motivo esatto dell&#39;errore.
* **[!UICONTROL Uploaded]**: Un batch viene creato in Adobe Experience Platform e i dati vengono quindi trasferiti al batch. Il campo ID batch mostra l’ID batch per il batch in Adobe Experience Platform. Adobe Experience Platform esegue anche una convalida post sul batch. Il batch viene inizialmente contrassegnato come caricato fino al completamento del passaggio di convalida post. Dopo il caricamento, un processo continua il polling di Adobe Experience Platform per lo stato del batch. Un batch può essere archiviato in Convalida del post con esito negativo o in stato di esito positivo in Adobe Experience Platform.
* **[!UICONTROL Success]**: Dopo il caricamento di un batch in Adobe Experience Platform, lo stato del processo (dopo la convalida nella piattaforma) viene controllato dopo un intervallo configurato. Uno stato &quot;Success&quot; ha identificato un&#39;acquisizione di dati riuscita in Adobe Experience Platform.

In alcuni casi, durante la pubblicazione della mappatura potrebbe verificarsi l&#39;errore di convalida riportato di seguito.

![](assets/aep_datamapping_ccpa.png)

Ciò si verifica quando lo schema XDM utilizzato non è stato aggiornato con il campo XDM più recente relativo alla gestione della privacy e contiene ancora il campo XDM &quot;ccpa&quot; obsoleto.

Per aggiornare lo schema XDM, procedere come segue:

1. Andate al set di dati su Adobe Experience Platform utilizzando il collegamento presente nella pagina di mappatura XDM.

1. Passa allo schema XDM.

1. Aggiungete il mixin **[!UICONTROL Profile Privacy]** allo schema.

   ![](assets/aep_datamapping_privacyfield.png)

1. Salvare lo schema, quindi riprovare a pubblicare la mappatura. La pubblicazione dovrebbe ora passare.

   ![](assets/aep_save_mapping.png)
