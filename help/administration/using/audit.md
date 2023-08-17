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

Il **[!UICONTROL Audit trail]** consente di accedere alla cronologia completa delle modifiche apportate all’interno dell’istanza.

**[!UICONTROL Audit trail]** acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano all’interno dell’istanza di Adobe Campaign Standard. Include una modalità autonoma di accedere alla cronologia dei dati per poter rispondere a domande quali: cosa è successo ai flussi di lavoro, risorse personalizzate e opzioni, chi li ha aggiornati per ultimo o cosa hanno fatto i tuoi utenti nell’istanza.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** è costituito da tre componenti:

* **Audit trail delle risorse personalizzate**: controlla l’attività e l’ultima modifica apportata alle risorse personalizzate.

  Per ulteriori informazioni su **[!UICONTROL Custom resources]**, fai riferimento a questo [pagina](../../developing/using/key-steps-to-add-a-resource.md).

* **Audit trail del flusso di lavoro**: controlla l’attività e l’ultima modifica apportata ai flussi di lavoro e, inoltre, lo stato dei flussi di lavoro, ad esempio:

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

  Per ulteriori informazioni su **[!UICONTROL Workflows]**, fai riferimento a questo [pagina](../../automating/using/get-started-workflows.md).

* **Option Audit trail**: controlla l’attività e l’ultima modifica apportata alle opzioni.

  Per ulteriori informazioni su **[!UICONTROL Options]**, fai riferimento a questo [pagina](../../administration/using/about-campaign-standard-settings.md).

Per impostazione predefinita, il periodo di conservazione è di 30 giorni.

## Accesso a Audit trail {#audit-access}

Per accedere all’Audit trail dell’istanza:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. Il **[!UICONTROL Audit trail]** viene visualizzata la finestra con l&#39;elenco delle entità. Adobe Campaign Standard controllerà le azioni di creazione, modifica ed eliminazione per flussi di lavoro, opzioni e risorse personalizzate.

   Dalla sezione **[!UICONTROL Search]** puoi filtrare l’entità in base a:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: tipo di entità tra Tutti, Flusso di lavoro, Risorsa personalizzata e Opzione.
   * **[!UICONTROL Entity name]**: ID del flusso di lavoro, opzione o risorsa personalizzata

   ![](assets/audit-trail_2.png)

1. Selezionate una delle entità per ulteriori informazioni sulle ultime modifiche.

1. La finestra Entità di audit fornisce informazioni più dettagliate sull’entità scelta, ad esempio:

   * **[!UICONTROL Entity]**: ID del flusso di lavoro, opzione o risorsa personalizzata.
   * **[!UICONTROL Action]**: ultima azione eseguita su questa entità.
   * **[!UICONTROL Changed by]**: nome utente dell’ultima persona che ha modificato questa entità.
   * **[!UICONTROL Changed date]**: data dell’ultima azione eseguita su questa entità.
   * **[!UICONTROL Content]**: blocco di codice che fornisce ulteriori informazioni su ciò che è stato modificato esattamente nell’entità.

   In questo esempio, possiamo vedere che il flusso di lavoro WKF110 è stato avviato il 26 agosto dall’amministratore Business di questa istanza.

   ![](assets/audit-trail_3.png)

## Attiva/disattiva Audit trail {#enable-disable-audit}

>[!NOTE]
>
> Solo gli amministratori funzionali possono abilitare o disabilitare Audit trail. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/users-management.md#functional-administrators).

Audit trail può essere facilmente attivato o disattivato per un’attività specifica.

Per eseguire questa operazione:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Selezionate una delle seguenti opzioni a seconda dell&#39;entità da disattivare:

   * **[!UICONTROL XtkAudit_Workflows]** per gestire Audit trail per i flussi di lavoro.
   * **[!UICONTROL XtkAudit_Option]** per gestire Audit trail per le opzioni.
   * **[!UICONTROL XtkAudit_CusResource]** per gestire Audit trail per le risorse personalizzate.
   * **[!UICONTROL XtkAudit_Enable_All]** per gestire Audit trail per ogni entità.

     >[!NOTE]
     >
     >Se il **[!UICONTROL XtkAudit_Enable_All]** è impostato su 0, il **[!UICONTROL Audit trail]** La funzione verrà completamente disabilitata, indipendentemente dagli altri valori delle singole opzioni.

   ![](assets/audit-trail_5.png)

1. Dal tuo **[!UICONTROL Options]** pagina, imposta **[!UICONTROL Value (integer)]** a 0 se si desidera disabilitare **[!UICONTROL Audit trail]** o a 1 per abilitarlo.

   ![](assets/audit-trail_6.png)

1. Fai clic su **[!UICONTROL Save]**.
