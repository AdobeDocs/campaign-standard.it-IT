---
title: Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle applicazioni mobili
description: Scopri come creare e aggiornare le informazioni sul profilo in base ai dati delle applicazioni mobili.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Creazione e aggiornamento delle informazioni sul profilo in base ai dati delle applicazioni mobili

## Panoramica

Questa pagina descrive i passaggi per sviluppare un flusso di lavoro che crea/aggiorna i dati del profilo dopo che un’applicazione mobile invia i dati Raccogli PII, su base pianificata.

* **PII** sta per &quot;Informazioni personali&quot;. Può trattarsi di qualsiasi dato, comprese le informazioni che non compaiono nella tabella Profilo dal database di Campaign, come ad esempio Analytics for Mobile [Punti di interesse](../../integrating/using/about-campaign-points-of-interest-data-integration.md). I dati PII sono definiti dallo sviluppatore di app mobili, solitamente con un addetto al marketing.
* **Raccogli PII** è un’operazione HTTP-POST per un’API di ripristino in Adobe Campaign Standard da un’app mobile.

L&#39;obiettivo di questo caso d&#39;uso è quello di creare o aggiornare un profilo Campaign Standard, se i dati PII restituiti da un&#39;applicazione mobile contengono dati relativi al profilo.

## Prerequisiti

Esistono diversi passaggi di configurazione da seguire per abilitare le notifiche push in Campaign Standard, prima che i profili possano essere creati o aggiornati in base ai dati di abbonamento alle app mobili:

1. [Creare un’applicazione mobile](../../administration/using/configuring-a-mobile-application.md)
1. [Integrare l’SDK di Adobe Mobile con la tua app mobile](../../administration/using/supported-mobile-use-cases.md).
1. [Configurare Adobe Campaign per l’invio di notifiche push](../../administration/using/configuring-a-mobile-application.md).

## Passaggio 1: estendere la risorsa Profilo per le notifiche push/sottoscrizioni

Per poter creare o aggiornare la risorsa Profilo con i dati PII, devi prima estendere la risorsa Profilo con i campi desiderati. Per eseguire questa operazione:

* Identifica i campi PII inviati dall’applicazione mobile.
* Identifica il campo da utilizzare per la riconciliazione per associare i dati PII ai dati del profilo.

![](assets/update_profile1.png)

In questo esempio, la **[!UICONTROL Fields]** riflette i dati PII inviati dall’applicazione mobile. La **[!UICONTROL Link to profiles]** indica il campo utilizzato per associare i dati PII ai dati del profilo, dove **cusEmail** mappa su **@email**.

La mappatura dei dati del profilo durante l’estensione del **[!UICONTROL Subscriptions to an Application]** la risorsa è di SOLA LETTURA. Viene utilizzato per la riconciliazione. Il profilo deve essere inserito nel sistema con i dati necessari per riconciliare il profilo con i dati PII. Nel nostro caso, un indirizzo e-mail per il profilo deve corrispondere a un’e-mail inviata dal servizio Raccogli PII per consentire la riconciliazione:

* Raccogli PII viene ricevuto da un’app mobile per un utente il cui nome è &quot;Jane&quot;, il cui cognome è &quot;Doe&quot; e l’indirizzo e-mail è janedoe@doe.com.
* Separatamente, i dati del profilo devono esistere (ad esempio, i dati devono essere immessi manualmente o provengono già da un’altra risorsa) dove l’indirizzo E-mail del profilo è janedoe@doe.com.

**Argomenti correlati:**

* [Estensione degli abbonamenti a una risorsa dell’applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Creazione o estensione di una risorsa esistente](../../developing/using/key-steps-to-add-a-resource.md).

## Passaggio 2: creare il flusso di lavoro

L’utilizzo di un flusso di lavoro in Campaign Standard consente a un amministratore di identificare e sincronizzare in modo univoco i dati tra i dati AppSubscription (Sottoscrittore) e i dati Profile o Recipient. Anche se un aggiornamento basato su un flusso di lavoro non sincronizza i dati del profilo in tempo reale, non dovrebbe causare blocchi di database o sovraccarichi indebiti.

I passaggi principali per creare il flusso di lavoro sono i seguenti:

1. Utilizza un **[!UICONTROL Query]** o **[!UICONTROL Incremental query]** per ottenere un elenco degli abbonamenti più recenti.
1. Utilizza un **[!UICONTROL Reconciliation]** attività per mappare i dati PII con il profilo .
1. Aggiungi un processo di verifica.
1. Utilizza un **[!UICONTROL Update data]** per aggiornare o creare il profilo con i dati PII.

In questo flusso di lavoro si assumono i seguenti requisiti:

