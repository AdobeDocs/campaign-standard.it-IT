---
solution: Campaign Standard
product: campaign
title: Archiviazione di messaggi in  Adobe Campaign Standard
description: Scopri come archiviare le e-mail con  Adobe Campaign Standard utilizzando un indirizzo e-mail CCN.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 0f057375e5cd63605af460f08cd39bed00435184
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 5%

---


# Archiviazione di e-mail con indirizzi Ccn{#archiving-emails}

Puoi configurare  Adobe Campaign per conservare una copia dei messaggi e-mail inviati dalla piattaforma tramite CCN e-mail.

In particolare, se l&#39;azienda deve archiviare tutti i messaggi e-mail in uscita per garantire la conformità, è possibile abilitare questa funzionalità. Consente di inviare una copia nascosta esatta dei messaggi inviati corrispondenti a un indirizzo e-mail CCN (invisibile ai destinatari della consegna) che è necessario specificare.

Una volta attivato, è necessario attivare CCN e-mail dall&#39;opzione **[!UICONTROL Archive emails]** nel modello di consegna e-mail.

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
>Al momento i messaggi e-mail archiviati non possono essere inviati con il  Adobe Campaign Enhanced MTA.

## Attivazione dell&#39;archiviazione delle e-mail {#activating-email-archiving}

Una volta attivato, il CCN e-mail viene attivato nel [modello e-mail](../../start/using/marketing-activity-templates.md), tramite un&#39;opzione dedicata:

1. Vai a **Risorse** > **Modelli** > **Modelli di consegna**.
1. Duplica il modello **[!UICONTROL Send via email]** fornito.
1. Selezionate il modello duplicato.
1. Fate clic sul pulsante **[!UICONTROL Edit properties]** per modificare le proprietà del modello.
1. Espandere la sezione **[!UICONTROL Send]**.
1. Selezionare la casella **[!UICONTROL Archive emails]** per conservare una copia di tutti i messaggi inviati per ogni consegna basata su questo modello.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Se le e-mail inviate all&#39;indirizzo CCN vengono aperte e su cui si fa clic, queste verranno prese in considerazione nelle **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** dell&#39;analisi di invio, il che potrebbe causare errori di calcolo.