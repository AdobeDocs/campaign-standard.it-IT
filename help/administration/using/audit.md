---
title: Audit Trail
description: Monitorare azioni ed eventi con Campaign Audit Trail
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: bda6f8d5-3bcf-498c-a7c4-d3c2c79b9510
source-git-commit: 64da7ac09e1b0fbf13ba1e563b6dc7be995b1640
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 3%

---

# Audit trail {#audit}

La **[!UICONTROL Audit trail]** consente di accedere alla cronologia completa delle modifiche apportate all’interno dell’istanza.

**[!UICONTROL Audit trail]** acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano all’interno della tua istanza Adobe Campaign Standard. Include un modo self-service per accedere alla cronologia dei dati e rispondere a domande quali: gli eventi relativi ai flussi di lavoro, alle risorse personalizzate e alle opzioni, l’ultimo utente che li ha aggiornati o le operazioni eseguite dagli utenti nell’istanza.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** è costituito da tre componenti:

* **Audit trail per risorse personalizzate**: controlla l’attività e l’ultima modifica apportata alle risorse personalizzate.

   Per ulteriori informazioni su **[!UICONTROL Custom resources]**, fai riferimento a [page](../../developing/using/key-steps-to-add-a-resource.md).

* **Workflow Audit trail**: controlla l’attività e l’ultima modifica apportata ai flussi di lavoro e, in aggiunta, lo stato dei flussi di lavoro quali:

   * Creato
   * Modificato
   * Eliminato
   * Inizio flusso di lavoro
   * Pausa workflow
   * Interruzione del flusso di lavoro
   * Riavvio del flusso di lavoro
   * Pulizia del flusso di lavoro
   * Simulazione flusso di lavoro
   * Attivazione flusso di lavoro
   * Interruzione immediata del flusso di lavoro
   * Riavvio del flusso di lavoro con lo stesso utente
   * Riavvio del flusso di lavoro - Comando sconosciuto

   Per ulteriori informazioni su **[!UICONTROL Workflows]**, fai riferimento a [page](../../automating/using/get-started-workflows.md).

* **Opzione Audit trail**: controlla l’attività e l’ultima modifica apportata alle opzioni.

   Per ulteriori informazioni su **[!UICONTROL Options]**, fai riferimento a [page](../../administration/using/about-campaign-standard-settings.md).

Per impostazione predefinita, il periodo di conservazione è di 30 giorni.

## Accesso a Audit trail {#audit-access}

Per accedere alla traccia di audit della tua istanza:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. La **[!UICONTROL Audit trail]** viene visualizzata la finestra con l’elenco delle entità. Adobe Campaign Standard controllerà le azioni di creazione, modifica ed eliminazione per i flussi di lavoro, le opzioni e le risorse personalizzate.

   Da **[!UICONTROL Search]** puoi filtrare l’entità in base a:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: Tipo di entità tra Tutto, Flusso di lavoro, Risorsa personalizzata e Opzione.
   * **[!UICONTROL Entity name]**: ID del flusso di lavoro, dell’opzione o della risorsa personalizzata

   ![](assets/audit-trail_2.png)

1. Seleziona una delle entità per ulteriori informazioni sulle ultime modifiche.

1. La finestra dell’entità Audit fornisce informazioni più dettagliate sull’entità selezionata, ad esempio:

   * **[!UICONTROL Entity]**: ID del flusso di lavoro, dell’opzione o della risorsa personalizzata.
   * **[!UICONTROL Action]**: Ultima azione eseguita su questa entità.
   * **[!UICONTROL Changed by]**: Nome utente dell’ultima persona che ha modificato l’entità.
   * **[!UICONTROL Changed date]**: Data dell’ultima azione eseguita su questa entità.
   * **[!UICONTROL Content]**: Blocco di codice che fornisce ulteriori informazioni sulle modifiche apportate esattamente nell’entità.

   In questo esempio, l’amministratore aziendale di questa istanza ha avviato il flusso di lavoro WKF110 il 26 agosto.

   ![](assets/audit-trail_3.png)

## Attiva/disattiva traccia di audit {#enable-disable-audit}

>[!NOTE]
>
> Solo gli amministratori funzionali possono abilitare o disabilitare Audit trail. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/users-management.md#functional-administrators).

La traccia di controllo può essere facilmente attivata o disattivata per una specifica attività.

Per eseguire questa operazione:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Seleziona una delle seguenti opzioni a seconda dell’entità da disabilitare:

   * **[!UICONTROL XtkAudit_Workflows]** per gestire la traccia di audit per i flussi di lavoro.
   * **[!UICONTROL XtkAudit_Option]** opzione per gestire la traccia di controllo per le opzioni.
   * **[!UICONTROL XtkAudit_CusResource]** per gestire l&#39;Audit trail per le risorse personalizzate.
   * **[!UICONTROL XtkAudit_Enable_All]** per gestire la traccia di audit per ogni entità.

      >[!NOTE]
      >
      >Se la **[!UICONTROL XtkAudit_Enable_All]** è impostato su 0, **[!UICONTROL Audit trail]** la funzionalità verrà disabilitata completamente, indipendentemente dagli altri valori delle singole opzioni.
   ![](assets/audit-trail_5.png)

1. Dal tuo **[!UICONTROL Options]** imposta la **[!UICONTROL Value (integer)]** a 0 se desideri disattivare il **[!UICONTROL Audit trail]** o a 1 per abilitarlo.

   ![](assets/audit-trail_6.png)

1. Fai clic su **[!UICONTROL Save]**.
