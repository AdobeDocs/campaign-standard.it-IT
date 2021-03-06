---
title: Invio di notifiche interne
description: Scopri come inviare notifiche di sistema in tempo reale agli utenti di Adobe Campaign
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Invio di notifiche interne{#sending-internal-notifications}

Adobe Campaign ti offre la possibilità di ricevere notifiche relative a importanti attività di sistema direttamente all’interno dell’applicazione. Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di intervenire immediatamente e direttamente sulle notifiche di attività dall’interno dell’applicazione. Il risultato per i team è un&#39;agilità avanzata, un&#39;efficienza e un&#39;esecuzione più fluida delle campagne.

![](assets/pulse_3.png)

Puoi configurare le notifiche per i seguenti oggetti:

* **[!UICONTROL A/B Test emails]**: al creatore dell’e-mail e al modificatore o ai modificatori viene notificato che è stata scelta una variante (modalità automatica) o che è necessario scegliere una variante (modalità manuale). Facendo clic sulla notifica viene visualizzata l’e-mail corrispondente. Le notifiche vengono attivate per impostazione predefinita nel modello di test A/B predefinito. Per disattivarle, modifica le proprietà dell’e-mail o del modello e-mail e deseleziona la casella che si trova in **Generale > Notifiche**. Per ulteriori informazioni sulle e-mail di test A/B, consulta [Creazione di un test AB](../../channels/using/designing-an-a-b-test-email.md). Per ulteriori informazioni sulle proprietà delle e-mail, consulta [Elenco delle proprietà delle e-mail](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: ogni membro del gruppo di sicurezza selezionato riceve una notifica (e-mail e notifica in-app) ogni volta che un flusso di lavoro viene restituito per errore. Facendo clic sulla notifica o sul collegamento e-mail viene visualizzato il flusso di lavoro corrispondente. Le notifiche sono disattivate per impostazione predefinita nel modello di flusso di lavoro predefinito. Se desideri attivarli, modifica le proprietà del flusso di lavoro o del modello di flusso di lavoro e aggiungi un gruppo di sicurezza in **Generale > Esecuzione > Gestione errori > Autorità di vigilanza**. Per ulteriori informazioni sui gruppi di sicurezza, consulta [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md). Per ulteriori informazioni sulle proprietà del flusso di lavoro, consulta [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
