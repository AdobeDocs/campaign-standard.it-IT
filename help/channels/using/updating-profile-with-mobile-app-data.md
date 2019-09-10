---
title: Creazione e aggiornamento di informazioni sul profilo basate sui dati dell'applicazione mobile
seo-title: Creazione e aggiornamento di informazioni sul profilo basate sui dati dell'applicazione mobile
description: Creazione e aggiornamento di informazioni sul profilo basate sui dati dell'applicazione mobile
seo-description: Scopri come creare e aggiornare le informazioni sul profilo basate sui dati delle applicazioni mobili.
page-status-flag: never-activated
uuid: 8 cf 74 cad-b 1 ba -4 aad -83 bd -7289 cb 22 d 5 f 4
contentOwner: lemaitre
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: notifiche push
discoiquuid: dc 944 c 85-2059-46 df-b 396-676 fe 3617 dd 1
context-tags: delivery, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2b514387a803de25c6ddcc41bdf0e56692cfa446

---


# Creazione e aggiornamento di informazioni sul profilo basate sui dati dell'applicazione mobile

## Panoramica

Questa pagina descrive i passaggi necessari per sviluppare un flusso di lavoro che crea/aggiorna dati di profilo dopo che un'applicazione Mobile invia dati PII, su base pianificata.

* **PII** è «Informazioni personali». Possono essere presenti dati, comprese informazioni che non vengono visualizzate nella tabella Profilo dal database Campagna, ad esempio Analytics per i [punti di interesse mobili](../../integrating/using/about-campaign-points-of-interest-data-integration.md). Il PII è definito dallo sviluppatore di app mobili, in genere con un esperto di marketing.
* **L'opzione Raccogli PII** è un'operazione HTTP-POST a un'API REST in Adobe Campaign Standard da un'app mobile.

L'obiettivo di questo caso d'uso è quello di creare o aggiornare un profilo Campaign Standard, se i dati PII restituiti da un'applicazione Mobile contengono dati relativi al profilo.

## Prerequisiti

Esistono vari passaggi di configurazione da seguire per abilitare le notifiche push in Campaign Standard, prima che i profili possano essere creati o aggiornati in base ai dati iscrizione app mobili:

