---
title: Messaggi transazionali evento
seo-title: Messaggi transazionali evento
description: Messaggi transazionali evento
seo-description: Informazioni su come creare e pubblicare un messaggio transazionale evento.
page-status-flag: never-activated
uuid: d 747 feb 5-58 fb -4 e 12-a 176-404 f 0 eca 5391
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: transactional-messaging
discoiquuid: 4 f 6317 a 1-9 dfe -4714-bc 1 c -393629 d 855 cd
context-tags: Deliverytransactionaltemplate, overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e08b7e01956a9106937cb72ab790cb2e98999fcd

---


# Event transactional messages{#event-transactional-messages}

Potete inviare messaggi transazionali evento per un evento. Questo tipo di messaggi transazionali non contiene informazioni sul profilo: la destinazione di consegna è definita dai dati contenuti nell'evento stesso.

Once you have created and published an event (the cart abandonment as explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send an transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Affinché l'evento attivi l'invio di un messaggio transazionale, dovete personalizzare il messaggio, quindi testarlo e pubblicarlo.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. I messaggi transazionali degli eventi non contengono informazioni sul profilo, pertanto non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con profili). See [Fatigue rules](../../administration/using/fatigue-rules.md#choosing-the-channel).

## Defining a test profile in a transactional message {#defining-a-test-profile-in-a-transactional-message}

Definire un profilo di test adattabile, che ti consentirà di visualizzare l'anteprima del messaggio e di inviarne una prova.

### Creating a test profile within the transactional message {#creating-a-test-profile-within-the-transactional-----------message}

1. To access the message that you created, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Create un profilo di prova che verrà collegato all'evento.

   ![](assets/message-center_test-profile.png)

1. Specify the information to send in JSON format in the **[!UICONTROL Event data used for personalization]** section. Si tratta del contenuto che verrà utilizzato per visualizzare l'anteprima del messaggio e quando il profilo di prova riceve la prova.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Potete anche immettere le informazioni relative alla tabella del profilo. See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Una volta creato, il profilo di prova sarà prespecificato nel messaggio transazionali. Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

### Creating a test profile outside the transactional message {#creating-a-test-profile-outside-the-transactional-----------message}

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section of the page of the test profile that you have chosen, select the event that you have just created. In questo esempio, seleziona "Abbandono carrello (evtcartabandonment)".
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. Salvate le modifiche.

Ora potete accedere al messaggio che avete creato e selezionare il profilo di prova aggiornato.

**Argomenti correlati:**

* [Gestione dei profili di prova](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [Definizione dei tipi di pubblico](../../audiences/using/creating-audiences.md)

## Personalizing a transactional message {#personalizing-a-transactional-message}

Per configurare la personalizzazione in un messaggio di transazione, segui i passaggi seguenti:

1. Click the **[!UICONTROL Content]** block to modify your message's subject and content. Per questo esempio, importare un modello HTML contenente immagini, il foglio di stile e un file HTML. Importing HTML templates is presented in the [Loading an existing content](../../designing/using/selecting-an-existing-content.md) section.

   ![](assets/message-center_6.png)

1. Immettete il contenuto del messaggio. In questo esempio sono stati aggiunti tre campi di personalizzazione: cognome, ultimo prodotto consultato, importo totale carrello. Il collegamento al carrello abbandonato è un collegamento a un URL esterno che reindirizzerà la persona al carrello. Questo parametro non viene gestito in Adobe Campaign.

   To add fields that you defined when you created your event (see [Configuring an event](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message)), insert a personalization field in the message content. You can find the fields by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Per arricchire il contenuto del messaggio, aggiungete campi selezionandoli dalla tabella in cui avete collegato l'evento. In our example, select the **[!UICONTROL Title (salutation)]** field in the **[!UICONTROL Profile]** table.

   ![](assets/message-center_7-enrichment.png)

   The steps for inserting a personalization field are detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

   ![](assets/message-center_8.png)

1. Visualizzate l'anteprima del messaggio selezionando il profilo definito per l'evento.

   The steps for previewing a message are detailed in the [Previewing messages](../../sending/using/preparing-the-send.md) section.

   ![](assets/message-center_9.png)

   Potete controllare che i campi di personalizzazione corrispondano alle informazioni inserite nel profilo di prova. For more on this, see [Defining a test profile in a transactional message](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

È possibile creare elenchi di prodotti che fanno riferimento a una o più raccolte di dati nel contenuto di un'e-mail transazionale. Ad esempio, in un messaggio e-mail di abbandono del carrello puoi includere un elenco di tutti i prodotti che si trovavano nei carrelli degli utenti quando hanno lasciato il tuo sito Web, con un'immagine, il prezzo e un collegamento a ciascun prodotto.

>[!CAUTION]
>
>Product listings are only available when editing transactional email messages through the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) interface.

Per aggiungere un elenco di prodotti abbandonato in un messaggio transazionale, segui i passaggi indicati di seguito.

Potete inoltre guardare un set di video che descrive i passaggi necessari per configurare gli elenchi di prodotti in un messaggio e-mail. For more on this, see [this page](https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html).

>[!NOTE]
>
>Adobe Campaign non supporta gli elenchi nidificati di prodotti, il che significa che non puoi includere un elenco di prodotti all'interno di un altro.

### Defining a product listing {#defining-a-product-listing}

Prima di poter utilizzare un elenco di prodotti in un messaggio di transazione, è necessario definire a livello di evento l'elenco dei prodotti e i campi per ciascun prodotto dell'elenco che desiderate visualizzare. For more on this, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Trascinare un componente struttura nell'area di lavoro. For more on this, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

   Ad esempio, selezionate un componente struttura a colonne e aggiungete un componente testo, un componente immagine e un componente pulsante. For more on this, see [Adding fragments and components](../../designing/using/defining-the-email-structure.md#adding-fragments-and-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Selezionate la modalità di visualizzazione degli elementi della raccolta:

   * **[!UICONTROL Row]**: orizzontalmente, ovvero ogni elemento in una riga sotto l'altro.
   * **[!UICONTROL Column]**: verticale, ovvero ogni elemento accanto all'altro sulla stessa riga.
   >[!NOTE]
   >
   >The **[!UICONTROL Column]** option is only available when using a multicolumn structure component ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** and **[!UICONTROL 4:4 column]** ). Durante la modifica dell'elenco dei prodotti, compila solo la prima colonna: le altre colonne non saranno considerate. For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

1. Selezionate la raccolta di dati creata durante la configurazione dell'evento correlato al messaggio transazionale. You can find it under the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   Ad esempio, se selezionate 2, il primo elemento della raccolta non verrà visualizzato nell'e-mail. L'elenco dei prodotti verrà avviato sul secondo elemento.

1. Selezionate il numero massimo di elementi da visualizzare nell'elenco.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

Per visualizzare un elenco di prodotti provenienti dall'evento collegato all'e-mail transazionale, attenetevi alla procedura seguente.

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   Il campo di personalizzazione selezionato è ora visualizzato nel riquadro Impostazioni.

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   Il campo di personalizzazione selezionato viene ora visualizzato nella posizione desiderata nel contenuto dell'e-mail.

1. Procedete in modo simile per inserire il prezzo.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** &gt; **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!CAUTION]
   >
   >Per motivi di sicurezza, inserire il campo di personalizzazione all'interno di un collegamento a partire da un nome di dominio statico corretto.

   ![](assets/message-center_loop_link_select.png)

   Il campo di personalizzazione selezionato è ora visualizzato nel riquadro Impostazioni.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Trascinate uno o più componenti di contenuto e modificateli in base alle vostre esigenze.

   ![](assets/message-center_loop_fallback.png)

   Il contenuto di riserva verrà visualizzato se la raccolta è vuota quando l'evento viene attivato, ad esempio se un cliente non ha nulla nel carrello.

1. Nel riquadro Impostazioni, modificate gli stili per l'elenco dei prodotti. For more on this, see [Editing email styles](../../designing/using/editing-email-styles.md).
1. Visualizzate l'anteprima dell'e-mail utilizzando un profilo di prova collegato all'evento transactional rilevante e per il quale avete definito i dati della raccolta. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/event-transactional-messages.md#defining-a-test-profile-in-a-transactional-message).

## Testing a transactional message {#testing-a-transactional-message}

Dopo aver salvato il messaggio transazionale, ora puoi inviare una prova per testarla.

![](assets/message-center_10.png)

The steps for sending a proof are detailed in the [Sending a proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.

## Publishing a transactional message {#publishing-a-transactional-message}

Dopo aver selezionato il messaggio transazionale, puoi pubblicarlo.

![](assets/message-center_12.png)

Ora, quando viene attivato l'evento «Abbandono del carrello», viene richiesto automaticamente un messaggio contenente il titolo e il cognome del destinatario, l'URL del carrello, l'ultimo prodotto consultato o un elenco di prodotti se avete definito un elenco di prodotti e il numero totale del carrello da inviare.

To access reports concerning your transactional message, use the **[!UICONTROL Reports]** button. See [Reports](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspending a transactional message publication {#suspending-a-transactional-message-publication}

You can suspend publishing your transactional message by using the **[!UICONTROL Pause]** button, for example, to modify the data contained in the message. Gli eventi non vengono più elaborati, ma sono mantenuti in coda nel database Adobe Campaign.

The queued events are kept during a period of time that is defined in the REST API (see [REST API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)) or in the trigger event if you are using the Triggers core service (see [Working with Campaign and Experience Cloud Triggers](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

When clicking **[!UICONTROL Resume]**, all of the queued events (provided that they are not expired) are processed. Adesso contengono tutte le modifiche eseguite mentre la pubblicazione del modello è stata sospesa.

## Unpublishing a transactional message {#unpublishing-a-transactional-message}

Clicking **[!UICONTROL Unpublish]** allows you to cancel the transactional message publication, but also the publication of the corresponding event, which deletes from the REST API the resource corresponding to the event that you previously created. Ora, anche se l'evento viene attivato attraverso il sito Web, i messaggi corrispondenti non vengono più inviati e non vengono memorizzati nel database.

![](assets/message-center_unpublish-template.png)

>[!NOTE]
>
>Per pubblicare nuovamente il messaggio, dovete tornare alla configurazione degli eventi corrispondente, pubblicarlo e pubblicare il messaggio. For more on this, see [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

Se annullate la pubblicazione di un messaggio transazionale in pausa, potrebbe essere necessario attendere fino a 24 ore prima di pubblicarla nuovamente. This is to let the **[!UICONTROL Database cleanup]** workflow clean all the events that were sent to the queue. The steps for pausing a message are detailed in the [Suspending a transactional message publication](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication) section.

The **[!UICONTROL Database cleanup]** workflow, which runs every day at 4am, is accessible through **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]**.

## Deleting a transactional message {#deleting-a-transactional-message}

![](assets/message-center_delete-template.png)

By selecting a transactional message, you can delete it with the **[!UICONTROL Delete element]** button even if it has already been published. Tuttavia, l'eliminazione di un messaggio transazionale può essere eseguita solo in determinate condizioni:

* **Messaggi transazionali**: Per eliminare un messaggio transazionale, il messaggio deve essere non pubblicato e non deve essere messo in pausa.

   Se il messaggio transazionali non viene pubblicato, la configurazione dell'evento deve non essere pubblicata per eliminare correttamente il messaggio transazionali, a meno che un altro messaggio di transazione non sia collegato all'evento corrispondente. For more information on how to unpublish a transactional message, refer to this [section](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

   >[!CAUTION]
   >
   >Eliminando un messaggio transazionale che ha già inviato delle notifiche, vengono eliminati anche i registri di invio e di tracciamento.

* **Messaggi transazionali da un modello di evento out-of-the-box (messaggi transazionali interni)**: Per eliminare un messaggio transazionale interno, il messaggio deve essere non pubblicato e non deve essere messo in pausa.

   Inoltre, non deve essere l'unico messaggio transazionale nell'evento, altri messaggi devono essere collegati all'evento corrispondente.

## Transactional message retry process {#transactional-message-retry-process}

Un messaggio transazionale non consegnato è soggetto a tentativi automatici che vengono eseguiti fino alla scadenza della distribuzione. For more on the delivery duration, see [Validity period parameters](../../administration/using/configuring-email-channel.md#validity-period-parameters).

Quando un messaggio di transazione non viene inviato, sono disponibili due tentativi:

* A livello di messaggistica transazionale, un messaggio transazionale può fallire prima che l'evento venga assegnato a una consegna dell'esecuzione, ossia tra il ricevimento dell'evento e la preparazione della consegna. See [Event processing retry process](../../channels/using/event-transactional-messages.md#event-processing-retry-process).
* A livello di processo di invio, una volta che l'evento è stato assegnato a una consegna di esecuzione, il messaggio transazionali potrebbe non riuscire a causa di un errore temporaneo. See [Message sending retry process](../../channels/using/event-transactional-messages.md#message-sending-retry-process).

### Event processing retry process {#event-processing-retry-process}

Se l'evento non può essere assegnato a una consegna di esecuzione, l'elaborazione dell'evento viene posticipata. I tentativi vengono quindi eseguiti finché non viene assegnato a una nuova consegna dell'esecuzione.

>[!NOTE]
>
>Un evento posticipato non viene visualizzato nei registri di invio transazionali, perché non è assegnato ancora a un'esecuzione dell'esecuzione.

Ad esempio, l'evento non poteva essere assegnato a una consegna di esecuzione poiché il suo contenuto non era corretto, si verificava un problema con diritti di accesso o branding, veniva rilevato un errore durante l'applicazione delle regole di tipologie, ecc. In questo caso, potete mettere in pausa il messaggio, modificarlo per risolvere il problema e pubblicarlo di nuovo. Il sistema di tentativi, quindi, lo assegnerà a una nuova consegna dell'esecuzione.

### Message sending retry process {#message-sending-retry-process}

Una volta che l'evento è stato assegnato a una consegna di esecuzione, il messaggio transazionali potrebbe non riuscire a causa di un errore temporaneo, se la casella postale del destinatario è completa ad esempio. For more on this, see [Retries after a delivery temporary failure](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Quando un evento viene assegnato a una consegna di esecuzione, viene visualizzato nei registri di invio di questa consegna dell'esecuzione e solo in questa fase. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message.

### Limitations {#limitations}

**Invio di registri di registro**

Nel processo di tentativi, i registri di invio della nuova consegna dell'esecuzione non vengono immediatamente aggiornati (l'aggiornamento viene eseguito tramite un flusso di lavoro pianificato). It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**Consegna esecuzione non riuscita**

Non è possibile interrompere la consegna di un'esecuzione. Tuttavia, se l'esecuzione corrente dell'esecuzione non riesce, ne viene creata una nuova non appena viene ricevuto un nuovo evento e tutti i nuovi eventi vengono elaborati da questa nuova consegna dell'esecuzione. Nessun nuovo evento viene elaborato dalla distribuzione dell'esecuzione non riuscita.

Se alcuni eventi già assegnati a una distribuzione di esecuzione sono stati posticipati e se la consegna dell'esecuzione non riesce, il sistema di tentativi non assegna gli eventi posticipati alla nuova consegna dell'esecuzione, vale a dire che questi eventi vanno persi.
