---
title: Monitoraggio di una distribuzione in Adobe Campaign Standard
description: Scopri come monitorare la consegna in Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa92475c1f8b37f995ebdc74c4a1f43692a53c21

---


# Monitoraggio di una consegna{#monitoring-a-delivery}

Esistono diversi modi per monitorare una consegna e misurarne l&#39;impatto:

* **Registri** messaggi: Tali registri sono accessibili direttamente dal dashboard dei messaggi. Mostra i dettagli dell’invio, quale destinazione è stata esclusa e perché, nonché le informazioni di tracciamento come aperture e clic.

   Per visualizzare i registri dei messaggi, fai clic sull&#39;icona in basso a destra del **[!UICONTROL Deployment]**blocco.

   Diverse schede contengono informazioni (se presenti) relative a **[!UICONTROL Sending logs]**,**[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]****[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Consultate[Registri](#delivery-logs)di consegna.

   ![](assets/sending_delivery1.png)

   Il registro contiene tutti i messaggi relativi alla consegna e alle prove. Icone specifiche consentono di identificare errori o avvisi. Per ulteriori informazioni, consulta [Approvare i messaggi](../../sending/using/previewing-messages.md).

   Per esportare il registro, fate clic sul **[!UICONTROL Export list]**pulsante .

   ![](assets/sending_delivery2.png)

* **Avvisi** di distribuzione: Per tenere traccia dei successi o degli errori di consegna, Adobe Campaign fornisce un sistema di avvisi e-mail che invia notifiche per informare gli utenti di importanti attività del sistema.
* **Rapporti**: Dal dashboard dei messaggi, puoi accedere a diversi rapporti per questo messaggio specifico. È inoltre disponibile un **[!UICONTROL Reports]**menu che consente di accedere a un elenco completo di report predefiniti o personalizzati da utilizzare per delineare metriche specifiche correlate al messaggio o alla campagna.
* Un amministratore può anche esportare i registri in un file separato che può essere elaborato con i propri strumenti di reporting o BI. Per ulteriori informazioni, consultate [Esportazione dei registri](../../automating/using/exporting-logs.md).

**Argomenti correlati:**

* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti](../../reporting/using/about-dynamic-reports.md)

## Registri di consegna {#delivery-logs}

### Invio di registri {#sending-logs}

La **[!UICONTROL Sending logs]**scheda offre una cronologia di ogni occorrenza della consegna. L&#39;elenco dei messaggi inviati e i relativi stati è memorizzato qui. Consente di visualizzare lo stato di consegna per ciascun destinatario.

Per ogni profilo con **[!UICONTROL Sent]**stato, la**[!UICONTROL Date]** colonna mostra quando è stato inviato il messaggio.

![](assets/sending_delivery3.png)

Per accedere ai dettagli di un registro di invio specifico, fai clic sull’icona matita a destra della riga corrispondente.

![](assets/sending_access-sending-log.png)

Tutti i dettagli del registro di invio sono di sola lettura. È inoltre possibile visualizzare un&#39;anteprima della pagina mirror.

![](assets/sending_sending-log.png)

>[!NOTE]
>
>Se l&#39;URL del server della pagina mirror non è sicuro (ovvero se non inizia con https://), il rendering della pagina mirror non può essere visualizzato dall&#39;interfaccia utente di Campaign. Questo server viene definito durante la [configurazione dei marchi](../../administration/using/branding.md#configuring-and-using-brands).

### Registri di esclusione {#exclusion-logs}

La **[!UICONTROL Exclusion logs]**scheda elenca tutti i messaggi che sono stati esclusi dalla destinazione inviata e specifica il motivo dell&#39;errore di invio.

![](assets/sending_delivery4.png)

### Cause di esclusione {#exclusion-causes}

Nella **[!UICONTROL Exclusion causes]**scheda viene visualizzato il volume (in numero di messaggi) dei messaggi esclusi dall&#39;invio di destinazione.

![](assets/sending_delivery5.png)
