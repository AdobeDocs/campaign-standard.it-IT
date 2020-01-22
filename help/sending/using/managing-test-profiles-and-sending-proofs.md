---
title: Gestione dei profili di test e invio delle prove
description: Scoprite come gestire profili e prove di test.
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
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Gestione dei profili di test e invio delle prove{#managing-test-profiles-and-sending-proofs}

## Informazioni sui profili di test {#about-test-profiles}

I profili di test consentono di eseguire il targeting di altri destinatari che non soddisfano i criteri di targeting definiti. Vengono aggiunti al pubblico di un messaggio per rilevare qualsiasi uso fraudolento del database del destinatario o per assicurarsi che le e-mail arrivino nelle caselle in entrata.

Potete gestire i profili di test dal menu avanzato **[!UICONTROL Profiles & audiences > Test profiles]**.

Un profilo di test contiene informazioni di contatto fittizie, o informazioni di contatto controllate dal mittente, che possono quindi essere utilizzate in un messaggio nei seguenti contesti:

* Per l&#39;invio di **prove**: la prova è un messaggio specifico utilizzato per controllare il messaggio prima di inviare la consegna finale ai destinatari. Un profilo di prova è incaricato di controllare la consegna, per quanto riguarda il contenuto e il formato. Consultate [Invio delle prove](#sending-proofs).
* Per il rendering **e-** mail: il profilo di test del rendering e-mail viene utilizzato per verificare il modo in cui un messaggio viene visualizzato in base alla inbox del messaggio che lo riceve. Ad esempio, webmail, servizio messaggi, dispositivi mobili ecc. Consultate Rendering [](../../sending/using/email-rendering.md)e-mail.

   Il rendering **e-** mail utilizzato è di sola lettura. I profili di test con questo utilizzo sono disponibili solo out-of-the-box in Adobe Campaign.

* Come **abbondanza**: il messaggio viene inviato al profilo di test esattamente come viene inviato alla destinazione principale. Consultate [Utilizzo delle trappole](#using-traps).
* Per **visualizzare in anteprima** i messaggi: quando visualizzate l&#39;anteprima di un messaggio per verificare gli elementi di personalizzazione, potete selezionare un profilo di test. Consultate [Anteprima dei messaggi](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Gestione dei profili di test {#managing-test-profiles}

### Creazione di profili di test {#creating-test-profiles}

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **Profili e pubblico > Profili** di prova per accedere all&#39;elenco dei profili di test.

   ![](assets/test_profile_creation_1.png)

1. Dal **[!UICONTROL Test profiles]**dashboard, fate clic su** Crea **.

   ![](assets/test_profile_creation_2.png)

1. Immettere i dati per questo profilo.

   ![](assets/test_profile_creation_3.png)

1. Selezionate l’utilizzo desiderato per il profilo di test.

   ![](assets/test_profile_creation_4.png)

1. Inserire i canali di contatto **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, nonché l&#39;indirizzo del profilo di prova, se necessario.

   >[!NOTE]
   >
   >Potete definire un formato e-mail preferito: **[!UICONTROL Text]**o**[!UICONTROL HTML]**.

1. Specificate un tipo di evento e i dati per questo evento se desiderate utilizzare questo profilo di test per testare la personalizzazione di un messaggio transazionale.
1. Fate clic **[!UICONTROL Create]**per salvare il profilo di test.

Il profilo di test verrà quindi aggiunto all&#39;elenco dei profili.

**Argomento correlato:**

[Creazione di un video profilo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) di prova

### Modifica dei profili di prova {#editing-test-profiles}

Per modificare un profilo di test e consultare i dati ad esso collegati o modificarlo:

1. Selezionate il profilo di prova da modificare facendo clic sull’immagine.
1. Consultate o modificate i campi.

   ![](assets/test_profile_edit.png)

1. Fate clic **[!UICONTROL Save]**se avete inserito le modifiche, oppure selezionate il nome del profilo di test e quindi**[!UICONTROL Test profiles]** nella sezione nella parte superiore dello schermo per tornare al dashboard dei profili di test.

## Invio di prove {#sending-proofs}

Una prova è un messaggio specifico che consente di verificare un messaggio prima di inviarlo alla destinazione principale.

I destinatari della prova hanno il compito di approvare il messaggio (contenuto e modulo). Sono definiti nei profili **di** test. Per ulteriori informazioni, consultate [Gestione dei profili](#managing-test-profiles)di test.

Per inviare una prova, i profili di test devono essere inclusi nel pubblico del messaggio.

In un messaggio:

1. Fate clic sul **[!UICONTROL Send a test]**pulsante.

   ![](assets/bat_select.png)

1. Selezionare il tipo di prova da utilizzare:

   * **[!UICONTROL Email rendering]**: selezionate questa opzione per verificare il modo in cui il messaggio viene ricevuto in base alle inbox di destinazione. Per ulteriori informazioni, consultate Rendering[e-](../../sending/using/email-rendering.md)mail.
   * **[!UICONTROL Proof]**: selezionate questa opzione per verificare il messaggio prima di inviarlo alla destinazione principale. I destinatari della prova hanno il compito di approvare la consegna, verificandone il contenuto e il formato.
   * **[!UICONTROL Proof + Email rendering]**: questa opzione combina le due opzioni precedenti.
   ![](assets/bat_select1.png)

1. Conferma la tua scelta.

   Le prove vengono inviate ai profili di test.

   ![](assets/bat_select2.png)

1. È possibile visualizzare le prove utilizzando l&#39;elenco a **[!UICONTROL Proofs]**discesa.

   ![](assets/bat_view.png)

1. Selezionate una prova per accedere al relativo riepilogo. Per un messaggio e-mail, se avete selezionato l’opzione di rendering **e-mail come tipo di prova, l’** **[!UICONTROL Access email rendering]**icona viene visualizzata a destra dell’etichetta della prova. Consultate Rendering[](../../sending/using/email-rendering.md)e-mail.

   ![](assets/bat_view2.png)

A seconda dei commenti delle persone che ricevono la prova, potrebbe essere necessario modificare il contenuto della consegna. Una volta apportate le modifiche, è necessario riavviare la preparazione e-mail e inviare nuovamente una prova. È possibile accedere a ogni nuova prova utilizzando il **[!UICONTROL Show proofs]**pulsante.

Devi inviare tutte le prove necessarie fino a quando non avrai completato il contenuto della consegna. Una volta fatto questo, è possibile inviare la consegna alla destinazione principale e chiudere il ciclo di approvazione.

**Argomento correlato:**

[Invio di un test, preparazione e invio di un video e-mail](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)

## Utilizzo delle trappole {#using-traps}

Quando si utilizzano i trap, il messaggio viene inviato al profilo di test esattamente come viene inviato alla destinazione principale, come mezzo per identificare se il file client viene utilizzato in modo fraudolento.

Le trame sono state originariamente progettate per le consegne per corrispondenza diretta. Consentono di:
* Verificare che il provider di posta diretta invii effettivamente la comunicazione.
* Ricevi la posta nello stesso momento e nelle stesse condizioni dei tuoi clienti.
* Conservate una copia esatta della posta inviata.
* Verificate che l&#39;elenco dei client non venga utilizzato in modo improprio dal provider di posta diretta. In effetti, se qualsiasi altra comunicazione viene inviata all&#39;indirizzo del profilo di test, il file client potrebbe essere stato utilizzato senza che l&#39;utente ne fosse a conoscenza. Per questo motivo l&#39;indirizzo del profilo di prova dovrebbe essere utilizzato solo a questo scopo.

Per ulteriori informazioni sull&#39;aggiunta di trappole all&#39;audience di una corrispondenza diretta, consultate [Aggiunta di profili](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)di test e trap.

Per gli altri canali di comunicazione, potete aggiungere profili di test di trapping alla destinazione principale al fine di:
* Verifica che il messaggio sia stato inviato correttamente.
* Ottieni e conserva una copia esatta del tuo messaggio.
* Monitora quando è stato inviato e ricevuto.

Per utilizzare un profilo di test come trap, deve essere incluso nel pubblico del messaggio.

>[!NOTE]
>
>A differenza dei profili di test utilizzati per [prove](#sending-proofs) o rendering [delle](../../sending/using/email-rendering.md)e-mail, il messaggio viene inviato contemporaneamente alla destinazione principale e ai profili di test utilizzati come trappole.

Quando si definisce l&#39;audience di un messaggio:

1. Dalla **[!UICONTROL Test profiles]**scheda, selezionate un profilo di test. Accertatevi che sia utilizzato**[!UICONTROL Trap]** come previsto.

   ![](assets/trap_select.png)

1. Una volta che il contenuto del messaggio è pronto, fai clic sul **[!UICONTROL Prepare]**pulsante. See[Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Accertatevi di aver selezionato una destinazione principale. In caso contrario, il messaggio non può essere inviato.

1. Fate clic sul **[!UICONTROL Confirm]**pulsante. See[Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

Il messaggio viene inviato alla destinazione principale e al profilo di test.

>[!NOTE]
>
>Quando si utilizza un profilo di prova come trap, per tutti i campi arricchiti di un messaggio, i dati aggiuntivi corrispondenti vengono scelti in modo casuale da un profilo di destinazione reale e assegnati al profilo di prova dell’abbondanza. Per ulteriori informazioni sull&#39;arricchimento, consulta [questo esempio](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
