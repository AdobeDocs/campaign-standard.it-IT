---
title: Consegna SMS
description: L'attività di consegna SMS consente di configurare l'invio di un SMS singolo o ricorrente in un flusso di lavoro.
page-status-flag: mai attivato
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di canale
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,principale;consegna,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Consegna SMS{#sms-delivery}

## Descrizione {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

L' **[!UICONTROL SMS delivery]** attività consente di configurare l'invio di un SMS in un flusso di lavoro. Può trattarsi di un **singolo SMS inviato** e inviato solo una volta, o può essere un SMS **ricorrente** .

I singoli messaggi SMS inviati sono SMS standard, inviati una volta.

I messaggi SMS ricorrenti consentono di inviare gli stessi SMS più volte a destinazioni diverse in un determinato periodo di tempo. È possibile aggregare le consegne per periodo al fine di ottenere rapporti che corrispondano alle proprie esigenze.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL SMS delivery]** attività viene generalmente utilizzata per automatizzare l'invio di un SMS a una destinazione calcolata nello stesso flusso di lavoro.

Se collegato a un pianificatore, puoi definire messaggi SMS ricorrenti.

I destinatari di SMS sono definiti a monte dell'attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l'invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL SMS delivery]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell'attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante nella barra delle azioni del flusso di lavoro. Questo pulsante è specifico per l' **[!UICONTROL SMS delivery]** attività. Le proprietà SMS sono accessibili tramite la barra delle azioni nel dashboard SMS.

1. Selezionate la modalità di invio SMS:

   * **[!UICONTROL SMS]**: l'SMS viene inviato una sola volta. Potete specificare qui se desiderate aggiungere o meno una transizione in uscita all'attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring SMS]**: l'SMS viene inviato più volte, in base alla frequenza definita in un' **[!UICONTROL Scheduler]** attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di raggruppare tutte le invii che si verificano durante il periodo definito in un'unica visualizzazione, denominata anche esecuzione **** ricorrente, a cui è possibile accedere dall'elenco delle attività di marketing dell'applicazione.

      Ad esempio, per un SMS di compleanno periodico, inviato ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla vostra consegna su base mensile, anche se l'SMS viene inviato ogni giorno.

1. Selezionare un tipo di SMS. I tipi di SMS provengono dai modelli SMS definiti in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Immettere le proprietà generali dell'SMS. Potete anche allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta SMS.
1. Definire il contenuto SMS. Consultare la sezione relativa alla [creazione di un messaggio](../../channels/using/creating-an-sms-message.md)SMS.
1. Per impostazione predefinita, l' **[!UICONTROL SMS delivery]** attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all' **[!UICONTROL SMS delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell'attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato l'SMS. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, numero non valido, ecc.) sono escluse da questa transizione.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, viene portata direttamente al dashboard SMS. È possibile modificare solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L'invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l'avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l' **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo di SMS consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre in caso di SMS ricorrenti).

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. Per visualizzarli, seleziona l' **[!UICONTROL Show recurring executions]** opzione nel pannello di ricerca delle attività di marketing.

Nelle consegne principali, a cui è possibile accedere dall'elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell' **[!UICONTROL SMS delivery]** attività). A tal fine, aprire la visualizzazione dettagli del **[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

## Esempio {#example}

![](assets/wkf_sms_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un SMS viene inviato a un profilo il cui compleanno è in quel giorno. Per eseguire questa operazione:

* Questo **[!UICONTROL Scheduler]** consente di avviare il flusso di lavoro ogni giorno alle 8 del mattino.

   ![](assets/wkf_delivery_example_2.png)

* L' **[!UICONTROL Query]** attività consente di calcolare i profili che hanno fornito un numero di telefono cellulare e il cui compleanno è il giorno corrente, ogni volta che il flusso di lavoro viene eseguito. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

   ![](assets/wkf_delivery_example_3.png)

* Il **[!UICONTROL SMS]** problema è ricorrente. Le mandate sono aggregate per mese. Tutti gli SMS inviati in un mese vengono quindi aggregati in una singola vista. In un anno, vengono quindi eseguite 365 consegne, che vengono raggruppate in 12 viste (dette anche esecuzioni **** ricorrenti) nell'interfaccia di Adobe Campaign. I dettagli della cronologia e del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_sms_example_4.png)

Per un altro esempio di invio di SMS in un flusso di lavoro, consultate Caso di [utilizzo: Workflow di retargeting che invia una nuova distribuzione a non-openers](../../automating/using/workflow-cross-channel-retargeting.md).
