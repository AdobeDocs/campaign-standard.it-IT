---
solution: Campaign Standard
product: campaign
title: Archiviazione di messaggi in Adobe Campaign Standard
description: Scopri come archiviare le e-mail con Adobe Campaign Standard utilizzando un indirizzo e-mail CCN.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: Business Practitioner
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
translation-type: tm+mt
source-git-commit: f7d77f524a6c141066056e53fc8616f35189fc39
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 6%

---

# Archiviazione di e-mail con indirizzi Ccn{#archiving-emails}

Puoi configurare Adobe Campaign per mantenere una copia delle e-mail inviate dalla piattaforma tramite CCN e-mail.

In particolare, se la tua organizzazione deve archiviare tutti i messaggi e-mail in uscita per garantire la conformità, puoi abilitare questa funzionalità. Ti consente di inviare una copia nascosta esatta dei messaggi inviati corrispondenti a un indirizzo e-mail CCN (invisibile ai destinatari della consegna) che devi specificare.

Una volta attivato, è necessario attivare Ccn e-mail dall’opzione **[!UICONTROL Archive emails]** nel modello di consegna e-mail.

>[!NOTE]
>
>Adobe Campaign non gestisce i file archiviati. Permette infatti di inviare i messaggi di tua scelta a un indirizzo dedicato, dal quale possono essere elaborati e archiviati utilizzando un sistema esterno.

## Recommendations e limitazioni {#recommendations-and-limitations}

* Questa funzione è facoltativa. Controlla il contratto di licenza e contatta il responsabile dell’account per attivarla.
* L’indirizzo CCN desiderato deve essere fornito al team di Adobe che lo configurerà per te.
* Puoi utilizzare un solo indirizzo e-mail CCN.
* Vengono prese in considerazione solo le e-mail inviate con successo. I rimbalzi non lo sono.
* Per motivi di privacy, le e-mail CCN devono essere elaborate da un sistema di archiviazione in grado di memorizzare informazioni personali (PII) sicure.
* Quando crei un nuovo modello di consegna, Ccn e-mail non è abilitato per impostazione predefinita, anche se l’opzione è stata acquistata. Devi attivarlo manualmente in ogni modello di consegna in cui desideri utilizzarlo.

>[!NOTE]
>
>Attualmente le e-mail archiviate vengono ancora inviate dal modulo di archiviazione legacy, che utilizza un semplice relay SMTP.

## Attivazione dell&#39;archiviazione dei messaggi e-mail {#activating-email-archiving}

Una volta abilitato, Ccn e-mail viene attivato nel [modello e-mail](../../start/using/marketing-activity-templates.md) tramite un&#39;opzione dedicata:

1. Vai a **Risorse** > **Modelli** > **Modelli di consegna**.
1. Duplica il modello preconfigurato **[!UICONTROL Send via email]** .
1. Seleziona il modello duplicato.
1. Fai clic sul pulsante **[!UICONTROL Edit properties]** per modificare le proprietà del modello.
1. Espandi la sezione **[!UICONTROL Send]**.
1. Seleziona la casella **[!UICONTROL Archive emails]** per conservare una copia di tutti i messaggi inviati per ogni consegna basata su questo modello.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Se le e-mail inviate all’indirizzo CCN vengono aperte e fai clic su di esse, verranno prese in considerazione nelle sezioni **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** dell’analisi di invio, il che potrebbe causare errori di calcolo.
