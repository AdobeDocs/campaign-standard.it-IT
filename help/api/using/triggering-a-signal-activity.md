---
title: Attivazione di attività di segnale
description: Scopri come attivare un’attività di segnale con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f94e98f-fe04-4369-8946-1380e02cdece
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 2%

---

# Attivazione di attività di segnale {#triggering-a-signal-activity}

In un flusso di lavoro Adobe Campaign Standard, può essere presente una o più attività **Segnale esterno**. Queste attività sono &quot;ascoltatori&quot; che attendono di essere attivati.

Le API di Campaign Standard consentono di attivare un’attività **External signal** per chiamare un flusso di lavoro. La chiamata API può includere parametri che verranno acquisiti nelle variabili degli eventi del flusso di lavoro (un nome del pubblico di cui eseguire il targeting, un nome di file da importare, una parte del contenuto del messaggio, ecc.). In questo modo, puoi integrare facilmente le automatizzazioni Campaign con il tuo sistema esterno.

>[!NOTE]
>
>Le attività del segnale esterno non possono essere attivate più spesso di ogni 10 minuti e il flusso di lavoro di destinazione deve essere già in esecuzione.

Per attivare un flusso di lavoro, segui i passaggi seguenti:

1. Esegui una richiesta **GET** sul flusso di lavoro per recuperare l&#39;URL di attivazione dell&#39;attività del segnale esterno.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Esegui una richiesta **POST** sull&#39;URL restituito per attivare l&#39;attività del segnale, con il parametro **&quot;source&quot;** nel payload. Questo attributo è obbligatorio e ti consente di indicare l’origine della richiesta di attivazione.

Se desideri chiamare il flusso di lavoro con i parametri, aggiungili al payload con l&#39;attributo **&quot;parameters&quot;** . La sintassi è costituita dal nome del parametro seguito dal relativo valore (sono supportati i seguenti tipi: **stringa**, **numero**, **booleano** e **data/ora**).

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
>Quando aggiungi un parametro al payload, accertati che i suoi valori **name** e **type** siano coerenti con le informazioni dichiarate nell’attività External signal . Inoltre, la dimensione del carico utile non deve superare i 64 Ko.

<br/>

***Richiesta di esempio***

Esegui una richiesta di GET sul flusso di lavoro.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’attività del segnale del flusso di lavoro e l’url del trigger associato.

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

Per attivare un’attività di segnale, esegui una richiesta POST sull’url del trigger con la &quot;sorgente&quot;. Aggiungi gli attributi &quot;parameters&quot; se desideri chiamare il flusso di lavoro con i parametri.

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

Se uno dei parametri non è dichiarato nell’attività del segnale esterno, la richiesta di POST restituisce l’errore seguente, indicando quale parametro manca.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
