---
title: Invio di prove
description: Scoprite come inviare le prove di stampa.
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
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# Invio di prove {#sending-proofs}

## Informazioni sulle prove {#about-proofs}

Una prova è un messaggio specifico che consente di verificare un messaggio prima di inviarlo alla destinazione principale. I destinatari della prova hanno il compito di approvare il messaggio (contenuto e modulo).

Esistono due tipi di destinatari della prova:

* **I profili** di test consentono di eseguire il targeting di altri destinatari che non soddisfano i criteri di targeting definiti.

   Possono essere aggiunti al pubblico di un messaggio per rilevare qualsiasi uso fraudolento del database del destinatario o per assicurarsi che le e-mail arrivino nelle caselle in entrata. Per ulteriori informazioni, consultate [Gestione dei profili](../../audiences/using/managing-test-profiles.md)di test.

   >[!NOTE]
   >
   >Per inviare una prova, i profili di test devono essere inclusi nel pubblico del messaggio.

* **I profili** di sostituzione consentono di posizionarsi nella posizione di uno dei profili di destinazione e di ottenere una rappresentazione esatta del messaggio che il profilo riceverà. Per ulteriori informazioni, consultate [Verifica dei messaggi e-mail tramite profili](../../sending/using/testing-messages-using-target.md)di destinazione.

   >[!NOTE]
   >
   >Questa funzione è disponibile solo per il canale e-mail.

## Invio di una prova {#sending-a-proof}

Per inviare le prove di stampa, effettuate le seguenti operazioni:

1. Verificate che i destinatari delle prove siano stati configurati:
   * **I profili** di test devono essere inclusi nel pubblico del messaggio.
   * **I profili** di sostituzione devono essere aggiunti una volta completata la preparazione dei messaggi (vedere [questa sezione](../../sending/using/testing-messages-using-target.md)).

1. Fate clic sul **[!UICONTROL Send a test]** pulsante.

   ![](assets/bat_select.png)

1. Selezionare il tipo di prova da utilizzare:

   * **[!UICONTROL Email rendering]**: selezionate questa opzione per verificare il modo in cui il messaggio viene ricevuto in base alle inbox di destinazione. Per ulteriori informazioni, consultate Rendering [e-](../../sending/using/email-rendering.md)mail.
   * **[!UICONTROL Proof]**: selezionate questa opzione per verificare il messaggio prima di inviarlo alla destinazione principale. I destinatari della prova hanno il compito di approvare la consegna, verificandone il contenuto e il formato.
   * **[!UICONTROL Proof + Email rendering]**: questa opzione combina le due opzioni precedenti.
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >Il rendering e-mail è disponibile solo con i profili di prova. Se al messaggio non sono stati aggiunti profili di prova, solo l&#39; **[!UICONTROL Proof]** opzione sarà disponibile per la selezione.

1. Conferma la tua scelta.

   Le prove vengono inviate ai destinatari configurati.

   ![](assets/bat_select2.png)

1. È possibile visualizzare le prove utilizzando l&#39;elenco a **[!UICONTROL Proofs]** discesa.

   ![](assets/bat_view.png)

1. Selezionate una prova per accedere al relativo riepilogo. Per un messaggio e-mail, se avete selezionato l’opzione di rendering **e-mail come tipo di prova, l’** **[!UICONTROL Access email rendering]** icona viene visualizzata a destra dell’etichetta della prova. Consultate Rendering [](../../sending/using/email-rendering.md)e-mail.

   ![](assets/bat_view2.png)

A seconda dei commenti delle persone che ricevono la prova, potrebbe essere necessario modificare il contenuto della consegna. Una volta apportate le modifiche, è necessario riavviare la preparazione e-mail e inviare nuovamente una prova. È possibile accedere a ogni nuova prova utilizzando il **[!UICONTROL Show proofs]** pulsante.

Devi inviare tutte le prove necessarie fino a quando non avrai completato il contenuto della consegna. Una volta fatto questo, è possibile inviare la consegna alla destinazione principale e chiudere il ciclo di approvazione.

## Configurazione dell&#39;oggetto delle prove {#configuring-proofs-subject-line}

Quando viene inviata una prova, per impostazione predefinita la sua riga oggetto è configurata con il prefisso **&quot;Proof&quot;** , oltre a un contatore che indica il numero della prova.

![](assets/proof-prefix.png)

Per modificare l&#39;oggetto predefinito da utilizzare, procedere come segue:

1. Nel dashboard dei messaggi, fai clic sul **[!UICONTROL Open properties]** pulsante.
1. Nella **[!UICONTROL Advanced parameters]** sezione, definire il prefisso che si desidera utilizzare per impostazione predefinita nella riga dell&#39;oggetto.

Per nascondere il numero della prova nell&#39;oggetto, attivare l&#39; **[!UICONTROL Hide proof prefix counter]** opzione.

>[!NOTE]
>
>Se si desidera nascondere l&#39;intero prefisso della prova, lasciare vuoto il **[!UICONTROL Subject line prefix]** campo.

![](assets/proof-prefix-configuration.png)

1. Clic **[!UICONTROL Confirm]**. Le impostazioni verranno applicate per impostazione predefinita a tutte le prove inviate per il messaggio selezionato.

**Argomento correlato:**

* [Invio di un test, preparazione e invio di un video e-mail](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
* [Verifica dei messaggi e-mail tramite profili](../../sending/using/testing-messages-using-target.md)di destinazione.
* [Gestione dei profili](../../audiences/using/managing-test-profiles.md)di test.
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Configurazione del canale e-mail](../../administration/using/configuring-email-channel.md)
