---
title: Configurazione della struttura dati della risorsa
description: Scopri come configurare la struttura dei dati.
page-status-flag: never-activated
uuid: 60fe80c0-9df6-4808-a432-60a1977216ea
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 4f22ee35-1d5f-4c75-95b4-3e38b85de26e
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6cf00f9b9bafdd54d8424a353b33dc689c0f59aa

---


# Configurazione della struttura dati della risorsa{#configuring-the-resource-s-data-structure}

Dopo aver creato una nuova risorsa personalizzata, è necessario configurare la struttura dei dati.

Quando modificate la risorsa, nella **[!UICONTROL Data structure]** scheda potete aggiungere:

* [Campi](#adding-fields-to-a-resource)
* [Tasti di identificazione](#defining-identification-keys)
* [Indici](#defining-indexes)
* [Collegamenti](#defining-links-with-other-resources)
* [Invio di registri](#defining-sending-logs-extension)

## Aggiunta di campi a una risorsa {#adding-fields-to-a-resource}

È possibile aggiungere nuovi campi a una risorsa per memorizzare i dati che non fanno parte del modello dati out-of-box.

1. Utilizzare il **[!UICONTROL Create element]** pulsante per creare un campo.
1. Specificare un&#39;etichetta, un ID, un tipo di campo e definire la lunghezza massima autorizzata per questo campo.

   Il **[!UICONTROL ID]** campo è obbligatorio e deve essere univoco per ciascun campo aggiunto.

   >[!NOTE]
   >
   >Utilizzate un massimo di 30 caratteri.

   ![](assets/schema_extension_4.png)

1. Per modificare uno dei campi, selezionare il **[!UICONTROL Edit Properties]** pulsante.

   ![](assets/schema_extension_24.png)

1. Nella **[!UICONTROL Field definition]** schermata, potete definire una categoria che verrà utilizzata per l&#39;audience e il targeting, o anche aggiungere una descrizione.

   ![](assets/schema_extension_5.png)

1. Selezionare l&#39; **[!UICONTROL Specify a list of authorized values]** opzione se è necessario definire i valori che verranno offerti all&#39;utente (valori di enumerazione).

   Quindi, fate clic **[!UICONTROL Create element]** e specificate un **[!UICONTROL Label]** e **[!UICONTROL Value]**. Aggiungete tutti i valori necessari.

1. Dopo aver aggiunto i campi, selezionate la **[!UICONTROL Add audit fields]** casella per includere i campi con dettagli sulla data di creazione, l’utente che ha creato la risorsa, la data e l’autore dell’ultima modifica.
1. Selezionate la **[!UICONTROL Add access authorization management fields]** casella per includere i campi in cui sono indicati gli utenti con diritti di accesso a tale risorsa.

   Questi campi vengono visualizzati nei dati e nei metadati che possono essere visualizzati una volta che è stato eseguito l&#39;aggiornamento del database. Per ulteriori informazioni, vedere [Aggiornamento della struttura](../../developing/using/updating-the-database-structure.md) del database.

1. Controllare il **[!UICONTROL Add automatic ID]** campo per generare automaticamente un ID. Le entità esistenti rimarranno vuote. Per ulteriori informazioni, consulta [Generazione di un ID univoco per i profili e le risorse](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)personalizzate.
1. Per modificare il modo in cui il nome degli elementi della risorsa verrà visualizzato negli elenchi e nelle fasi di creazione, selezionate la **[!UICONTROL Customize the title of the resource elements]** casella di controllo. Selezionare un campo tra quelli creati per la risorsa.

   ![](assets/schema_extension_18.png)

   >[!NOTE]
   >
   >Se non si seleziona questa opzione, la chiave primaria automatica (che viene creata automaticamente ogni volta che un&#39;entità viene aggiunta alla tabella) verrà utilizzata quando si elencano tutte le entità da questa tabella.

I campi della risorsa sono ora definiti.

## Definizione dei tasti di identificazione {#defining-identification-keys}

Ciascuna risorsa deve avere almeno una chiave univoca. Ad esempio, potete specificare una chiave in modo che due prodotti non possano avere lo stesso ID in una tabella di acquisto.

1. Specificate nella **[!UICONTROL Automatic primary key]** sezione le dimensioni per lo storage se desiderate che una chiave tecnica venga generata automaticamente e in modo incrementale.

   ![](assets/schema_extension_6.png)

1. Usate il **[!UICONTROL Create element]** pulsante per creare una chiave.

   I campi **[!UICONTROL Label]** e **[!UICONTROL ID]** sono completati per impostazione predefinita, ma è possibile modificarli.

   >[!NOTE]
   >
   >Utilizzate un massimo di 30 caratteri.

1. Per definire gli elementi che compongono la chiave, fare clic su **[!UICONTROL Create element]** e selezionare i campi creati per la risorsa.

   ![](assets/schema_extension_7.png)

   Le chiavi create vengono visualizzate nella **[!UICONTROL Custom keys]** sezione.

Vengono ora create le chiavi di identificazione per la risorsa.

>[!NOTE]
>
>Per informazioni sulle procedure ottimali per la creazione dei tasti di identificazione, consulta questa [sezione](../../developing/using/data-model-best-practices.md#keys).

## Definizione degli indici {#defining-indexes}

Un indice può fare riferimento a uno o più campi di risorse. Gli indici consentono al database di ordinare i record in modo da poterli recuperare più facilmente. Ottimizzano le prestazioni delle query SQL.

La definizione degli indici è consigliata ma non obbligatoria.

1. Utilizzare il **[!UICONTROL Create element]** pulsante per creare un indice.

   ![](assets/schema_extension_26.png)

1. I campi **[!UICONTROL Label]** e **[!UICONTROL ID]** sono completati per impostazione predefinita, ma è possibile modificarli.

   >[!NOTE]
   >
   >Utilizzate un massimo di 30 caratteri.

1. Per definire gli elementi che compongono questo indice, selezionare i campi tra quelli creati per la risorsa.

   ![](assets/schema_extension_27.png)

1. Clic **[!UICONTROL Confirm]**.

Gli indici creati vengono visualizzati nell&#39;elenco della **[!UICONTROL Index]** sezione.

>[!NOTE]
>
>Per informazioni sulle best practice per la creazione di indici, consulta questa [sezione](../../developing/using/data-model-best-practices.md#indexes).

## Definizione di collegamenti con altre risorse {#defining-links-with-other-resources}

Un collegamento descrive l&#39;associazione di una tabella con altre tabelle.

1. Usate il **[!UICONTROL Create element]** pulsante per creare un collegamento a una risorsa di destinazione.
1. Clic **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. Le risorse sono visualizzate in ordine alfabetico e possono essere filtrate per nome. Il nome tecnico viene visualizzato tra parentesi.

   Selezionate un elemento dall’elenco e fate clic su **[!UICONTROL Confirm]**.

   ![](assets/schema_extension_9.png)

1. Selezionare il **[!UICONTROL Link type]** secondo cardinalità. A seconda del tipo di cardinalità selezionato, il comportamento se i record vengono eliminati o duplicati può variare.

   I vari tipi di collegamento sono i seguenti:

   * **[!UICONTROL 1 cardinality simple link]**: una occorrenza della tabella di origine può avere al massimo una occorrenza corrispondente della tabella di destinazione.
   * **[!UICONTROL N cardinality collection link]**: una occorrenza della tabella di origine può avere diverse occorrenze corrispondenti della tabella di destinazione, ma una occorrenza della tabella di destinazione può avere al massimo una occorrenza corrispondente della tabella di origine.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: una occorrenza della tabella di origine può avere al massimo una occorrenza corrispondente della tabella di destinazione o nessuna. È **[!UICONTROL Link type]** possibile che questo tipo di problemi di prestazioni.
   ![](assets/schema_extension_29.png)

1. Nella **[!UICONTROL New link]** schermata, i campi **[!UICONTROL Label]** e **[!UICONTROL ID]** sono completati per impostazione predefinita, ma è possibile modificarli.

   >[!NOTE]
   >
   >Utilizzate un massimo di 30 caratteri.

   >[!IMPORTANT]
   >
   >Non è possibile rinominare un collegamento dopo la creazione. Per rinominare un collegamento, è necessario eliminarlo e crearlo di nuovo.

1. L&#39; **[!UICONTROL Category for the audience and targeting]** elenco consente di assegnare il collegamento a una categoria per renderlo più visibile nello strumento di modifica delle query.
1. Se necessario, la **[!UICONTROL Reverse link definition]** sezione consente di visualizzare l’etichetta e l’ID della risorsa nella risorsa di destinazione.
1. Definire il comportamento dei record a cui fa riferimento il collegamento nella **[!UICONTROL Behavior if deleted/duplicated]** sezione.

   Per impostazione predefinita, il record di destinazione viene eliminato una volta che il collegamento non vi fa più riferimento.

   ![](assets/schema_extension_16.png)

1. Nella **[!UICONTROL Join definition]** sezione, l&#39; **[!UICONTROL Use the primary keys to make the join]** opzione predefinita è selezionata, ma è possibile scegliere tra due opzioni:

   * **[!UICONTROL Use the primary key to make the join]**: Questa definizione di partecipazione consente di utilizzare la chiave primaria dei profili per riconciliarsi con la chiave primaria degli acquisti.
   * **[!UICONTROL Define specific join conditions]**: Questa definizione di partecipazione consente di selezionare manualmente i campi che verranno uniti a entrambe le risorse. Se i dati non sono configurati correttamente, il record **Acquisto** non sarà visibile.
   ![](assets/schema_extension_17.png)

I collegamenti creati vengono visualizzati nell&#39;elenco della **[!UICONTROL Links]** sezione.

>[!NOTE]
>
>Per informazioni sulle best practice per la creazione di indici, consulta questa [sezione](../../developing/using/data-model-best-practices.md#links).

**Esempio: Collegare una risorsa creata con la risorsa &#39;Profili&#39;**

In questo esempio, vogliamo collegare una nuova risorsa **Acquisto** con la risorsa personalizzata **Profili** :

1. Creare la nuova risorsa **Acquisto** .
1. Per collegarlo alla risorsa **personalizzata Profili** , apri la **[!UICONTROL Links]** sezione nella **[!UICONTROL Data structure]** scheda e fai clic su **[!UICONTROL Create element]**.
1. Selezionate la risorsa di destinazione, qui **[!UICONTROL Profiles (profile)]**.
1. In questo esempio, mantenere selezionato il tipo di **[!UICONTROL 1 cardinality simple link]** collegamento predefinito.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Scegliete una definizione di join, mantenendo il valore predefinito **[!UICONTROL Use the primary key to make the join]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. Se necessario, potete definire una schermata di dettaglio per poter modificare **Purchase** e collegarlo a un profilo.

   Aprite la **[!UICONTROL Detail screen configuration]** sezione e verificate il **[!UICONTROL Define a detail screen]** pulsante per configurare la schermata corrispondente a ciascun elemento della risorsa. Se non selezionate questa casella, la visualizzazione dettagliata degli elementi di questa risorsa non sarà accessibile.

1. Clic **[!UICONTROL Create element]**.
1. Selezionate la risorsa collegata e fate clic su **[!UICONTROL Add]**.

   La nuova risorsa sarà quindi disponibile nel menu avanzato selezionando **[!UICONTROL Client data]** > **[!UICONTROL Purchase]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Al termine della configurazione, fate clic su **[!UICONTROL Confirm]**.

   Ora potete pubblicare la nuova risorsa.

Aggiungendo questo collegamento, una scheda **Acquisto** viene aggiunta alla schermata di dettaglio dei profili dal menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Profiles]** . Nota: è specifico per la **[!UICONTROL Profile]** risorsa.

![](assets/custom_resource_link_to_profile.png)

## Definizione dell’estensione dei registri di invio {#defining-sending-logs-extension}

L’estensione del registro di invio consente di:

* estensione delle funzionalità dei rapporti dinamici mediante l&#39; **aggiunta di campi personalizzati del profilo**
* per estendere i dati dei log di invio con il codice **del segmento e i dati di profilo**

**Estendi con un codice di segmento**

L’utente può estendere i registri con il codice del segmento proveniente dal motore del flusso di lavoro.

Il codice del segmento deve essere definito nel flusso di lavoro.

Per attivare questa estensione, selezionare l&#39;opzione **[!UICONTROL Add segment code]**.

![](assets/sendinglogsextension_1.png)

Per ulteriori informazioni sul codice del segmento, consulta la sezione [Segmentazione](../../automating/using/segmentation.md) .

**Estendi con un campo profilo**

>[!NOTE]
>
>L&#39;amministratore avrebbe dovuto estendere la risorsa Profilo con un campo personalizzato.

![](assets/sendinglogsextension_2.png)

Fate clic su **[!UICONTROL Add field]** e selezionate un campo personalizzato dalla risorsa del profilo.

Per generare una nuova dimensione secondaria collegata alla dimensione Profilo, selezionate l’ **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** opzione.

![](assets/sendinglogsextension_3.png)

Da Generazione di rapporti dinamici, puoi trascinare la dimensione del campo personalizzato in una tabella a forma libera.

Per ulteriori informazioni su Dynamic Reporting (Generazione di rapporti dinamica), consultare l&#39; [Elenco dei componenti](../../reporting/using/list-of-components-.md).

>[!IMPORTANT]
>
>Il numero di campi inviati a Dynamic Reporting è limitato a 20.

## Modifica delle proprietà delle risorse {#editing-resource-properties}

Nella schermata delle risorse personalizzate, il **[!UICONTROL Summary]** riquadro indica lo stato della risorsa appena creata. È possibile gestire il relativo accesso e le relative proprietà generali.

![](assets/schema_extension_3.png)

1. Fate clic sul **[!UICONTROL Edit properties]** pulsante per aggiungere una descrizione.

   ![](assets/schema_extension_30.png)

1. Se necessario, modificate l’etichetta e l’ID della risorsa.

   >[!NOTE]
   >
   >Utilizzate un massimo di 30 caratteri.

1. Se è necessario limitare l&#39;accesso a questa risorsa a determinate unità organizzative, specificatele qui. Solo gli utenti di unità autorizzate potranno lavorare con questa risorsa nell&#39;applicazione.
1. Salvare le modifiche.

Le modifiche vengono salvate. Per applicarle, è necessario pubblicare di nuovo la risorsa.

## Generazione di un ID univoco per profili e risorse personalizzate {#generating-a-unique-id-for-profiles-and-custom-resources}

Per impostazione predefinita, i profili e le risorse personalizzate non dispongono di ID business al momento della creazione. Potete abilitare un&#39;opzione che genera automaticamente un ID univoco al momento della creazione degli elementi. Questo ID può essere utilizzato per:

* Identificare facilmente i record esportati in uno strumento esterno.
* Riconciliare i record durante l&#39;importazione di dati aggiornati elaborati in un&#39;altra applicazione.

Può essere abilitata solo per profili e risorse personalizzate.

1. Create un&#39;estensione alla risorsa dei profili o create una nuova risorsa.
1. Nella definizione della struttura dati, selezionare l&#39; **[!UICONTROL Add automatic ID field]** opzione, nella **[!UICONTROL Fields]** sezione.

   ![](assets/option_id_field.png)

   >[!NOTE]
   >
   >Solo i nuovi record avranno un ID ACS. Il **[!UICONTROL ACS ID]** campo rimarrà vuoto per i profili o gli elementi creati prima di attivare questa opzione.

1. Salvate e pubblicate le modifiche apportate alla risorsa. Se desiderate che questo meccanismo venga applicato agli elementi creati tramite l&#39;API, verificate l&#39;opzione per estendere l&#39;API.

Il **[!UICONTROL ACS ID]** campo è ora disponibile e popolato automaticamente quando nuovi elementi vengono creati manualmente, dall&#39;API o inseriti da un flusso di lavoro di importazione. Il campo ID ACS è un campo UUID ed è indicizzato.

Quando si esportano profili o risorse personalizzate, è ora possibile aggiungere la **[!UICONTROL ACS ID]** colonna se è stata attivata per tale risorsa. Puoi riutilizzare questo ID nei tuoi strumenti esterni per identificare i record.

![](assets/export_id_field.png)

Quando reimportate dati elaborati o aggiornati in un&#39;altra applicazione (ad esempio un CRM), potete facilmente riconciliarli con questo ID univoco.

>[!NOTE]
>
>Il **[!UICONTROL ACS ID]** campo non viene aggiornato per i profili o gli elementi creati prima di abilitare l&#39;opzione. Solo i nuovi record avranno un ID ACS.
>
>Questo campo è in modalità di sola lettura. Non potete modificarlo.
