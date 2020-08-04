---
title: Invio di bozze
description: Scopri come inviare bozze.
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
translation-type: ht
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76
workflow-type: ht
source-wordcount: '592'
ht-degree: 100%

---


# Invio di bozze {#sending-proofs}

## Informazioni sulle bozze {#about-proofs}

Una bozza è un messaggio specifico che ti consente di testare un messaggio prima di inviarlo al target principale. I destinatari della bozza hanno il compito di approvare il messaggio dal punto di vista del contenuto e della forma.

Esistono due tipi di destinatari della bozza:

* I **profili di test** ti consentono di eseguire il targeting di altri destinatari che non soddisfano i criteri di targeting definiti.

   Possono essere aggiunti al pubblico di un messaggio per rilevare qualsiasi uso fraudolento del tuo database di destinatari o per assicurarti che le e-mail arrivino nelle caselle in entrata. Per ulteriori informazioni, consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).

   >[!NOTE]
   >
   >Per inviare una bozza, i profili di test devono essere inclusi nel pubblico del messaggio.

* I **profili di sostituzione** ti consentono di collocarti nella posizione di uno dei profili target e di ottenere una rappresentazione esatta del messaggio che il profilo riceverà. Per ulteriori informazioni, consulta [Verifica dei messaggi e-mail tramite profili target](../../sending/using/testing-messages-using-target.md).

   >[!NOTE]
   >
   >Questa funzione è disponibile solo per il canale e-mail.

## Invio di una bozza {#sending-a-proof}

Per inviare le bozze, effettua le seguenti operazioni:

1. Verifica che i destinatari delle bozze siano stati configurati:
   * I **profili di test** devono essere inclusi nel pubblico del messaggio.
   * I **profili di sostituzione** devono essere aggiunti una volta completata la preparazione del messaggio. A questo proposito, consulta [questa sezione](../../sending/using/testing-messages-using-target.md).

1. Fai clic sul pulsante **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Seleziona il tipo di bozza da utilizzare:

   * **[!UICONTROL Email rendering]**: scegli questa opzione per verificare la modalità di ricezione di un messaggio in base alle caselle in entrata target. Per ulteriori informazioni, consulta [Rendering di e-mail](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: seleziona questa opzione per eseguire il test del messaggio prima di inviarlo al target principale. I destinatari della bozza hanno il compito di approvare la consegna tramite la verifica di contenuto e formato.
   * **[!UICONTROL Proof + Email rendering]**: questa opzione combina le due opzioni precedenti.
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >Il rendering di e-mail è disponibile solo con i profili di test. Se non sono stati aggiunti profili di test al messaggio, potrà essere selezionata solo l’opzione **[!UICONTROL Proof]**.

1. Conferma la tua scelta.

   Le bozze vengono inviate ai destinatari che sono stati configurati.

   ![](assets/bat_select2.png)

1. È possibile visualizzare le bozze utilizzando l’elenco a discesa **[!UICONTROL Proofs]**.

   ![](assets/bat_view.png)

1. Seleziona una bozza per accedere al relativo riepilogo. Per un’e-mail, se hai selezionato l’opzione **Rendering di e-mail** come tipo di bozza, l’icona **[!UICONTROL Access email rendering]** viene visualizzata a destra dell’etichetta della bozza. Consulta [Rendering di e-mail](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

A seconda dei commenti delle persone che ricevono la bozza, ti potrebbe venir richiesto di modificare il contenuto della consegna. Una volta apportate le modifiche, dovrai riavviare la preparazione dell’e-mail e inviare nuovamente una bozza. È possibile accedere a ogni nuova bozza utilizzando il pulsante **[!UICONTROL Show proofs]**.

Devi inviare tutte le bozze necessarie fino a quando non avrai finalizzato il contenuto della consegna. Al termine della procedura, potrai inviare la consegna al target principale e chiudere così il ciclo di approvazione.

## Configurazione della riga dell’oggetto delle bozze {#configuring-proofs-subject-line}

Quando viene inviata una bozza, per impostazione predefinita la sua riga oggetto è configurata con il prefisso **&quot;Proof&quot;**, cui viene aggiunto un contatore che ne indica il numero.

![](assets/proof-prefix.png)

Per modificare la riga dell’oggetto predefinita da utilizzare, procedi come segue:

1. Nel dashboard dei messaggi, fai clic sul pulsante **[!UICONTROL Open properties]**.
1. Nella sezione **[!UICONTROL Advanced parameters]**, definisci il prefisso che vuoi utilizzare per impostazione predefinita nella riga dell’oggetto.

Per nascondere il numero della bozza nella riga dell’oggetto, attiva l’opzione **[!UICONTROL Hide proof prefix counter]**.

>[!NOTE]
>
>Se vuoi nascondere l’intero prefisso della bozza, lascia vuoto il campo **[!UICONTROL Subject line prefix]**.

![](assets/proof-prefix-configuration.png)

1. Fai clic su **[!UICONTROL Confirm]**. Le impostazioni verranno applicate come predefinite a tutte le bozze inviate per il messaggio selezionato.

**Argomento correlato:**

* [Invio di un test, preparazione e invio di un video e-mail](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
* [Verifica dei messaggi e-mail tramite profili target](../../sending/using/testing-messages-using-target.md).
* [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md).
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Configurazione del canale e-mail](../../administration/using/configuring-email-channel.md)
