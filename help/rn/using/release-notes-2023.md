---
title: Note sulla versione 2023
description: In questa pagina sono elencate tutte le versioni del 2023 di Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 5817c4d2-4788-4695-bf9a-ec04cc042190
TQID: https://experienceleague.adobe.com/YpZ3cQVh6CeVyCkOChGYLBUo1dMueoWh1AkFj3ycRwk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 463
ht-degree: 100%

---

# Note sulla versione 2023 {#release-notes-2023}

## Versione 23.2 - Autunno/inverno 2023 {#fall-23}

>[!AVAILABILITY]
>
>Questa versione è disponibile solo per alcune organizzazioni (disponibilità limitata). Per ulteriori informazioni, contatta il rappresentante Adobe.

### Miglioramenti {#fall-23-rn-improvements}

* **Integrazione con Adobe Experience Manager**. Durante la creazione di un modello di consegna personalizzato per i messaggi transazionali in Adobe Experience Manager, ora puoi selezionare e utilizzare i campi di personalizzazione definiti in Campaign Standard in un elenco a discesa. [Ulteriori informazioni](../../integrating/using/creating-email-experience-manager.md)

* **Scadenza cookie**: la scadenza predefinita dei cookie è ora impostata su 6 mesi, in linea con i consigli dell’Agenzia francese per la protezione dei dati (CNIL).

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
