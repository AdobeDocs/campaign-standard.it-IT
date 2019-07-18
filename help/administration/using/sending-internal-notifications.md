---
title: Invio di notifiche interne
seo-title: Invio di notifiche interne
description: Invio di notifiche interne
seo-description: Scopri come inviare notifiche di sistema in tempo reale agli utenti di Adobe Campaign.
page-status-flag: never-activated
uuid: f 196 f 025-dbb 9-4268-9 d 7 d-ff 626994 b 447
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: application-settings
discoiquuid: 4 d 51229 a -745 a -4 f 24-b 1 c 2-22 fa 203 b 499 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Sending internal notifications{#sending-internal-notifications}

Adobe Campaign vi offre la possibilità di ricevere notifiche su importanti attività del sistema direttamente all'interno dell'applicazione. Le notifiche in tempo reale tengono informati gli interessati e forniscono agli utenti la possibilità di intervenire immediatamente e direttamente sulle notifiche dell'attività dall'interno dell'applicazione. Il risultato per i team è l'agilità avanzata, l'efficienza e l'esecuzione più fluida delle campagne.

![](assets/pulse_3.png)

È possibile configurare le notifiche per i seguenti oggetti:

* **[!UICONTROL A/B Test emails]**: l'autore e i modificatori dell'e-mail ricevono una notifica che è stata scelta una variante (modalità automatica) o che è necessario scegliere una variante (modalità manuale). Facendo clic sulla notifica viene visualizzata l'e-mail corrispondente. Le notifiche sono attivate per impostazione predefinita nel modello di test A/B integrato. If you want to deactivate them, edit the properties of the email or the email template and uncheck the box located under **General &gt; Notifications**. For more information on A/B Test emails, refer to [Creating an AB Test](../../channels/using/designing-an-a-b-test-email.md). For more on email properties, refer to [List of email properties](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: Ogni membro del gruppo di sicurezza selezionato riceve notifica (e-mail e notifica in-app) ogni volta che un flusso di lavoro viene visualizzato in un errore. Facendo clic sulla notifica o sul collegamento e-mail viene visualizzato il flusso di lavoro corrispondente. Per impostazione predefinita, le notifiche sono disattivate nel modello di flusso di lavoro preimpostato. If you want to activate them, edit the properties of the workflow or workflow template and add a security group under **General &gt; Execution &gt; Error management &gt; Supervisors**. For more information on security groups, refer to [Managing groups and users](../../administration/using/managing-groups-and-users.md). For more on workflow properties, refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

