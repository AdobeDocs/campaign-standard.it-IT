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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# Utilizzo delle “trappole” {#using-traps}

Quando si utilizzano le trap, il messaggio viene inviato al [profilo di test](../../audiences/using/managing-test-profiles.md) così come viene inviato al target principale, come mezzo per identificare se il file client viene utilizzato in modo fraudolento.

Le trappole sono state originariamente progettate per le consegne di direct mailing. Consentono di:

* Verifica che il provider di direct mailing stia inviando effettivamente la comunicazione.
* Ricevi la posta nello stesso momento e nelle stesse condizioni dei tuoi clienti.
* Conserva una copia esatta dell’e-mail inviata.
* Verifica che l’elenco dei clienti non venga utilizzato in modo improprio dal provider di direct mailing. In effetti, se viene inviata qualsiasi altra comunicazione all’indirizzo del tuo profilo di test, il file client potrebbe essere stato utilizzato a tua insaputa. Per questo motivo, l’indirizzo del profilo di test deve essere utilizzato solo a questo scopo.

Per ulteriori informazioni sull’aggiunta di trap al pubblico di una direct mailing, consulta [Aggiunta di profili di test e di trappole](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Per gli altri canali di comunicazione, puoi aggiungere profili di test di abbondanza al target principale per:

* Verifica che il messaggio sia stato inviato correttamente.
* Ottieni e conserva una copia esatta del messaggio.
* Tieni traccia di quando è stato inviato e ricevuto.

Per utilizzare un profilo di test come una trappola, è necessario includerlo nel pubblico del messaggio.

>[!NOTE]
>
>A differenza dei profili di test utilizzati per [bozze](../../sending/using/sending-proofs.md) o [rendering di e-mail](../../sending/using/email-rendering.md), il messaggio viene inviato contemporaneamente al target principale e ai profili di test utilizzati come trappole.

Quando definisci il pubblico di un messaggio:

1. Dalla sezione **[!UICONTROL Test profiles]** , seleziona un profilo di test. Assicurati che abbia **[!UICONTROL Trap]** come uso previsto.

   ![](assets/trap_select.png)

1. Quando il contenuto del messaggio è pronto, fai clic su **[!UICONTROL Prepare]** pulsante. Consulta [Preparazione dell’invio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Assicurati di aver selezionato una destinazione principale. In caso contrario, il messaggio non può essere inviato.

1. Fai clic sul pulsante **[!UICONTROL Confirm]**. Consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Il messaggio viene inviato al target principale e al profilo di test.

Puoi utilizzare le &quot;trappole&quot; per inviare messaggi transazionali. In questo caso, il profilo di test riceverà un messaggio per ogni configurazione dell’evento. Per ulteriori informazioni sulla messaggistica transazionale, consulta [sezione](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Quando si utilizza un profilo di test come trappola, per tutti i campi arricchiti in un messaggio, i dati aggiuntivi corrispondenti vengono scelti in modo casuale da un profilo di destinazione reale e assegnati al profilo di test della trappola. Per ulteriori informazioni sull’arricchimento, consulta [questo esempio](../../automating/using/enriching-profile-data-file.md).
