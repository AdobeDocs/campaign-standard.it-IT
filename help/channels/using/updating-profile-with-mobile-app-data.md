---
title: Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle applicazioni mobili
description: Scopri come creare e aggiornare le informazioni sul profilo in base ai dati delle applicazioni mobili.
page-status-flag: mai attivato
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: lemaite
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: notifiche push
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle applicazioni mobili

## Panoramica

Questa pagina descrive i passaggi per sviluppare un flusso di lavoro che crea/aggiorna i dati del profilo dopo che un'applicazione mobile invia Raccogli dati PII, su base programmata.

* **PII** sta per "Informazioni personali". Può trattarsi di qualsiasi dato, comprese le informazioni che non compaiono nella tabella Profilo del database Campaign, come, ad esempio, Analytics for Mobile [Points of Interest](../../integrating/using/about-campaign-points-of-interest-data-integration.md). Il PII è definito da Mobile App Developer, in genere con un esperto di marketing.
* **Collect PII** è un'operazione HTTP-POST su un'API Rest in Adobe Campaign Standard da un'app mobile.

L'obiettivo di questo caso d'uso è creare o aggiornare un profilo Campaign Standard, se i dati PII restituiti da un'applicazione mobile contengono dati relativi al profilo.

## Prerequisiti

Prima di creare o aggiornare i profili in base ai dati dell'iscrizione all'app mobile, è necessario seguire diversi passaggi di configurazione per abilitare le notifiche push in Campaign Standard:

