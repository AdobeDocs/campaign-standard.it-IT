---
solution: Campaign Standard
product: campaign
title: Perché utilizzare le API di Campaign Standard?
description: Ulteriori informazioni sulle API di Campaign Standard e perché utilizzarle.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---


# Perché utilizzare le API di Campaign Standard {#why-using-campaign-standard-apis}

Adobe Campaign Standard fornisce API che consentono l’integrazione dei sistemi esistenti con la piattaforma Campaign per risolvere problemi nel mondo reale in tempo reale.

I siti web pubblici come la pagina di registrazione o di rinuncia devono connettersi ai sistemi di back-end per memorizzare le informazioni sul profilo. I sistemi di back-end come Adobe Campaign hanno la flessibilità e la capacità di acquisire i dati di profilo in e di eseguire operazioni personalizzate su di essi.

Di seguito sono riportati alcuni esempi:

* Prospettive di registrazione online.
* Gestione delle preferenze di comunicazione marketing e profilo cliente esistenti.
* Attivazione della comunicazione transazionale basata su eventi: conferma dell&#39;ordine, itinerario di prenotazione, reimpostazione della password, ecc.
* Persino la comunicazione via e-mail di abbandono del carrello.

Registrati le pagine di destinazione forniscono ai clienti o potenziali clienti la possibilità di registrare il loro nome e indirizzo e-mail. Una volta acquisite le informazioni e le preferenze del profilo, Campaign Standard può inviare messaggi personalizzati in base agli interessi della persona.

Sono costruiti con gli elementi seguenti:

1. Un modulo di registrazione con listener API della campagna.

   ![testo alt](assets/apis_uc1.png)

1. Azioni personalizzate da eseguire in base alle caselle di controllo. Un cliente che seleziona &quot;Offerte speciali e-mail&quot; riceverà un&#39;altra mail personalizzata con un buono regalo rispetto al normale processo di registrazione.

   ![testo alt](assets/apis_uc2.png)

1. Un profilo può cambiare i propri dettagli dopo aver fatto clic sul collegamento &quot;Aggiorna dettagli&quot; nell&#39;e-mail. Questo porta il profilo alla pagina &quot;Aggiorna il tuo profilo e i dettagli delle preferenze&quot;. Per eseguire l’operazione, i dettagli del profilo (Pkey) vengono passati al server Campaign e il profilo viene recuperato e rappresentato. Una volta che il profilo fa clic sul pulsante &quot;Aggiorna&quot;, le informazioni vengono aggiornate nel sistema (tramite un comando PATCH).

   ![testo alt](assets/apis_uc3.png)

È disponibile una raccolta di richieste per acquisire familiarità con le richieste API di Campaign Standard. Questa raccolta in formato JSON fornisce richieste API predefinite che rappresentano casi d’uso comuni.

I passaggi seguenti descrivono un caso d’uso dettagliato per importare e utilizzare la raccolta per creare un profilo nel database di Campaign Standard.

>[!NOTE]
>
>Il nostro esempio utilizza Postman. Tuttavia, sentiti libero di usare il tuo client REST preferito.

1. Scarica la raccolta JSON facendo clic [qui](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Apri Postman, quindi seleziona il menu **File** / **Importa**.

1. Trascina e rilascia il file scaricato nella finestra . Vengono visualizzate le richieste API predefinite, pronte per essere utilizzate.

   ![testo alt](assets/postman_collection.png)

1. Seleziona la richiesta **Creazione di un profilo**, quindi aggiorna la richiesta POST e la scheda **Intestazioni** con le tue informazioni (&lt;ORGANIZATION>, &lt;API_KEY>, &lt;ACCESS_TOKEN>). Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/setting-up-api-access.md).

   ![testo alt](assets/postman_uc1.png)

1. Compila la scheda **Corpo** con le informazioni che desideri aggiungere al nuovo profilo, quindi fai clic sul pulsante **Invia** per eseguire la richiesta.

   ![testo alt](assets/postman_uc2.png)

1. Una volta creato un oggetto, ad esso viene associata una chiave primaria (PKey). È visibile nella risposta alla richiesta, così come in altri attributi.

   ![testo alt](assets/postman_uc3.png)

1. Apri l’istanza di Campaign Standard, quindi verifica che il profilo sia creato, con tutte le informazioni del payload.

   ![testo alt](assets/postman_uc4.png)
