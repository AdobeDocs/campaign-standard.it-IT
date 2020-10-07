---
title: Messaggi sulle transazioni degli eventi
description: Scopri come creare e pubblicare un messaggio sulle transazioni degli eventi.
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '2480'
ht-degree: 89%

---


# Messaggi sulle transazioni degli eventi{#event-transactional-messages}

Puoi inviare messaggi sulle transazioni destinati a un evento. Questo tipo di messaggi sulle transazioni non contiene informazioni del profilo: il target di consegna è definito dai dati contenuti nell’evento stesso.

Dopo aver creato e pubblicato un evento come l’abbandono del carrello, illustrato all’interno della [presente sezione](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle), il relativo messaggio sulle transazioni viene creato in automatico.

I passaggi di configurazione sono descritti nella sezione [Configurazione di un evento per l’invio di un messaggio sulle transazioni](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

>[!NOTE]
>
>I messaggi transazionali relativi agli eventi non contengono informazioni sui profili, pertanto non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con profili). Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md#choosing-the-channel).

Per fare in modo che l’evento attivi l’invio di un messaggio transazionale, devi personalizzare il messaggio, verificarlo e pubblicarlo.

## Accesso ai messaggi transazionali {#accessing-transactional-messages}

Per accedere al messaggio transazionale creato:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Fai clic sul messaggio desiderato per modificarlo.

>[!IMPORTANT]
>
>Per accedere ai messaggi transazionali, devi far parte del gruppo di sicurezza **[!UICONTROL Administrators (all units)]**.

## Personalizzazione di un messaggio sulle transazioni {#personalizing-a-transactional-message}

Questo esempio illustra come personalizzare un messaggio di transazione aggiungendo tre campi definiti al momento della [creazione dell’evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message): nome, ultimo prodotto consultato, importo totale del carrello.

