---
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: ht
source-wordcount: '465'
ht-degree: 100%

---


# Ultima versione{#latest-release}

![Pannello di controllo](assets/do-not-localize/cp-icon.png) **Nuova versione del Pannello di controllo**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=it){target="_blank"}.


## Versione 23.2 - Autunno/inverno 2023 {#fall-23}

>[!AVAILABILITY]
>
>Questa versione è disponibile solo per alcune organizzazioni (disponibilità limitata). Per ulteriori informazioni, contatta il rappresentante Adobe.

### Miglioramenti {#fall-23-rn-improvements}

* **Integrazione con Adobe Experience Manager**. Durante la creazione di un modello di consegna personalizzato per i messaggi transazionali in Adobe Experience Manager, ora puoi selezionare e utilizzare i campi di personalizzazione definiti in Campaign Standard in un elenco a discesa. [Ulteriori informazioni](../../integrating/using/creating-email-experience-manager.md)

* **Scadenza cookie**: la scadenza predefinita dei cookie è ora impostata su 6 mesi, in linea con le raccomandazioni dell’Agenzia francese per la protezione dei dati (CNIL).

* **Miglioramento della ricerca nel profilo**: la ricerca nel profilo è stata ottimizzata per ridurne gli scenari di timeout

* **Localizzazione**: le traduzioni del termine “pubblico” quando si fa riferimento a un gruppo di profili definiti per ricevere un messaggio sono state armonizzate in tutti i prodotti di esperienza digitale per le seguenti lingue:

   * Tedesco: Zielgruppe
   * Portoghese brasiliano: público-alvo
   * Spagnolo: público destinatario

  Queste modifiche verranno implementate gradualmente con le prossime versioni dell’interfaccia utente e della documentazione.


### Altre modifiche {#fall-23-rn-other-changes}

* La messaggistica transazionale ora supporta l’utilizzo di più affinità separate da virgole. [Ulteriori informazioni](../../sending/using/managing-typologies.md)

### Correzioni {#fall-23-rn-fixes}

* È stata risolta una regressione che poteva causare problemi di prestazioni se si utilizzavano flussi di lavoro di grandi dimensioni. (CAMP-53369)
* È stato risolto un problema che impediva il funzionamento del collegamento in un avviso e-mail o in una notifica di un flusso di lavoro. (CAMP-51874)

## Versione 23.1 - Rilascio in primavera/estate 2023 {#apr-23}

### Miglioramenti {#e-rn-improvements}

* Il servizio di messaggistica push è stato modernizzato per ottimizzare il supporto. (CAMP-47959)
* Il servizio di messaggistica SMS è stato migliorato per garantire una maggiore stabilità. (CAMP-52217)
* Adobe ha apportato diverse correzioni di accessibilità per migliorare la facilità d’uso complessiva dell’applicazione. Di seguito sono riportati alcuni esempi di miglioramenti dell’accessibilità:
   * L’accessibilità da tastiera dell’interfaccia è stata ottimizzata in molte schermate.
   * L’applicazione è stata perfezionata per gli utenti touch screen.
   * Il colore di diversi elementi nell’interfaccia è stato modificato per migliorare la visibilità.

### Altre modifiche {#e-rn-changes}

* Il **Flusso di lavoro per la creazione di arricchimenti di reportistica** preconfigurato è stato aggiunto. Dopo aver importato una mappatura target da un’istanza all’altra, esegui semplicemente il flusso di lavoro per importare le voci di arricchimento di reportistica corrispondenti. (CAMP-52452)

### Problemi risolti{#e-rn-patches}

* È stato risolto un problema che poteva causare un errore di timeout durante la visualizzazione del rapporto sugli **Hot click**. (CAMP-51582)
* È stato risolto un problema che poteva impedire l’utilizzo dell’integrazione con il servizio **Luoghi**. (CAMP-51923)
* È stato risolto un problema che poteva impedire il corretto funzionamento del modulo di pianificazione del flusso di lavoro. (CAMP-52003)
* È stato risolto un problema che impediva la visualizzazione dei dettagli di raggruppamento nella versione PDF di un rapporto dinamico personalizzato con un volume elevato di dati. (CAMP-52178)
* È stato risolto un problema che poteva mostrare un errore durante l’accesso ai rapporti. (CAMP-52500)
* È stato risolto un problema che applicava erroneamente a tutti i canali il parametro **Limita le istanze MTA per questo account** del connettore SMS invece di applicarlo solo a SMS. (CAMP-52640)
