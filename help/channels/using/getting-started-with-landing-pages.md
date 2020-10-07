---
title: Passaggi principali per impostare una pagina di destinazione
description: Scopri i passaggi principali per impostare una pagina di destinazione
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1006'
ht-degree: 100%

---


# Guida introduttiva alle pagine di destinazione {#getting-started-with-landing-pages}

I passaggi principali per impostare pagine di destinazione sono i seguenti:

![](assets/lp_steps.png)

In questa pagina trovi informazioni su ciascuno di questi passaggi, oltre a riferimenti ai documenti dedicati per ulteriori dettagli.

**Argomenti correlati:**

* [ tutorial sulla creazione di una pagina di destinazione](https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/communication-channels/landing-pages/landing-page-create-and-edit.html)
* [Creazione di un servizio](../../audiences/using/creating-a-service.md)
* [Impostazione di un doppio processo di consenso](setting-up-a-double-opt-in-process.md)

## Limitazioni della pagina di destinazione{#landing-page-limitations}

La sezione seguente elenca i limiti da conoscere prima di iniziare a impostare pagine di destinazione.

**Scrittura e aggiornamento dei dati**

* Le pagine di destinazione sono limitate solo alle risorse **[!UICONTROL Profile]** e **[!UICONTROL Subscription]**. Puoi salvare e aggiornare il record da **[!UICONTROL Profile]** e da un abbonamento o dal suo annullamento a un **[!UICONTROL Service]**.
Per ulteriori informazioni sulla configurazione delle risorse, consulta [Configurazione della struttura dati della risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!CAUTION]
>
>Una pagina di destinazione non può visualizzare o aggiornare dati provenienti da qualsiasi altra risorsa che non sia **[!UICONTROL Profile]** e **[!UICONTROL Subscription]**.

**Precaricamento**

* La pagina di destinazione non può visualizzare automaticamente un elenco di record e non può elencare servizi con profili già abbonati. Per ulteriori informazioni sui servizi, consulta questa [pagina](../../audiences/using/creating-a-service.md).

* La pagina di destinazione con un modulo precompilato (i dati vengono precaricati con la pagina) è accessibile solo da un’e-mail di Adobe Campaign. Non è possibile accedere a tale modulo da una pagina di un sito web.

**Riconciliazione**

* Il comportamento di riconciliazione è il seguente: non appena viene trovato un corrispondente, il processo di riconciliazione viene interrotto. Ciò significa che è possibile eseguire la riconciliazione solo su un record di profilo e non su più record in presenza di duplicati.

Ad esempio, desideri inviare la seguente pagina di destinazione di acquisizione ai profili per aggiornare il database di Campaign con i numeri di cellulare corrispondenti.

![](assets/landing_page_limitation_1.png)

Se uno dei profili inserisce nuove informazioni nella pagina di destinazione ma è già presente un suo duplicato, viene aggiornato il profilo corrispondente alla data di creazione più recente, in quanto la priorità dei profili dipende solo dalla data di creazione.

In questo caso è stato aggiornato solo il primo profilo, perché si trattava della voce più datata.

![](assets/landing_page_limitation_2.png)

**Verifica delle pagine di destinazione**

* Le pagine di destinazione funzionano solo sui profili e non sui profili di test, il che significa che è impossibile sottoporre a test le pagine di destinazione come parte di una bozza e-mail.

## Passaggio 1: configurare il modello della pagina di destinazione {#configure-the-landing-page-template}

Prima di impostare una pagina di destinazione, il primo passaggio consiste nel configurare un modello di pagina di destinazione che corrisponda alle tue esigenze. Al termine della preparazione del modello, tutte le pagine di destinazione basate su di esso vengono preconfigurate con i parametri desiderati.

1. Seleziona **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** dal menu avanzato, tramite il logo di Adobe Campaign, quindi duplica il modello da utilizzare.
1. Nelle proprietà del modello, specifica tutti i parametri comuni alle pagine di destinazione. Ad esempio: la dimensione di targeting, i parametri di accesso alla pagina per visitatori identificati o non identificati, le azioni specifiche per la convalida del modulo da parte di un visitatore, il brand/logo da utilizzare nel contenuto, ecc. Per ulteriori informazioni sulle proprietà delle pagine di destinazione, consulta [questa sezione](../../channels/using/configuring-landing-page.md).
1. Salva le modifiche.

