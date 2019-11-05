---
title: Informazioni su Adobe Experience Cloud Triggers
description: Tracciando comportamenti specifici dei clienti con Adobe Analytics, ora puoi inviare e-mail personalizzate ai tuoi clienti in Adobe Campaign.
page-status-flag: mai attivato
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: utilizzo di attivatori per campagne
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,panoramica;trigger,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni su Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

L'integrazione tra il servizio di base Attivazione di Experience Cloud **[!UICONTROL Triggers]** e Adobe Campaign consente di inviare e-mail personalizzate ai clienti come reazione a comportamenti specifici tracciati sul sito Web da Adobe Analytics (entro 15 minuti).

In Adobe Experience Cloud, puoi definire i diversi attivatori, vale a dire i comportamenti dei clienti che desideri monitorare, come tutti i clienti che hanno abbandonato la visita sul tuo sito Web, che hanno effettuato una ricerca sul tuo sito Web, ma che non hanno effettuato un acquisto, né i clienti la cui sessione è scaduta. Quando crei un attivatore, definisci la condizione del trigger e i dati che verranno inviati nell'evento (caricamento) ad Adobe Campaign.

 In Adobe Campaign, selezionate l'attivatore precedentemente creato, arricchite i dati dell'evento con i dati del datamart e definite un modello di messaggio transazionale collegato a tale attivatore. Ad esempio, quando un cliente abbandona la visita sul sito Web, un evento viene inviato ad Adobe Campaign, che può quindi sfruttare l'evento tramite un'e-mail di remarketing inviata al cliente entro 15 minuti.

**Argomenti correlati:**

* Scopri i diversi tipi di trigger: Documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)Adobe Experience Cloud.
* Guardate il video [Trigger Note Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) (Attivazione dei messaggi di commento in base alle attivitàdel sito).
* Scopri i nostri due casi di utilizzo [di Triggers di abbandono](../../integrating/using/abandonment-triggers-use-cases.md).

## Attiva il processo utente {#triggers-user-process}

>[!CAUTION]
>
>Prima di eseguire i passaggi utente principali, è necessario configurare la funzionalità. Per ulteriori informazioni, consulta [Attivazione della funzionalità](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configurazione di soluzioni e servizi](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) e [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

I passaggi principali del processo utente, in Adobe Campaign, sono:

1. Crea un evento di attivazione collegato a un trigger Adobe Experience Cloud esistente.
1. Pubblicate l'evento di attivazione.
1. Definire il contenuto del modello di messaggio transazionale.
1. Verificate il modello (create un profilo di test e inviate una prova).
1. Pubblicate il modello di messaggio transazionale.

I casi di utilizzo completi sono descritti in [questa sezione](../../integrating/using/abandonment-triggers-use-cases.md).

## Note importanti {#important-notes}

Di seguito sono riportate alcune note importanti da tenere in considerazione prima di utilizzare Triggers - Integrazione della campagna:

* Le notifiche push non sono supportate per gli attivatori. Sono supportati solo e-mail e SMS.
* Puoi arricchire il trigger con metadati acquisiti tramite Analytics, ad esempio ID e-mail, nome pagina e così via.
* Puoi riconciliare l'attivatore con un profilo memorizzato in Campaign Standard e utilizzare i campi del profilo per personalizzare il messaggio.
* Non appena viene ricevuto, l'attivatore viene elaborato, riconciliato e inviato. Ci vogliono circa 5-15 minuti a seconda del volume di attivatori ricevuti, del numero di campi di personalizzazione utilizzati nel modello.

>[!NOTE]
>
>Per ulteriori informazioni su best practice e limitazioni tecniche, consulta [Triggers, procedure ottimali e limitazioni](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

