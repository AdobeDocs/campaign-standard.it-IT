---
title: Guida introduttiva all’integrazione con Microsoft Dynamics 365
description: Scopri come iniziare a utilizzare l'integrazione con Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 10%

---


# Guida introduttiva all’integrazione con Microsoft Dynamics 365

Attiva i dati CRM sulla comunicazione tra canali: scopri come trasferire i contatti da Microsoft Dynamics 365 a  Adobe Campaign e condividere i dati sulle prestazioni delle campagne (invii, aperture, clic e rimbalzi) da  Adobe Campaign a Microsoft Dynamics 365.

Le versioni supportate sono elencate [in questa sezione](#support-software-versions).

>[!CAUTION]
>
>Questa funzionalità non è disponibile come funzione predefinita del prodotto. La sua implementazione richiede l’intervento della Consulenza Adobe. Per maggiori informazioni, contatta un rappresentante Adobe di fiducia.

## Principi

L&#39;integrazione  Adobe Campaign e Microsoft Dynamics 365 consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema CRM, rendendo disponibili tutti i dati di contatto pertinenti per le attività della campagna.

Al contrario, come profili all&#39;interno  Adobe Campaign interagiscono con i messaggi, tali dati (ad es.: invia, apre, fa clic e rimbalza) automaticamente in Microsoft Dynamics 365 per tenere i record di contatto completi anche con l&#39;attività di marketing.

L&#39;integrazione supporta anche entità personalizzate, consentendo la sincronizzazione delle entità [](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) personalizzate in Dynamics 365 con le entità personalizzate corrispondenti in Campaign.

Questa integrazione è stata progettata per supportare quattro casi di utilizzo principali:

1. Sincronizzazione dei contatti da Dynamics 365 a Campaign in modo che possano essere indirizzati alle campagne di marketing
1. Sincronizzazione di entità personalizzate da Dynamics 365 a Campaign per consentirne l&#39;utilizzo per la segmentazione e la personalizzazione
1. Invio di eventi di marketing tramite e-mail (invii, aperture, clic e rimbalzi) da Campaign a Dynamics 365 per visualizzare l&#39;archivio vendite nell&#39;interfaccia di Dynamics 365
1. Sincronizzazione degli stati di rifiuto (ad es. non inviare via e-mail) tra Dynamics 365 e ACS per mantenere le preferenze sulla privacy dei clienti.

## Vantaggi principali

* Messaggistica coerente tra vendite e marketing

L&#39;integrazione  Adobe Campaign e Microsoft Dynamics 365 consente a entrambi i sistemi di accedere alle informazioni sui clienti e alla cronologia marketing delle e-mail, consentendo a tutti i messaggi al cliente di condividere gli stessi messaggi coerenti.

* Vista olistica di tutti i dati di potenziali clienti

Integrando  Adobe Campaign con Dynamics 365, è possibile condividere e accedere alla cronologia marketing delle e-mail su ogni contatto dall&#39;interno del sistema CRM.

* Attiva dati Dynamics 365 su qualsiasi canale

Con i dati di contatto sincronizzati su  Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, inclusi push mobile, in-app, e-mail o posta diretta. Indipendentemente dal canale preferito da ciascun contatto, Campaign ha coperto i dati.

>[!CAUTION]
>
>Per la sincronizzazione di contatti e entità personalizzata, questa integrazione considera Dynamics 365 come l&#39;origine della verità.  Eventuali modifiche agli attributi sincronizzati devono essere apportate in Dynamics 365, non in Campaign.  Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte durante la sincronizzazione.

## Versioni software di supporto {#support-software-versions}

Questa integrazione richiede le seguenti versioni software:

* Microsoft Dynamics 365 per Vendite online, versione più recente

*  Adobe Campaign Standard, ultima versione
