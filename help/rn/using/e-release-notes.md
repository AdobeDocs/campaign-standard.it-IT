---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: b00a0b9e4536d388ccfef3cca0315cabd0d99670
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 30%

---

# Note preliminari sulla versione {#new-release}

Questa pagina descrive nuove funzioni, miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 22.2 - Giugno 2022 {#rn-2022}

**Miglioramenti**

* **Adobe Notification Service** - Campaign viene fornito con Adobe Notification Service che consente alle soluzioni Experience Cloud di segnalare agli utenti Experience Cloud le attività pertinenti. A partire dalla versione 22.2, l’esperienza utente è stata migliorata: le notifiche seguono un ordine di priorità e quelle generate dai prodotti sono separate dagli annunci relativi allo stato dei sistemi Adobe. Inoltre, se una notifica fa riferimento a uno specifico flusso di lavoro, ora puoi accedere al flusso di lavoro corrispondente direttamente dall’e-mail o dalla notifica visualizzata all’interno del prodotto.  Per ulteriori informazioni sulle notifiche di Adobe Campaign, consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Ottimizzazione all&#39;avvio del flusso di lavoro** - Adobe ha aggiunto una nuova funzionalità che può regolare il numero di flussi di lavoro che iniziano circa nello stesso momento. Questo aiuterebbe a evitare picchi di CPU che avrebbero potuto causare interruzioni del servizio o tempi di inattività. Adobe lo attiverà dopo la versione 22.2. Non vi sono ulteriori azioni sul cliente riguardo lo stesso.

* **Accessibilità** - Adobe ha apportato diverse correzioni di accessibilità per migliorare la facilità d’uso complessiva dell’applicazione. Queste funzioni sono attualmente abilitate solo per i primi sviluppatori e verranno implementate a tutti i clienti nella versione ACS 2.3. Esempi di miglioramenti dell’accessibilità includono:

   * Controllo dell&#39;esistenza di un indicatore di messa a fuoco visibile per gli elementi attivabili su ogni schermo
   * Creazione di punti di riferimento per una navigazione più semplice
   * Aggiunta di nome, ruolo, valore e stato per molti controlli
   * Correzione dei problemi rilevati con ordine di attivazione dinamica sulle schermate principali

**Aggiornamento della sicurezza**

* Apache Tomcat è stato aggiornato dalla versione 7 alla versione 8.5.

**Patch**

* È stato risolto un problema sul flusso di lavoro tecnico Fatturazione a causa di un errore di chiave duplicato. (CAMP-51029)
* Aggiunta della categoria mancante del browser Microsoft Edge nei report di tracciamento. In precedenza erano categorizzate con le aperture Microsoft Chrome. (CAMP-51165)
* È stato risolto un problema relativo alle richieste RGPD che non eliminavano dati da tabelle figlio. (CAMP-48276)
* È stato risolto un problema in E-mail Designer che impediva il salvataggio della condizione di visibilità di un frammento in un modello di messaggio transazionale. (CAMP-50338)
* È stato risolto un problema nei rapporti di Campaign a causa del quale l’intervallo di date non veniva preso in considerazione. (CAMP-50991)
* È stato corretto un errore che causava errori nelle e-mail pianificate: impossibile avviare l’analisi della consegna perché la consegna era ancora nello stato &quot;Riprova in sospeso&quot;. (CAMP-50302)
* È stato risolto un problema in E-mail Designer durante l’anteprima di un’e-mail con una sostituzione di profilo. (CAMP-49312)
* È stato risolto un problema relativo al valore vuoto nelle enumerazioni personalizzate: quando crei una risorsa personalizzata con un campo che è un’enumerazione di testo e contiene un solo valore, questo valore viene impostato per impostazione predefinita, in modo da poter creare una query su questo campo come richiesta semplice. (CAMP-50606)
