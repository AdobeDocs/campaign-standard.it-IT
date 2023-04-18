---
title: Note sulla versione 2022
description: In questa pagina sono elencate tutte le versioni di Adobe Campaign Standard del 2022.
feature: Overview
role: User
level: Beginner
exl-id: 8c722084-988d-47bd-98ad-9f5a422980a0
source-git-commit: 362f1f6605bc9667a80cddf2bd1bef4338cda31a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Note sulla versione 2022{#release-notes-2022}

## Versione 22.3.2 {#feb-23}

### Aggiornamento della sicurezza{#rn-security2}

Questa versione include il seguente aggiornamento della sicurezza: Debian è stato aggiornato a v11.0.

## Versione 22.3 - Autunno/inverno 2022 {#sept-22}

### Aggiornamento della sicurezza{#rn-security}

Questa versione include il seguente aggiornamento della sicurezza: Apache Tomcat è stato aggiornato da v7.0 a v8.0.

### Correzioni{#rn-fixes}

* È stato risolto un problema relativo ai rapporti pianificati, che venivano attivati un’ora prima del tempo programmato. (CAMP-51502)
* È stato risolto un problema sugli indicatori di consegna nella dashboard delle consegne che non corrispondevano ai registri di invio (nms:broadLogRcp). (CAMP-51127)
* È stato risolto un problema che impediva l’estensione delle risorse personalizzate con il connettore ACS (offerta Prime). (CAMP-51033)
* È stato migliorato il processo di pubblicazione delle risposte alle richieste di accesso a dati personali per evitare ritardi. (CAMP-50613)

## Versione 22.2 - Giugno 2022 {#june-2022}

**Miglioramenti**

* **Adobe Notification Service** - Campaign viene fornito con Adobe Notification Service che consente alle soluzioni Experience Cloud di segnalare agli utenti Experience Cloud le attività pertinenti. A partire dalla versione 22.2, l’esperienza utente è stata migliorata: le notifiche seguono un ordine di priorità e quelle generate dai prodotti sono separate dagli annunci relativi allo stato dei sistemi Adobe. Inoltre, se una notifica fa riferimento a uno specifico flusso di lavoro, ora puoi accedere al flusso di lavoro corrispondente direttamente dall’e-mail o dalla notifica visualizzata all’interno del prodotto.  Per ulteriori informazioni sulle notifiche di Adobe Campaign, consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).

<!--
* **Optimization in Workflow startup** - Adobe has added a new capability which can tune the number of workflows that start around the same time. This would help prevent CPU spikes that could have led to service interruptions or downtime. Adobe would enable it after 22.2 release. There is no further action item on customer regarding the same.
-->

* **Accessibilità**: Adobe ha apportato diverse correzioni di accessibilità per migliorare la facilità d’uso complessiva dell’applicazione. Queste funzionalità sono attualmente abilitate solo per un gruppo iniziale di utenti e verranno estese a tutti i clienti nelle prossime versioni. I miglioramenti dell’accessibilità includono, ad esempio:

   * Indicatore visibile di attivazione per gli elementi attivabili su ogni schermata
   * Punti di riferimento nella pagina per una navigazione più semplice
   * Aggiunta di nome, ruolo, valore e stato per molti controlli
   * Correzione dei problemi rilevati nelll’ordine di attivazione dinamica sulle schermate principali


**Patch**

* È stato risolto un problema sul flusso di lavoro tecnico Billing (Fatturazione) dovuto a un errore di chiave duplicata. (CAMP-51029)
* Nei report di tracciamento è stata aggiunta la categoria mancante del browser Microsoft Edge. In precedenza le aperture venivano categorizzate come aperture in Microsoft Chrome. (CAMP-51165)
* È stato risolto un problema relativo alle richieste GDPR a causa del quale i dati non venivano eliminati dalle tabelle secondarie. (CAMP-48276)
* È stato risolto un problema in E-mail Designer che impediva il salvataggio della condizione di visibilità di un frammento in un modello per messaggi transazionali. (CAMP-50338)
* È stato risolto un problema nei rapporti di Campaign a causa del quale l’intervallo di date non veniva preso in considerazione. (CAMP-50991)
* È stato corretto un errore che causava il mancato funzionamento delle e-mail pianificate: l’analisi della consegna non veniva avviata perché la consegna risultava ancora nello stato “Nuovo tentativo in sospeso”. (CAMP-50302)
* È stato risolto un problema in E-mail Designer durante l’anteprima di un’e-mail con una sostituzione di profilo. (CAMP-49312)
* È stato risolto un problema relativo al valore vuoto nelle enumerazioni personalizzate: nella creazione di una risorsa personalizzata con un campo di tipo enumerazione di testo contenente un solo valore, questo ora viene impostato per impostazione predefinita, affinché sia possibile creare una query su questo campo come richiesta semplice. (CAMP-50606)


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
<p>Apache log4j ha risolto le vulnerabilità riportate nella versione di Apache log4j v2.17.1. Adobe Campaign Standard utilizza Apache log4j e questa versione include il più recente Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Correzioni di sicurezza**

