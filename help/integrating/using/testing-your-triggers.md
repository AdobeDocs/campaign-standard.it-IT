---
title: Verifica degli attivatori
description: Scopri suggerimenti per la risoluzione dei problemi, utili per risolvere i problemi più comuni che possono verificarsi quando utilizzi Triggers con Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
TQID: https://experienceleague.adobe.com/bbNySA5tCj7hDs3YG9AlPGgOUS42r3or0j-QhwIzXEw
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 1%

---

# Verifica degli attivatori{#testing-your-triggers}

I seguenti suggerimenti per la risoluzione dei problemi consentono di risolvere i problemi più comuni che possono verificarsi quando si utilizzano Triggers con Adobe Campaign:

**La funzionalità è attivata?**

Per verificare se l&#39;integrazione Triggers - Campaign è attivata, fai clic sul logo Adobe Campaign, nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Dovresti visualizzare l&#39;elemento **[!UICONTROL Experience Cloud Triggers]**.

Se lo vedi, passa al passaggio successivo.

In caso contrario, contatta il responsabile dell’account Adobe o il partner di servizi professionali. Vedere [Attivazione della funzionalità](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Crea un trigger**

Segui i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) per creare un trigger.

Se il trigger viene creato, passare al passaggio successivo. In caso contrario, significa che la connessione del punto finale del trigger non è riuscita. Controlla se è stato eseguito il provisioning di Triggers in Experience Cloud (Activation services). In caso contrario, contatta il responsabile dell’account Adobe o il partner di servizi professionali. Sono richieste le seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione
* Società di accesso ad Analytics (può essere la stessa del nome della società Marketing Cloud)

**Prova a pubblicare il trigger**

Segui i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) per pubblicare il trigger.

Se la pubblicazione ha avuto esito positivo, passare al passaggio successivo. In caso contrario, contatta Adobe per riavviare l’istanza e riprova.

**Genera il trigger dal sito Web**

Segui i passaggi descritti in [Modifica del modello di messaggio transazionale](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) per modificare e pubblicare il modello transazionale. Quindi, testa la generazione del trigger dal sito web.

Se il trigger viene ricevuto da Analytics, passa al passaggio successivo. In caso contrario, verificare quanto segue:

* Trigger abilitato per Analytics
* Il sito web utilizzato MCID e Analytics è abilitato in DTM
* Durante la creazione di trigger viene utilizzata la suite di rapporti di Analytics corretta

**Il trigger è ricevuto da Campaign?**

In caso contrario, controlla se il trigger viene ricevuto dalla pipeline.

In caso contrario, contatta Adobe per verificare la configurazione dei punti finali della pipeline.

In caso affermativo, attieniti alle seguenti linee guida:

* Controlla il tipo di ID di riconciliazione nell’origine dati di Campaign.
* L’origine dati CustomerId viene creata tramite Attributi del cliente.
* Controlla l’ID dell’origine dati.
* Chiedi ad Adobe di riavviare l’istanza di Campaign dopo la configurazione dell’origine dati.
* Controlla i problemi di analisi del trigger nel report del trigger.

**Il trigger si trova nello stato in sospeso?**

In caso contrario, passare al passaggio successivo. In caso affermativo, attieniti alle seguenti linee guida:

* Verifica che il modello transazionale sia pubblicato.
* Verifica che il profilo non sia in fase di inserisco nell&#39;elenco Bloccati di.
* Controlla l’applicazione delle regole di tipologia.
* Controlla i registri del messaggio transazionale.

**Il messaggio è valido?**

Se il messaggio non è valido, verificare quanto segue:

* Per i campi di personalizzazione dell’arricchimento del trigger contrassegnati come non validi, convalida il modello transazionale dalle raccolte eventCusResource associate.
* Convalidare il formato del messaggio
