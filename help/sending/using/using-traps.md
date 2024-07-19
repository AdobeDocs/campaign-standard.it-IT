---
title: Utilizzo delle “trappole”
description: Scopri come utilizzare le trappole nei messaggi.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Seed Address
role: User
level: Intermediate
exl-id: 0482a946-35b1-426f-8505-42adcd1c3bbb
source-git-commit: ee3ab5304e80ea098f7e172f6b3f4af4324e8eb4
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 2%

---

# Utilizzo delle “trappole” {#using-traps}

Quando si utilizzano le trap, il messaggio viene inviato al [profilo di test](../../audiences/using/managing-test-profiles.md) esattamente come viene inviato alla destinazione principale, in modo da identificare se il file client viene utilizzato in modo fraudolento.

Le trappole sono state originariamente progettate per le consegne di direct mailing. Consentono di:

* Verifica che il provider di direct mailing stia inviando effettivamente la comunicazione.
* Ricevi la posta nello stesso momento e nelle stesse condizioni dei tuoi clienti.
* Conserva una copia esatta dell’e-mail inviata.
* Verifica che l’elenco dei clienti non venga utilizzato in modo improprio dal provider di direct mailing. In effetti, se viene inviata qualsiasi altra comunicazione all’indirizzo del tuo profilo di test, il file client potrebbe essere stato utilizzato a tua insaputa. Per questo motivo, l’indirizzo del profilo di test deve essere utilizzato solo a questo scopo.

Per ulteriori informazioni sull&#39;aggiunta di trap al pubblico di una direct mailing, consulta [Aggiunta di profili di test e di trap](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Per gli altri canali di comunicazione, puoi aggiungere profili di test di abbondanza al target principale per:

* Verifica che il messaggio sia stato inviato correttamente.
* Ottieni e conserva una copia esatta del messaggio.
* Tieni traccia di quando è stato inviato e ricevuto.

Per utilizzare un profilo di test come una trappola, è necessario includerlo nel pubblico del messaggio.

>[!NOTE]
>
>A differenza dei profili di test utilizzati per [bozze](../../sending/using/sending-proofs.md) o [rendering di e-mail](../../sending/using/email-rendering.md), il messaggio viene inviato contemporaneamente alla destinazione principale e ai profili di test utilizzati come trap.

Quando definisci il pubblico di un messaggio:

1. Dalla scheda **[!UICONTROL Test profiles]**, selezionare un profilo di test. Assicurarsi che **[!UICONTROL Trap]** sia l&#39;uso previsto.

   ![](assets/trap_select.png)

1. Quando il contenuto del messaggio è pronto, fare clic sul pulsante **[!UICONTROL Prepare]**. Vedere [Preparazione dell&#39;invio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Assicurati di aver selezionato una destinazione principale. In caso contrario, il messaggio non può essere inviato.

1. Fai clic sul pulsante **[!UICONTROL Confirm]**. Consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Il messaggio viene inviato al target principale e al profilo di test.

Puoi utilizzare le &quot;trappole&quot; per inviare messaggi transazionali. In questo caso, il profilo di test riceverà un messaggio per ogni configurazione dell’evento. Per ulteriori informazioni sui messaggi transazionali, consulta questa [sezione](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Quando si utilizza un profilo di test come trappola, i campi arricchiti all’interno di un messaggio vengono selezionati in modo casuale dai profili di destinazione effettivi e assegnati al profilo di test della trappola. Tuttavia, tieni presente che se il profilo di destinazione reale viene escluso a causa delle regole di tipologia applicate durante la preparazione del primo messaggio, la preparazione della consegna avrà esito negativo. Questo errore si verifica perché i valori dei campi arricchiti non possono essere sostituiti dal profilo di trap. Di conseguenza, le regole di tipologia di esclusione potrebbero non essere applicate correttamente ai destinatari effettivi.
>
>Per evitare questa situazione, evita di utilizzare i profili di test di trappole contemporaneamente alle regole di filtro o di affaticamento nella tipologia transazionale. Ulteriori informazioni sull’arricchimento. Per ulteriori informazioni sull&#39;arricchimento, vedere [questo esempio](../../automating/using/enriching-profile-data-file.md).
