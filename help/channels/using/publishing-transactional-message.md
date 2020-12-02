---
solution: Campaign Standard
product: campaign
title: Messaggi sulle transazioni degli eventi
description: Scopri come creare e pubblicare un messaggio sulle transazioni degli eventi.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 4e157a582de836fa325d95593491c756209b205e
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 77%

---


# Ciclo di vita dei messaggi transazionali {#publishing-transactional-message}

Quando il [messaggio transazionale](../../channels/using/editing-transactional-message.md) è pronto per essere inviato, può essere pubblicato.

I passaggi per testare, pubblicare, mettere in pausa, annullare la pubblicazione ed eliminare un evento sono descritti di seguito. Questa sezione descrive anche il processo dei tentativi di messaggistica transazionali.

## Processo di pubblicazione della messaggistica transazionale {#transactional-messaging-pub-process}

Il grafico seguente illustra il processo complessivo di pubblicazione dei messaggi transazionali.

![](assets/message-center_pub-process.png)

Per ulteriori informazioni sulla pubblicazione di un messaggio transazionale, vedere [questa sezione](#publishing-a-transactional-message).
Per ulteriori informazioni sull&#39;interruzione di un messaggio transazionale, vedere [questa sezione](#suspending-a-transactional-message-publication).
Per ulteriori informazioni sull&#39;annullamento della pubblicazione di un messaggio transazionale, vedere [questa sezione](#unpublishing-a-transactional-message).

Per ulteriori informazioni sulla pubblicazione e l&#39;annullamento della pubblicazione di un evento, vedere [questa sezione](../../channels/using/publishing-transactional-event.md).

## Verifica di un messaggio sulle transazioni {#testing-a-transactional-message}

È innanzitutto necessario creare un profilo di test specifico che consenta di controllare correttamente il messaggio transazionale.

### Definizione di un profilo di test specifico {#defining-specific-test-profile}

Definite un profilo di test che sarà collegato all&#39;evento, per consentirvi di visualizzare l&#39;anteprima del messaggio e inviare una prova pertinente.

1. Dal dashboard dei messaggi transazionali, fate clic sul pulsante **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Specifica le informazioni da inviare in formato JSON nella sezione **[!UICONTROL Event data used for personalization]**. Tale contenuto verrà utilizzato al momento della visualizzazione dell’anteprima del messaggio e quando il profilo di test riceve la bozza.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Puoi inoltre inserire le informazioni relative alla tabella del profilo. Vedere [Arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)<!--and [Personalizing a transactional message](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)-->.

1. Una volta creato, il profilo di test verrà prespecificato nel messaggio di transazione. Per controllare la destinazione della bozza, fai clic sul blocco **[!UICONTROL Test profiles]** del messaggio.

   ![](assets/message-center_5.png)

Puoi anche creare un nuovo profilo di test o usarne uno già esistente nel menu **[!UICONTROL Test profiles]**. Per eseguire questa operazione:

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Nella sezione **[!UICONTROL Event]**, selezionate l&#39;evento appena creato. In questo esempio, seleziona &quot;Abbandono carrello (EVTcartAbandonment)&quot;.
1. Nella casella di testo **[!UICONTROL Event data]**, specifica le informazioni da inviare in formato JSON.

   ![](assets/message-center_3.png)

1. Salva le modifiche.
1. Accedete al messaggio creato e selezionate il profilo di test aggiornato.

**Argomenti correlati:**

* [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)
* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)

### Invio della prova {#sending-proof}

Dopo aver creato uno o più profili di test specifici e aver salvato il messaggio transazionale, potete inviare una prova per verificarlo.

![](assets/message-center_10.png)

I passaggi per l&#39;invio di una prova sono descritti nella sezione [Invio di prove di validità](../../sending/using/sending-proofs.md).

## Pubblicazione di un messaggio sulle transazioni {#publishing-a-transactional-message}

Dopo aver controllato il messaggio sulle transazioni, puoi eseguirne la pubblicazione.

![](assets/message-center_12.png)

Ora, non appena si attiva l’evento &quot;Abbandono carrello&quot;, viene visualizzato automaticamente un messaggio contenente il titolo e il cognome del destinatario, l’URL del carrello, l’ultimo prodotto visionato o un elenco di prodotti, se definito, e l’importo totale del carrello da inviare.

