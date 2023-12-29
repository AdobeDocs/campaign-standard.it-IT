---
title: Guida introduttiva all’integrazione con Microsoft Dynamics 365
description: Scopri come iniziare a utilizzare l’integrazione con Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 4%

---

# Guida introduttiva all’integrazione con Microsoft Dynamics 365

Attiva i dati CRM sulla comunicazione cross-channel: scopri come trasferire i contatti da Microsoft Dynamics 365 a Adobe Campaign e condividere i dati delle prestazioni della campagna (invii, aperture, clic e mancati recapiti) da Adobe Campaign a Microsoft Dynamics 365.

Questa integrazione richiede le seguenti versioni software:

* Microsoft Dynamics 365 solo per vendite online, versione più recente

* Adobe Campaign Standard, versione più recente

>[!CAUTION]
>
>Questa funzionalità non è disponibile come funzione predefinita del prodotto. La sua implementazione richiede l’intervento della Consulenza Adobe. Per maggiori informazioni, contatta un rappresentante Adobe di fiducia.
>

## Principi

L’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema di gestione delle relazioni con i clienti, rendendo disponibili tutti i dati di contatto rilevanti per le attività della campagna.

Al contrario, quando i profili all’interno di Adobe Campaign Standard interagiscono con i messaggi, tali dati (ad esempio, invii, aperture, clic e mancati recapiti) fluiscono automaticamente in Microsoft Dynamics 365 per mantenere i record dei contatti completi anche dell’attività di marketing.

L’integrazione supporta anche l’abilitazione di [entità personalizzate](../../integrating/using/d365-acs-self-service-app-settings.md) in Dynamics 365 da sincronizzare con **risorse personalizzate** in Campaign.

Questa integrazione è progettata per supportare quattro casi d’uso principali:

1. Sincronizzazione dei contatti da Dynamics 365 a Campaign per includerli nelle campagne di marketing
1. Sincronizzazione delle entità personalizzate da Dynamics 365 a Campaign per utilizzarle per la segmentazione e la personalizzazione
1. Invio di eventi di marketing e-mail (invii, aperture, clic e mancati recapiti) da Campaign a Dynamics 365 per la visualizzazione nell’archivio delle vendite nell’interfaccia di Dynamics 365
1. Sincronizzazione degli stati di rinuncia (ad es., non inviare e-mail) tra Dynamics 365 e Campaign per mantenere le preferenze di privacy dei clienti.

I principali vantaggi sono:

* Messaggistica coerente tra vendite e marketing: l’integrazione di Adobe Campaign Standard con l’integrazione di Dynamics 365 consente a entrambi i sistemi di accedere alle informazioni sul cliente e alla cronologia del marketing via e-mail, consentendo a tutti i messaggi inviati al cliente di condividere la stessa messaggistica coerente.

* Vista olistica di tutti i dati dei clienti e dei potenziali clienti: integrando Adobe Campaign Standard con Dynamics 365, è possibile condividere e accedere alla cronologia del marketing e-mail su ogni contatto dall’interno del sistema di gestione delle relazioni con i clienti.

* Attiva i dati di Dynamics 365 su qualsiasi canale: con i dati di contatto sincronizzati con Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, incluso mobile push, in-app, e-mail o direct mail. La campagna &quot;ti ha coperto&quot; indipendentemente dal canale preferito da ciascun contatto.

>[!CAUTION]
>
>Questa integrazione considera Dynamics 365 come l’origine di riferimento per la sincronizzazione di contatti ed entità personalizzate.  Eventuali modifiche agli attributi sincronizzati devono essere eseguite in Dynamics 365 e non in Adobe Campaign Standard.  Se vengono apportate modifiche in Campaign, queste possono eventualmente essere sovrascritte durante la sincronizzazione.
>

## Passaggi chiave per implementare l’integrazione di Microsoft Dynamics 365{#request-and-implement-this-integration}

Per eseguire il provisioning di questa integrazione, segui i passaggi indicati di seguito.

Per richiedere e configurare l’integrazione, segui i dettagli del diagramma di flusso e del diagramma di flusso riportati di seguito.

![](assets/provisioning-wf.png)

Dettagli del diagramma di flusso (mappa ai passaggi precedenti):

* **Passaggio 1** - Si presume che si disponga già di una licenza per Microsoft Dynamics 365 per Sales e per Adobe Campaign Standard o che si stia procedendo all&#39;acquisto di tale licenza.
* **Passaggio 2** - L&#39;offerta di integrazione standard è gratuita per tutti i clienti; tuttavia, potrebbero essere previsti costi aggiuntivi a seconda delle esigenze. Ulteriori informazioni su [Best practice e limitazioni](../../integrating/using/d365-acs-notices-and-recommendations.md). Sarà necessario firmare un nuovo ordine di vendita (CA) per poter trarre vantaggio dall&#39;integrazione se non è stato incluso nella CA originale.
* **Passaggio 3** : completa i passaggi di pre-integrazione per Dynamics 365 e Campaign. Consulta [Configura questa integrazione](#configure-this-integration).
* **Passaggio 4** : il team di onboarding di Adobe ti fornirà l’accesso all’interfaccia utente dell’applicazione di integrazione.
* **Passaggio 5** : potrai configurare mappature di dati, sostituzioni, filtri e così via. e verifica l’integrazione dall’interfaccia utente dell’applicazione di integrazione.

  >[!IMPORTANT]
  >
  > Se hai bisogno della configurazione di rinuncia bidirezionale o da Campaign a Dynamics 365, dovrai richiedere al tuo contatto tecnico Adobe di impostare i flussi di lavoro di rinuncia nell’istanza Campaign. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configura questa integrazione {#configure-this-integration}

Per questa integrazione è necessario eseguire il provisioning e la configurazione di tre sistemi:

* **Adobe Campaign Standard**: devi impostare l’accesso API e configurare una nuova integrazione per lo strumento di integrazione. Per ottenere questo risultato, consulta [questo articolo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: devi creare una nuova registrazione all’app e consentire a un utente dell’applicazione di utilizzare l’integrazione.  Per configurare Microsoft Dynamics 365 per questa integrazione, fare riferimento a [questo articolo](../../integrating/using/d365-acs-configure-d365.md).
* **Integrazione di Adobe Campaign Standard con l’app self-service Microsoft Dynamics 365**: dovrai seguire i passaggi descritti in [questo articolo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Per ogni sistema, questi passaggi devono essere eseguiti da un **amministratore**.
>
>I passaggi descritti in questa documentazione ti guideranno attraverso la creazione di integrazioni/registrazioni che richiedono l’assegnazione di autorizzazioni e/o l’accesso come amministratore.  È tua responsabilità accertarti che questi passaggi siano conformi alle politiche aziendali prima di eseguire e di eseguirli con attenzione.
>

### Richiedi supporto

I ticket di supporto possono essere registrati con l’Assistenza clienti di Adobe.

Per qualsiasi problema relativo ai flussi di dati di integrazione, assicurati di includere le seguenti informazioni:

* **Proprietario processo**: ingegneri
* **ID processo ES**: fornito durante il processo di onboarding
* **Titolo processo**: integrazione Microsoft Dynamics 365/Adobe Campaign Standard
* **Descrizione problema**: descrizione del problema

La copertura del supporto dell’integrazione è attualmente 24x5 (disponibile dal lunedì al venerdì, esclusi i giorni festivi e i periodi di pausa degli Adobi).
