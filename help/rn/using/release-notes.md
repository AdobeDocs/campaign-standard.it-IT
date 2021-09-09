---
solution: Campaign Standard
product: campaign
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: cedb8a0837d9c0339149efd2a99c777a12ef260d
workflow-type: tm+mt
source-wordcount: '1074'
ht-degree: 38%

---


# Ultima versione{#latest-release}

## Versione 21.3 - Settembre 2021 {#release-21-3---sept-2021}

Di seguito sono elencate nuove funzioni, miglioramenti e correzioni inclusi nell’ultima versione di Campaign Standard.

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
* L’elenco degli utenti è ora limitato solo agli amministratori. (CAMP-47260)
* Le variabili di ambiente non possono più essere utilizzate come parte dell’espansione dei parametri in un URL. (CAMP-47268)

**Miglioramenti**

* Durante la creazione di una consegna ricorrente in un flusso di lavoro, collegata a un contenuto Adobe Experience Manager, ora lo stato di approvazione del contenuto viene controllato prima dell’invio.
* Il limite di connessione al database è ora allineato con il pacchetto Campaign per evitare errori di connessione.
* Una nuova verifica di coerenza nella pubblicazione delle risorse personalizzate impedisce agli utenti di creare indici duplicati, causando errori di pubblicazione. Un messaggio di errore migliorato richiede all’utente di rinominare l’indice se necessario.

**Altre modifiche**

* Il servizio Connettore dati e Destinazioni pubblico di Adobe Experience Platform è ora obsoleto con Campaign Standard. Se utilizzi queste funzionalità, devi passare ad Origini e Destinazioni di Adobe e adattare la tua implementazione. [Ulteriori informazioni](../../integrating/using/get-started-sources-destinations.md)
* Le funzioni obsolete e rimosse sono elencate in [questa pagina](deprecated-features.md).
* È stata introdotta una nuova funzione di aggregazione “StringAgg” per concatenare i valori di una colonna di tipo stringa. (CAMP-47077) [Ulteriori informazioni](../../automating/using/list-of-functions.md#aggregates)
* Il flusso di lavoro tecnico **Aggiorna indicatori di consegna** (updateDeliveryIndicators) è stato migliorato per migliorare le prestazioni.
* I modelli di messaggistica in-app sono ora disponibili per tutte le lingue supportate in Campaign Standard.
* I tempi di preparazione della consegna sono stati ottimizzati per i messaggi transazionali riducendo il numero di chiamate al server di tracciamento durante l’analisi della consegna.
* Un nuovo messaggio di avviso informa gli utenti di un elevato tasso di mancato recapito.
* Sono stati migliorati i messaggi di errore del registro e gli avvisi per facilitare il debug quando i registri di tracciamento non sono stati recuperati correttamente. (CAMP-48939, CAMP-47360)
* Ora puoi personalizzare completamente gli URL, incluso il nome di dominio. [Ulteriori informazioni](../../designing/using/personalization.md#personalizing-urls)

**Patch**

* È stato corretto un errore di timeout che si verificava durante l’importazione di contenuti e-mail da un URL. (CAMP-49054)
* È stato corretto un errore (-69) causato da una fine della sessione, quando si accede a un URL con segnalibro o si aggiorna una pagina dal browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* È stato risolto un problema che si verificava durante la sincronizzazione delle regole dal server di recapito messaggi precedente al nuovo server di recapito messaggi. (CAMP-48923)
* È stato risolto un problema che si verificava durante il caricamento di un modello e-mail con tag HTML in Email Designer. (CAMP-48243)
* È stato corretto un errore a causa del quale il contenuto Adobe Experience Manager non veniva caricato durante la creazione di messaggi transazionali con E-mail Designer. (CAMP-49075)
* È stato risolto un problema nell’interfaccia a causa del quale veniva aggiunta troppa spaziatura tra la barra superiore e il contenuto.
* È stato risolto un problema relativo ai messaggi transazionali che poteva causare un errore di pubblicazione durante l’utilizzo dei blocchi di contenuto Campaign nel contenuto Adobe Experience Manager. (CAMP-49233)
* È stato risolto un problema che poteva causare un messaggio di errore in caso di errore di autenticazione. L’utente viene ora reindirizzato alla pagina di accesso.
* È stato risolto un problema di visualizzazione del token che poteva impedire agli utenti di modificare o condividere un rapporto.
* È stato risolto un problema durante la pubblicazione di una risorsa personalizzata che utilizzava un’espressione di filtro con relazioni di tabella 1-n. (CAMP-48740)
* È stato risolto un problema di formattazione della data che impediva il recupero delle date di contatto di consegna nelle transizioni del flusso di lavoro. (CAMP-48871)
* È stato risolto un problema che impediva l’estensione dei registri di invio durante la creazione di una dimensione di profilo personalizzata.
* È stato risolto un problema che poteva causare un errore nelle consegne con più varianti di lingua. D’ora in poi, se un utente elimina la variante di lingua predefinita, prima di creare copie di lingue è necessario impostare come predefinita un’altra variante di lingua. (CAMP-48235)
* È stato risolto un problema che causava la visualizzazione di spazi vuoti aggiuntivi nei messaggi e-mail in Outlook se l&#39;utente aveva selezionato l&#39;opzione **Mostra solo su dispositivi mobili** durante la progettazione del messaggio. (CAMP-48902)
* È stato risolto un problema che causava la mancanza dell’ultima data di esecuzione del campo dell’attività di query incrementale dalla scheda **Dati elaborati** dopo l’esecuzione del flusso di lavoro di query incrementale. (CAMP-48879)
* È stato risolto un problema che impediva la corretta definizione di un codice di segmento dinamico nell&#39;attività del flusso di lavoro **Segmentazione** . (CAMP-48727)
* È stato corretto un errore che si verificava in modo casuale durante il tentativo di salvare un flusso di lavoro dopo averlo modificato. (CAMP-48695)
* È stato risolto un problema che impediva la pubblicazione di risorse personalizzate a causa di uno schema di dati del trigger rimanente anche dopo l’eliminazione del trigger. (CAMP-48523)
* È stato risolto un problema che impediva il rispetto delle richieste del ciclo di feedback, perché il processo InMail non era in grado di recuperare i registri di consegna da aggiornare. (CAMP-48705)
* È stato risolto un problema che impediva la corretta definizione delle opzioni di esclusione nell&#39;attività del flusso di lavoro **Esclusione** .(CAMP-48355)
* È stato risolto un problema che si verificava quando le attività di arricchimento nei flussi di lavoro includevano abbonamenti o annullamenti di abbonamenti da un servizio. Questo problema ha causato l&#39;arresto anomalo.
* È stato risolto un problema che poteva impedire l’esecuzione dei flussi di lavoro.
* È stato risolto un problema che poteva impedire agli utenti di rinominare o eliminare i gruppi di sicurezza predefiniti dall’interfaccia utente.
* È stato risolto un problema che poteva impedire agli utenti di eliminare un processo di pubblicazione di eventi incompleto.
* È stato risolto un problema che causava un errore nel flusso di lavoro di pulizia del database. (CAMP-49097)
