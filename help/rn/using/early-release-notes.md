---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 5435e1dbfbe08399c488322320ac5bb8e681a79d
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 10%

---

# Note preliminari sulla versione {#new-release}

Questa pagina descrive nuove funzioni, miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 22.1 - Febbraio 2022 {#feb-2022}


**Novità**


<table> 
<thead> 
<tr> 
<th> <strong>Aggiornamento di sicurezza per le vulnerabilità di sicurezza di Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j ha risolto le vulnerabilità riportate nella versione di Apache log4j v2.17.1. Adobe Campaign Standard utilizza Apache log4j e in questa versione include l’ultimo log4j di Apache v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Correzioni di sicurezza**

* Nuovo meccanismo di firma URL per il tracciamento incluso in questa versione. Il meccanismo precedente era stato disattivato per evitare un problema che causava il blocco errato di alcuni collegamenti di tracciamento validi e firmati dopo la modifica da parte di strumenti di sicurezza di terze parti. (CAMP-48983)

**Miglioramenti**

* È stata migliorata l’elaborazione dei dati di reporting per evitare il sovraccarico del sistema. (CAMP-47578)
* Dopo aver inviato i messaggi in-app, ora puoi scegliere di disattivare la consegna. Ciò ti consente di eliminare la consegna senza perdere dati di reporting. (CAMP-48469)
* Per evitare problemi, gli utenti non possono più utilizzare lo stesso nome per una colonna di tabella personalizzata di quella utilizzata per la chiave primaria automatica nel database, `"<dataType><resourceName>Id"`. (CAMP-49358)
* Ora puoi monitorare la consegna e tenere traccia dei registri di lavoro con il nuovo **Storico dei processi** dal dashboard dei messaggi. (CAMP-49840)
* È stata migliorata la stabilità e la salute del database, riducendo le coppie morte, quando un gran numero di messaggi vengono inviati in tutti i canali nel tempo. (CAMP-49755, CAMP-49792, CAMP-49849)
* Per garantire l’aggiornamento automatico delle connessioni al database in caso di arresto anomalo o riavvio del database, sono stati implementati miglioramenti in Campaign Mail Transfer Agent (MTA). (CAMP-48063)


**Patch**

* È stato risolto un problema relativo alla **Invia rapporto ora** in Rapporti dinamici: i processi di generazione di PDF non sono riusciti con consegne che includono più varianti. (CAMP-49120)
* È stato risolto un problema che impediva agli utenti di aggiornare o scollegare il contenuto di Adobe Experience Manager (AEM) dalle consegne di Adobe Campaign Standard quando un contenuto duplicato in AEM condivideva la stessa chiave (cq:uuid). (CAMP-49161)
* È stato corretto un errore che si verificava durante l’accesso a un’istanza in cui le pagine non venivano caricate, non era possibile aprire le consegne o salvare eventuali modifiche in sospeso. (CAMP-50195)
* È stato risolto un problema che impediva l’apertura dei criteri di avviso di consegna se il campo **Filtro di consegna** applicato da questo criterio non è stato compilato. (CAMP-49093)
* È stato risolto un problema che si verificava durante la modifica del **Secondaria** nelle consegne in-app che impedivano di tenere conto delle modifiche. (CAMP-50250)
* È stato corretto un errore nelle istanze giapponesi che impediva agli utenti di scegliere più volte al giorno come **Frequenza di esecuzione** in **Scheduler** attività. (CAMP-50247)
* È stato risolto un problema che si verificava durante l’utilizzo di un’interfaccia utente giapponese e che mostrava un messaggio di errore durante la selezione di un’ora in un’attività Scheduler . (CAMP-49289)
* È stato risolto un errore relativo ai rapporti di notifica push che visualizzavano le notifiche push ignorate come **Apri** anziché **Impression**. (CAMP-45980)
* È stato risolto un problema che poteva causare errori all’apertura di un report. (CAMP-49222)
* È stato risolto un problema che poteva causare un errore nella preparazione dell’e-mail dopo l’eliminazione di un collegamento al contenuto AEM. (CAMP-49877)
* Per risolvere vari problemi, il meccanismo dei tentativi è stato migliorato per le consegne, incluso il contenuto importato da un URL. (CAMP-48888)
* È stato risolto un problema che si verificava dopo la creazione di un nuovo filtro in una risorsa personalizzata e il suo utilizzo come chiave di riconciliazione in una pagina di destinazione. Se la risorsa personalizzata è stata pubblicata nuovamente, il filtro è stato rimosso dall’elenco delle chiavi di riconciliazione disponibili per la pagina di destinazione. (CAMP-49516)
* È stato risolto un problema nelle pagine di destinazione che si verificava quando si utilizzavano condizioni dinamiche con le caselle di controllo. (CAMP-48604)
* È stato risolto un problema che si verificava in una **Query** attività quando si utilizza la condizione di filtro &quot;attivato o prima di ottobre&quot;. Quando si lavora da un&#39;istanza impostata su un fuso orario europeo, il mese selezionato per il filtro è stato visualizzato in Settembre anziché Ottobre, a causa di un problema durante la conversione del fuso orario. (CAMP-48602)
* Per ottimizzare il recapito messaggi, ora Adobe Campaign invia e-mail utilizzando la codifica a 7 bit anziché a 8 bit. Questo impedisce ai relè intermedi di annullare la validità della firma DKIM che potrebbe influire sull’autenticità dei messaggi. (CAMP-49016)
* Sono state migliorate le prestazioni durante la duplicazione dei tipi di pubblico al fine di evitare problemi quando si lavora con tipi di pubblico di grandi dimensioni. (CAMP-49639)
* È stato risolto un problema che poteva impedire a un filtro personalizzato di visualizzare i risultati corretti quando utilizzato in un **Query** attività. (CAMP-49417)
* È stato corretto un errore che causava la visualizzazione di un messaggio di errore durante il tentativo di utilizzo di un frammento in una consegna con una virgola nel nome. Il problema è stato risolto e ora è possibile utilizzare le virgole nei nomi dei frammenti. (CAMP-49216)