---
solution: Campaign Standard
product: campaign
title: Utilizzo delle “trappole”
description: Scopri come utilizzare le trappole nei messaggi.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Indirizzo del seme
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 2%

---


# Utilizzo delle “trappole”{#using-traps}

Quando utilizzi le trappole, il messaggio viene inviato al [profilo di test](../../audiences/using/managing-test-profiles.md) proprio come viene inviato al target principale, in modo da identificare se il file client viene utilizzato in modo fraudolento.

Le trappole sono state originariamente progettate per le consegne di direct mailing. Consentono di:

* Verifica che il provider di direct mailing stia inviando effettivamente la comunicazione.
* Ricevi la posta contemporaneamente e nelle stesse condizioni dei tuoi clienti.
* Conserva una copia esatta della posta inviata.
* Verifica che il provider di direct mailing non utilizzi in modo improprio l’elenco dei client. In effetti, se qualsiasi altra comunicazione viene inviata all&#39;indirizzo del tuo profilo di test, il tuo file client potrebbe essere stato utilizzato senza che te ne accorgi. Per questo motivo l’indirizzo del profilo di test deve essere utilizzato solo a questo scopo.

Per ulteriori informazioni sull’aggiunta di trappole al pubblico di una direct mailing, consulta [Aggiunta di profili di test e di trappola](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Per gli altri canali di comunicazione, puoi aggiungere profili di test di trappola al target principale per:

* Verifica che il messaggio sia stato inviato correttamente.
* Ottieni e conserva una copia esatta del tuo messaggio.
* Monitora quando è stato inviato e ricevuto.

Per utilizzare un profilo di test come trappola, deve essere incluso nel pubblico del messaggio.

>[!NOTE]
>
>A differenza dei profili di test utilizzati per [bozze](../../sending/using/sending-proofs.md) o [rendering di e-mail](../../sending/using/email-rendering.md), il messaggio viene inviato contemporaneamente al target principale e ai profili di test utilizzati come trappole.

Quando definisci il pubblico di un messaggio:

1. Dalla scheda **[!UICONTROL Test profiles]** , seleziona un profilo di test. Assicurati che abbia **[!UICONTROL Trap]** come uso previsto.

   ![](assets/trap_select.png)

1. Quando il contenuto del messaggio è pronto, fai clic sul pulsante **[!UICONTROL Prepare]** . Consulta [Preparazione dell&#39;invio](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Assicurati di aver selezionato una destinazione principale. In caso contrario, il messaggio non può essere inviato.

1. Fai clic sul pulsante **[!UICONTROL Confirm]**. Consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Il messaggio viene inviato al target principale e al profilo di test.

Puoi utilizzare le trappole per l’invio di messaggi transazionali. In questo caso, il profilo di test riceverà un messaggio per ogni configurazione dell’evento. Per ulteriori informazioni sulla messaggistica transazionale, consulta questa [sezione](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Quando si utilizza un profilo di test come trappola, per tutti i campi arricchiti in un messaggio, i dati aggiuntivi corrispondenti vengono prelevati in modo casuale da un profilo di destinazione reale e assegnati al profilo di test di trappola. Per ulteriori informazioni sull&#39;arricchimento, consulta [questo esempio](../../automating/using/enriching-profile-data-file.md).
