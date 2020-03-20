---
title: Gestione dei profili di test
description: Scoprite come gestire i profili di test.
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
source-git-commit: 767d4233236019213003961aae1abb317198e581

---


# Gestione dei profili di test {#managing-test-profiles}

## Informazioni sui profili di test {#about-test-profiles}

I profili di test consentono di eseguire il targeting di altri destinatari che non soddisfano i criteri di targeting definiti. Vengono aggiunti al pubblico di un messaggio per rilevare qualsiasi uso fraudolento del database del destinatario o per assicurarsi che le e-mail arrivino nelle caselle in entrata.

Potete gestire i profili di test dal menu avanzato **[!UICONTROL Profiles & audiences > Test profiles]**.

Un profilo di test contiene informazioni di contatto fittizie, o informazioni di contatto controllate dal mittente, che possono quindi essere utilizzate in un messaggio nei seguenti contesti:

* Per l&#39;invio di **prove**: La prova è un messaggio specifico utilizzato per controllare il messaggio prima di inviare la consegna finale ai destinatari. Un profilo di prova è incaricato di controllare la consegna, per quanto riguarda il contenuto e il formato. Consultate [Invio delle prove](../../sending/using/sending-proofs.md).
* Per il rendering **e-** mail: Il profilo di test del rendering e-mail viene utilizzato per verificare il modo in cui un messaggio viene visualizzato in base alla inbox del messaggio che lo riceve. Ad esempio, webmail, servizio messaggi, dispositivi mobili ecc. Consultate Rendering [](../../sending/using/email-rendering.md)e-mail.

   Il rendering **e-** mail utilizzato è di sola lettura. I profili di test con questo utilizzo sono disponibili solo out-of-the-box in Adobe Campaign.

* Come **abbondanza**: Il messaggio viene inviato al profilo di test esattamente come viene inviato alla destinazione principale. Consultate [Utilizzo delle trappole](../../sending/using/using-traps.md).
* Per **visualizzare in anteprima** i messaggi: Quando visualizzate l&#39;anteprima di un messaggio per verificare gli elementi di personalizzazione, potete selezionare un profilo di test. Consultate [Anteprima dei messaggi](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Creazione di profili di test {#creating-test-profiles}

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **Profili e pubblico > Profili** di prova per accedere all&#39;elenco dei profili di test.

   ![](assets/test_profile_creation_1.png)

1. Dal **[!UICONTROL Test profiles]** dashboard, fate clic su **Crea**.

   ![](assets/test_profile_creation_2.png)

1. Immettere i dati per questo profilo.

   ![](assets/test_profile_creation_3.png)

1. Selezionate l’utilizzo desiderato per il profilo di test.

   ![](assets/test_profile_creation_4.png)

1. Inserire i canali di contatto **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, nonché l&#39;indirizzo del profilo di prova, se necessario.

   >[!NOTE]
   >
   >Potete definire un formato e-mail preferito: **[!UICONTROL Text]** o **[!UICONTROL HTML]**.

1. Specificate un tipo di evento e i dati per questo evento se desiderate utilizzare questo profilo di test per testare la personalizzazione di un messaggio transazionale.
1. Fate clic **[!UICONTROL Create]** per salvare il profilo di test.

Il profilo di test verrà quindi aggiunto all&#39;elenco dei profili.

**Argomento correlato:**

[Video sulla creazione di un profilo](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) di prova

## Modifica dei profili di prova {#editing-test-profiles}

Per modificare un profilo di test e consultare i dati ad esso collegati o modificarlo:

1. Selezionate il profilo di prova da modificare facendo clic sull’immagine.
1. Consultate o modificate i campi.

   ![](assets/test_profile_edit.png)

1. Fate clic **[!UICONTROL Save]** se avete inserito le modifiche, oppure selezionate il nome del profilo di test e quindi **[!UICONTROL Test profiles]** nella sezione nella parte superiore dello schermo per tornare al dashboard dei profili di test.
