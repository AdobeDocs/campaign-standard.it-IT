---
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# Ultima versione{#latest-release}

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
* Ora puoi monitorare la consegna e tenere traccia dei registri di processo con la nuova funzione a discesa **Job history** (Storico dei processi) nella dashboard dei messaggi. (CAMP-49840)
* Sono state migliorate la stabilità e l‘integrità del database, riducendo le tuple morte, quando nel tempo vengono inviati un gran numero di messaggi in tutti i canali. (CAMP-49755, CAMP-49792, CAMP-49849)
* Sono stati implementati miglioramenti in Campaign Mail Transfer Agent (MTA), per garantire l’aggiornamento automatico delle connessioni in caso di arresto anomalo o riavvio del database. (CAMP-48063)


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


## Versione 21.3 - Settembre 2021 {#release-21-3---sept-2021}

Di seguito sono elencati le nuove funzioni, i miglioramenti e le correzioni inclusi nell’ultima versione di Campaign Standard.

**Novità**

<table> 
<thead> 
<tr> 
<th> <strong>Interfaccia unificata di Experience Cloud</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La barra dell’intestazione di Adobe Campaign è stata modificata per offrirti un’esperienza migliore e unificata in tutti i prodotti e i servizi Experience Cloud. Queste modifiche sono state progettate per rendere il lavoro più facile e includono:</p>
<ul>
<li>Passaggio più semplice da un’organizzazione all’altra o a un’altra applicazione.</li>
<li>Guida utente migliorata: Experience League è ora accessibile direttamente dal prodotto e i risultati delle ricerche includono anche i forum della community e altri contenuti video, per consentirti di accedere più facilmente a più contenuti e aiutarti a trarre il massimo dall’applicazione. Inoltre, è stato aggiunto un meccanismo di feedback nel menu Help, per agevolare la segnalazione di problemi e la condivisione di idee.</li>
<li>Notifiche migliorate: il menu a discesa Notifications ora include due schede, una per le notifiche sui tuoi prodotti e una per gli annunci globali sui prodotti.</li>
</ul>
<p>Per ulteriori informazioni consulta la <a href="../../start/using/interface-description.md#top-bar">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Audit Trail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La nuova funzione Audit Trail acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano in Adobe Campaign. Permette di accedere in autonomia alla cronologia dei dati per poter rispondere a domande quali:</p>
<ul>
<li>Cos’è successo a un dato flusso di lavoro e chi l’ha aggiornato per ultimo?</li>
<li>Chi ha effettuato gli ultimi cambiamenti?</li>
<li>Qual era lo stato precedente?</li>
</ul>
<p>Adobe Campaign ora controlla le azioni di creazione, modifica ed eliminazione per: flussi di lavoro, opzioni, risorse personalizzate. Vengono inoltre tracciate le modifiche di tali elementi.</p>
<p>Per ulteriori informazioni, consulta la <a href="../../administration/using/audit.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modalità diagnostica per i flussi di lavoro</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Ora puoi eseguire i flussi di lavoro Campaign in modalità diagnostica. Questa modalità registra le informazioni utili per risolvere eventuali problemi di esecuzione. L’intero piano di esecuzione viene registrato se una query del flusso di lavoro richiede, per impostazione predefinita, più di un minuto.</p>
<p>Per ulteriori informazioni consulta la <a href="../../automating/using/managing-execution-options.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Miglioramenti della sicurezza**

* È stata migliorata la sicurezza per la protezione contro gli attacchi SSRF. (CAMP-47836)
* L’elenco degli utenti è ora limitato ai soli amministratori. (CAMP-47260)
* Le variabili di ambiente non possono più essere utilizzate come parte dell’espansione dei parametri in un URL. (CAMP-47268)

**Miglioramenti**

