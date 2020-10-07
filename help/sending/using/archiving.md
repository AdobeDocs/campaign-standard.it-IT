---
title: Archiviazione di messaggi in  Adobe Campaign Standard
description: Scopri come archiviare le e-mail con  Adobe Campaign Standard utilizzando un indirizzo e-mail CCN.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 5%

---


# Archiviazione di e-mail con indirizzi Ccn{#archiving-emails}

Puoi configurare  Adobe Campaign per conservare una copia dei messaggi e-mail inviati dalla piattaforma tramite CCN e-mail.

In particolare, se l&#39;azienda deve archiviare tutti i messaggi e-mail in uscita per garantire la conformità, è possibile abilitare questa funzionalità. Consente di inviare una copia nascosta esatta dei messaggi inviati corrispondenti a un indirizzo e-mail CCN (invisibile ai destinatari della consegna) che è necessario specificare.

Una volta attivato, è necessario attivare CCN e-mail dall’ **[!UICONTROL Archive emails]** opzione nel modello di consegna e-mail.

>[!NOTE]
>
> Adobe Campaign non gestisce i file archiviati. Consente di inviare i messaggi di vostra scelta a un indirizzo dedicato, da dove possono essere elaborati e archiviati utilizzando un sistema esterno.

## Recommendations e limitazioni {#recommendations-and-limitations}

* Questa funzione è facoltativa. Controlla il contratto di licenza e contatta il responsabile dell’account per attivarla.
* L&#39;indirizzo CCN scelto deve essere fornito al team di Adobi  che lo configurerà per voi.
* È possibile utilizzare un solo indirizzo e-mail CCN.
* Vengono prese in considerazione solo le e-mail inviate correttamente. I rimbalzi non lo sono.
* Per motivi di privacy, le e-mail in CCN devono essere elaborate da un sistema di archiviazione in grado di memorizzare informazioni personali (PII) sicure.
* Quando si crea un nuovo modello di consegna, CCN e-mail non è abilitata per impostazione predefinita, anche se l&#39;opzione è stata acquistata. È necessario attivarlo manualmente in ogni modello di consegna in cui si desidera utilizzarlo.

>[!NOTE]
>
>Attualmente le e-mail archiviate non possono essere inviate con l&#39;MTA avanzata di Adobe Campaign , anche se si è già aggiornati all&#39;MTA avanzata.

## Attivazione dell&#39;archiviazione delle e-mail {#activating-email-archiving}

Una volta attivato, il CCN di e-mail viene attivato nel modello [di](../../start/using/marketing-activity-templates.md)e-mail tramite un&#39;opzione dedicata:

1. Andate a **Risorse** > **Modelli** > Modelli **di** consegna.
1. Duplica il modello predefinito **[!UICONTROL Send via email]** .
1. Selezionate il modello duplicato.
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. Expand the **[!UICONTROL Send]** section.
1. Selezionare la **[!UICONTROL Archive emails]** casella per conservare una copia di tutti i messaggi inviati per ogni consegna basata su questo modello.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Se le e-mail inviate all&#39;indirizzo CCN vengono aperte e si fa clic su di esse, queste verranno prese in considerazione nell&#39;analisi **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** dall&#39;analisi di invio, il che potrebbe causare errori di calcolo.