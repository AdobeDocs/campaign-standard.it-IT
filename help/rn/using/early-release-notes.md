---
solution: Campaign Standard
product: campaign
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Panoramica
role: Business Practitioner
level: Beginner
exl-id: d86b9bc4-4c99-4d88-bc28-b6049bf7c2a9
hide: true
hidefromtoc: true
source-git-commit: 48079dbd2517117b3f351ecdb8bf2b665f53bdb6
workflow-type: tm+mt
source-wordcount: '1008'
ht-degree: 3%

---

# Note sulla versione anticipate {#new-release}

Questa pagina descrive nuove funzioni, miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).


## Versione 21.2 - giugno 2021 {#release-21-2---june-2021}

**Miglioramenti**

* Durante la progettazione di una pagina di destinazione, è ora possibile aggiungere una casella di controllo obbligatoria che i profili devono selezionare prima di inviare il modulo.

* Per l’integrazione Triggers, è stato migliorato il messaggio di errore visualizzato quando non sono presenti dati di riconciliazione in arrivo nel payload del trigger: &quot;Dati alias mancanti dal payload&quot;.

* Sono state migliorate le prestazioni per il recupero delle notifiche push dalla coda.

**Altre modifiche**

* Il meccanismo di firma URL per i collegamenti di tracciamento è stato disattivato per evitare un problema che causava il blocco errato di alcuni collegamenti di tracciamento validi e firmati dopo la modifica da parte di strumenti di sicurezza di terze parti.

* Nelle consegne con più varianti, gli utenti non possono più creare copie per lingua se la variante predefinita è stata eliminata. Durante la creazione della copia in lingua viene ora visualizzato un messaggio. (CAMP-48235)

* Il processo di eliminazione del profilo in due fasi (obsoleto a partire dalla versione 19.4 di Campaign) ora è disattivato per impostazione predefinita. In precedenza era necessario disattivarlo manualmente dall’interfaccia di Campaign prima di utilizzare il servizio core Privacy. In caso contrario, lo stato delle richieste di cancellazione rimarrà in sospeso senza essere state completate.

* È stata introdotta una nuova funzione di aggregazione &#39;StringAgg&#39; per concatenare i valori di una colonna di tipo stringa. (CAMP-47077)

* Nei rapporti dinamici, il segmento **Escludi prova** è stato rimosso. (CAMP-46161)

* È stato aggiunto un nuovo messaggio di avviso per informare l’utente quando viene caricato un certificato iOS senza il valore platformPrincipal nell’applicazione Campaign.

* La dimensione massima di un messaggio e-mail ora è impostata su 100 MB per impostazione predefinita. Questo limite consente di evitare eventuali errori che potrebbero aumentare indefinitamente le dimensioni di un’e-mail e causare un arresto anomalo del sistema. (CAMP-47445)

* L’integrazione del servizio core Assets con la finestra di progettazione e-mail può ora essere utilizzata dagli utenti standard.

* È stato aggiunto un nuovo messaggio per confermare la riuscita della migrazione da un’applicazione push v4 a un’applicazione push v5.

**Patch**

* È stato risolto un problema che impediva l&#39;applicazione dell&#39;opzione di scadenza per la tabella di registro del processo batch (**xtkjoblog**). Ciò impediva la corretta eliminazione della tabella.

* È stato risolto un problema che impediva la modifica dell&#39;ordine dei filtri in un&#39;attività del flusso di lavoro **Segmentation** . (CAMP-48357)

* È stata corretta una regressione da 20.4 che poteva causare un errore di consegne con un valore null. (CAMP-48591)

* È stato risolto un problema che impediva l&#39;invio di un rapporto tramite il menu **Condividi** > **Invia rapporto ora** o **Invia rapporto secondo programma** . (CAMP-47798)

* È stata corretta una regressione che poteva portare a tassi di apertura non corretti per Gmail a causa del filtro degli eventi di tracciamento ricevuti dagli account Gmail. (CAMP-46504)

* Sono stati risolti diversi problemi che causavano discrepanze di dati tra report in Adobe Campaign Standard e report in Adobe Analytics. (CAMP-47671, CAMP-47296)

* È stato risolto un problema che impediva l’accesso ai registri di consegna dopo la mancata preparazione. (CAMP-48296)

* È stato risolto un problema che poteva visualizzare un messaggio di errore durante il tentativo di modificare, eliminare o inviare un rapporto personalizzato. (CAMP-47789, CAMP-47798)