1. [Creare un'applicazione mobile](../../administration/using/configuring-a-mobile-application.md)
1. [Integra l'SDK di Adobe Mobile con l'applicazione mobile](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html).
1. [Configura Adobe Campaign per l'invio di notifiche push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

## Passaggio 1 - Estensione della risorsa Profilo per notifiche push/iscrizioni

Per poter creare o aggiornare la risorsa Profilo con i dati PII, occorre prima estendere la risorsa Profilo con i campi desiderati. A tal fine:

* Identificare i campi PII che vengono inviati dall'applicazione Mobile.
* Identifica il campo da usare per la riconciliazione per associare i dati PII ai dati di profilo.

![](assets/update_profile1.png)

In questo esempio, la **[!UICONTROL Fields]** sezione riflette i dati PII inviati dall'applicazione Mobile. La **[!UICONTROL Link to profiles]** sezione indica il campo utilizzato per associare il PII con i dati di profilo, dove **cusemail** mappa su **@ email**.

La mappatura per i dati di profilo quando si estende **[!UICONTROL Subscriptions to an Application]** la risorsa è di SOLA LETTURA. Viene utilizzato per la riconciliazione. Il profilo deve essere inserito nel sistema con i dati necessari per riconciliare il profilo con i dati PII. Nel nostro caso, un indirizzo e-mail per il profilo deve corrispondere a un'e-mail dal Raccoglitore PII per consentire la riconciliazione:

* L'elemento PII viene ricevuto da un'app mobile per un utente dove il loro nome è "Jane, Cognome Name è" Doe "e l'indirizzo e-mail è janedoe@doe.com.
* Separatamente, i dati profilo devono esistere (ad esempio, i dati devono essere immessi manualmente o già derivati da altre risorse) in cui l'indirizzo e-mail del profilo è janedoe@doe.com.

**Argomenti correlati:**

* [Estensione delle iscrizioni a una risorsa dell'applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Creazione o estensione di una risorsa esistente](../../developing/using/key-steps-to-add-a-resource.md).

## Passaggio 2 - Create il flusso di lavoro

L'utilizzo di un flusso di lavoro in Campaign Standard consente a un amministratore di identificare e sincronizzare in modo univoco i dati tra i dati appiscrizione (utente iscritto) e Profilo o Destinatario. Mentre un aggiornamento basato su flusso di lavoro non sincronizza i dati di profilo in tempo reale, non deve causare blocchi o blocchi di database indebiti.

I passaggi principali per creare il flusso di lavoro sono:

1. Utilizzate un'attività **[!UICONTROL Query]** o **[!UICONTROL Incremental query]** un'attività per ottenere un elenco delle iscrizioni più recenti.
1. Utilizzate un **[!UICONTROL Reconciliation]** 'attività per mappare i dati PII con il profilo.
1. Aggiungete un processo di verifica.
1. Usate un elemento **[!UICONTROL Update data]** per aggiornare o creare il profilo con i dati PII.

I seguenti requisiti sono interpretati in questo flusso di lavoro:

* Tutti i campi/Tutti i campi che sono stati estesi devono essere disponibili per creare/aggiornare la tabella profilo.
* La tabella Profilo può essere estesa ai campi di supporto non supportati in modo nativo (ad esempio, Dimensioni T-shirt).
* Qualsiasi campo dalla tabella appiscrizione vuoto non deve essere aggiornato nella tabella profilo.
* Tutti i record aggiornati nella tabella appiscrizione devono essere inclusi nella successiva esecuzione del flusso di lavoro.

Per creare il flusso di lavoro, effettuate le operazioni seguenti:

1. Trascinate e rilasciate le seguenti attività nell'area di lavoro e collegatele:
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. Configurate l' **[!UICONTROL Scheduler]** attività. Nella **[!UICONTROL General]** scheda, impostate ( **[!UICONTROL Execution frequency]** ad esempio, "Daily"), the **[!UICONTROL Time]** (ad esempio, "1:00:00 AM") e the **[!UICONTROL Start]** (ad esempio, la data odierna).

   ![](assets/update_profile2.png)

1. Configurate l' **[!UICONTROL Incremental query]** attività.
   1. Nella **[!UICONTROL Properties]** scheda, fare clic sull **[!UICONTROL Select an element]** 'icona **[!UICONTROL Resource]** del campo, quindi selezionare l' **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elemento.

      ![](assets/update_profile3.png)

   1. Nella **[!UICONTROL Target]** scheda, trascina il **[!UICONTROL Mobile application]** filtro, quindi seleziona un nome applicazione Mobile.

      ![](assets/update_profile4.png)

   1. Nella **[!UICONTROL Processed data]** scheda, selezionare **[!UICONTROL Use a date field]**, quindi aggiungere il **[!UICONTROL Last modified (lastModified)]** campo come **[!UICONTROL Path to the date field]**.

      ![](assets/update_profile5.png)

1. Configurate l' **[!UICONTROL Update data]** attività.
   1. Nella **[!UICONTROL Identification]** scheda, accertatevi che la dimensione **[UICONTROL di aggiornamento]** sia impostata su "Profili (profilo)", quindi fate clic sul **[!UICONTROL Create element]** pulsante per aggiungere un campo come criterio di riconciliazione.

      ![](assets/update_profile_createelement.png)

   1. Nel **[!UICONTROL Source]** campo, selezionate un campo dalla tabella appsubscrsiptionrcp come campo di riconciliazione. Può essere l'e-mail del profilo, crmid, marketingcloudid ecc. In questo esempio, useremo il campo "Email (cusemail)".
   1. Nel **[!UICONTROL Destination]** campo, selezionate un campo dalla tabella del profilo per riconciliare i dati dalla tabella appsubscriptionrcp. Può essere l'e-mail del profilo o qualsiasi campo esteso come crmid, marketingcloudid ecc. In questo esempio, è necessario selezionare il campo "Email (email)" per mapparlo con il campo "Email (cusemail)" dalla tabella appsubscriptionrcp.

      ![](assets/update_profile7.png)

   1. Nella **[!UICONTROL Fields to update]** scheda, fai clic sul **[!UICONTROL Create element]** pulsante, quindi mappi i campi provenienti dalla tabella appsubscriptionrcp (**[!UICONTROL Source]** campo) con i campi che desideri aggiornare nella tabella Profilo (**[!UICONTROL Destination]** campo).
   1. Nel **[!UICONTROL Enabled if]** campo, aggiungere un'espressione per fare in modo che il campo corrispondente nella tabella Profilo venga aggiornato solo se il campo sorgente contiene un valore. A tal fine, seleziona il campo dall'elenco, quindi aggiungi il messaggio "!= "" (se il campo Sorgente è "[target/@ cusemail]" nell'Editor espressioni, assicuratevi di digitare[] "target/@ cusemsem!!"= "").

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >In questo caso, il flusso di lavoro esegue un UPSERT ma, poiché è basato su un dato di query incrementale, viene inserito solo. La modifica della query può influenzare i dati inseriti o aggiornati.
      >Inoltre, le impostazioni nella scheda Campi per l'aggiornamento determinano i campi inseriti o aggiornati in condizioni specifiche. Queste impostazioni possono essere univoche per ogni applicazione o cliente. Quando si configurano le impostazioni in base ai dati appsubscriptionrcp, prestare attenzione durante la configurazione di tali impostazioni in base ai dati appsubscriptionrcp può cambiare le informazioni personali degli utenti senza convalida.

   1. Quando sono stati aggiunti tutti i campi da inserire o aggiornare nel profilo, fare clic **[!UICONTROL Confirm]** su.

      ![](assets/update_profile9.png)

1. Salvate il flusso di lavoro, quindi fate clic su Avvia per avviare il processo di workflow.

   ![](assets/update_profile10.png)
