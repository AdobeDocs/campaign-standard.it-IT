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
source-wordcount: '495'
ht-degree: 3%

---

# Audit trail {#audit}

**[!UICONTROL Audit trail]** consente di accedere alla cronologia completa delle modifiche apportate all&#39;interno dell&#39;istanza.

**[!UICONTROL Audit trail]** acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano nell&#39;istanza Adobe Campaign Standard. Include una modalità autonoma di accedere alla cronologia dei dati per poter rispondere a domande quali: cosa è successo ai flussi di lavoro, risorse personalizzate e opzioni, chi li ha aggiornati per ultimo o cosa hanno fatto i tuoi utenti nell’istanza.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** è costituito da tre componenti:

* **Audit trail delle risorse personalizzate**: controlla l&#39;attività e l&#39;ultima modifica apportata alle risorse personalizzate.

  Per ulteriori informazioni su **[!UICONTROL Custom resources]**, fare riferimento a questa [pagina](../../developing/using/key-steps-to-add-a-resource.md).

* **Audit trail flusso di lavoro**: controlla l&#39;attività e l&#39;ultima modifica apportata ai flussi di lavoro e, inoltre, lo stato dei flussi di lavoro, ad esempio:

   * Creato
   * Modificato
   * Eliminato
   * Avvio flusso di lavoro
   * Pausa flusso di lavoro
   * Interruzione flusso di lavoro
   * Riavvio flusso di lavoro
   * Pulizia flusso di lavoro
   * Simulazione flusso di lavoro
   * Riattivazione flusso di lavoro
   * Arresto immediato del flusso di lavoro
   * Riavvio del flusso di lavoro con lo stesso utente
   * Comando Riavvio flusso di lavoro sconosciuto

  Per ulteriori informazioni su **[!UICONTROL Workflows]**, fare riferimento a questa [pagina](../../automating/using/get-started-workflows.md).

* **Option Audit trail**: controlla l&#39;attività e l&#39;ultima modifica apportata alle opzioni.

  Per ulteriori informazioni su **[!UICONTROL Options]**, fare riferimento a questa [pagina](../../administration/using/about-campaign-standard-settings.md).

Per impostazione predefinita, il periodo di conservazione è di 30 giorni.

## Accesso a Audit trail {#audit-access}

Per accedere all’Audit trail dell’istanza:

1. In Adobe Campaign Standard, dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. Viene visualizzata la finestra **[!UICONTROL Audit trail]** con l&#39;elenco delle entità. Adobe Campaign Standard controllerà le azioni di creazione, modifica ed eliminazione per flussi di lavoro, opzioni e risorse personalizzate.

   Dal menu **[!UICONTROL Search]**, puoi filtrare l&#39;entità in base a:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: tipo di entità tra tutti, flusso di lavoro, risorsa personalizzata e opzione.
   * **[!UICONTROL Entity name]**: ID del flusso di lavoro, opzione o risorsa personalizzata

   ![](assets/audit-trail_2.png)

1. Selezionate una delle entità per ulteriori informazioni sulle ultime modifiche.

1. La finestra Entità di audit fornisce informazioni più dettagliate sull’entità scelta, ad esempio:

   * **[!UICONTROL Entity]**: ID del flusso di lavoro, opzione o risorsa personalizzata.
   * **[!UICONTROL Action]**: ultima azione eseguita su questa entità.
   * **[!UICONTROL Changed by]**: nome utente dell&#39;ultima persona che ha modificato l&#39;entità.
   * **[!UICONTROL Changed date]**: data dell&#39;ultima azione eseguita su questa entità.
   * **[!UICONTROL Content]**: blocco di codice che fornisce ulteriori informazioni su ciò che è stato modificato esattamente nell&#39;entità.

   In questo esempio, possiamo vedere che il flusso di lavoro WKF110 è stato avviato il 26 agosto dall’amministratore Business di questa istanza.

   ![](assets/audit-trail_3.png)

## Attiva/disattiva Audit trail {#enable-disable-audit}

>[!NOTE]
>
> Solo gli amministratori funzionali possono abilitare o disabilitare Audit trail. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/users-management.md#functional-administrators).

Audit trail può essere facilmente attivato o disattivato per un’attività specifica.

Per eseguire questa operazione:

1. In Adobe Campaign Standard, dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Selezionate una delle seguenti opzioni a seconda dell&#39;entità da disattivare:

   * Opzione **[!UICONTROL XtkAudit_Workflows]** per gestire l&#39;Audit trail per i flussi di lavoro.
   * Opzione **[!UICONTROL XtkAudit_Option]** per gestire l&#39;audit trail per le opzioni.
   * Opzione **[!UICONTROL XtkAudit_CusResource]** per gestire l&#39;audit trail per le risorse personalizzate.
   * Opzione **[!UICONTROL XtkAudit_Enable_All]** per gestire l&#39;audit trail per ogni entità.

     >[!NOTE]
     >
     >Se l&#39;opzione **[!UICONTROL XtkAudit_Enable_All]** è impostata su 0, la funzionalità **[!UICONTROL Audit trail]** verrà completamente disabilitata, indipendentemente dagli altri valori delle singole opzioni.

   ![](assets/audit-trail_5.png)

1. Dalla pagina **[!UICONTROL Options]**, impostare **[!UICONTROL Value (integer)]** su 0 se si desidera disabilitare **[!UICONTROL Audit trail]** o su 1 per abilitarlo.

   ![](assets/audit-trail_6.png)

1. Fai clic su **[!UICONTROL Save]**.