Per ulteriori informazioni sui modelli delle pagine di destinazione, consulta [questa sezione](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## Passaggio 2: creare e configurare la pagina di destinazione {#create-and-configure-the-landing-page}

Crea una nuova pagina di destinazione in un programma o in una campagna dal modello definito nel passaggio precedente.

1. Crea la pagina di destinazione in base al modello desiderato.
1. Immetti i parametri generali della pagina di destinazione (etichetta, descrizione, ecc.).
1. Accedi quindi al dashboard della pagina di destinazione. Se necessario, modifica le proprietà della pagina di destinazione (consulta [Configurazione di una pagina di destinazione](../../channels/using/configuring-landing-page.md)). Per impostazione predefinita le proprietà sono quelle configurate nel modello della pagina di destinazione.
Per motivi di sicurezza e prestazioni della piattaforma, ti consigliamo vivamente di impostare una data di scadenza nelle proprietà della pagina di destinazione. Al termine la pubblicazione della pagina di destinazione viene automaticamente annullata alla data selezionata. Per ulteriori informazioni sui parametri di validità, consulta [questa sezione](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

>[!NOTE]
>
>Le modifiche apportate sono valide solo per la pagina di destinazione in fase di modifica. Se desideri applicare queste modifiche ad altre pagine di destinazione, puoi eseguirle in un modello dedicato e quindi creare altre pagine di destinazione da quel modello.

## Passaggio 3: progettare la pagina di destinazione {#design-the-landing-page}

Puoi ora definire il contenuto della pagina di destinazione. Per impostazione predefinita, la pagina di destinazione contiene tre pagine accessibili mediante le frecce di scorrimento: la pagina del contenuto principale, una pagina di conferma e una pagina di errore.

![](assets/lp-steps4.png)

Per impostazione predefinita in ogni pagina sono configurati più campi. Se necessario, puoi modificarne proprietà e mappatura.

Puoi anche configurare il comportamento del pulsante di conferma quando un profilo fa clic su di esso e personalizzare il contenuto in base alle esigenze (immagine, campi di personalizzazione, ecc.). Ad esempio, puoi inserire il nome di un profilo nella pagina di conferma della pagina di destinazione, per ringraziarlo della registrazione.

Per ulteriori informazioni sulla progettazione di una pagina di destinazione, consulta [questa sezione](../../channels/using/designing-a-landing-page.md).

## Passaggio 4: verifica della pagina di destinazione {#test-the-landing-page}

Dopo la definizione della pagina di destinazione, puoi simulare la modalità di esecuzione e funzionamento quando è disponibile online.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>Puoi eseguire i test della pagina di destinazione solo con profili e non su profili di test. Durante l’invio del modulo, i dati del profilo selezionato vengono effettivamente aggiornati. Per evitare di modificare profili reali, utilizza un profilo cliente inesistente.

Se sei soddisfatto del funzionamento della pagina di destinazione, puoi pubblicarla per renderla disponibile online.

Per ulteriori informazioni su come verificare una pagina di destinazione, consulta [questa sezione](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-).

## Passaggio 5: pubblicare la pagina di destinazione {#publish-the-landing-page}

Se i test hanno avuto esito positivo, puoi pubblicare la pagina di destinazione utilizzando il pulsante **[!UICONTROL Publish]** presente nella barra delle azioni del dashboard. Un blocco di monitoraggio mostra l’avanzamento e lo stato della pubblicazione.

La pubblicazione della pagina di destinazione la rende accessibile online. Dopo la pubblicazione, puoi sempre aggiornarla: a questo scopo devi ripubblicarla dopo ogni modifica. Puoi inoltre annullare la pubblicazione di una pagina di destinazione in qualsiasi momento in modo che non sia più disponibile.

![](assets/lp-steps6.png)

Dopo la pubblicazione, la pagina di destinazione è pronta per essere utilizzata. Puoi quindi implementare diversi meccanismi che ti consentano di accedervi per acquisire nuovi profili nel database o ottenere ulteriori informazioni sui profili esistenti.

Per ulteriori informazioni sulla pubblicazione di una pagina di destinazione, consulta [questa sezione](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page).
