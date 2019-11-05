---
title: Regole di controllo
description: Scopri come rafforzare il controllo di qualità dei messaggi con le regole di controllo.
page-status-flag: mai attivato
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: regole di utilizzo
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Regole di controllo{#control-rules}

Le regole di controllo consentono all'utente di verificare la validità e la qualità dei messaggi prima dell'invio, come la visualizzazione dei caratteri, la dimensione dei messaggi SMS, il formato dell'indirizzo, ecc.

Una serie di regole predefinite disponibili in Adobe Campaign garantisce i controlli standard:

* **[!UICONTROL Check subject]** (e-mail): verifica che l'oggetto e l'indirizzo del mittente non contengano caratteri speciali che possono causare problemi a determinati agenti di trasferimento di posta e verifica che l'oggetto del messaggio sia stato completato.
* **[!UICONTROL Check URL labels]** (e-mail): verifica che ciascun URL di tracciamento disponga di un’etichetta.
* **[!UICONTROL Check URLs]** (e-mail): verifica gli URL di tracciamento (presenza del carattere "&amp;").
* **[!UICONTROL Check proof size]** (tutti i canali): genera un messaggio di errore se la popolazione di destinazione della prova supera i 100 destinatari.
* **Controlla il collegamento** di annullamento iscrizione (e-mail): verifica la presenza di almeno un URL di annullamento iscrizione (rinuncia) in ciascun contenuto (HTML e testo).
* **[!UICONTROL Check delivery size]** (tutti i canali): verifica la dimensione dei messaggi.
* **[!UICONTROL Check social network sharing link]** (e-mail): verifica la presenza di un collegamento a una pagina mirror quando si inserisce nel contenuto un collegamento di condivisione social network (ViralLinks).
* **[!UICONTROL A/B Test]**: estrae la popolazione di prova per una consegna con un test A/B.

Potete scegliere il momento in cui la regola verrà applicata da una delle fasi del ciclo di vita della consegna. Selezionare il valore da applicare nell'elenco a discesa dal **[!UICONTROL Phase]** campo della regola di tipologia.

![](assets/typology_phase.png)

I valori possibili sono:

* **All'inizio del targeting**

   La regola di controllo può essere applicata in questa fase in modo che il passaggio di personalizzazione non venga eseguito in caso di errore.

* **Dopo il targeting**

   Se è necessario conoscere il volume del target per applicare la regola di controllo, selezionare questa fase.

   Ad esempio, la regola di controllo delle dimensioni **della prova di** controllo si applica dopo l'area di targeting: questa regola impedisce la preparazione della personalizzazione dei messaggi in presenza di troppi destinatari di prova.

* **All'inizio della personalizzazione**

   Questa fase deve essere selezionata se il controllo riguarda l'approvazione della personalizzazione dei messaggi. La personalizzazione dei messaggi viene effettuata durante la fase di analisi.

* **Al termine dell'analisi**

   Quando un controllo richiede il completamento della personalizzazione dei messaggi, seleziona questa fase.

>[!NOTE]
>
>Per motivi di sicurezza, il contenuto delle regole di controllo non può essere modificato. Il **[!UICONTROL Code]** campo è di sola lettura.
