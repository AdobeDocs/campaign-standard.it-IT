---
title: Introduzione all'integrazione con Microsoft Dynamics 365
description: Scopri come iniziare a utilizzare l'integrazione con Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21135f27fd1d8297edd3dd067446d09c39de9f4f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---


# Introduzione all&#39;integrazione con Microsoft Dynamics 365

>[!IMPORTANT]
>
>Questa integrazione non è al momento disponibile. È in corso di sviluppo un nuovo connettore che sarà disponibile in futuro. Per ulteriori informazioni, contattate il rappresentante commerciale di Adobe.

Attiva i dati CRM sulla comunicazione tra canali: scopri come trasferire i contatti da Microsoft Dynamics 365 ad Adobe Campaign e condividere i dati sulle prestazioni delle campagne (invii, aperture, clic e rimbalzi) da Adobe Campaign a Microsoft Dynamics 365.

>[!NOTE]
>
>L&#39;integrazione con Microsoft Dynamics 365 / Adobe Campaign Standard supporta solo l&#39;app **Vendite** Microsoft Dynamics 365.

## Principi

L&#39;integrazione di Adobe Campaign e Microsoft Dynamics 365 consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema CRM, rendendo disponibili tutti i dati di contatto pertinenti per le attività della campagna.

Al contrario, come profili all&#39;interno di Adobe Campaign interagiscono con i messaggi, tali dati (ad es.: invia, apre, fa clic e rimbalza) automaticamente in Microsoft Dynamics 365 per tenere i record Contatto completi anche con l&#39;attività di marketing.

L&#39;ultima versione dell&#39;integrazione aggiunge anche il supporto per le entità personalizzate, consentendo la sincronizzazione delle entità personalizzate in Dynamics 365 con le entità personalizzate corrispondenti in Campaign.

Questa integrazione è stata progettata per supportare tre casi di utilizzo principali:

1. Sincronizzazione dei contatti da Dynamics 365 a Campaign per consentire il targeting dei contatti nelle campagne di marketing
1. Invio di eventi di marketing tramite e-mail (invii, aperture, clic e rimbalzi) da Campaign a Dynamics 365 per visualizzare l&#39;archivio vendite nell&#39;interfaccia di Dynamics 365
1. Sincronizzazione di entità personalizzate da Dynamics 365 a Campaign per consentirne l&#39;utilizzo per la segmentazione e la personalizzazione

## Vantaggi principali

* Messaggistica coerente tra vendite e marketing

L&#39;integrazione di Adobe Campaign e Microsoft Dynamics 365 consente a entrambi i sistemi di accedere alle informazioni sui clienti e alla cronologia del marketing delle e-mail, consentendo a tutti i messaggi al cliente di condividere gli stessi messaggi coerenti.

* Vista olistica di tutti i dati di potenziali clienti

Integrando Adobe Campaign con Dynamics 365, è possibile condividere e accedere alla cronologia marketing delle e-mail su ogni contatto dal sistema CRM.

* Attiva dati Dynamics 365 su qualsiasi canale

Con i dati di contatto sincronizzati con Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, inclusi push mobile, in-app, e-mail o posta diretta. Indipendentemente dal canale preferito da ogni Contatti, Campaign ha coperto la questione.

>[!CAUTION]
>
>Per la sincronizzazione dei contatti, questa integrazione considera Dynamics 365 come l&#39;origine della verità.  Eventuali modifiche agli attributi di contatto sincronizzati devono essere apportate in Dynamics 365, non in Campaign.  Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte durante la sincronizzazione.
