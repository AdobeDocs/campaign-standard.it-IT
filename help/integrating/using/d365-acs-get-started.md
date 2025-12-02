---
title: Introduzione all’integrazione con Microsoft Dynamics 365
description: Scopri come iniziare a utilizzare l’integrazione con Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 4%

---

# Introduzione all’integrazione con Microsoft Dynamics 365

Attiva i dati CRM sulla comunicazione cross-channel: scopri come trasmettere i contatti da Microsoft Dynamics 365 ad Adobe Campaign e condividere i dati delle prestazioni della campagna (invii, aperture, clic e mancati recapiti) da Adobe Campaign a Microsoft Dynamics 365.

Questa integrazione richiede le seguenti versioni software:

* Microsoft Dynamics 365 solo per vendite online, ultima versione

* Adobe Campaign Standard, versione più recente

>[!CAUTION]
>
>Questa funzionalità non è disponibile come funzione predefinita del prodotto. La sua implementazione richiede l’intervento della Consulenza Adobe. Per maggiori informazioni, contatta un rappresentante Adobe di fiducia.
>

## Principi

L’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema di gestione delle relazioni con i clienti, rendendo disponibili tutti i dati di contatto rilevanti per le attività della campagna.

Al contrario, quando i profili all’interno di Adobe Campaign Standard interagiscono con i messaggi, tali dati (ad esempio, invii, aperture, clic e mancati recapiti) fluiscono automaticamente in Microsoft Dynamics 365 per mantenere i record dei contatti completi anche dell’attività di marketing.

L&#39;integrazione supporta anche l&#39;abilitazione di [entità personalizzate](../../integrating/using/d365-acs-self-service-app-settings.md) in Dynamics 365 per la sincronizzazione con le **risorse personalizzate** corrispondenti in Campaign.

Questa integrazione è progettata per supportare quattro casi d’uso principali:

1. Sincronizzazione dei contatti da Dynamics 365 a Campaign per includerli nelle campagne di marketing
1. Sincronizzazione delle entità personalizzate da Dynamics 365 a Campaign per utilizzarle per la segmentazione e la personalizzazione
1. Invio di eventi di marketing e-mail (invii, aperture, clic e mancati recapiti) da Campaign a Dynamics 365 per la visualizzazione nell’archivio delle vendite nell’interfaccia di Dynamics 365
1. Sincronizzazione degli stati di rinuncia (ad es., non inviare e-mail) tra Dynamics 365 e Campaign per mantenere le preferenze di privacy dei clienti.

I principali vantaggi sono:

* Messaggistica coerente tra vendite e marketing: l’integrazione di Adobe Campaign Standard con l’integrazione di Dynamics 365 consente a entrambi i sistemi di accedere alla cronologia di marketing del cliente insight e dell’e-mail, consentendo a tutti i messaggi inviati al cliente di condividere lo stesso messaggio coerente.

* Vista olistica di tutti i dati dei clienti e dei potenziali clienti: integrando Adobe Campaign Standard con Dynamics 365, è possibile condividere e accedere alla cronologia del marketing e-mail su ogni contatto dall’interno del sistema di gestione delle relazioni con i clienti.

* Attiva i dati di Dynamics 365 su qualsiasi canale: con i dati di contatto sincronizzati con Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, incluso mobile push, in-app, e-mail o direct mail. La campagna &quot;ti ha coperto&quot; indipendentemente dal canale preferito da ciascun contatto.

>[!CAUTION]
>
>Questa integrazione considera Dynamics 365 come l’origine di riferimento per la sincronizzazione di contatti ed entità personalizzate.  Eventuali modifiche agli attributi sincronizzati devono essere eseguite in Dynamics 365 e non in Adobe Campaign Standard.  Se vengono apportate modifiche in Campaign, queste possono eventualmente essere sovrascritte durante la sincronizzazione.
>

## Passaggi chiave per implementare l’integrazione con Microsoft Dynamics 365{#request-and-implement-this-integration}

Per eseguire il provisioning di questa integrazione, segui i passaggi indicati di seguito.

Per richiedere e configurare l’integrazione, segui i dettagli del diagramma di flusso e del diagramma di flusso riportati di seguito.

![](assets/provisioning-wf.png)

Dettagli del diagramma di flusso (mappa ai passaggi precedenti):

* **Passaggio 1** - Si presume che si disponga già di una licenza per Microsoft Dynamics 365 per Sales e per Adobe Campaign Standard o che si stia per acquistarla.
* **Passaggio 2** - L&#39;offerta di integrazione standard è gratuita per tutti i clienti; tuttavia, potrebbero essere applicati costi aggiuntivi a seconda delle tue esigenze. Ulteriori informazioni su [Best practice e limitazioni](../../integrating/using/d365-acs-notices-and-recommendations.md). Sarà necessario firmare un nuovo ordine di vendita (CA) per poter trarre vantaggio dall&#39;integrazione se non è stato incluso nella CA originale.
* **Passaggio 3** - Completare i passaggi di preintegrazione per Dynamics 365 e Campaign. Consulta [Configurare questa integrazione](#configure-this-integration).
* **Passaggio 4** - Il team di onboarding di Adobe ti fornirà l&#39;accesso all&#39;interfaccia utente dell&#39;applicazione di integrazione.
* **Passaggio 5** - Potrai configurare mappature dati, sostituzioni, filtri, ecc. e verifica l’integrazione dall’interfaccia utente dell’applicazione di integrazione.

  >[!IMPORTANT]
  >
  > Se hai bisogno della configurazione di rinuncia bidirezionale o da Campaign a Dynamics 365, dovrai richiedere al tuo contatto tecnico Adobe di configurare i flussi di lavoro di rinuncia nell’istanza Campaign. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configura questa integrazione {#configure-this-integration}

Per questa integrazione è necessario eseguire il provisioning e la configurazione di tre sistemi:

* **Adobe Campaign Standard**: è necessario impostare l&#39;accesso API e configurare una nuova integrazione per lo strumento di integrazione. Per ottenere questo risultato, fare riferimento a [questo articolo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: è necessario creare una nuova registrazione dell&#39;app e consentire a un utente dell&#39;applicazione di utilizzare l&#39;integrazione.  Per configurare Microsoft Dynamics 365 per questa integrazione, consultare [questo articolo](../../integrating/using/d365-acs-configure-d365.md).
* Integrazione di **Adobe Campaign Standard con l&#39;app self-service Microsoft Dynamics 365**: segui i passaggi descritti in [questo articolo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Per ogni sistema, questi passaggi devono essere eseguiti da un **amministratore**.
>
>I passaggi descritti in questa documentazione ti guideranno attraverso la creazione di integrazioni/registrazioni che richiedono l’assegnazione di autorizzazioni e/o l’accesso come amministratore.  È tua responsabilità accertarti che questi passaggi siano conformi alle politiche aziendali prima di eseguire e di eseguirli con attenzione.
>

### Richiedi supporto

I ticket di supporto possono essere registrati presso l’Assistenza clienti di Adobe.

Per qualsiasi problema relativo ai flussi di dati di integrazione, assicurati di includere le seguenti informazioni:

* **Proprietario processo**: ingegneri
* **ID processo ES**: fornito durante il processo di onboarding
* **Titolo processo**: integrazione Microsoft Dynamics 365 / Adobe Campaign Standard
* **Descrizione problema**: descrizione del problema

La copertura del supporto dell’integrazione è attualmente 24x5 (disponibile dal lunedì al venerdì, esclusi i giorni festivi e i periodi di pausa di Adobe).
