---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 9ab2e49203315e4c31a1bc268cd17bd0351a5349
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 86%

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
<p>In seguito all’aggiornamento della versione di Apache log4j v2.17.0 di dicembre 2021, per garantire che i nostri clienti non siano interessati dai possibili effetti indesiderati dell’introduzione di ulteriori modifiche al sistema al di fuori della normale pianificazione della versione, abbiamo effettuato l’aggiornamento internamente e lo stiamo preparando per la distribuzione con questa versione.</p>
</td> 
</tr> 
</tbody> 
</table>

**Correzioni di sicurezza**

* In questa versione è incluso un nuovo meccanismo di firma URL per il tracciamento. Il precedente meccanismo è stato disattivato per evitare un problema che causava il blocco errato di alcuni collegamenti di tracciamento validi e firmati dopo la modifica da parte di strumenti di sicurezza di terze parti. (CAMP-48983)
* Rafforzare la sicurezza per accedere ai file di configurazione dell&#39;applicazione e del server: La sicurezza delle API di accesso ai file JavaScript è ora limitata alle directory sandbox. (CAMP-49411)

**Miglioramenti**

* È stata migliorata l’elaborazione dei dati di reporting per evitare il sovraccarico del sistema. (CAMP-47578)
* Dopo aver inviato i messaggi in-app, ora puoi scegliere di disattivare la consegna. Ciò consente di eliminare la consegna senza perdere dati di reporting. (CAMP-48469)
* Per evitare problemi, per una colonna di tabella personalizzata gli utenti non possono più utilizzare lo stesso nome utilizzato per la chiave primaria automatica nel database, `"<dataType><resourceName>Id"`. (CAMP-49358)

**Patch**

* È stato risolto un problema relativo all’opzione **Send report now** (Invia rapporto ora) nei rapporti dinamici: i processi di generazione di PDF non riuscivano in presenza di consegne con più varianti. (CAMP-49120)
* È stato risolto un problema che impediva agli utenti di aggiornare o scollegare il contenuto di Adobe Experience Manager (AEM) dalle consegne di Adobe Campaign Standard quando un contenuto duplicato in AEM condivideva la stessa chiave (cq:uuid). (CAMP-49161)
* È stato corretto un errore che si verificava durante l’accesso a un’istanza in cui le pagine non venivano caricate oppure non era possibile aprire le consegne o salvare eventuali modifiche in sospeso. (CAMP-50195)
* È stato risolto un problema che impediva l’apertura dei criteri di avviso di consegna se non veniva compilato il campo **Delivery filter** (Filtro di consegna) applicato da questo criterio. (CAMP-49093)
* È stato risolto un problema che si verificava durante la modifica del pulsante **Secondary** (Secondario) nelle consegne in-app, impedendo di tenere conto delle modifiche. (CAMP-50250)
* Nelle istanze in giapponese, è stato corretto un errore che impediva agli utenti di scegliere Several times a day (Più volte al giorno) come **Execution frequency** (Frequenza di esecuzione) nell’attività **Scheduler** (Pianificazione). (CAMP-50247)
* È stato risolto un problema che si verificava durante l’utilizzo di un’interfaccia utente giapponese, che causava un messaggio di errore durante la selezione di un orario in un modulo di pianificazione attività. (CAMP-49289)
* È stato risolto un errore relativo ai rapporti di notifica push che mostravano le notifiche push ignorate come **Open** (Aperta) anziché **Impression**. (CAMP-45980)
* È stato risolto un problema che poteva causare errori all’apertura di un report. (CAMP-49222)
* È stato risolto un problema che poteva causare un errore nella preparazione dell’e-mail dopo l’eliminazione di un collegamento al contenuto AEM. (CAMP-49877)
* Per risolvere vari problemi, il meccanismo di Riprova è stato migliorato per le consegne che includono contenuto importato da un URL. (CAMP-48888)
* È stato risolto un problema che si verificava dopo la creazione di un nuovo filtro in una risorsa personalizzata e il suo utilizzo come chiave di riconciliazione in una pagina di destinazione. Se la risorsa personalizzata veniva pubblicata nuovamente, il filtro veniva rimosso dall’elenco delle chiavi di riconciliazione disponibili per la pagina di destinazione. (CAMP-49516)
* È stato risolto un problema nelle pagine di destinazione che si verificava quando si utilizzavano condizioni dinamiche con le caselle di controllo. (CAMP-48604)
* È stato risolto un problema che si verificava in un’attività di **Query** se si utilizzava la condizione di filtro “entro il mese di ottobre”. Lavorando da un’istanza impostata su un fuso orario europeo, il mese selezionato per il filtro mostrava settembre anziché ottobre, a causa di un problema di conversione del fuso orario. (CAMP-48602)
* Per ottimizzare il recapito messaggi, ora le e-mail vengono inviate utilizzando la codifica a 7 bit anziché a 8 bit. Questo impedisce ai relè di annullare la validità della firma DKIM durante la conversione da 8 a 7 bit. (CAMP-49016)
* Sono state migliorate le prestazioni durante la duplicazione dei tipi di pubblico al fine di evitare problemi quando si lavora con tipi di pubblico di grandi dimensioni. (CAMP-49639)
* È stato risolto un problema che poteva impedire a un filtro personalizzato di mostrare i risultati corretti se utilizzato in un’attività di **Query**. (CAMP-49417)
* È stato corretto un errore a causa del quale veniva visualizzato un messaggio di errore durante il tentativo di utilizzare in una consegna un frammento il cui nome conteneva una virgola. Il problema è stato risolto e ora è possibile utilizzare le virgole nei nomi dei frammenti. (CAMP-49216)