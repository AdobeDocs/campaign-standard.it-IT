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

Adobe Campaign consente di ricevere notifiche relative a importanti attività del sistema direttamente all’interno dell’applicazione. Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di agire immediatamente e direttamente sulle notifiche di attività dall’interno dell’applicazione. Il risultato per i team è l’agilità avanzata, l’efficienza e l’esecuzione più fluida delle campagne.

![](assets/pulse_3.png)

Puoi configurare le notifiche per i seguenti oggetti:

* **[!UICONTROL A/B Test emails]**: il creatore e il modificatore dell’e-mail vengono informati che è stata scelta una variante (modalità automatica) o che è necessario scegliere una variante (modalità manuale). Facendo clic sulla notifica viene visualizzata l’e-mail corrispondente. Le notifiche vengono attivate per impostazione predefinita nel modello di test A/B predefinito. Se desideri disattivarli, modifica le proprietà dell’e-mail o del modello e-mail e deseleziona la casella che si trova in **Generale > Notifiche**. Per ulteriori informazioni sulle e-mail per test A/B, consulta [Creazione di un test AB](../../channels/using/designing-an-a-b-test-email.md). Per ulteriori informazioni sulle proprietà delle e-mail, consulta [Elenco delle proprietà e-mail](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: a ogni membro del gruppo di sicurezza selezionato viene inviata una notifica (e-mail e notifica in-app) ogni volta che un flusso di lavoro è in errore. Facendo clic sulla notifica o sul collegamento e-mail viene visualizzato il flusso di lavoro corrispondente. Le notifiche vengono disattivate per impostazione predefinita nel modello di flusso di lavoro preconfigurato. Se desideri attivarle, modifica le proprietà del flusso di lavoro o del modello di flusso di lavoro e aggiungi un gruppo di sicurezza in **Generale > Esecuzione > Gestione errori > Supervisori**. Per ulteriori informazioni sui gruppi di sicurezza, fare riferimento a [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md). Per ulteriori informazioni sulle proprietà dei flussi di lavoro, consulta [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
