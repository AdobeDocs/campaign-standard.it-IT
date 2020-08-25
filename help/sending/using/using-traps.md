---
title: Utilizzo delle “trappole”
description: Scopri come utilizzare i trap nei messaggi.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---


# Utilizzo delle “trappole”{#using-traps}

Quando si utilizzano i trap, il messaggio viene inviato al profilo [di](../../audiences/using/managing-test-profiles.md) prova così come viene inviato alla destinazione principale, in modo da identificare se il file client viene utilizzato in modo fraudolento.

Le trame sono state originariamente progettate per le consegne per corrispondenza diretta. Consentono di:

* Verificare che il provider di posta diretta invii effettivamente la comunicazione.
* Ricevi la posta nello stesso momento e nelle stesse condizioni dei tuoi clienti.
* Tenete una copia esatta della posta che è stata inviata.
* Verificate che l&#39;elenco dei client non venga utilizzato in modo improprio dal provider di posta diretta. In effetti, se qualsiasi altra comunicazione viene inviata all&#39;indirizzo del profilo di test, il file client potrebbe essere stato utilizzato senza che l&#39;utente ne fosse a conoscenza. Per questo motivo l&#39;indirizzo del profilo di prova dovrebbe essere utilizzato solo a questo scopo.

Per ulteriori informazioni sull&#39;aggiunta di trappole all&#39;audience di una corrispondenza diretta, consultate [Aggiunta di profili](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)di test e trap.

Per gli altri canali di comunicazione, potete aggiungere profili di test di trapping alla destinazione principale al fine di:

* Verifica che il messaggio sia stato inviato correttamente.
* Ottieni e conserva una copia esatta del tuo messaggio.
* Monitora quando è stato inviato e ricevuto.

Per utilizzare un profilo di test come trap, deve essere incluso nel pubblico del messaggio.

>[!NOTE]
>
>A differenza dei profili di test utilizzati per [prove](../../sending/using/sending-proofs.md) o per il rendering [delle](../../sending/using/email-rendering.md)e-mail, il messaggio viene inviato contemporaneamente alla destinazione principale e ai profili di test utilizzati come trappole.

Quando si definisce l&#39;audience di un messaggio:

1. Dalla **[!UICONTROL Test profiles]** scheda, selezionate un profilo di test. Accertatevi che sia utilizzato **[!UICONTROL Trap]** come previsto.

   ![](assets/trap_select.png)

1. Una volta che il contenuto del messaggio è pronto, fai clic sul **[!UICONTROL Prepare]** pulsante. See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Accertatevi di aver selezionato una destinazione principale. In caso contrario, il messaggio non può essere inviato.

1. Fai clic sul pulsante **[!UICONTROL Confirm]**. Consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Il messaggio viene inviato alla destinazione principale e al profilo di test.

Potete utilizzare i trap per inviare messaggi transazionali. In questo caso, il profilo di test riceverà un messaggio per la configurazione dell&#39;evento. For more on transactional messaging, see this [section](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Quando si utilizza un profilo di prova come trap, per tutti i campi arricchiti di un messaggio, i dati aggiuntivi corrispondenti vengono scelti in modo casuale da un profilo di destinazione reale e assegnati al profilo di prova dell’abbondanza. Per ulteriori informazioni sull&#39;arricchimento, consulta [questo esempio](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
