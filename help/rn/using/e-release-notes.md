---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: ht
source-wordcount: '235'
ht-degree: 100%

---


# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 23.2 - Autunno/inverno 2023 {#fall-23}

>[!AVAILABILITY]
>
>Questa versione è disponibile solo per alcune organizzazioni (disponibilità limitata). Per ulteriori informazioni, contatta il rappresentante Adobe.

### Miglioramenti {#e-rn-improvements}

* **Integrazione con Adobe Experience Manager**. Durante la creazione di un modello di consegna personalizzato per i messaggi transazionali in Adobe Experience Manager, ora puoi selezionare e utilizzare i campi di personalizzazione definiti in Campaign Standard in un elenco a discesa.

* **Scadenza cookie**: la scadenza predefinita dei cookie è ora impostata su 6 mesi, in linea con le raccomandazioni dell’Agenzia francese per la protezione dei dati (CNIL).

* **Miglioramento della ricerca nel profilo**: la ricerca nel profilo è stata ottimizzata per ridurne gli scenari di timeout

* **Localizzazione**: le traduzioni del termine “pubblico” quando si fa riferimento a un gruppo di profili definiti per ricevere un messaggio sono state armonizzate in tutti i prodotti di esperienza digitale per le seguenti lingue:

   * Tedesco: Zielgruppe
   * Portoghese brasiliano: público-alvo
   * Spagnolo: público destinatario

  Queste modifiche verranno implementate gradualmente con le prossime versioni dell’interfaccia utente e della documentazione.

### Altre modifiche {#e-rn-other-changes}

* La messaggistica transazionale ora supporta l’utilizzo di più affinità separate da virgole.

### Correzioni {#e-rn-fixes}

* È stata risolta una regressione che poteva causare problemi di prestazioni se si utilizzavano flussi di lavoro di grandi dimensioni. (CAMP-53369)
* È stato risolto un problema che impediva il funzionamento del collegamento e-mail in un avviso o in una notifica di un flusso di lavoro. (CAMP-51874)