* Durante la creazione di una consegna ricorrente in un flusso di lavoro, collegata a un contenuto Adobe Experience Manager, ora lo stato di approvazione del contenuto viene controllato prima dell’invio.
* Il limite di connessione al database è ora allineato con il pacchetto Campaign per evitare errori di connessione.
* Una nuova verifica di coerenza nella pubblicazione delle risorse personalizzate impedisce agli utenti di creare indici duplicati, che causano errori di pubblicazione. Se necessario, un messaggio di errore migliorato chiede all’utente di rinominare l’indice. [Ulteriori informazioni](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Altre modifiche**

* Il servizio Connettore dati e Destinazioni pubblico di Adobe Experience Platform è ora obsoleto con Campaign Standard. Se utilizzi queste funzionalità, devi passare ad origini e destinazioni di Adobe e adattare la tua implementazione. [Ulteriori informazioni](../../integrating/using/get-started-sources-destinations.md)
* Le funzioni obsolete e rimosse sono elencate in [questa pagina](deprecated-features.md).
* È stata introdotta una nuova funzione di aggregazione “StringAgg” per concatenare i valori di una colonna di tipo stringa. (CAMP-47077) [Ulteriori informazioni](../../automating/using/list-of-functions.md#aggregates)
* Il flusso di lavoro tecnico **Aggiorna indicatori di consegna** (updateDeliveryIndicators) è stato migliorato per potenziarne le prestazioni.
* I modelli di messaggistica in-app sono ora disponibili per tutte le lingue supportate in Campaign Standard.
* I tempi di preparazione della consegna sono stati ottimizzati per i messaggi transazionali riducendo il numero di chiamate al server di tracciamento durante l’analisi della consegna.
* Un nuovo messaggio di avviso informa gli utenti di un elevato tasso di mancato recapito.
* Sono stati migliorati i messaggi di errore del registro e gli avvisi per facilitare il debug quando i registri di tracciamento non sono stati recuperati correttamente. (CAMP-48939, CAMP-47360)
* Ora puoi personalizzare completamente gli URL, incluso il nome di dominio. [Ulteriori informazioni](../../designing/using/personalization.md#personalizing-urls)

**Patch**

* È stato corretto un errore di timeout che si verificava durante l’importazione di contenuti e-mail da un URL. (CAMP-49054)
* È stato corretto un errore (-69) causato dalla fine della sessione, quando si accede a un URL contrassegnato con segnalibro o si aggiorna una pagina dal browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* È stato risolto un problema che si verificava durante la sincronizzazione delle regole dal server di recapito messaggi precedente al nuovo server di recapito messaggi. (CAMP-48923)
* È stato risolto un problema che si verificava durante il caricamento di un modello e-mail con tag HTML in Email Designer. (CAMP-48243)
* È stato corretto un errore a causa del quale il contenuto di Adobe Experience Manager non veniva caricato durante la creazione di messaggi transazionali con Email Designer. (CAMP-49075)
* È stato risolto un problema nell’interfaccia a causa del quale veniva aggiunta troppa spaziatura tra la barra superiore e il contenuto.
* È stato risolto un problema relativo ai messaggi transazionali che poteva causare un errore di pubblicazione durante l’utilizzo dei blocchi di contenuto Campaign in contenuti Adobe Experience Manager. (CAMP-49233)
* È stato risolto un problema che poteva causare un messaggio di errore in caso di autenticazione non riuscita. L’utente viene ora reindirizzato alla pagina di accesso.
* È stato risolto un problema di visualizzazione del token che poteva impedire agli utenti di modificare o condividere un rapporto.
* È stato risolto un problema riscontrato durante la pubblicazione di una risorsa personalizzata che utilizzava un’espressione di filtro con relazioni di tabella 1-n. (CAMP-48740)
* È stato risolto un problema di formattazione della data che impediva il recupero delle date di contatto di consegna nelle transizioni del flusso di lavoro. (CAMP-48871)
* È stato risolto un problema che impediva l’estensione dei registri di invio durante la creazione di una dimensione di profilo personalizzata.
* È stato risolto un problema che poteva causare un errore nelle consegne con più varianti di lingua. D’ora in poi, se si elimina la variante di lingua predefinita, prima di creare copie per lingue si deve impostare come predefinita un’altra variante di lingua. (CAMP-48235)
* È stato risolto un problema che causava la visualizzazione di spazi vuoti aggiuntivi nei messaggi e-mail in Outlook se l’utente aveva selezionato l’opzione **Mostra solo su dispositivi mobili** durante la progettazione del messaggio. (CAMP-48902)
* È stato risolto un problema che causava la mancanza dell’ultima data di esecuzione del campo dell’attività di query incrementale dalla scheda **Dati elaborati** dopo l’esecuzione del flusso di lavoro di query incrementale. (CAMP-48879)
* È stato risolto un problema che impediva la corretta definizione di un codice di segmento dinamico nell’attività del flusso di lavoro **Segmentazione**. (CAMP-48727)
* È stato corretto un errore che si verificava in modo casuale durante il tentativo di salvare un flusso di lavoro dopo averlo modificato. (CAMP-48695)
* È stato risolto un problema che impediva la pubblicazione di risorse personalizzate a causa della persistenza di uno schema di dati del trigger anche dopo l’eliminazione di quest’ultimo. (CAMP-48523)
* È stato risolto un problema che impediva il rispetto delle richieste del ciclo di feedback, perché il processo InMail non era in grado di recuperare i registri di consegna da aggiornare. (CAMP-48705)
* È stato risolto un problema che impediva la corretta definizione delle opzioni di esclusione nell’attività del flusso di lavoro **Esclusione**.(CAMP-48355)
* È stato risolto un problema che si verificava quando le attività di arricchimento nei flussi di lavoro includevano abbonamenti o annullamenti di abbonamenti da un servizio. Questo problema causava l’arresto dell’applicazione.
* È stato risolto un problema che poteva impedire l’esecuzione dei flussi di lavoro.
* È stato risolto un problema che poteva impedire agli utenti di rinominare o eliminare i gruppi di sicurezza predefiniti dall’interfaccia utente.
* È stato risolto un problema che poteva impedire agli utenti di eliminare un processo di pubblicazione evento incompleto.
* È stato risolto un problema che causava un errore nel flusso di lavoro di pulizia del database. (CAMP-49097)