* Tutti i campi che sono stati estesi devono essere disponibili per creare/aggiornare la tabella del profilo.
* La tabella Profilo può essere estesa per supportare campi non supportati in modo nativo (ad esempio, Dimensioni T-shirt).
* Qualsiasi campo della tabella AppSubscription vuoto non deve essere aggiornato nella tabella Profilo.
* Qualsiasi record aggiornato nella tabella AppSubscription deve essere incluso nella prossima esecuzione del flusso di lavoro.

Per creare il flusso di lavoro, trascina e rilascia le seguenti attività nell’area di lavoro e collegale: **[!UICONTROL Start]**, **[!UICONTROL Scheduler]**, **[!UICONTROL Incremental query]**, **[!UICONTROL Update data]**.

![](assets/update_profile0.png)

Quindi segui i passaggi seguenti per configurare ogni attività.

### Configura le **[!UICONTROL Scheduler]** attività

In **[!UICONTROL General]** imposta la **[!UICONTROL Execution frequency]** (ad esempio, &quot;Giornaliero&quot;), il **[!UICONTROL Time]** (ad esempio, &quot;1:00:00 AM&quot;), e **[!UICONTROL Start]** (ad esempio, Data odierna).

![](assets/update_profile2.png)

### Configura le **[!UICONTROL Incremental query]** attività.

1. In **[!UICONTROL Properties]** fai clic sulla scheda **[!UICONTROL Select an element]** dell&#39;icona **[!UICONTROL Resource]** , quindi seleziona il **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elemento.

   ![](assets/update_profile3.png)

1. In **[!UICONTROL Target]** trascina **[!UICONTROL Mobile application]** , quindi seleziona un nome di applicazione mobile.

   ![](assets/update_profile4.png)

1. In **[!UICONTROL Processed data]** scheda , seleziona **[!UICONTROL Use a date field]**, quindi aggiungi la **[!UICONTROL Last modified (lastModified)]**  campo come **[!UICONTROL Path to the date field]**.

   ![](assets/update_profile5.png)

### Configura le **[!UICONTROL Update data]** attività.

1. In **[!UICONTROL Identification]** assicurati che la **[!UICONTROL Dimension to update]** è impostato su &quot;Profiles (profile)&quot;, quindi fai clic sul **[!UICONTROL Create element]** per aggiungere un campo come criterio di riconciliazione.

   ![](assets/update_profile_createelement.png)

1. In **[!UICONTROL Source]** seleziona un campo dalla tabella appSubscriptionRcp come campo di riconciliazione. Può essere l’e-mail, il crmId, il marketingCloudId, ecc. del profilo. In questo esempio, utilizza il campo &quot;Email (cusEmail)&quot;.

1. In **[!UICONTROL Destination]** seleziona un campo dalla tabella del profilo per riconciliare i dati dalla tabella appSubscriptionRcp. Può essere l’e-mail del profilo o qualsiasi campo esteso come crmId, marketingCloudId, ecc. In questo esempio, è necessario selezionare il campo &quot;Email (email)&quot; per mapparlo con il campo &quot;Email (cusEmail)&quot; dalla tabella appSubscriptionRcp.

   ![](assets/update_profile7.png)

1. In **[!UICONTROL Fields to update]** fai clic sulla scheda **[!UICONTROL Create element]** , quindi mappa i campi provenienti dalla tabella appSubscriptionRcp (**[!UICONTROL Source]** con i campi che desideri aggiornare nella tabella Profilo (**[!UICONTROL Destination]** (campo).

1. In **[!UICONTROL Enabled if]** aggiungi un’espressione per garantire che il campo corrispondente nella tabella Profilo sia aggiornato solo se il campo di origine contiene un valore. A questo scopo, seleziona il campo dall’elenco, quindi aggiungi il &quot;!espressione =&#39;&quot; (se il campo Origine è `[target/@cusEmail]` nell’editor espressioni assicurati di digitare `[target/@cusEmail] != ''"`).

   ![](assets/update_profile8.png)

>[!NOTE]
>
>In questo caso, il flusso di lavoro esegue un UPSERT ma si basa su un **[!UICONTROL Incremental query]** i dati vengono inseriti solo. La modifica della query può influire sui dati inseriti o aggiornati.
>Inoltre, le impostazioni nella scheda Campi da aggiornare determinano quali campi vengono inseriti o aggiornati in condizioni specifiche. Queste impostazioni possono essere univoche per ogni applicazione o cliente.
>Presta attenzione durante la configurazione di queste impostazioni in quanto possono esservi conseguenze indesiderate, in quanto l’aggiornamento dei record nel Profilo in base ai dati appSubscriptionRcp può modificare le informazioni personali degli utenti senza convalida.

Quando tutti i campi da inserire/aggiornare nel profilo sono stati aggiunti, fai clic su **[!UICONTROL Confirm]**.

![](assets/update_profile9.png)

Salva il flusso di lavoro, quindi fai clic su **[!UICONTROL Start]** per eseguire il flusso di lavoro.

![](assets/update_profile10.png)
