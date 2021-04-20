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
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '848'
ht-degree: 5%

---


# Guida introduttiva all’integrazione con Microsoft Dynamics 365

Attiva i dati CRM sulla comunicazione cross-channel: scopri come passare i contatti da Microsoft Dynamics 365 ad Adobe Campaign e condividere i dati sulle prestazioni delle campagne (invii, aperture, clic e mancati recapiti) da Adobe Campaign a Microsoft Dynamics 365.

Questa integrazione richiede le seguenti versioni software:

* Microsoft Dynamics 365 solo per vendita online, versione più recente

* Adobe Campaign Standard, versione più recente

>[!CAUTION]
>
>Questa funzionalità non è disponibile come funzione predefinita del prodotto. La sua implementazione richiede l’intervento della Consulenza Adobe. Per maggiori informazioni, contatta un rappresentante Adobe di fiducia.


## Principi

L’integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema CRM, rendendo disponibili tutti i dati di contatto pertinenti per le attività della campagna.

Al contrario, in qualità di profili all’interno di Adobe Campaign Standard interagiscono con i messaggi, tali dati (ad esempio: invia, apre, fa clic e non recapitato) automaticamente in Microsoft Dynamics 365 per mantenere i record di contatto completi anche con l’attività di marketing.

L’integrazione supporta anche l’abilitazione di [entità personalizzate](../../integrating/using/d365-acs-self-service-app-settings.md) in Dynamics 365 per la sincronizzazione con le corrispondenti **risorse personalizzate** in Campaign.

Questa integrazione è stata progettata per supportare quattro casi d’uso principali:

1. Sincronizzazione dei contatti da Dynamics 365 a Campaign in modo che possano essere indirizzati nelle campagne di marketing
1. Sincronizzazione di entità personalizzate da Dynamics 365 a Campaign per utilizzarle per la segmentazione e la personalizzazione
1. Invio di eventi di marketing e-mail (invii, aperture, clic, mancati recapiti) da Campaign a Dynamics 365 per visualizzarli nell’archivio delle vendite nell’interfaccia di Dynamics 365
1. Sincronizzazione degli stati di rinuncia (ad esempio, non inviare e-mail) tra Dynamics 365 e Campaign per mantenere le preferenze sulla privacy dei clienti.

I vantaggi principali sono:

* Messaggistica coerente tra vendite e marketing: l’integrazione di Adobe Campaign Standard con l’integrazione con Dynamics 365 consente a entrambi i sistemi di accedere alle informazioni sui clienti e alla cronologia delle e-mail marketing, consentendo a tutti i messaggi al cliente di condividere gli stessi messaggi coerenti.

* Vista olistica di tutti i dati relativi a potenziali clienti e clienti: integrando Adobe Campaign Standard con Dynamics 365, è possibile condividere e accedere alla cronologia di marketing e-mail su ogni contatto dal sistema CRM.

* Attiva i dati di Dynamics 365 su qualsiasi canale: con i dati di contatto sincronizzati con Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, compresi push mobile, in-app, e-mail o direct mail. Campagna &quot;ti sei coperto&quot; indipendentemente dal canale preferito da ogni contatto.

>[!CAUTION]
>
>Questa integrazione considera Dynamics 365 come l’origine della verità per il contatto e la sincronizzazione personalizzata delle entità.  Eventuali modifiche agli attributi sincronizzati devono essere eseguite in Dynamics 365, non in Adobe Campaign Standard.  Se le modifiche vengono apportate in Campaign, possono essere successivamente sovrascritte durante la sincronizzazione.


## Passaggi chiave per l’implementazione dell’integrazione con Microsoft Dynamics 365{#request-and-implement-this-integration}

Per eseguire il provisioning di questa integrazione, segui i passaggi riportati di seguito.

Per richiedere e configurare l’integrazione, segui i dettagli del diagramma di flusso e del diagramma di flusso qui sotto.

![](assets/provisioning-wf.png)

Dettagli diagramma di flusso (mappa ai passaggi precedenti):

* **Passaggio 1** : si presume che tu abbia già o stia effettuando l’acquisto di una licenza per Microsoft Dynamics 365 per le vendite e per Adobe Campaign Standard.
* **Passaggio 2**  - L&#39;offerta di integrazione standard è gratuita per tutti i clienti; tuttavia, possono essere applicati costi aggiuntivi in base alle tue esigenze. Ulteriori informazioni su [Best practice e limitazioni](../../integrating/using/d365-acs-notices-and-recommendations.md). Per usufruire dell&#39;integrazione, sarà necessario firmare un nuovo ordine di vendita (SO) se non è stato incluso nell&#39;SO originale.
* **Passaggio 3** : completa i passaggi precedenti all’integrazione per Dynamics 365 e Campaign. Consulta [Configurare questa integrazione](#configure-this-integration).
* **Passaggio 4**  - Il team di onboarding Adobe ti fornirà l&#39;accesso all&#39;interfaccia utente dell&#39;applicazione di integrazione (UI).
* **Passaggio 5** : puoi configurare le mappature dei dati, le sostituzioni, i filtri, ecc. e verifica l’integrazione dall’interfaccia utente dell’applicazione di integrazione.

   >[!IMPORTANT]
   >
   > Se hai bisogno della configurazione di rinuncia bidirezionale o Campaign a Dynamics 365, dovrai effettuare la richiesta al contatto tecnico Adobe per impostare i flussi di lavoro di rinuncia nell’istanza Campaign. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configura questa integrazione {#configure-this-integration}

Per questa integrazione è necessario eseguire il provisioning e configurare tre sistemi:

* **Adobe Campaign Standard**: devi configurare l’accesso API e configurare una nuova integrazione per lo strumento di integrazione. A questo scopo, fai riferimento a [questo articolo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: devi creare una nuova registrazione dell&#39;app e abilitare un utente dell&#39;applicazione per utilizzare l&#39;integrazione.  Per configurare Microsoft Dynamics 365 per questa integrazione, consulta [questo articolo](../../integrating/using/d365-acs-configure-d365.md).
* **Integrazione di Adobe Campaign Standard con l’app** self-service di Microsoft Dynamics 365: dovrai seguire i passaggi descritti in  [questo articolo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Per ogni sistema, questi passaggi devono essere eseguiti da un **amministratore**.
>
>I passaggi di questa documentazione ti guideranno attraverso la creazione di integrazioni/registrazioni che richiedono l’assegnazione di autorizzazioni e/o l’accesso dell’amministratore.  È tua responsabilità assicurarsi che questi passaggi siano conformi alle politiche aziendali prima di eseguire e eseguirli con attenzione.


### Richiedi supporto

I ticket di assistenza possono essere registrati con l’Assistenza clienti Adobe.

Per qualsiasi problema relativo ai flussi di dati di integrazione, accertati di includere le seguenti informazioni:

* **Proprietario** del processo: Architetti di ingegneria
* **ID** processo ES: Fornito durante il processo di onboarding
* **Titolo** del processo: Integrazione con Microsoft Dynamics 365 / Adobe Campaign Standard
* **Descrizione** del problema: Descrizione del problema

La copertura del supporto per l&#39;integrazione è attualmente di 24 ore su 24, 5 giorni su 7 (dal lunedì al venerdì, esclusi i periodi di Adobe e di pausa).