* In questa versione è incluso un nuovo meccanismo di firma URL per il tracciamento. Il precedente meccanismo è stato disattivato per evitare un problema che causava il blocco errato di alcuni collegamenti di tracciamento validi e firmati dopo la modifica da parte di strumenti di sicurezza di terze parti. (CAMP-48983)

**Miglioramenti**

* È stata migliorata l’elaborazione dei dati di reporting per evitare il sovraccarico del sistema. (CAMP-47578)
* Dopo aver inviato i messaggi in-app, ora puoi scegliere di disattivare la consegna. Ciò consente di eliminare la consegna senza perdere dati di reporting. (CAMP-48469)
* Per evitare problemi, per una colonna di tabella personalizzata gli utenti non possono più utilizzare lo stesso nome utilizzato per la chiave primaria automatica nel database, `"<dataType><resourceName>Id"`. (CAMP-49358)
* Ora puoi monitorare la consegna e tenere traccia dei registri di processo con la nuova funzione a discesa **Job history** (Storico dei processi) nella dashboard dei messaggi. [Ulteriori informazioni](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* Sono state migliorate la stabilità e l‘integrità del database, riducendo le tuple morte, quando nel tempo vengono inviati un gran numero di messaggi in tutti i canali. (CAMP-49755, CAMP-49792, CAMP-49849)
* Sono stati implementati miglioramenti in Campaign Mail Transfer Agent (MTA), per garantire l’aggiornamento automatico delle connessioni in caso di arresto anomalo o riavvio del database. (CAMP-48063)
* Una nuova opzione di tracciamento, **Use Tracking pixel at the top of the email** (Utilizza pixel di tracciamento nella parte superiore dell’e-mail), è stata aggiunta alle proprietà e-mail per spostare il pixel di tracciamento nella parte superiore dell’e-mail invece che nella parte inferiore. (CAMP-49672)

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
* Per risolvere vari problemi, il meccanismo di Riprova è stato migliorato per le consegne che includono contenuto importato da un URL. [Ulteriori informazioni](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* È stato risolto un problema che si verificava dopo la creazione di un nuovo filtro in una risorsa personalizzata e il suo utilizzo come chiave di riconciliazione in una pagina di destinazione. Se la risorsa personalizzata veniva pubblicata nuovamente, il filtro veniva rimosso dall’elenco delle chiavi di riconciliazione disponibili per la pagina di destinazione. (CAMP-49516)
* È stato risolto un problema nelle pagine di destinazione che si verificava quando si utilizzavano condizioni dinamiche con le caselle di controllo. (CAMP-48604)
* È stato risolto un problema che si verificava in un’attività di **Query** se si utilizzava la condizione di filtro “entro il mese di ottobre”. Lavorando da un’istanza impostata su un fuso orario europeo, il mese selezionato per il filtro mostrava settembre anziché ottobre, a causa di un problema di conversione del fuso orario. (CAMP-48602)
* Per ottimizzare il recapito messaggi, ora Adobe Campaign invia le e-mail utilizzando la codifica a 7 bit anziché a 8 bit. Questo impedisce ai relè intermedi di annullare la validità della firma DKIM che potrebbe influire sull’autenticità dei messaggi. (CAMP-49016)
* Sono state migliorate le prestazioni durante la duplicazione dei tipi di pubblico al fine di evitare problemi quando si lavora con tipi di pubblico di grandi dimensioni. (CAMP-49639)
* È stato risolto un problema che poteva impedire a un filtro personalizzato di mostrare i risultati corretti se utilizzato in un’attività di **Query**. (CAMP-49417)
* È stato corretto un errore a causa del quale veniva visualizzato un messaggio di errore durante il tentativo di utilizzare in una consegna un frammento il cui nome conteneva una virgola. Il problema è stato risolto e ora è possibile utilizzare le virgole nei nomi dei frammenti. (CAMP-49216)
