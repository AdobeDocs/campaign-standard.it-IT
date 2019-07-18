---
title: Informazioni su Adobe Experience Cloud Triggers
seo-title: Informazioni su Adobe Experience Cloud Triggers
description: Informazioni su Adobe Experience Cloud Triggers
seo-description: Tenendo traccia dei comportamenti specifici dei clienti con Adobe Analytics, ora puoi inviare e-mail personalizzate ai tuoi clienti in Adobe Campaign.
page-status-flag: never-activated
uuid: 0 aa 4 bd 6 e -1 bb 5-4 d 0 b -913 b-eca 93 f 050 acd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-triggers
discoiquuid: e 526 b 205-2 d 01-4 a 8 b -9685-ba 1 d 9 a 1 f 459 f
context-tags: trigger, overview; trigger, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

In Adobe Experience Cloud puoi definire i diversi attivatori, ossia i comportamenti cliente che desideri monitorare, come tutti i clienti che hanno abbandonato la visita sul tuo sito Web, che hanno effettuato una ricerca sul tuo sito Web, che hanno fatto una ricerca, oppure persino i client la cui sessione è scaduta. Quando crei un trigger, definisci la condizione dell'attivatore e i dati che verranno inviati nell'evento (pload) ad Adobe Campaign.

In Adobe Campaign, selezionate l'attivatore creato in precedenza, ingrandite i dati dell'evento con i dati di datamart e definite un modello di messaggio transazionali collegato a tale trigger. Ad esempio, quando un cliente abbandona la visita sul sito Web, un evento viene inviato ad Adobe Campaign che può quindi sfruttare questo evento tramite un'e-mail di remarketing inviata al client entro 15 minuti.

**Argomenti correlati:**

* Learn about the different types of triggers: [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Watch the [Trigger Remarketing Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) video.
* Discover our two [Abandonment Triggers use cases](../../integrating/using/abandonment-triggers-use-cases.md).

## Triggers user process {#triggers-user-process}

>[!CAUTION]
>
>Prima di eseguire i passaggi principali dell'utente, è necessario configurare la funzionalità. For more on this refer to [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) and [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

I passaggi principali del processo utente, in Adobe Campaign, sono:

1. Crea un evento di attivazione collegato a un attivatore Adobe Experience Cloud esistente.
1. Pubblicate l'evento di attivazione.
1. Definire il contenuto del modello di messaggio transazionali.
1. Testate il modello (create un profilo di prova e inviate una prova).
1. Pubblicate il modello di messaggio transazionali.

Complete use cases are described in [this section](../../integrating/using/abandonment-triggers-use-cases.md).

## Important notes {#important-notes}

Di seguito sono riportate alcune note importanti da prendere in considerazione prima di utilizzare gli attivatori - Integrazione della campagna:

* Le notifiche push non sono supportate per le attivazioni. Sono supportati solo E-mail e SMS.
* Potete arricchire il trigger con metadati acquisiti attraverso Analytics come ID e-mail, nome pagina ecc.
* Puoi riconciliare il trigger a un profilo memorizzato in Campaign Standard e utilizzare i campi del profilo per personalizzare il messaggio.
* Non appena viene ricevuto un trigger, viene elaborato e riconciliato e inviato. Sono necessari circa 5 o 15 minuti a seconda del volume di attivatori ricevuti, il numero di campi di personalizzazione utilizzati nel modello.

>[!NOTE]
>
>For more on best practices and technical limitations, refer to [Triggers best practices and limitations](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

