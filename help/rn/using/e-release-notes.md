---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 485927b217fb68064897dd877c2f4a6dd208d443
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 21%

---


# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.
>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 23.1 - Rilascio in primavera/estate 2023 {#apr-23}

### Miglioramenti {#e-rn-improvements}

* Il servizio di messaggistica push è stato aggiornato per migliorare il supporto. (CAMP-47959)
* Il servizio SMS è stato migliorato per garantire una migliore stabilità. (CAMP-52217)
* Adobe ha apportato diverse correzioni di accesso facilitato per migliorare la facilità d’uso complessiva dell’applicazione. Di seguito sono riportati alcuni esempi di miglioramenti dell’accessibilità:
   * L’accessibilità da tastiera dell’interfaccia è stata ottimizzata in molte schermate.
   * L’applicazione è stata migliorata per gli utenti touch screen.
   * Il colore di diversi elementi nell’interfaccia è stato modificato per migliorare la visibilità.

### Altre modifiche {#e-rn-changes}

* Il prodotto pronto all&#39;uso **Flusso di lavoro per la creazione di contenuti di reporting** è stato aggiunto. Dopo aver importato una mappatura di destinazione da un’istanza all’altra, esegui semplicemente il flusso di lavoro per importare le voci di arricchimento di reporting corrispondenti. (CAMP-52452)

### Problemi risolti{#e-rn-patches}

* È stato risolto un problema che poteva causare un errore di timeout durante la visualizzazione del **Hot click** rapporto. (CAMP-51582)
* È stato risolto un problema che poteva impedire l’utilizzo dell’integrazione con **Luoghi** servizio. (CAMP-51923)
* È stato risolto un problema che poteva impedire il corretto funzionamento della pianificazione del flusso di lavoro. (CAMP-52003)
* È stato risolto un problema che impediva la visualizzazione dei dettagli di suddivisione durante la visualizzazione della versione PDF di un rapporto dinamico personalizzato con un volume elevato di dati. (CAMP-52178)
* È stato risolto un problema che poteva visualizzare un errore durante l’accesso ai rapporti. (CAMP-52500)
* È stato risolto un problema che applicava erroneamente il **Limita le istanze MTA per questo account** Parametro del connettore SMS per tutti i canali invece di applicarlo solo a SMS. (CAMP-52640)
