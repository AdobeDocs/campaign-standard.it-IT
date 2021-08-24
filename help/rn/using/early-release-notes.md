---
solution: Campaign Standard
product: campaign
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Panoramica
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 89514dad1e318f32dafd3d8add664c37b03c8fb7
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 45%

---

# Note preliminari sulla versione {#new-release}

Questa pagina descrive nuove funzioni, miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).


## Versione 21.3 - Settembre 2021 {#release-21-3---sept-2021}


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
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
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
<p>La nuova funzionalità Audit Trail acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano all’interno di Adobe Campaign. Include un modo self-service per accedere alla cronologia dei dati e rispondere a domande quali:</p>
<ul>
<li>Cos’è successo a questo flusso di lavoro e chi l’ha aggiornato per ultimo?</li>
<li>Chi ha effettuato gli ultimi cambiamenti?</li>
<li>Qual era lo stato precedente?</li>
</ul>
<p>Adobe Campaign ora controlla le azioni di creazione, modifica ed eliminazione per: flussi di lavoro, opzioni, risorse personalizzate. Vengono inoltre monitorate le modifiche apportate a tali elementi.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modalità diagnostica flusso di lavoro</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Ora puoi eseguire i flussi di lavoro Campaign in modalità diagnostica. Questa modalità registra le informazioni per risolvere eventuali problemi di esecuzione. L’intero piano di esecuzione viene registrato se una query del flusso di lavoro richiede, per impostazione predefinita, più di un minuto.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**Miglioramenti**

* Durante la creazione di una consegna ricorrente in un flusso di lavoro, collegata a un contenuto Adobe Experience Manager, lo stato di approvazione del contenuto viene ora controllato prima dell’invio.
* Il limite di connessione al database è ora allineato con il pacchetto Campaign per evitare errori di connessione.
* È stato aggiunto un controllo di coerenza durante la creazione di indici nelle risorse personalizzate e sono stati migliorati i messaggi di errore.

**Patch**

* È stato corretto un errore di timeout durante l’importazione di contenuto e-mail da un URL. (CAMP-49054)
* È stato corretto un errore (-69) causato dalla fine della sessione, quando si accede a un URL contrassegnato con segnalibro o si aggiorna una pagina dal browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* È stato risolto un problema che si verificava durante la sincronizzazione delle regole dal server di recapito messaggi legacy al nuovo server di recapito messaggi. (CAMP-48923)
* È stato risolto un problema che si verificava durante il caricamento di un modello e-mail con tag HTML in E-mail Designer. (CAMP-48243)