Per accedere ai rapporti relativi al messaggio sulle transazioni, usa il pulsante **[!UICONTROL Reports]**. Vedere [Report dinamici](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

### Sospensione di una pubblicazione di un messaggio sulle transazioni {#suspending-a-transactional-message-publication}

Puoi sospendere la pubblicazione del messaggio sulle transazioni utilizzando, ad esempio, il pulsante **[!UICONTROL Pause]** per la modifica dei dati contenuti nel messaggio. Pertanto, gli eventi non vengono più elaborati, ma rimangono in coda nel database di Adobe Campaign.

Gli eventi in coda vengono conservati durante un periodo di tempo definito nell&#39;API REST (consultare la [documentazione REST API](../../api/using/managing-transactional-messages.md) o nell&#39;evento di attivazione se si utilizza il servizio di base Triggers (vedere [Informazioni su Adobe Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Durante la selezione di **[!UICONTROL Resume]**, vengono elaborati tutti gli eventi in coda, purché non siano scaduti. Adesso tali eventi contengono tutte le modifiche apportate durante la sospensione della pubblicazione del modello.

### Annullamento della pubblicazione di un messaggio sulle transazioni {#unpublishing-a-transactional-message}

Facendo clic su **[!UICONTROL Unpublish]** puoi annullare la pubblicazione dei messaggi sulle transazioni, ma anche la pubblicazione dell’evento corrispondente, che elimina dall’API REST la risorsa corrispondente all’evento creato in precedenza.

![](assets/message-center_unpublish-template.png)

Adesso, anche se l’evento viene attivato nel sito web, i messaggi corrispondenti non saranno più inviati e pertanto non verranno memorizzati nel database.

>[!NOTE]
>
>Per pubblicare di nuovo il messaggio, è necessario tornare alla configurazione dell&#39;evento corrispondente, [pubblicare l&#39;evento](../../channels/using/publishing-transactional-event.md), quindi [pubblicare il messaggio](#publishing-a-transactional-message).

Se annulli la pubblicazione di un messaggio sulle transazioni in sospensione, potresti dover attendere fino a 24 ore prima di poterlo pubblicare nuovamente. In questo modo, il flusso di lavoro **[!UICONTROL Database cleanup]** eliminerà tutti gli eventi inviati alla coda.

La procedura per la sospensione di un messaggio è spiegata nei dettagli nella sezione [Sospensione della pubblicazione di un messaggio sulle transazioni](#suspending-a-transactional-message-publication).

Il flusso di lavoro **[!UICONTROL Database cleanup]**, che viene eseguito ogni giorno alle 4.00, è accessibile tramite **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

### Eliminazione di un messaggio sulle transazioni {#deleting-a-transactional-message}

Dopo aver annullato la pubblicazione di un messaggio sulle transazioni o se tale messaggio non è ancora stato pubblicato, puoi eseguirne l’eliminazione dall’elenco dei messaggi sulle transazioni. Per eseguire questa operazione:

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Passa il mouse sopra il messaggio desiderato.
1. Fai clic sul pulsante **[!UICONTROL Delete element]**.

![](assets/message-center_delete-template.png)

Tuttavia, l’eliminazione di un messaggio sulle transazioni può essere eseguita solo in presenza di determinate condizioni:

* Assicurati che il messaggio sulle transazioni presenti lo stato **[!UICONTROL Draft]**, altrimenti non potrai eliminarlo. Lo stato **[!UICONTROL Draft]** si applica a un messaggio che non è ancora stato pubblicato o che è stato [annullato](#unpublishing-a-transactional-message) (e non è stato [sospeso](#suspending-a-transactional-message-publication)).

* **Messaggi sulle transazioni**: a meno che un altro messaggio sulle transazioni non sia collegato all’evento corrispondente, se il messaggio sulle transazioni non viene pubblicato, anche la configurazione dell’evento deve essere annullata onde consentire una corretta eliminazione del messaggio sulle transazioni. Per ulteriori informazioni, consulta [Annullamento della pubblicazione di un evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).

   >[!IMPORTANT]
   >
   >Se elimini un messaggio sulle transazioni che ha già inviato delle notifiche, verranno cancellati anche i registri di invio e di tracciamento.

* **Messaggi sulle transazioni da un modello di evento predefinito (messaggi sulle transazioni interni)**: se un messaggio sulle transazioni interno è l’unico associato all’evento corrispondente, non è possibile eseguirne l’eliminazione. Devi innanzitutto creare un altro messaggio sulle transazioni effettuandone la duplicazione o utilizzando il menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]** .

## Procedura per l’esecuzione di un nuovo tentativo di messaggio sulle transazioni {#transactional-message-retry-process}

Un messaggio sulle transazioni temporaneamente non consegnato è soggetto all’esecuzione di tentativi automatici fino alla scadenza della consegna. Per ulteriori informazioni sulla durata della consegna, consulta [Parametri del periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando un messaggio sulle transazioni non viene inviato, vi sono due sistemi di esecuzione di un nuovo tentativo:

* A livello di messaggistica sulle transazioni, un messaggio di questo tipo può avere esito negativo prima che l’evento venga assegnato a una consegna di esecuzione, che si trova tra la ricezione dell’evento e la preparazione della consegna. Consulta [Procedura per l’esecuzione di un nuovo tentativo di elaborazione degli eventi](#event-processing-retry-process).
* A livello del processo di invio, una volta che l’evento è stato assegnato a una consegna di esecuzione, il messaggio sulle transazioni potrebbe avere esito negativo a causa di un errore temporaneo. Consulta [Procedura per l’esecuzione di un nuovo tentativo invio del messaggio](#message-sending-retry-process).

### Procedura per l’esecuzione di un nuovo tentativo di elaborazione degli eventi {#event-processing-retry-process}

Se l’evento non può essere assegnato a una consegna di esecuzione, l’elaborazione dell’evento viene posticipata. I tentativi vengono quindi eseguiti fino a quando l’evento non viene assegnato a una nuova consegna di esecuzione.

>[!NOTE]
>
>Un evento posticipato non viene visualizzato nei registi di invio del messaggio sulle transazioni, poiché non è ancora stato assegnato a una consegna di esecuzione.

Ad esempio, non è stato possibile assegnare l’evento a una consegna di esecuzione perché il relativo contenuto non era corretto, si è verificato un problema con i diritti di accesso o con il marchio, è stato rilevato un errore durante l’applicazione delle regole di tipologia e così via. In questo caso, puoi sospendere il messaggio, modificarlo per risolvere il problema e infine pubblicarlo nuovamente. Il sistema di esecuzione di un nuovo tentativo lo assegnerà a una nuova consegna di esecuzione.

### Procedura per l’esecuzione di un nuovo tentativo di invio del messaggio {#message-sending-retry-process}

Una volta che l’evento è stato assegnato a una consegna di esecuzione, il messaggio sulle transazioni può non riuscire a causa di un errore temporaneo, ad esempio se la cassetta postale del destinatario è piena. Per ulteriori informazioni, consulta [Tentativi dopo un errore temporaneo di consegna](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando un evento viene assegnato a un’esecuzione di consegna, viene visualizzato nei registri di invio dell’esecuzione di consegna e solo in questa fase. Le consegne non riuscite vengono visualizzate nella scheda **[!UICONTROL Execution list]** dei registri di invio dei messaggi transazionali.

### Limitazioni del processo di ripetizione {#limitations}

**Invio dell’aggiornamento dei registri**

Nel processo di esecuzione dei nuovi tentativi, i registri di invio della nuova consegna esecuzione non vengono aggiornati immediatamente, poiché tale procedura avviene tramite un flusso di lavoro pianificato. Ciò significa che il messaggio potrebbe trovarsi nello stato **[!UICONTROL Pending]** anche se l’evento sulle transazioni è stato elaborato dalla nuova consegna di esecuzione.

**Consegna di esecuzione non riuscita**

Non è possibile interrompere la consegna dell’esecuzione. Tuttavia, se la consegna dell’esecuzione corrente ha esito negativo, ne viene creata una nuova non appena viene ricevuto un nuovo evento, e tutti i nuovi eventi vengono elaborati dalla nuova consegna dell’esecuzione. Nessun nuovo evento viene elaborato dalla consegna dell’esecuzione non riuscita.

Se alcuni eventi già assegnati a una consegna dell’esecuzione sono stati posticipati e se tale consegna ha esito negativo, il sistema dei tentativi non assegna gli eventi posticipati alla nuova consegna dell’esecuzione, il che significa che tali eventi andranno perduti.
