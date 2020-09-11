---
title: Richiedere e configurare l’integrazione con Microsoft Dynamics 365
description: Scopri come richiedere e configurare Microsoft Dynamics 365 con integrazione Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e90f878814e65a9a61ee4013d94fd0bf3b1f7875
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# Richiedere e configurare l’integrazione con Microsoft Dynamics 365

Per eseguire il provisioning di questa integrazione, è necessario seguire i passaggi indicati di seguito.

Seguite i dettagli del diagramma di flusso e del diagramma di flusso riportati di seguito per richiedere e configurare l&#39;integrazione.

![](assets/provisioning-wf.png)

Dettagli diagramma di flusso (mappatura ai passaggi precedenti):

* **Passaggio 1** - Si presume che si sia già in procinto di acquistare una licenza per Microsoft Dynamics 365 per le vendite e per  Adobe Campaign Standard.

* **Fase 2** - L&#39;offerta standard di integrazione è gratuita per tutti i clienti; tuttavia, possono essere applicati costi aggiuntivi in base alle esigenze (vedere [Garanzie e limiti](../../integrating/using/ms-dynamics-365-integration-guardrails.md)di integrazione). Per sfruttare l&#39;integrazione, sarà necessario firmare un nuovo ordine di vendita.

* **Passaggio 3** - Completa i passaggi preliminari all&#39;integrazione per Dynamics 365 e Campaign. Consultate [Configurare questa integrazione](#configure-this-integration).

* **Passaggi 4-7** - Il team di configurazione del Adobe  collaborerà con voi durante il processo di onboarding.

## Configurare questa integrazione {#configure-this-integration}

Per questa integrazione è necessario configurare tre sistemi:  Adobe Campaign Standard, Microsoft Dynamics 365 per le vendite e lo strumento di integrazione. Gli articoli di configurazione sono collegati di seguito.

>[!CAUTION]
>
>Per ciascun sistema, questi passaggi devono essere eseguiti da un amministratore.
>
>I passaggi descritti negli articoli di seguito guidano l&#39;utente nella creazione di integrazioni/registrazioni che richiedono l&#39;assegnazione di autorizzazioni e/o l&#39;accesso dell&#39;amministratore.  È responsabilità dell&#39;utente assicurarsi che questi passaggi siano conformi alle politiche aziendali prima di eseguire e di eseguirli con attenzione.

In  ADOBE CAMPAIGN, è necessario configurare l&#39;accesso alle API e una nuova integrazione per lo strumento di integrazione. A tal fine, consultate [questo articolo](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

In MICROSOFT DYNAMICS 365, è necessario creare una nuova registrazione dell&#39;app e consentire a un utente dell&#39;applicazione di utilizzare l&#39;integrazione.  Per configurare Microsoft Dynamics 365 per questa integrazione, consultare [questo articolo](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Dovrete collaborare con il team di configurazione del Adobe  per configurare la configurazione per i flussi di dati di ingresso, uscita e rinuncia.


## Richiedi assistenza

I biglietti di supporto possono essere registrati con  Adobe Custom Care, come al solito; Se necessario, l&#39;Assistenza clienti fornirà il personale di supporto.

Per qualsiasi problema relativo ai flussi di dati di integrazione, accertatevi di includere la suite di rapporti come parte della descrizione del problema, così come le seguenti informazioni:

* Proprietario processo: Architetti di ingegneria

* ID processo ES: [Fornito durante il processo di onboarding]

* Titolo processo: Integrazione Adobe Campaign Standard Dynamics 365 / 

* Descrizione problema: [Descrizione del problema]

La copertura del supporto per l&#39;integrazione è attualmente di 24 ore su 24, 5 giorni su 5 (dal lunedì al venerdì, esclusi  giorni festivi e di pausa per il Adobe).