---
title: Regole di controllo
description: Scopri come rafforzare il controllo di qualità dei messaggi con le regole di controllo.
page-status-flag: never-activated
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 40de67f4c918b26de6d306ce6af5cb8832741d6f

---


# Regole di controllo {#control-rules}

Le regole di controllo consentono di verificare la validità e la qualità dei messaggi prima dell&#39;invio, come la visualizzazione dei caratteri, la dimensione dei messaggi SMS, il formato dell&#39;indirizzo, ecc.

>[!NOTE]
>
>Per motivi di sicurezza, le regole di controllo sono di sola lettura e non possono essere modificate.

## Regole di controllo predefinite {#default-control-rules}

Un insieme di regole predefinite garantisce i controlli standard. La tabella seguente fornisce informazioni su queste regole, nonché sui relativi canali e fasi [di](#control-rules-execution-phases)esecuzione.

| Etichetta | Canale | Fase di esecuzione | Descrizione |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | E-mail | All&#39;inizio della personalizzazione | Estrae la popolazione di prova per una consegna con un test A/B. |
| **[!UICONTROL Check delivery size]** | Tutto | Dopo il targeting | Controlla la dimensione dei messaggi. |
| **[!UICONTROL Check email content is not empty]** | E-mail | Dopo il targeting | Genera un errore se il contenuto del messaggio è vuoto. |
| **[!UICONTROL Check In-App content for broadcast template]** | In-App | All&#39;inizio personalizzazione | Controlla che il contenuto/gli attivatori in-app non siano vuoti per il modello di trasmissione. |
| **[!UICONTROL Check In-App content for profile template]** | In-App | All&#39;inizio della personalizzazione | Controlla che il contenuto o gli attivatori in-app non siano vuoti per il modello di profilo. |
| **[!UICONTROL Check In-App content for subscriber template]** | In-App | All&#39;inizio della personalizzazione | Controlla che il contenuto o gli attivatori in-app non siano vuoti per il modello di sottoscrittore. |
| **[!UICONTROL Check proof size]** | Tutto | Dopo il targeting | Genera un messaggio di errore se la popolazione di destinazione della prova supera i 100 destinatari. |
| **[!UICONTROL Check social network sharing link]** | E-mail | All&#39;inizio della personalizzazione | Controlla la presenza di un collegamento a una pagina mirror quando si inserisce nel contenuto un collegamento di condivisione social network (ViralLinks). |
| **[!UICONTROL Check subject]** | E-mail | All&#39;inizio della personalizzazione | Controlla che l&#39;oggetto e l&#39;indirizzo del mittente non contengano caratteri speciali che potrebbero causare problemi in alcuni agenti di trasferimento della posta e verifica che l&#39;oggetto del messaggio sia stato completato. |
| **[!UICONTROL Check unsubscription link]** | E-mail | All&#39;inizio della personalizzazione | Controlla la presenza di almeno un URL di annullamento sottoscrizione (opzione di rifiuto) in ciascun contenuto (HTML e testo). |
| **[!UICONTROL Check URL labels]** | E-mail | All&#39;inizio della personalizzazione | Controlla che ciascun URL di tracciamento disponga di un&#39;etichetta. |
| **[!UICONTROL Check URLs]** | E-mail | All&#39;inizio della personalizzazione | Controlla gli URL di tracciamento (presenza del carattere &quot;&amp;&quot;). |

## Fase di esecuzione delle regole di controllo (fasi di esecuzione delle regole di controllo)

Le regole di controllo possono essere applicate in diverse fasi del ciclo di vita della consegna:

* **All&#39;inizio del targeting**: La regola di controllo può essere applicata in questa fase in modo che il passaggio di personalizzazione non venga eseguito in caso di errore.

* **Dopo il targeting**: L&#39;esecuzione dopo il targeting consente di conoscere il volume della destinazione per applicare la regola di controllo.

   Ad esempio, la regola di controllo delle dimensioni **della prova di** controllo si applica dopo l&#39;area di targeting: questa regola impedisce la preparazione della personalizzazione dei messaggi in presenza di troppi destinatari di prova.

* **All&#39;inizio della personalizzazione**: Si applica quando il controllo riguarda l&#39;approvazione della personalizzazione dei messaggi. La personalizzazione dei messaggi viene effettuata durante la fase di analisi.

* **Al termine dell&#39;analisi**: Quando un controllo richiede il completamento della personalizzazione dei messaggi.
