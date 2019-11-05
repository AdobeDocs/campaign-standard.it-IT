---
title: Monitoraggio di una consegna
description: Scopri come monitorare una consegna.
page-status-flag: mai attivato
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: monitoring-messages
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: consegna,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Monitoraggio di una consegna{#monitoring-a-delivery}

Esistono diversi modi per monitorare una consegna e misurarne l'impatto:

* **Registri** messaggi: Tali registri sono accessibili direttamente dal dashboard dei messaggi. Mostra i dettagli dell’invio, quale destinazione è stata esclusa e perché, nonché le informazioni di tracciamento come aperture e clic.

   Per visualizzare i registri dei messaggi, fai clic sull'icona in basso a destra del **[!UICONTROL Deployment]** blocco.

   Diverse schede contengono informazioni (se presenti) relative a **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]****[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Consultate [Registri](#delivery-logs)di consegna.

   ![](assets/sending_delivery1.png)

   Il registro contiene tutti i messaggi relativi alla consegna e alle prove. Icone specifiche consentono di identificare errori o avvisi. Per ulteriori informazioni, consulta [Approvare i messaggi](../../sending/using/previewing-messages.md).

   Per esportare il registro, fate clic sul **[!UICONTROL Export list]** pulsante .

   ![](assets/sending_delivery2.png)

* **Avvisi** di distribuzione: Per tenere traccia dei successi o degli errori di consegna, Adobe Campaign fornisce un sistema di avvisi e-mail che invia notifiche per informare gli utenti di importanti attività del sistema.
* **Rapporti**: Dal dashboard dei messaggi, puoi accedere a diversi rapporti per questo messaggio specifico. È inoltre disponibile un **[!UICONTROL Reports]** menu che consente di accedere a un elenco completo di report predefiniti o personalizzati da utilizzare per delineare metriche specifiche correlate al messaggio o alla campagna.
* Un amministratore può anche esportare i registri in un file separato che può essere elaborato con i propri strumenti di reporting o BI. Per ulteriori informazioni, consultate [Esportazione dei registri](../../automating/using/exporting-logs.md).

**Argomenti correlati:**

* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti](../../reporting/using/about-dynamic-reports.md)

## Registri di consegna {#delivery-logs}

### Invio di registri {#sending-logs}

La **[!UICONTROL Sending logs]** scheda offre una cronologia di ogni occorrenza della consegna. L'elenco dei messaggi inviati e i relativi stati è memorizzato qui. Consente di visualizzare lo stato di consegna per ciascun destinatario.

Per ogni profilo con **[!UICONTROL Sent]** stato, la **[!UICONTROL Date]** colonna mostra quando è stato inviato il messaggio.

![](assets/sending_delivery3.png)

### Registri di esclusione {#exclusion-logs}

La **[!UICONTROL Exclusion logs]** scheda elenca tutti i messaggi che sono stati esclusi dalla destinazione inviata e specifica il motivo dell'errore di invio.

![](assets/sending_delivery4.png)

### Cause di esclusione {#exclusion-causes}

Nella **[!UICONTROL Exclusion causes]** scheda viene visualizzato il volume (in numero di messaggi) dei messaggi esclusi dall'invio di destinazione.

![](assets/sending_delivery5.png)

