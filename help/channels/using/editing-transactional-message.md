---
solution: Campaign Standard
product: campaign
title: Messaggi sulle transazioni degli eventi
description: Scopri come creare e pubblicare un messaggio sulle transazioni degli eventi.
page-status-flag: never-activated
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '1582'
ht-degree: 69%

---


# Modifica di un messaggio transazionale {#editing-transactional-message}

Dopo aver creato e pubblicato un evento<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->, viene automaticamente creato il messaggio transazionale corrispondente. I passaggi per configurare e pubblicare l&#39;evento sono descritti nella sezione [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md) e [Pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md).

I passaggi per accedere, modificare e personalizzare questo messaggio sono descritti di seguito.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). See [Fatigue rules](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

Quando il messaggio è pronto, può essere testato e pubblicato. Vedere [Durata dei messaggi transazionali](../../channels/using/publishing-transactional-message.md).

## Accesso ai messaggi transazionali {#accessing-transactional-messages}

Per accedere al messaggio transazionale creato:

1. Fate clic sul logo **[!UICONTROL Adobe Campaign]**, nell&#39;angolo in alto a sinistra.
1. Seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Fai clic sul messaggio desiderato per modificarlo.

>[!IMPORTANT]
>
>Per accedere ai messaggi transazionali, devi far parte del gruppo di sicurezza **[!UICONTROL Administrators (all units)]**. Per ulteriori informazioni, vedere [Gestione utenti](../../administration/using/users-management.md#functional-administrators).

## Personalizzazione di un messaggio sulle transazioni {#personalizing-a-transactional-message}

Per impostare la personalizzazione in un messaggio sulle transazioni, segui i passaggi riportati di seguito.

>[!NOTE]
>
>In questa sezione viene descritto come personalizzare un messaggio transazionale **basato su eventi**.  I passaggi di configurazione per creare un messaggio transazionale basato su eventi sono descritti in [questa sezione](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
>
>Le specificità dei messaggi transazionali **basati sul profilo** sono riportate di seguito [sotto](#profile-transactional-message-specificities).

Ad esempio, desiderate inviare una notifica agli utenti del vostro sito Web che hanno aggiunto prodotti al loro carrello e che lasciano il sito senza dover proseguire con i loro acquisti. Questo esempio è illustrato nella sezione [Principio operativo dei messaggi transazionali](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle).

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare l’oggetto e il contenuto del messaggio. Ai fini del presente esempio, seleziona un modello contenente immagini e testo. Per ulteriori informazioni sui modelli di contenuto delle e-mail, vedere [Progettazione di e-mail utilizzando i modelli](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Aggiungi un oggetto e modifica il contenuto del messaggio in base alle tue esigenze.

   >[!NOTE]
   >
   >Il collegamento al carrello abbandonato porta a un URL esterno che reindirizzerà il consumatore al proprio carrello. Tale parametro non è gestito all’interno di Adobe Campaign.

1. Nell’esempio attuale, vuoi aggiungere tre campi precedentemente definiti durante la [creazione dell’evento](../../channels/using/configuring-transactional-event.md): nome, ultimo prodotto visionato, importo totale del carrello. A tal fine, [inserisci un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) nel contenuto del messaggio.

1. Puoi accedere ai campi in questione tramite **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Per arricchire il contenuto del messaggio, aggiungi i campi selezionandoli dalla tabella a cui hai collegato l’evento. In questo esempio, selezionare il campo **[!UICONTROL Title (salutation)]** nella tabella **[!UICONTROL Profile]** attraverso **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Inserisci tutti i campi richiesti.

   ![](assets/message-center_8.png)

1. Per visualizzare l’anteprima del messaggio, seleziona il profilo definito per l’evento.

   La procedura per la visualizzazione dell’anteprima di un messaggio è spiegata nei dettagli nella sezione [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Puoi verificare che i campi di personalizzazione corrispondano alle informazioni inserite nel profilo di test. Per ulteriori informazioni, vedere [Definizione di un profilo di test specifico](../../channels/using/publishing-transactional-message.md#defining-specific-test-profile).

## Utilizzo degli elenchi di prodotti in un messaggio sulle transazioni {#using-product-listings-in-a-transactional-message}

Puoi creare elenchi di prodotti che fanno riferimento a una o più raccolte di dati presenti nel contenuto di un’e-mail sulle transazioni. Ad esempio, in un messaggio e-mail di abbandono del carrello puoi includere un elenco di tutti i prodotti presenti nei carrelli degli utenti al momento dell’uscita dal sito web, aggiungendo un’immagine, il prezzo e il collegamento a ciascun prodotto.

>[!IMPORTANT]
>
>Gli elenchi dei prodotti sono disponibili solo durante la modifica dei messaggi e-mail sulle transazioni tramite l’interfaccia di [E-mail Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Per aggiungere un elenco di prodotti abbandonati in un messaggio sulle transazioni, segui i passaggi indicati di seguito.

È inoltre possibile guardare [questo set di video](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html?lang=en#configure-product-listings-in-transactional-emails) per illustrare i passaggi necessari per configurare gli elenchi di prodotti in un messaggio e-mail transazionale.

>[!NOTE]
>
>Adobe Campaign non supporta elenchi di prodotti nidificati, il che significa che non puoi includere un elenco di prodotti all’interno di un altro.

### Definizione di un elenco di prodotti {#defining-a-product-listing}

Prima di poter utilizzare un elenco di prodotti in un messaggio sulle transazioni, è necessario definire a livello di evento l’elenco dei prodotti e i campi per ciascun prodotto da visualizzare. Per ulteriori informazioni, consulta [Definizione delle raccolte di dati](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Nel messaggio sulle transazioni, fai clic sul blocco **[!UICONTROL Content]** per modificare il contenuto dell’e-mail.
1. Trascina e rilascia un componente struttura all’interno dell’area di lavoro. Per ulteriori informazioni, vedere [Definizione della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Ad esempio, seleziona un componente struttura a una colonna e aggiungi un componente testo, un componente immagine e un componente pulsante. Per ulteriori informazioni, vedere [Utilizzo dei componenti di contenuto](../../designing/using/designing-from-scratch.md#about-content-components).

1. Seleziona il componente struttura appena creato, quindi fai clic sull’icona **[!UICONTROL Enable product listing]** nella barra degli strumenti contestuale.

   ![](assets/message-center_loop_create.png)

   Il componente struttura viene evidenziato con una cornice arancione e le impostazioni **[!UICONTROL Product listing]** sono visualizzate nella palette a sinistra.

   ![](assets/message-center_loop_palette.png)

1. Seleziona la modalità di visualizzazione degli elementi della raccolta:

   * **[!UICONTROL Row]**: orizzontale, ovvero ogni elemento posto sulla riga inferiore al precedente.
   * **[!UICONTROL Column]**: verticale, ovvero ciascun elemento posto accanto all’altro sulla medesima riga.

   >[!NOTE]
   >
   >L’opzione **[!UICONTROL Column]** è disponibile solo quando è in uso un componente struttura a più colonne ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** e **[!UICONTROL 4:4 column]** ). Quando modifichi l’elenco dei prodotti, compila solo la prima colonna: le altre non saranno prese in considerazione. Per ulteriori informazioni sulla selezione dei componenti struttura, vedere [Definizione della struttura dell&#39;e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Seleziona la raccolta dati creata durante la configurazione dell’evento correlato al messaggio sulle transazioni, disponibile nel nodo **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_loop_selection.png)

   Per ulteriori informazioni sulla configurazione dell’evento, consulta [Definizione delle raccolte di dati](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Utilizza l’elenco a discesa **[!UICONTROL First item]** per selezionare l’elemento che avvierà l’elenco visualizzato nel messaggio e-mail.

   Ad esempio, se scegli 2, il primo elemento della raccolta non verrà visualizzato nell’e-mail. L’elenco dei prodotti partirà dal secondo elemento.

1. Seleziona il numero massimo di elementi da visualizzare nell’elenco.

   >[!NOTE]
   >
   >Se desideri che gli elementi dell’elenco siano visualizzati in verticale ( **[!UICONTROL Column]** ), il numero massimo è limitato in base al componente struttura selezionato (2, 3 o 4 colonne). Per ulteriori informazioni sulla selezione dei componenti struttura, consulta [Modifica della struttura delle e-mail](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Popolamento dell’elenco dei prodotti {#populating-the-product-listing}

Per visualizzare un elenco dei prodotti provenienti dall’evento collegato al messaggio e-mail sulle transazioni, attieniti alla procedura seguente.

Per ulteriori informazioni sulla creazione di una raccolta e dei campi correlati durante la configurazione dell’evento, consulta [Definizione delle raccolte di dati](../../channels/using/configuring-transactional-event.md#defining-data-collections).

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

1. Nel riquadro Impostazioni, modifica gli stili per l’elenco dei prodotti. Per ulteriori informazioni, vedere [Gestione degli stili e-mail](../../designing/using/styles.md).
1. Visualizza l’anteprima del messaggio e-mail utilizzando un profilo di prova collegato all’evento sulle transazioni rilevante per il quale hai definito i dati della raccolta. Ad esempio, aggiungi le seguenti informazioni nella sezione **[!UICONTROL Event data]** relativa al profilo di test da utilizzare:

   ![](assets/message-center_loop_test-profile_payload.png)

   Per approfondimenti sulla definizione di un profilo di test in un messaggio sulle transazioni, consulta [questa sezione](../../channels/using/publishing-transactional-message.md#defining-specific-test-profile).

## Specificità dei messaggi transazionali basati su profilo {#profile-transactional-message-specificities}

Puoi inviare messaggi transazionali basati sui profili di marketing dei clienti, che ti consentono di sfruttare tutte le informazioni di profilo per personalizzare il contenuto del messaggio, utilizzare il collegamento di annullamento dell&#39;iscrizione e applicare regole di tipologia di marketing come [regole di affaticamento](../../sending/using/fatigue-rules.md).

* Per ulteriori informazioni sulle differenze tra i messaggi transazionali basati sugli eventi e quelli basati sui profili, vedere [questa sezione](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types).

* I passaggi di configurazione per creare un messaggio transazionale basato sul profilo sono descritti in [questa sezione](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

### Modifica di un messaggio di transazione profilo {#editing-profile-transactional-message}

I passaggi per creare, personalizzare e pubblicare un messaggio transazionale di profilo sono principalmente gli stessi del messaggio transazionale di un evento.

Le differenze sono elencate di seguito.

1. [Passa al messaggio transazionale creato per modificarlo.](#accessing-transactional-messages)
1. Nel messaggio transazionale, fai clic sulla sezione **[!UICONTROL Content]**. Oltre ai modelli di e-mail transazionali, potete anche scegliere qualsiasi modello di e-mail per la risorsa **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Seleziona il modello di e-mail predefinito. Analogamente a tutte le e-mail di marketing, include un **collegamento di annullamento dell&#39;iscrizione**.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Per ulteriori informazioni sui modelli, vedere [questa sezione](../../designing/using/using-reusable-content.md#content-templates).

1. Inoltre, a differenza delle configurazioni basate su eventi in tempo reale, è possibile accedere direttamente a tutte le informazioni di profilo **per personalizzare il messaggio.** Puoi aggiungere [campi di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) come faresti per qualsiasi altra e-mail di marketing standard.

1. Salva le modifiche prima di pubblicare il messaggio. Per ulteriori informazioni, consulta [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

### Monitoraggio della consegna dei messaggi transazionali di profilo {#monitoring-a-profile-transactional-message-delivery}

Dopo la pubblicazione del messaggio e il completamento dell’integrazione con il sito puoi monitorare la consegna.

1. Fai clic sull’icona in basso a destra del blocco **[!UICONTROL Deployment]** per visualizzare il registro di consegna del messaggio.

   Per ulteriori informazioni sull&#39;accesso ai registri, vedere [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md).

1. Seleziona la scheda **[!UICONTROL Sending logs]**. Nella colonna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica che un profilo ha acconsentito.

   ![](assets/message-center_marketing_sending_logs.png)

1. Selezionate la scheda **[!UICONTROL Exclusions logs]** per visualizzare i destinatari che sono stati esclusi dalla destinazione del messaggio, ad esempio gli indirizzi sul elenco Bloccati.

   ![](assets/message-center_marketing_exclusion_logs.png)

Per ogni profilo che ha rinunciato, la regola di tipologia **[!UICONTROL Address on denylist]** ha escluso il destinatario corrispondente.

Questa regola fa parte di una tipologia specifica che si applica a tutti i messaggi transazionali basati sulla tabella **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Argomenti correlati**:

* Integrare l&#39;attivazione degli eventi (../../channels/using/getting-started-with-transactional-msg.md#integration-event-trigger)
* [Informazioni su tipologie e regole di tipologia](../../sending/using/about-typology-rules.md)
