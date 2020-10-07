---
title: Attivazione di attività di segnale
description: Scopri come attivare un'attività di segnale con le API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---


# Attivazione di attività di segnale {#triggering-a-signal-activity}

In un flusso di lavoro Adobe Campaign Standard , possono essere presenti una o più attività di segnale **** esterno. Queste attività sono &quot;listener&quot; che attendono di essere attivati.

Le API Campaign Standard consentono di attivare un&#39;attività di segnale **** esterno per chiamare un flusso di lavoro. La chiamata API può includere parametri che verranno assimilati nelle variabili degli eventi del flusso di lavoro (un nome di pubblico per il targeting, un nome di file per l&#39;importazione, una parte del contenuto del messaggio, ecc.). In questo modo, puoi integrare facilmente le automatizzazioni Campaign con il sistema esterno.

>[!NOTE]
>
>Le attività di segnale esterno non possono essere attivate più spesso di 10 minuti e il flusso di lavoro di destinazione deve essere già in esecuzione.

Per attivare un flusso di lavoro, effettuate le seguenti operazioni:

1. Eseguite una richiesta di **GET** sul flusso di lavoro per recuperare l&#39;URL di attivazione dell&#39;attività del segnale esterno.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Eseguite una richiesta di **POST** sull&#39;URL restituito per attivare l&#39;attività del segnale, con il parametro **&quot;source&quot;** nel payload. Questo attributo è obbligatorio e consente di indicare l&#39;origine della richiesta di attivazione.

Se desiderate richiamare il flusso di lavoro con i parametri, aggiungeteli al payload con l&#39;attributo **&quot;parameters&quot;** . La sintassi è composta dal nome del parametro seguito dal relativo valore (sono supportati i seguenti tipi: **stringa**, **numero**, **booleano** e **data/ora**).

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>Quando aggiungete un parametro al payload, accertatevi che i relativi valori di **nome** e **tipo** siano coerenti con le informazioni dichiarate nell&#39;attività del segnale esterno. Inoltre, la dimensione del carico utile non deve superare i 64 Ko.

<br/>

***Richiesta di esempio***

Eseguite una richiesta di GET sul flusso di lavoro.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;attività del segnale del flusso di lavoro e l&#39;URL del trigger associato.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Per attivare un&#39;attività di segnale, esegui una richiesta di POST sull&#39;URL di attivazione con il &quot;source&quot;. Aggiungete gli attributi &quot;parametri&quot; se desiderate richiamare il flusso di lavoro con i parametri.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Se uno dei parametri non è dichiarato nell&#39;attività del segnale esterno, la richiesta POST restituisce l&#39;errore seguente, indicando quale parametro manca.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
