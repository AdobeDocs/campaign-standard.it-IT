---
title: Consegna SMS
description: L'attività di consegna SMS consente di configurare l'invio di un SMS singolo o ricorrente in un flusso di lavoro.
page-status-flag: never-activated
uuid: 736078c6-ac91-4440-825b-4a6ae31894ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 978592b8-989a-446a-8a84-12b7fecfc130
context-tags: sms,main;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 0%

---


# Consegna SMS{#sms-delivery}

## Descrizione {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

L&#39; **[!UICONTROL SMS delivery]** attività consente di configurare l&#39;invio di un SMS in un flusso di lavoro. Può trattarsi di un **singolo SMS inviato** e inviato solo una volta, o può essere un SMS **ricorrente** .

I singoli messaggi SMS inviati sono SMS standard, inviati una volta.

I messaggi SMS ricorrenti consentono di inviare gli stessi SMS più volte a destinazioni diverse in un determinato periodo di tempo. È possibile aggregare le consegne per periodo al fine di ottenere rapporti che corrispondano alle proprie esigenze.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL SMS delivery]** attività viene generalmente utilizzata per automatizzare l&#39;invio di un SMS a una destinazione calcolata nello stesso flusso di lavoro.

Se collegato a un pianificatore, puoi definire messaggi SMS ricorrenti.

I destinatari di SMS sono definiti a monte dell&#39;attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l&#39;invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un&#39;attività pianificatore nel flusso di lavoro per automatizzare l&#39;esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL SMS delivery]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell&#39;attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante nella barra delle azioni del flusso di lavoro. Questo pulsante è specifico per l&#39; **[!UICONTROL SMS delivery]** attività. Le proprietà SMS sono accessibili tramite la barra delle azioni nel dashboard SMS.

1. Selezionate la modalità di invio SMS:

   * **[!UICONTROL SMS]**: l&#39;SMS viene inviato una sola volta. Potete specificare qui se desiderate aggiungere o meno una transizione in uscita all&#39;attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring SMS]**: l&#39;SMS viene inviato più volte, in base alla frequenza definita in un&#39; **[!UICONTROL Scheduler]** attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di raggruppare tutte le invii che si verificano durante il periodo definito in un&#39;unica visualizzazione, denominata anche esecuzione **** ricorrente, a cui è possibile accedere dall&#39;elenco delle attività di marketing dell&#39;applicazione.

      Ad esempio, per un SMS di compleanno periodico, inviato ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla vostra consegna su base mensile, anche se l&#39;SMS viene inviato ogni giorno.

1. Selezionare un tipo di SMS. I tipi di SMS provengono dai modelli SMS definiti in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** menu.
1. Immettere le proprietà generali dell&#39;SMS. Potete anche allegarlo a una campagna esistente. L&#39;etichetta dell&#39;attività di consegna del flusso di lavoro viene aggiornata con l&#39;etichetta SMS.
1. Definite il contenuto SMS. Consultare la sezione relativa alla [creazione di un messaggio](../../channels/using/creating-an-sms-message.md)SMS.
1. Per impostazione predefinita, l&#39; **[!UICONTROL SMS delivery]** attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all&#39; **[!UICONTROL SMS delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell&#39;attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato l&#39;SMS. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, numero non valido, ecc.) sono escluse da questa transizione.

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

Quando riaprite l&#39;attività, viene portata direttamente al dashboard SMS. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L&#39;invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l&#39;avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l&#39; **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all&#39;interno di un flusso di lavoro sono accessibili nell&#39;elenco delle attività di marketing dell&#39;applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo di SMS consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre in caso di SMS ricorrenti).

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. Per visualizzarli, seleziona l&#39; **[!UICONTROL Show recurring executions]** opzione nel pannello di ricerca delle attività di marketing.

Nelle consegne principali, a cui è possibile accedere dall&#39;elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell&#39; **[!UICONTROL SMS delivery]** attività). A tal fine, aprire la visualizzazione dettagli del **[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
