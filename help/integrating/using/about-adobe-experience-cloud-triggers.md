---
title: Informazioni su Adobe Experience Cloud Triggers
description: Tracciando comportamenti specifici dei clienti con Adobe Analytics, ora puoi inviare e-mail personalizzate ai clienti in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
context-tags: trigger,overview;trigger,main
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 9dc75d6a-d79a-49aa-a0c0-b1dd6c144ce6
source-git-commit: ea69225fdf8b69025ff93b87b5b47ac9095b0eea
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 91%

---

# Informazioni su Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

L’integrazione tra il servizio core Activation di Experience Cloud **[!UICONTROL Triggers]** e Adobe Campaign ti consente di inviare e-mail personalizzate ai clienti per reagire a comportamenti specifici tracciati sul sito web da Adobe Analytics (entro 15 minuti).

In Adobe Experience Cloud, puoi definire i diversi trigger, vale a dire i comportamenti dei clienti che desideri monitorare, come tutti i clienti che hanno abbandonato la visita sul sito web, che hanno effettuato una ricerca sul sito web senza effettuare un acquisto o anche i clienti con una sessione scaduta. Quando crei un trigger, definisci la relativa condizione e i dati che vengono inviati nell’evento (caricamento) in Adobe Campaign.

In Adobe Campaign, selezioni il trigger precedentemente creato, arricchisci i dati dell’evento con i dati del data mart e definisci un modello di messaggio transazionale collegato a esso. Ad esempio, quando un cliente abbandona la visita sul tuo sito web, viene inviato un evento ad Adobe Campaign che può quindi sfruttarlo tramite un’e-mail di remarketing inviata al cliente entro 15 minuti.

Il diagramma seguente illustra il funzionamento di questa integrazione.

![](assets/triggers_diagram.png)

**Argomenti correlati:**

* Scopri i diversi tipi di trigger: [Documentazione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/triggers.html).
* Guarda il video [Trigger dei messaggi di remarketing basati sull’attività del sito](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html#step-two).
* Scopri i nostri due [casi di utilizzo di attivatori di abbandono](../../integrating/using/abandonment-triggers-use-cases.md).

## Attiva il processo utente {#triggers-user-process}

>[!CAUTION]
>
>Prima di eseguire i passaggi utente principali, devi configurare la funzionalità. Per ulteriori informazioni, consulta [Attivazione della funzionalità](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configurazione di soluzioni e servizi](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) e [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

In Adobe Campaign i passaggi principali del processo utente consistono nel:

1. Creare un evento trigger collegato a un trigger esistente in Adobe Experience Cloud;
1. Pubblicare l’evento trigger;
1. Definire il contenuto del modello di messaggio transazionale;
1. Verificare il modello (creare un profilo di test e inviare una bozza);
1. Pubblicare il modello di messaggio transazionale.

I casi di utilizzo completi sono descritti in [questa sezione](../../integrating/using/abandonment-triggers-use-cases.md).

## Note importanti {#important-notes}

Di seguito sono riportate alcune note importanti da considerare prima di utilizzare l’integrazione Triggers - Campaign:

* Le notifiche push non sono supportate per i trigger. Sono supportati solo e-mail e SMS.
* Puoi arricchire il trigger con metadati acquisiti tramite Analytics, ad esempio ID e-mail, nome pagina, ecc.
* Puoi riconciliare il trigger con un profilo archiviato in Campaign Standard e utilizzare i campi del profilo per personalizzare il messaggio.
* Il trigger viene elaborato, riconciliato e inviato subito dopo la sua ricezione. Ci vogliono circa 5-15 minuti a seconda del volume di trigger ricevuti e del numero di campi di personalizzazione utilizzati nel modello.

>[!NOTE]
>
>Per ulteriori informazioni sulle best practice e limitazioni tecniche, consulta [Best practice e limitazioni dei trigger](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).
