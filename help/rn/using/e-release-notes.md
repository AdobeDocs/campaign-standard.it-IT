---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# Note preliminari sulla versione {#new-release}

Questa pagina descrive nuove funzioni, miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 22.2 - Giugno 2022 {#rn-2022}

**Miglioramenti**

* **Adobe Notification Service** - Campaign viene fornito con Adobe Notification Service che consente alle soluzioni Experience Cloud di segnalare agli utenti Experience Cloud le attività pertinenti. A partire dalla versione 22.2, l’esperienza utente è stata migliorata: le notifiche seguono un ordine di priorità e quelle generate dai prodotti sono separate dagli annunci relativi allo stato dei sistemi Adobe. Inoltre, se una notifica fa riferimento a uno specifico flusso di lavoro, ora puoi accedere al flusso di lavoro corrispondente direttamente dall’e-mail o dalla notifica visualizzata all’interno del prodotto.  Per ulteriori informazioni sulle notifiche di Adobe Campaign, consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Ottimizzazione all’avvio del flusso di lavoro**: Adobe ha aggiunto una nuova funzionalità che può regolare il numero di flussi di lavoro che iniziano circa nello stesso momento. Questa dovrebbe contribuire a evitare picchi di utilizzo della CPU e conseguenti interruzioni o non disponibilità del servizio. Adobe attiverà queta funzionalità dopo il rilascio della versione 22.2. Non sono richieste ulteriori azioni da parte del cliente riguardo questa funzione.

* **Accessibilità**: Adobe ha apportato diverse correzioni di accessibilità per migliorare la facilità d’uso complessiva dell’applicazione. Queste funzioni sono attualmente abilitate solo per un gruppo iniziale di clienti e verranno estese a tutti i clienti nella versione ACS 22.3. I miglioramenti dell’accessibilità includono, ad esempio:

   * Indicatore visibile di attivazione per gli elementi attivabili su ogni schermata
   * Punti di riferimento nella pagina per una navigazione più semplice
   * Aggiunta di nome, ruolo, valore e stato per molti controlli
   * Correzione dei problemi rilevati nelll’ordine di attivazione dinamica sulle schermate principali

**Aggiornamento della sicurezza**

* Apache Tomcat è stato aggiornato dalla versione 7 alla versione 8.5.


**Patch**

* È stato risolto un problema sul flusso di lavoro tecnico Billing (Fatturazione) dovuto a un errore di chiave duplicata. (CAMP-51029)
* Nei report di tracciamento è stata aggiunta la categoria mancante del browser Microsoft Edge. In precedenza le aperture venivano categorizzate come aperture in Microsoft Chrome. (CAMP-51165)
* È stato risolto un problema relativo alle richieste GDPR a causa del quale i dati non venivano eliminati dalle tabelle secondarie. (CAMP-48276)
* È stato risolto un problema in E-mail Designer che impediva il salvataggio della condizione di visibilità di un frammento in un modello per messaggi transazionali. (CAMP-50338)
* È stato risolto un problema nei rapporti di Campaign a causa del quale l’intervallo di date non veniva preso in considerazione. (CAMP-50991)
* È stato corretto un errore che causava il mancato funzionamento delle e-mail pianificate: l’analisi della consegna non veniva avviata perché la consegna risultava ancora nello stato “Nuovo tentativo in sospeso”. (CAMP-50302)
* È stato risolto un problema in E-mail Designer durante l’anteprima di un’e-mail con una sostituzione di profilo. (CAMP-49312)
* È stato risolto un problema relativo al valore vuoto nelle enumerazioni personalizzate: nella creazione di una risorsa personalizzata con un campo di tipo enumerazione di testo contenente un solo valore, questo ora viene impostato per impostazione predefinita, affinché sia possibile creare una query su questo campo come richiesta semplice. (CAMP-50606)
