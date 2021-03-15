---
solution: Campaign Standard
product: campaign
title: Invio di notifiche interne
description: Scopri come inviare notifiche di sistema in tempo reale ai tuoi utenti Adobe Campaign.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Impostazioni delle istanze
role: Amministratore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Invio di notifiche interne{#sending-internal-notifications}

Adobe Campaign ti offre la possibilità di ricevere notifiche relative a importanti attività di sistema direttamente all’interno dell’applicazione. Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di intervenire immediatamente e direttamente sulle notifiche di attività dall’interno dell’applicazione. Il risultato per i team è un&#39;agilità avanzata, un&#39;efficienza e un&#39;esecuzione più fluida delle campagne.

![](assets/pulse_3.png)

Puoi configurare le notifiche per i seguenti oggetti:

* **[!UICONTROL A/B Test emails]**: al creatore dell’e-mail e al modificatore o ai modificatori viene notificato che è stata scelta una variante (modalità automatica) o che è necessario scegliere una variante (modalità manuale). Facendo clic sulla notifica viene visualizzata l’e-mail corrispondente. Le notifiche vengono attivate per impostazione predefinita nel modello di test A/B predefinito. Se desideri disattivarli, modifica le proprietà dell’e-mail o del modello e-mail e deseleziona la casella che si trova in **Generale > Notifiche**. Per ulteriori informazioni sulle e-mail di test A/B, consulta [Creazione di un test AB](../../channels/using/designing-an-a-b-test-email.md). Per ulteriori informazioni sulle proprietà delle e-mail, consulta [Elenco delle proprietà delle e-mail](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: ogni membro del gruppo di sicurezza selezionato riceve una notifica (e-mail e notifica in-app) ogni volta che un flusso di lavoro viene restituito per errore. Facendo clic sulla notifica o sul collegamento e-mail viene visualizzato il flusso di lavoro corrispondente. Le notifiche sono disattivate per impostazione predefinita nel modello di flusso di lavoro predefinito. Per attivarli, modifica le proprietà del flusso di lavoro o del modello di flusso di lavoro e aggiungi un gruppo di sicurezza in **Generale > Esecuzione > Gestione errori > Supervisori**. Per ulteriori informazioni sui gruppi di sicurezza, consulta [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md). Per ulteriori informazioni sulle proprietà del flusso di lavoro, consulta [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