* È stato risolto un problema che causava il mancato funzionamento delle chiamate API durante la creazione di una nuova risorsa personalizzata e l’abilitazione dell’opzione **Non sincronizzare** . (CAMP-48014)

* È stato risolto un problema a causa del quale le risorse personalizzate abilitate con l&#39;opzione **Non sincronizzare** potevano fare riferimento a uno schema rielaborato o eliminato. Questo problema causava un errore durante la pubblicazione delle risorse personalizzate.

* È stato risolto un problema di rinuncia SMS quando si utilizzano più codici brevi sullo stesso account esterno.

* È stato risolto un problema che impediva l’accesso a un nuovo criterio di avviso sulla consegna (&quot;la risorsa a cui si sta tentando di accedere non è raggiungibile&quot;) dopo la pubblicazione del database. (CAMP-48221)

* È stato risolto un problema a causa del quale in alcune istanze mancavano i registri di tracciamento. È stato aggiunto un nuovo flusso di lavoro tecnico (**trackingLogRecovery**) per ripristinare questi registri di tracciamento persi e deve essere utilizzato solo da Adobe interno.

* È stato risolto un problema a causa del quale nei rapporti dinamici non venivano visualizzati dati di consegna. I rapporti sono stati impostati su 0. (CAMP-47480)

* È stato risolto un problema che impediva al client HTTP JavaScript del server di connettersi all&#39;URL esterno.

* È stato risolto un problema che reimpostava un&#39;attività **Query incrementale** dopo la modifica del nome interno del flusso di lavoro. Ciò si verificava quando un campo data veniva utilizzato come modalità incrementale. (CAMP-47674)

* È stato risolto un problema che impediva la visualizzazione della miniatura di anteprima nel riepilogo della consegna durante la creazione di un messaggio e-mail multilingue con l’integrazione di Adobe Experience Manager. Questo problema si verificava quando si utilizzava il pulsante **Creazione copia in lingua** per creare le varianti dell’e-mail. (CAMP-47810)

* È stato risolto un problema che impediva agli utenti di accedere alla consegna principale dalla consegna figlio e-mail o SMS. (CAMP-47986)

* È stato risolto un problema che poteva causare un consumo eccessivo di CPU e memoria durante l’invio di messaggi transazionali tramite l’API REST con un evento personalizzato mancante. (CAMP-47147)

* È stato risolto un errore relativo all’API di messaggistica transazionale che talvolta impediva l’invio di messaggi in tempo reale.

* È stato risolto un problema a causa del quale i rapporti non venivano ricevuti dopo l’utilizzo dell’opzione **Invia rapporto secondo programma** . (CAMP-48583)

* È stato risolto un problema a causa del quale i rapporti ricevuti dopo l’utilizzo dell’opzione **Invia rapporto ora** risultavano incompleti e mancanti. (CAMP-48583)

* È stato risolto un problema relativo all’opzione **Invia report su pianificazione** nel report Dynamics a causa del quale il flusso di lavoro integrato **Condivisione report immediata** (reportSendingNow) non generava rapporti. (CAMP-47786)

* È stato risolto un problema relativo a E-mail Designer a causa del quale le dimensioni di un’immagine venivano ridotte durante il caricamento di un’immagine. (CAMP-47017)

* È stato risolto un problema che impediva la visualizzazione di ogni modello di Experience Manager disponibile durante la creazione di una consegna. (CAMP-48132)

* È stato corretto un errore che impediva al collegamento Campaign nella pagina Riepilogo di una consegna inviata di reindirizzare gli utenti alla campagna correlata. (CAMP-48012)

* È stato risolto un problema in E-mail Designer a causa del quale l’integrazione del servizio core Assets continuava a non riuscire quando si tentava di selezionare una risorsa. (CAMP-47446)

* È stato risolto un problema che bloccava alcune consegne di Journey Orchestration a causa del fatto che Campaign non supportava le marche temporali con un valore esatto (cioè con scadenza a 00) inviato dagli eventi dal Journey Orchestration.

* Il flusso di lavoro tecnico updateDeliveryIndicators è stato ottimizzato. Gli ID di consegna con lo stesso schema di registro di trasmissione/trackinglog ora sono raggruppati insieme. Questo limita il numero di query, migliorando così le prestazioni.
