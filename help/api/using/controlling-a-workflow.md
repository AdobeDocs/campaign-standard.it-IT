---
solution: Campaign Standard
product: campaign
title: Controllo dei flussi di lavoro
description: Scopri come controllare un flusso di lavoro con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 10%

---


# Controllo dei flussi di lavoro {#controlling-a-workflow}

Puoi controllare un flusso di lavoro direttamente dall’API REST tramite una richiesta POST contenente l’ID del flusso di lavoro e il comando di esecuzione richiesto:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Se l’ID del flusso di lavoro viene modificato in Adobe Campaign, la richiesta API non funzionerà più.

Sono disponibili quattro comandi di esecuzione per controllare un flusso di lavoro:

* Inizio
* Pausa
* Riprendi
* Interruzione

Per ulteriori informazioni sui comandi di esecuzione, consulta la [documentazione della campagna](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html).

<br/>

***Richieste di esempio***

* Avvia un flusso di lavoro.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* Interrompi un flusso di lavoro.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
