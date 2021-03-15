---
solution: Campaign Standard
product: campaign
title: Regole di controllo
description: Scopri come rafforzare il controllo della qualità dei messaggi con le regole di controllo.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Regole di tipologia
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 4%

---


# Regole di controllo {#control-rules}

Le regole di controllo ti consentono di verificare la validità e la qualità dei messaggi prima che vengano inviati, ad esempio la visualizzazione del carattere, la dimensione del messaggio SMS, il formato dell’indirizzo e così via.

>[!NOTE]
>
>Per motivi di sicurezza, le regole di controllo sono di sola lettura e non possono essere modificate.

## Regole di controllo predefinite {#default-control-rules}

Un insieme di regole predefinite assicura i controlli standard. La tabella seguente fornisce informazioni su queste regole, nonché sul relativo canale e sulle [fasi di esecuzione](#control-rules-execution-phases).

| Etichetta | Canale | Fase di esecuzione | Descrizione |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | E-mail | All&#39;inizio della personalizzazione | Estrae la popolazione di test per una consegna con un test A/B. |
| **[!UICONTROL Check delivery size]** | Tutto | Dopo il targeting | Controlla le dimensioni dei messaggi. |
| **[!UICONTROL Check email content is not empty]** | E-mail | Dopo il targeting | Genera un errore se il contenuto del messaggio è vuoto. |
| **[!UICONTROL Check In-App content for broadcast template]** | In-App | All’inizio della personalizzazione | Controlla che il contenuto o gli attivatori in-app non siano vuoti per il modello di trasmissione. |
| **[!UICONTROL Check In-App content for profile template]** | In-App | All&#39;inizio della personalizzazione | Controlla che il contenuto o gli attivatori in-app non siano vuoti per il modello di profilo. |
| **[!UICONTROL Check In-App content for subscriber template]** | In-App | All&#39;inizio della personalizzazione | Controlla che il contenuto o gli attivatori in-app non siano vuoti per il modello di sottoscrittore. |
| **[!UICONTROL Check proof size]** | Tutto | Dopo il targeting | Genera un messaggio di errore se la popolazione target della bozza supera i 100 destinatari. |
| **[!UICONTROL Check social network sharing link]** | E-mail | All&#39;inizio della personalizzazione | Controlla la presenza di un collegamento a una pagina speculare quando si include nel contenuto un collegamento di condivisione del social network (ViralLinks). |
| **[!UICONTROL Check subject]** | E-mail | All&#39;inizio della personalizzazione | Controlla che l&#39;oggetto e l&#39;indirizzo del mittente non contengano caratteri speciali che possono causare problemi a determinati agenti di trasferimento della posta e controlla che l&#39;oggetto del messaggio sia stato completato. |
| **[!UICONTROL Check unsubscription link]** | E-mail | All&#39;inizio della personalizzazione | Verifica la presenza di almeno un URL di annullamento dell’abbonamento (opt-out) in ciascun contenuto (HTML e testo). |
| **[!UICONTROL Check URL labels]** | E-mail | All&#39;inizio della personalizzazione | Controlla che ogni URL di tracciamento abbia un&#39;etichetta. |
| **[!UICONTROL Check URLs]** | E-mail | All&#39;inizio della personalizzazione | Controlla gli URL di tracciamento (presenza del carattere &quot;&amp;&quot;). |

## Fasi di esecuzione delle regole di controllo {#control-rules-execution-phases}

Le regole di controllo possono essere applicate in diverse fasi del ciclo di vita della consegna:

* **All’inizio del targeting**: La regola di controllo può essere applicata in questa fase in modo che il passaggio di personalizzazione non venga eseguito in caso di errore.

* **Dopo il targeting**: L’esecuzione dopo il targeting ti consente di conoscere il volume del target per applicare la regola di controllo.

   Ad esempio, la regola di controllo **Check proof size** si applica dopo la fase di targeting: questa regola impedisce la preparazione della personalizzazione dei messaggi se sono presenti troppi destinatari di bozza.

* **All’inizio della personalizzazione**: Si applica quando il controllo si riferisce all’approvazione della personalizzazione dei messaggi. La personalizzazione dei messaggi viene eseguita durante la fase di analisi.

* **Al termine dell&#39;analisi**: Quando un controllo richiede il completamento della personalizzazione dei messaggi.
