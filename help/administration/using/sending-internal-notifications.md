---
title: Invio di notifiche interne
description: Scoprite come inviare notifiche di sistema in tempo reale ai vostri utenti Adobe Campaign .
page-status-flag: never-activated
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---


# Invio di notifiche interne{#sending-internal-notifications}

 Adobe Campaign ti offre la possibilità di ricevere notifiche su importanti attività del sistema direttamente all&#39;interno dell&#39;applicazione. Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di agire immediatamente e direttamente sulle notifiche delle attività dall&#39;interno dell&#39;applicazione. Il risultato per i team è un&#39;agilità avanzata, un&#39;efficienza e un&#39;esecuzione più fluida delle campagne.

![](assets/pulse_3.png)

È possibile configurare le notifiche per i seguenti oggetti:

* **[!UICONTROL A/B Test emails]**: al creatore dell’e-mail e al modificatore o ai modificatori viene notificato che è stata scelta una variante (modalità automatica) o che è necessario scegliere una variante (modalità manuale). Facendo clic sulla notifica viene visualizzato il messaggio e-mail corrispondente. Le notifiche sono attivate per impostazione predefinita nel modello di test A/B fornito con il prodotto. Se desiderate disattivarli, modificate le proprietà del modello e-mail o del modello e-mail e deselezionate la casella in **Generale > Notifiche**. Per ulteriori informazioni sulle e-mail di test A/B, vedere [Creazione di un test](../../channels/using/designing-an-a-b-test-email.md)AB. Per ulteriori informazioni sulle proprietà delle e-mail, consulta [Elenco delle proprietà](../../administration/using/configuring-email-channel.md#list-of-email-properties)delle e-mail.

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: ogni membro del gruppo di protezione selezionato riceve una notifica (e-mail e notifica in-app) ogni volta che si verifica un errore in un flusso di lavoro. Facendo clic sulla notifica o sul collegamento e-mail viene visualizzato il flusso di lavoro corrispondente. Le notifiche sono disattivate per impostazione predefinita nel modello di flusso di lavoro predefinito. Se desiderate attivarli, modificate le proprietà del modello di flusso di lavoro o di flusso di lavoro e aggiungete un gruppo di sicurezza in **Generale > Esecuzione > Gestione errori > Autorità di vigilanza**. Per ulteriori informazioni sui gruppi di sicurezza, consultate [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md). Per ulteriori informazioni sulle proprietà del flusso di lavoro, vedere Proprietà [del](../../automating/using/managing-execution-options.md)flusso di lavoro.

   ![](assets/pulse_1.png)