To do this, you will [insert a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field) in the message content.

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare l’oggetto e il contenuto del messaggio. Ai fini del presente esempio, seleziona un modello contenente immagini e testo. Per ulteriori informazioni sui modelli di contenuto dell’e-mail, consulta [Progettazione mediante modelli](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Aggiungi un oggetto e modifica il contenuto del messaggio in base alle tue esigenze.

   >[!NOTE]
   >
   >Il collegamento al carrello abbandonato porta a un URL esterno che reindirizzerà il consumatore al proprio carrello. Tale parametro non è gestito all’interno di Adobe Campaign.

1. Sfoglia **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** per ottenere i campi di personalizzazione: nome, ultimo prodotto consultato, importo totale del carrello.

   ![](assets/message-center_7.png)

1. Per arricchire il contenuto del messaggio, aggiungi i campi selezionandoli dalla tabella a cui hai collegato l’evento. Nel nostro esempio, seleziona il campo **[!UICONTROL Title (salutation)]** nella tabella **[!UICONTROL Profile]** tramite **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Inserisci tutti i campi richiesti.

   ![](assets/message-center_8.png)

1. Per visualizzare l’anteprima del messaggio, seleziona il profilo definito per l’evento.

   La procedura per la visualizzazione dell’anteprima di un messaggio è spiegata nei dettagli nella sezione [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Puoi verificare che i campi di personalizzazione corrispondano alle informazioni inserite nel profilo di test. Per ulteriori informazioni al riguardo, consulta [Definizione di un profilo di test in un messaggio transazionale](../../channels/using/event-transactional-messages.md#defining-specific-test-profile).

## Utilizzo degli elenchi di prodotti in un messaggio sulle transazioni {#using-product-listings-in-a-transactional-message}

Puoi creare elenchi di prodotti che fanno riferimento a una o più raccolte di dati presenti nel contenuto di un’e-mail sulle transazioni. Ad esempio, in un messaggio e-mail di abbandono del carrello puoi includere un elenco di tutti i prodotti presenti nei carrelli degli utenti al momento dell’uscita dal sito web, aggiungendo un’immagine, il prezzo e il collegamento a ciascun prodotto.

Ulteriori informazioni in [questo video](https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html).

>[!IMPORTANT]
>
>Gli elenchi dei prodotti sono disponibili solo durante la modifica dei messaggi e-mail sulle transazioni tramite l’interfaccia di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).
>
>Adobe Campaign non supporta elenchi di prodotti nidificati, il che significa che non puoi includere un elenco di prodotti all’interno di un altro.

Nell&#39;esempio seguente, verranno illustrati i passaggi per aggiungere un elenco di prodotti abbandonati in un messaggio transazionale.

### Passaggio 1: Definire un elenco di prodotti {#defining-a-product-listing}

Prima di poter utilizzare un elenco di prodotti in un messaggio sulle transazioni, è necessario definire a livello di evento l’elenco dei prodotti e i campi per ciascun prodotto da visualizzare. Per ulteriori informazioni, consulta [Definizione delle raccolte di dati](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Nel messaggio sulle transazioni, fai clic sul blocco **[!UICONTROL Content]** per modificare il contenuto dell’e-mail.
1. Trascina e rilascia un componente struttura all’interno dell’area di lavoro. Per ulteriori informazioni, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Ad esempio, seleziona un componente struttura a una colonna e aggiungi un componente testo, un componente immagine e un componente pulsante. Per ulteriori informazioni, consulta [Aggiunta di frammenti e componenti](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleziona il componente struttura appena creato, quindi fai clic sull’icona **[!UICONTROL Enable product listing]** nella barra degli strumenti contestuale.

   ![](assets/message-center_loop_create.png)

   Il componente struttura viene evidenziato con una cornice arancione e le impostazioni **[!UICONTROL Product listing]** sono visualizzate nella palette a sinistra.

   ![](assets/message-center_loop_palette.png)

1. Seleziona la modalità di visualizzazione degli elementi della raccolta:

   * **[!UICONTROL Row]**: orizzontale, ovvero ogni elemento posto sulla riga inferiore al precedente.
   * **[!UICONTROL Column]**: verticale, ovvero ciascun elemento posto accanto all’altro sulla medesima riga.

   >[!NOTE]
   >
   >L’opzione **[!UICONTROL Column]** è disponibile solo quando è in uso un componente struttura a più colonne ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** e **[!UICONTROL 4:4 column]** ). Quando modifichi l’elenco dei prodotti, compila solo la prima colonna: le altre non saranno prese in considerazione. Per ulteriori informazioni sulla selezione dei componenti struttura, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleziona la raccolta dati creata durante la configurazione dell’evento correlato al messaggio sulle transazioni, disponibile nel nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Per ulteriori informazioni sulla configurazione dell’evento, consulta [Definizione delle raccolte di dati](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Utilizza l’elenco a discesa **[!UICONTROL First item]** per selezionare l’elemento che avvierà l’elenco visualizzato nel messaggio e-mail.

   Ad esempio, se scegli 2, il primo elemento della raccolta non verrà visualizzato nell’e-mail. L’elenco dei prodotti partirà dal secondo elemento.

1. Seleziona il numero massimo di elementi da visualizzare nell’elenco.

   >[!NOTE]
   >
   >Se desideri che gli elementi dell’elenco siano visualizzati in verticale ( **[!UICONTROL Column]** ), il numero massimo è limitato in base al componente struttura selezionato (2, 3 o 4 colonne). Per ulteriori informazioni sulla selezione dei componenti struttura, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Passaggio 2: Compilare l&#39;elenco dei prodotti {#populating-the-product-listing}

Per visualizzare un elenco dei prodotti provenienti dall’evento collegato al messaggio e-mail sulle transazioni, attieniti alla procedura seguente.

Per ulteriori informazioni sulla creazione di una raccolta e dei campi correlati durante la configurazione dell’evento, consulta [Definizione delle raccolte di dati](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Seleziona il componente immagine inserito, fai clic su **[!UICONTROL Enable personalization]** e sulla matita nel riquadro Impostazioni.

   ![](assets/message-center_loop_image.png)

1. Seleziona **[!UICONTROL Add personalization field]** nella finestra **[!UICONTROL Image source URL]** che si apre.

   Dal nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, apri il nodo corrispondente alla raccolta creata, in questo caso **[!UICONTROL Product list]**, quindi fai clic sul campo immagine definito (qui **[!UICONTROL Product image]**). Fai clic su **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   Il campo di personalizzazione selezionato viene ora visualizzato nel riquadro Impostazioni.

1. Nella posizione desiderata, seleziona **[!UICONTROL Insert personalization field]** dalla barra degli strumenti contestuale.

   ![](assets/message-center_loop_product.png)

1. Dal nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, apri il nodo corrispondente alla raccolta creata (qui **[!UICONTROL Product list]**) e seleziona il campo creato (qui **[!UICONTROL Product name]**). Fai clic su **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   Il campo di personalizzazione selezionato viene ora visualizzato nella posizione desiderata all’interno del contenuto dell’e-mail.

1. Procedi similmente per l’inserimento del prezzo.
1. Seleziona una parte di testo e fai clic su **[!UICONTROL Insert link]** nella barra degli strumenti contestuale.

   ![](assets/message-center_loop_link_insert.png)

1. Seleziona **[!UICONTROL Add personalization field]** nella finestra **[!UICONTROL Insert link]** che si apre.

   Dal nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**, apri il nodo corrispondente alla raccolta creata, in questo caso **[!UICONTROL Product list]**, quindi fai clic sul campo URL (qui **[!UICONTROL Product URL]**). Fai clic su **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >Per motivi di sicurezza, accertati di inserire il campo di personalizzazione all’interno di un collegamento che inizia con un nome di dominio statico appropriato.

   ![](assets/message-center_loop_link_select.png)

   Il campo di personalizzazione selezionato viene ora visualizzato nel riquadro Impostazioni.

1. Scegli il componente struttura sul quale viene applicato l’elenco di prodotti, quindi fai clic su **[!UICONTROL Show fallback]** per definire un contenuto predefinito.

   ![](assets/message-center_loop_fallback_show.png)

1. Trascina uno o più componenti di contenuto e modificali in base alle tue esigenze.

   ![](assets/message-center_loop_fallback.png)

   Il contenuto di fallback verrà visualizzato se la raccolta è vuota al momento di attivare l’evento, ad esempio se un cliente ha il carrello vuoto.

1. Nel riquadro Impostazioni, modifica gli stili per l’elenco dei prodotti. Per ulteriori informazioni, consulta [Modifica degli stili delle e-mail](../../designing/using/styles.md).
1. Visualizza l’anteprima del messaggio e-mail utilizzando un profilo di prova collegato all’evento sulle transazioni rilevante per il quale hai definito i dati della raccolta. Ad esempio, aggiungi le seguenti informazioni nella sezione **[!UICONTROL Event data]** relativa al profilo di test da utilizzare:

   ![](assets/message-center_loop_test-profile_payload.png)

   Per approfondimenti sulla definizione di un profilo di test in un messaggio sulle transazioni, consulta [questa sezione](../../channels/using/event-transactional-messages.md#defining-specific-test-profile).

## Verifica di un messaggio sulle transazioni {#testing-a-transactional-message}

È innanzitutto necessario creare un profilo di test specifico che consenta di controllare correttamente il messaggio transazionale.

### Definizione di un profilo di test specifico {#defining-specific-test-profile}

Definite un profilo di test che sarà collegato all&#39;evento, per consentirvi di visualizzare l&#39;anteprima del messaggio e inviare una prova pertinente.

1. From the transactional message dashboard, click the **[!UICONTROL Create test profile]** button.

   ![](assets/message-center_test-profile.png)

1. Specifica le informazioni da inviare in formato JSON nella sezione **[!UICONTROL Event data used for personalization]**. Tale contenuto verrà utilizzato al momento della visualizzazione dell’anteprima del messaggio e quando il profilo di test riceve la bozza.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Puoi inoltre inserire le informazioni relative alla tabella del profilo. Consulta [Arricchimento del contenuto dei messaggi transazionali](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Una volta creato, il profilo di test verrà prespecificato nel messaggio di transazione. Per controllare la destinazione della bozza, fai clic sul blocco **[!UICONTROL Test profiles]** del messaggio.

   ![](assets/message-center_5.png)

Puoi anche creare un nuovo profilo di test o usarne uno già esistente nel menu **[!UICONTROL Test profiles]**. Per eseguire questa operazione:

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. Nella **[!UICONTROL Event]** sezione, selezionate l’evento appena creato. In questo esempio, seleziona &quot;Abbandono carrello (EVTcartAbandonment)&quot;.
1. Nella casella di testo **[!UICONTROL Event data]**, specifica le informazioni da inviare in formato JSON.

   ![](assets/message-center_3.png)

1. Salva le modifiche.
1. Accedete al messaggio creato e selezionate il profilo di test aggiornato.

**Argomenti correlati:**

* [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)
* [Definizione dei tipi di pubblico](../../audiences/using/creating-audiences.md)

### Invio della prova {#sending-proof}

Dopo aver creato uno o più profili di test specifici e aver salvato il messaggio transazionale, potete inviare una prova per verificarlo.

![](assets/message-center_10.png)

La procedura per l’invio di una bozza è illustrata nella sezione [Invio di una bozza](../../sending/using/sending-proofs.md).

## Pubblicazione di un messaggio sulle transazioni {#publishing-a-transactional-message}

Dopo aver controllato il messaggio sulle transazioni, puoi eseguirne la pubblicazione.

![](assets/message-center_12.png)

Ora, non appena si attiva l’evento &quot;Abbandono carrello&quot;, viene visualizzato automaticamente un messaggio contenente il titolo e il cognome del destinatario, l’URL del carrello, l’ultimo prodotto visionato o un elenco di prodotti, se definito, e l’importo totale del carrello da inviare.

Per accedere ai rapporti relativi al messaggio sulle transazioni, usa il pulsante **[!UICONTROL Reports]**. Consulta [Rapporti](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

### Sospensione di una pubblicazione di un messaggio sulle transazioni {#suspending-a-transactional-message-publication}

Puoi sospendere la pubblicazione del messaggio sulle transazioni utilizzando, ad esempio, il pulsante **[!UICONTROL Pause]** per la modifica dei dati contenuti nel messaggio. Pertanto, gli eventi non vengono più elaborati, ma rimangono in coda nel database di Adobe Campaign.

Gli eventi in coda vengono conservati durante un periodo di tempo definito nell’API REST (consulta la documentazione [REST API](../../api/using/get-started-apis.md)) o nell’evento trigger, se utilizzi il servizio core Triggers (vedi [Utilizzo di Campaign e Triggers di Experience Cloud](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

Durante la selezione di **[!UICONTROL Resume]**, vengono elaborati tutti gli eventi in coda, purché non siano scaduti. Adesso tali eventi contengono tutte le modifiche apportate durante la sospensione della pubblicazione del modello.

### Annullamento della pubblicazione di un messaggio sulle transazioni {#unpublishing-a-transactional-message}

Facendo clic su **[!UICONTROL Unpublish]** puoi annullare la pubblicazione dei messaggi sulle transazioni, ma anche la pubblicazione dell’evento corrispondente, che elimina dall’API REST la risorsa corrispondente all’evento creato in precedenza.

![](assets/message-center_unpublish-template.png)

Adesso, anche se l’evento viene attivato nel sito web, i messaggi corrispondenti non saranno più inviati e pertanto non verranno memorizzati nel database.

>[!NOTE]
>
>Per pubblicare nuovamente il messaggio, devi tornare alla configurazione dell’evento corrispondente e pubblicarla, infine pubblicare il messaggio. Per ulteriori informazioni, consulta [Pubblicazione di un messaggio sulle transazioni](#publishing-a-transactional-message).

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

* **Messaggi sulle transazioni**: a meno che un altro messaggio sulle transazioni non sia collegato all’evento corrispondente, se il messaggio sulle transazioni non viene pubblicato, anche la configurazione dell’evento deve essere annullata onde consentire una corretta eliminazione del messaggio sulle transazioni. Per ulteriori informazioni, consulta [Annullamento della pubblicazione di un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).

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
>Quando un evento viene assegnato a un’esecuzione di consegna, viene visualizzato nei registri di invio dell’esecuzione di consegna e solo in questa fase. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message sending logs.

### Limitazioni del processo di ripetizione {#limitations}

**Invio dell’aggiornamento dei registri**

Nel processo di esecuzione dei nuovi tentativi, i registri di invio della nuova consegna esecuzione non vengono aggiornati immediatamente, poiché tale procedura avviene tramite un flusso di lavoro pianificato. Ciò significa che il messaggio potrebbe trovarsi nello stato **[!UICONTROL Pending]** anche se l’evento sulle transazioni è stato elaborato dalla nuova consegna di esecuzione.

**Consegna di esecuzione non riuscita**

Non è possibile interrompere la consegna dell’esecuzione. Tuttavia, se la consegna dell’esecuzione corrente ha esito negativo, ne viene creata una nuova non appena viene ricevuto un nuovo evento, e tutti i nuovi eventi vengono elaborati dalla nuova consegna dell’esecuzione. Nessun nuovo evento viene elaborato dalla consegna dell’esecuzione non riuscita.

Se alcuni eventi già assegnati a una consegna dell’esecuzione sono stati posticipati e se tale consegna ha esito negativo, il sistema dei tentativi non assegna gli eventi posticipati alla nuova consegna dell’esecuzione, il che significa che tali eventi andranno perduti.
