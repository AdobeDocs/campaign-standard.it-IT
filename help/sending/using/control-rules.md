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
TQID: https://experienceleague.adobe.com/lpPFofV3IPl7zmbaR4TOuyCcVqgjwI3maxr-jKzkd0Q
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 15%

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
| **[!UICONTROL Check delivery size]** | Tutti | Dopo il targeting | Controlla la dimensione dei messaggi. |
| **[!UICONTROL Check email content is not empty]** | E-mail | Dopo il targeting | Genera un errore se il contenuto del messaggio è vuoto. |
| **[!UICONTROL Check In-App content for broadcast template]** | In-app | All’inizio della personalizzazione | Controlla che il contenuto in-app e i trigger non siano vuoti per il modello di trasmissione. |
| **[!UICONTROL Check In-App content for profile template]** | In-app | All’inizio della personalizzazione | Controlla che il contenuto in-app e i trigger non siano vuoti per il modello di profilo. |
| **[!UICONTROL Check In-App content for subscriber template]** | In-app | All’inizio della personalizzazione | Controlla che il contenuto in-app e i trigger non siano vuoti per il modello di abbonato. |
| **[!UICONTROL Check proof size]** | Tutti | Dopo il targeting | Genera un messaggio di errore se la popolazione target della bozza supera i 100 destinatari. |
| **[!UICONTROL Check social network sharing link]** | E-mail | All’inizio della personalizzazione | Controlla la presenza di un collegamento a una pagina speculare quando si include nel contenuto un collegamento di condivisione social network (ViralLinks). |
| **[!UICONTROL Check subject]** | E-mail | All’inizio della personalizzazione | Verifica che l&#39;oggetto e l&#39;indirizzo del mittente non contengano caratteri speciali che potrebbero causare problemi a determinati agenti di trasferimento della posta e verifica che l&#39;oggetto del messaggio sia stato completato. |
| **[!UICONTROL Check unsubscription link]** | E-mail | All’inizio della personalizzazione | Verifica la presenza di almeno un URL di annullamento dell’abbonamento (rinuncia) in ogni contenuto (HTML e Testo). |
| **[!UICONTROL Check URL labels]** | E-mail | All’inizio della personalizzazione | Controlla che ogni URL di tracciamento abbia un’etichetta. |
| **[!UICONTROL Check URLs]** | E-mail | All’inizio della personalizzazione | Controlla gli URL di tracciamento (presenza del carattere &quot;&amp;&quot;). |

## Fasi di esecuzione delle regole di controllo {#control-rules-execution-phases}

Le regole di controllo possono essere applicate in diverse fasi del ciclo di vita della consegna:

* **All&#39;inizio del targeting**: è possibile applicare la regola di controllo in questa fase in modo che il passaggio di personalizzazione non venga eseguito in caso di errore.

* **Dopo il targeting**: l&#39;esecuzione dopo il targeting consente di conoscere il volume della destinazione per applicare la regola di controllo.

  Ad esempio, la regola di controllo **Verifica dimensione bozza** si applica dopo la fase di targeting: questa regola impedisce la preparazione della personalizzazione dei messaggi se sono presenti troppi destinatari bozza.

* **All&#39;inizio della personalizzazione**: si applica quando il controllo si riferisce all&#39;approvazione della personalizzazione dei messaggi. La personalizzazione dei messaggi viene eseguita durante la fase di analisi.

* **Al termine dell&#39;analisi**: quando un controllo richiede il completamento della personalizzazione dei messaggi.
