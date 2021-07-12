---
solution: Campaign Standard
product: campaign
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Panoramica
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 100%

---


# Ultima versione{#latest-release}

## Versione 21.2 - Giugno 2021 {#release-21-2---june-2021}

Di seguito sono elencati le nuove funzioni, i miglioramenti e le correzioni inclusi nella prossima versione di Campaign Standard. Di seguito sono elencate nuove funzioni, miglioramenti e correzioni inclusi in questa versione di Campaign Standard.

**Miglioramenti**

* Durante la progettazione di una pagina di destinazione, è ora possibile aggiungere una casella di controllo obbligatoria che i profili devono selezionare prima di inviare il modulo. Per ulteriori informazioni consulta la [documentazione dettagliata](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Per l’integrazione con gli Attivatori, è stato migliorato il messaggio di errore visualizzato quando non sono presenti dati di riconciliazione in arrivo nel payload dell’attivatore: “Alias data missing from payload”.

* Sono state migliorate le prestazioni per il recupero delle notifiche push dalla coda.

**Altre modifiche**

* Il meccanismo di firma URL per i collegamenti di tracciamento è stato disattivato per evitare un problema che causava il blocco errato di alcuni collegamenti di tracciamento validi e firmati dopo la modifica da parte di strumenti di sicurezza di terze parti.

* Nelle consegne con più varianti, gli utenti non possono più creare copie per lingua se la variante predefinita è stata eliminata. Durante la creazione della copia in lingua viene ora visualizzato un messaggio. (CAMP-48235)

* Il processo di eliminazione del profilo in due fasi (obsoleto a partire da Campaign 19.4) ora è disattivato per impostazione predefinita. In precedenza era necessario disattivarlo manualmente dall’interfaccia di Campaign prima di utilizzare il servizio core Privacy. In caso contrario, lo stato delle richieste di cancellazione rimane in sospeso senza arrivare al termine.

* Nei rapporti dinamici, è stato rimosso il segmento **Exclude Proof**. (CAMP-46161)

* È stato aggiunto un nuovo messaggio di avvertenza per informare l’utente quando viene caricato nell’applicazione Campaign un certificato iOS senza il valore platformPrincipal.

* La dimensione massima di un messaggio e-mail ora è impostata su 100 MB per impostazione predefinita. Questo limite consente di evitare eventuali errori che potrebbero aumentare indefinitamente le dimensioni di un’e-mail e causare un arresto anomalo del sistema. (CAMP-47445) [Ulteriori informazioni](../../sending/using/design-and-personalize.md#email-size)

* L’integrazione del servizio core Assets con Email Designer può ora essere utilizzata dagli utenti Standard.

* È stato aggiunto un nuovo messaggio per confermare la riuscita della migrazione da un’applicazione push v4 a un’applicazione push v5.

* Durante la creazione di token JSONWeb per l’autenticazione nell’API Campaign Standard, ora vengono **considerati** i profili di prodotto. Ciò significa che le unità organizzative e i ruoli assegnati al gruppo di sicurezza (che corrispondono al profilo prodotto su AdobeIO) verranno applicati all’account tecnico IMS necessario per le chiamate API Rest di Campaign Standard. (CAMP-47479)

**Patch**

* È stato risolto un problema che impediva l’applicazione dell’opzione di scadenza per la tabella di registro del processo batch (**xtkjoblog**). Ciò impediva la corretta eliminazione della tabella.

* È stato risolto un problema che impediva la modifica dell’ordine dei filtri in un’attività del flusso di lavoro **Segmentation**. (CAMP-48357)

* È stata corretta una regressione dalla versione 20.4 che poteva causare un errore di consegne con un valore null. (CAMP-48591)

* È stato risolto un problema che impediva l’invio di un rapporto tramite il menu **Share** > **Send Report Now** o **Send Report on Schedule**. (CAMP-47798)

* È stata corretta una regressione che poteva causare tassi di apertura errati per Gmail a causa del filtraggio degli eventi di tracciamento ricevuti dagli account Gmail. (CAMP-46504)

* Sono stati risolti diversi problemi che causavano discrepanze di dati tra i rapporti in Adobe Campaign Standard e Adobe Analytics. (CAMP-47671, CAMP-47296)

* È stato risolto un problema che impediva l’accesso ai registri di consegna in seguito alla preparazione non riuscita. (CAMP-48296)

* È stato risolto un problema a causa del quale poteva comparire un messaggio di errore durante il tentativo di modificare, eliminare o inviare un rapporto personalizzato. (CAMP-47789, CAMP-47798)

* È stato risolto un problema che causava il mancato funzionamento delle chiamate API durante la creazione di una nuova risorsa personalizzata e l’abilitazione dell’opzione **Do not synchronize**. (CAMP-48014)

* È stato risolto un problema a causa del quale le risorse personalizzate abilitate con l’opzione **Do not synchronize** potevano fare riferimento a uno schema rielaborato o eliminato. Questo problema causava un errore durante la pubblicazione delle risorse personalizzate.

* È stato risolto un problema di rinuncia SMS quando si utilizzano più codici brevi sullo stesso account esterno.

* È stato risolto un problema che impediva l’accesso a un nuovo criterio di avviso sulla consegna (“la risorsa a cui si sta tentando di accedere non è raggiungibile”) dopo la pubblicazione del database. (CAMP-48221)

* È stato risolto un problema che causava l’assenza di registri di tracciamento in alcune istanze di Campaign con reporting dinamico. È stato aggiunto un nuovo [flusso di lavoro tecnico](../../administration/using/technical-workflows.md) per ripristinare questi registri di tracciamento. (CAMP-47885)

* È stato risolto un problema a causa del quale nei rapporti dinamici non venivano visualizzati dati di consegna. I rapporti venivano impostati su 0. (CAMP-47480)

* È stato risolto un problema che impediva al client HTTP JavaScript del server di connettersi all’URL esterno.

* È stato risolto un problema a causa del quale un’attività **Incremental query** veniva ripristinata in seguito alla modifica del nome interno del flusso di lavoro. Ciò si verificava quando un campo data veniva utilizzato come modalità incrementale. (CAMP-47674)

* È stato risolto un problema che impediva la visualizzazione della miniatura di anteprima nel riepilogo della consegna durante la creazione di un messaggio e-mail multilingue con l’integrazione di Adobe Experience Manager. Questo problema si verificava quando si utilizzava il pulsante per la **creazione copia in lingua** per creare le varianti dell’e-mail. (CAMP-47810)

* È stato risolto un problema che impediva agli utenti di accedere alla consegna principale dalla consegna secondaria e-mail o SMS. (CAMP-47986)

* È stato risolto un problema che poteva causare un consumo eccessivo di CPU e memoria durante l’invio di messaggi transazionali tramite l’API REST se un evento personalizzato risultava mancante. (CAMP-47147)

* È stato risolto un errore relativo all’API di messaggistica transazionale che talvolta impediva l’invio di messaggi in tempo reale.

* È stato risolto un problema a causa del quale i rapporti non venivano ricevuti dopo l’utilizzo dell’opzione per **Send report on schedule**. (CAMP-48583, CAMP-47786)

* È stato risolto un problema a causa del quale i rapporti ricevuti dopo l’utilizzo dell’opzione **Send report now** risultavano incompleti e mancanti. (CAMP-48583)

* È stato risolto un problema relativo a E-mail Designer a causa del quale le dimensioni di un’immagine venivano ridotte durante il caricamento. (CAMP-47017)

* È stato risolto un problema che impediva la visualizzazione di ogni modello di Experience Manager disponibile durante la creazione di una consegna. (CAMP-48132)

* È stato corretto un errore che impediva al collegamento Campaign, nella pagina di riepilogo di una consegna inviata, di reindirizzare gli utenti alla campagna correlata. (CAMP-48012)

* È stato risolto un problema in E-mail Designer a causa del quale l’integrazione del servizio core Assets continuava a non riuscire nel tentativo di selezionare una risorsa. (CAMP-47446)

* È stato risolto un problema che bloccava alcune consegne di Journey Orchestration a causa del fatto che Campaign non supportava le marche temporali con un valore esatto (cioè con ultime cifre pari a 00) inviate dagli eventi da Journey Orchestration.