1. [Creare un'applicazione mobile](../../administration/using/configuring-a-mobile-application.md)
1. [Integra l’SDK di Adobe Mobile con la tua applicazione](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)mobile.
1. [Configura Adobe Campaign per inviare le notifiche](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)push.

## Passaggio 1 - Estendi la risorsa Profilo per le notifiche push/iscrizioni

Per poter creare o aggiornare la risorsa Profilo con i dati PII, devi prima estendere la risorsa Profilo con i campi desiderati. Per eseguire questa operazione:

* Identificare i campi PII inviati dall'applicazione mobile.
* Identificare il campo da utilizzare per la riconciliazione per associare i dati PII ai dati del profilo.

![](assets/update_profile1.png)

In questo esempio, la **[!UICONTROL Fields]** sezione riflette i dati PII inviati dall'applicazione mobile. La **[!UICONTROL Link to profiles]** sezione indica il campo utilizzato per associare il PII ai dati del profilo, dove **cusEmail** viene mappato su **@email**.

La mappatura dei dati del profilo durante l’estensione della **[!UICONTROL Subscriptions to an Application]** risorsa è SOLA LETTURA. Viene utilizzato per la riconciliazione. Il profilo deve essere inserito nel sistema con i dati necessari per riconciliare il profilo con i dati PII. Nel nostro caso, un indirizzo e-mail per il profilo deve corrispondere a un'e-mail inviata da Collect PII per consentire la riconciliazione:

* Raccogli PII viene ricevuto da un'app mobile per un utente il cui nome è "Jane, cognome è "Doe" e l'indirizzo e-mail è janedoe@doe.com.
* Separatamente, i dati del profilo devono esistere (ad esempio, i dati devono essere inseriti manualmente o provenire già da altre risorse), dove l'indirizzo e-mail del profilo è janedoe@doe.com.

**Argomenti correlati:**

* [Estensione delle sottoscrizioni a una risorsa dell’applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Creazione o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)esistente.

## Passaggio 2 - Creare il flusso di lavoro

L'utilizzo di un flusso di lavoro in Campaign Standard consente all'amministratore di identificare e sincronizzare in modo univoco i dati dell'AppSubscription (utente iscritto) con i dati del profilo o del destinatario. Un aggiornamento basato su flusso di lavoro non sincronizza i dati del profilo in tempo reale, ma non deve causare inutili blocchi del database o sovraccarichi.

I passaggi principali per creare il flusso di lavoro sono:

1. Utilizzate un'attività **[!UICONTROL Query]** **[!UICONTROL Incremental query]** o per ottenere un elenco delle sottoscrizioni più recenti.
1. Utilizzate un' **[!UICONTROL Reconciliation]** attività per mappare i dati PII con il profilo.
1. Aggiungere un processo di verifica.
1. Utilizzare un **[!UICONTROL Update data]** per aggiornare o creare il profilo con i dati PII.

In questo flusso di lavoro vengono considerati i seguenti requisiti:

* Tutti i campi che sono stati estesi devono essere disponibili per creare/aggiornare la tabella dei profili.
* La tabella Profilo può essere estesa per supportare i campi che non sono supportati in modo nativo (ad esempio, Dimensioni T-shirt).
* I campi della tabella AppSubscription vuoti non devono essere aggiornati nella tabella Profilo.
* Qualsiasi record aggiornato nella tabella AppSubscription deve essere incluso nell'esecuzione successiva del Workflow.

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

1. Trascinate e rilasciate le seguenti attività nell’area di lavoro e collegatele:
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. Configurare l' **[!UICONTROL Scheduler]** attività. Nella **[!UICONTROL General]** scheda, impostare **[!UICONTROL Execution frequency]** (ad esempio, "Daily"), **[!UICONTROL Time]** (ad esempio, "1:00:00 AM") e **[!UICONTROL Start]** (ad esempio, Data odierna).

   ![](assets/update_profile2.png)

1. Configurare l' **[!UICONTROL Incremental query]** attività.
   1. Nella **[!UICONTROL Properties]** scheda fare clic sull' **[!UICONTROL Select an element]** icona del **[!UICONTROL Resource]** campo, quindi selezionare l' **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elemento.

      ![](assets/update_profile3.png)

   1. Nella **[!UICONTROL Target]** scheda, trascina il **[!UICONTROL Mobile application]** filtro, quindi seleziona il nome di un'applicazione Mobile.

      ![](assets/update_profile4.png)

   1. Nella **[!UICONTROL Processed data]** scheda, selezionare **[!UICONTROL Use a date field]**, quindi aggiungere il **[!UICONTROL Last modified (lastModified)]** campo come **[!UICONTROL Path to the date field]**.

      ![](assets/update_profile5.png)

1. Configurare l' **[!UICONTROL Update data]** attività.
   1. Nella **[!UICONTROL Identification]** scheda, assicurarsi che il **[!UICONTROL Dimension to update]** campo sia impostato su "Profili (profilo)", quindi fare clic sul **[!UICONTROL Create element]** pulsante per aggiungere un campo come criterio di riconciliazione.

      ![](assets/update_profile_createelement.png)

   1. Nel **[!UICONTROL Source]** campo, seleziona un campo dalla tabella appSubscriptionRcp come campo di riconciliazione. Può trattarsi dell'e-mail del profilo, crmId, marketingCloudId, ecc. In questo esempio, utilizzeremo il campo "Email (cusEmail)".
   1. Nel **[!UICONTROL Destination]** campo, seleziona un campo dalla tabella del profilo per riconciliare i dati dalla tabella appSubscriptionRcp. Può essere l'e-mail del profilo o qualsiasi campo esteso come crmId, marketingCloudId, ecc. In questo esempio, è necessario selezionare il campo "Email (email)" per mapparlo con il campo "Email (cusEmail)" dalla tabella appSubscriptionRcp.

      ![](assets/update_profile7.png)

   1. Nella **[!UICONTROL Fields to update]** scheda, fai clic sul **[!UICONTROL Create element]** pulsante, quindi mappatura i campi provenienti dalla tabella appSubscriptionRcp (**[!UICONTROL Source]** campo) con i campi che vuoi aggiornare nella tabella Profilo (**[!UICONTROL Destination]** campo).
   1. Nel **[!UICONTROL Enabled if]** campo, aggiungere un'espressione per assicurare che il campo corrispondente nella tabella Profilo sia aggiornato solo se il campo di origine contiene un valore. A questo scopo, selezionare il campo dall'elenco, quindi aggiungere il simbolo "!espressione =''" (se il campo Sorgente è `[target/@cusEmail]` nell'editor Espressione, assicurarsi di digitare `[target/@cusEmail] != ''"`).

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >In questo caso, il Flusso di lavoro esegue un UPSERT, ma poiché si basa su dati di Query incrementale viene inserito solo. La modifica della query può influenzare i dati inseriti o aggiornati.
      >Inoltre, le impostazioni specificate nella scheda Campi da aggiornare determinano quali campi vengono inseriti o aggiornati in condizioni specifiche. Queste impostazioni possono essere univoche per ogni applicazione o cliente. Presta attenzione quando configuri queste impostazioni, in quanto potrebbero verificarsi conseguenze non desiderate, in quanto l'aggiornamento dei record nel Profilo basato sui dati appSubscriptionRcp può modificare le informazioni personali degli utenti senza convalida.

   1. Quando tutti i campi da inserire/aggiornare nel profilo sono stati aggiunti, fai clic su **[!UICONTROL Confirm]**.

      ![](assets/update_profile9.png)

1. Salva il flusso di lavoro, quindi fai clic su Avvia per avviare il processo Workflow.

   ![](assets/update_profile10.png)
