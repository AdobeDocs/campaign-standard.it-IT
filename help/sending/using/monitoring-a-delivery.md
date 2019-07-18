---
title: Monitoraggio di una consegna
seo-title: Monitoraggio di una consegna
description: Monitoraggio di una consegna
seo-description: Scopri come monitorare una distribuzione.
page-status-flag: never-activated
uuid: 7772 c 607-debd -40 fd -8322-4 d 49119979 b 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: monitoring-messages
discoiquuid: eb 9 fa 216-4568-423 a -9396-8 f 7 b 82181 ae 9
context-tags: distribuzione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Monitoring a delivery{#monitoring-a-delivery}

Esistono diversi modi per monitorare una consegna e misurarne l'impatto:

* **Registri dei messaggi**: Questi registri sono accessibili direttamente dal dashboard messaggio. Mostrano i dettagli dell'invio, la destinazione e il motivo, nonché le informazioni di tracciamento quali aperture e clic.

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Several tabs contain information (if it exists) regarding the **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** and **[!UICONTROL Tracked URLs]**. See [Delivery logs](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   ![](assets/sending_delivery1.png)

   Il registro contiene tutti i messaggi relativi alla consegna e alle prove. Le icone specifiche consentono di identificare errori o avvertenze. For more on this, see [Approving messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **Avvisi sulla distribuzione**: Per tenere traccia dei successi o degli errori della distribuzione, Adobe Campaign fornisce un sistema di avvisi e-mail che invia notifiche per informare gli utenti di importanti attività del sistema.
* **Rapporti**: Dal pannello del messaggio potete accedere a diversi rapporti per questo messaggio specifico. You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* Un amministratore può anche esportare i registri in un file separato che può essere elaborato nei propri strumenti di reporting o BI. For more on this, see [Exporting logs](../../automating/using/exporting-logs.md).

**Argomenti correlati:**

* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti](../../reporting/using/about-dynamic-reports.md)

## Delivery logs {#delivery-logs}

### Sending logs {#sending-logs}

**[!UICONTROL Sending logs]** La scheda offre una cronologia di ogni occorrenza di questa consegna. L'elenco dei messaggi inviati e i relativi stati sono memorizzati qui. Consente di visualizzare lo stato di consegna per ciascun destinatario.

For each profile with a **[!UICONTROL Sent]** status, the **[!UICONTROL Date]** column shows when the message was sent.

![](assets/sending_delivery3.png)

### Exclusion logs {#exclusion-logs}

The **[!UICONTROL Exclusion logs]** tab lists all the messages that have been excluded from the target sent and specifies the reason for the send failure.

![](assets/sending_delivery4.png)

### Exclusion causes {#exclusion-causes}

**[!UICONTROL Exclusion causes]** Nella scheda viene visualizzato il volume (in numero di messaggi) dei messaggi che sono stati esclusi dalla destinazione di destinazione.

![](assets/sending_delivery5.png)

