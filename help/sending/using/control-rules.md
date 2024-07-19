---
title: Regole di controllo
description: Scopri come rafforzare il controllo di qualità dei messaggi con le regole di controllo.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 14%

---

# Regole di controllo {#control-rules}

Le regole di controllo ti consentono di verificare la validità e la qualità dei messaggi prima che vengano inviati, come la visualizzazione del carattere, la dimensione del messaggio SMS, il formato dell’indirizzo e così via.

>[!NOTE]
>
>Per motivi di sicurezza, le regole di controllo sono di sola lettura e non possono essere modificate.

## Regole di controllo predefinite {#default-control-rules}

Un insieme di regole predefinite garantisce i controlli standard. La tabella seguente fornisce informazioni su queste regole, nonché sul relativo canale e sulle [fasi di esecuzione](#control-rules-execution-phases).

| Etichetta | Canale | Fase di esecuzione | Descrizione |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | E-mail | All’inizio della personalizzazione | Estrae la popolazione di test per una consegna con un test A/B. |
| **[!UICONTROL Check delivery size]** | Tutto | Dopo il targeting | Controlla la dimensione dei messaggi. |
| **[!UICONTROL Check email content is not empty]** | E-mail | Dopo il targeting | Genera un errore se il contenuto del messaggio è vuoto. |
| **[!UICONTROL Check In-App content for broadcast template]** | In-app | All’inizio della personalizzazione | Controlla che il contenuto in-app e i trigger non siano vuoti per il modello di trasmissione. |
| **[!UICONTROL Check In-App content for profile template]** | In-app | All’inizio della personalizzazione | Controlla che il contenuto in-app e i trigger non siano vuoti per il modello di profilo. |
| **[!UICONTROL Check In-App content for subscriber template]** | In-app | All’inizio della personalizzazione | Controlla che il contenuto in-app e i trigger non siano vuoti per il modello di abbonato. |
| **[!UICONTROL Check proof size]** | Tutto | Dopo il targeting | Genera un messaggio di errore se la popolazione target della bozza supera i 100 destinatari. |
| **[!UICONTROL Check social network sharing link]** | E-mail | All’inizio della personalizzazione | Controlla la presenza di un collegamento a una pagina speculare quando si include nel contenuto un collegamento di condivisione social network (ViralLinks). |
| **[!UICONTROL Check subject]** | E-mail | All’inizio della personalizzazione | Verifica che l&#39;oggetto e l&#39;indirizzo del mittente non contengano caratteri speciali che potrebbero causare problemi a determinati agenti di trasferimento della posta e verifica che l&#39;oggetto del messaggio sia stato completato. |
| **[!UICONTROL Check unsubscription link]** | E-mail | All’inizio della personalizzazione | Verifica la presenza di almeno un URL di annullamento dell’abbonamento (rinuncia) in ogni contenuto (HTML e Text). |
| **[!UICONTROL Check URL labels]** | E-mail | All’inizio della personalizzazione | Controlla che ogni URL di tracciamento abbia un’etichetta. |
| **[!UICONTROL Check URLs]** | E-mail | All’inizio della personalizzazione | Controlla gli URL di tracciamento (presenza del carattere &quot;&amp;&quot;). |

## Fasi di esecuzione delle regole di controllo {#control-rules-execution-phases}

Le regole di controllo possono essere applicate in diverse fasi del ciclo di vita della consegna:

* **All&#39;inizio del targeting**: è possibile applicare la regola di controllo in questa fase in modo che il passaggio di personalizzazione non venga eseguito in caso di errore.

* **Dopo il targeting**: l&#39;esecuzione dopo il targeting consente di conoscere il volume della destinazione per applicare la regola di controllo.

  Ad esempio, la regola di controllo **Verifica dimensione bozza** si applica dopo la fase di targeting: questa regola impedisce la preparazione della personalizzazione dei messaggi se sono presenti troppi destinatari bozza.

* **All&#39;inizio della personalizzazione**: si applica quando il controllo si riferisce all&#39;approvazione della personalizzazione dei messaggi. La personalizzazione dei messaggi viene eseguita durante la fase di analisi.

* **Al termine dell&#39;analisi**: quando un controllo richiede il completamento della personalizzazione dei messaggi.
