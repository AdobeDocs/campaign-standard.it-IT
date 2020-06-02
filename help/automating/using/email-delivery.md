---
title: Recapito e-mail
description: L'attività di distribuzione e-mail consente di configurare l'invio di un'e-mail singola o ricorrente in un flusso di lavoro.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6e87dc8f299f0c9fbb33e5e56c0a76cfef0aa9a6
workflow-type: tm+mt
source-wordcount: '993'
ht-degree: 0%

---


# Recapito e-mail{#email-delivery}

## Descrizione {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

L&#39; **[!UICONTROL Email delivery]** attività consente di configurare l&#39;invio di un&#39;e-mail in un flusso di lavoro. Può trattarsi di un&#39;e-mail di invio **** singolo e inviata una sola volta, oppure di un&#39;e-mail **ricorrente** .

Le e-mail singole sono e-mail standard, inviate una volta.

Le e-mail ricorrenti consentono di inviare la stessa e-mail più volte a destinazioni diverse in un determinato periodo di tempo. È possibile aggregare le consegne per periodo al fine di ottenere rapporti che corrispondano alle proprie esigenze.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Email delivery]** attività viene in genere utilizzata per automatizzare l&#39;invio di un&#39;e-mail a una destinazione calcolata nello stesso flusso di lavoro.

Se collegato a un pianificatore, puoi definire e-mail ricorrenti.

I destinatari e-mail sono definiti a monte dell&#39;attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l&#39;invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un&#39;attività pianificatore nel flusso di lavoro per automatizzare l&#39;esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Email delivery]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell&#39;attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante dalle azioni rapide dell&#39;attività. Questo pulsante è specifico per l&#39; **[!UICONTROL Email delivery]** attività. Le proprietà dell’e-mail sono accessibili tramite la barra delle azioni nel dashboard e-mail.

1. Selezionate la modalità di invio e-mail:

   * **[!UICONTROL Email]**: l’e-mail viene inviata una sola volta. Potete specificare qui se desiderate aggiungere o meno una transizione in uscita all&#39;attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring email]**: l&#39;e-mail viene inviata più volte, in base alla frequenza definita in un&#39; **[!UICONTROL Scheduler]** attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di raggruppare tutte le invii che si verificano durante il periodo definito in un&#39;unica e-mail denominata anche esecuzione **** ricorrente e accessibile dall&#39;elenco delle attività di marketing dell&#39;applicazione.

      Ad esempio, per un&#39;e-mail di compleanno ricorrente, inviata ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla consegna mensile anche se l&#39;e-mail viene inviata ogni giorno.
   >[!NOTE]
   >
   >Le consegne ricorrenti vengono preparate in base al periodo **di** aggregazione. Ad esempio, se il periodo di aggregazione è &quot;per giorno&quot;, la consegna verrà preparata solo una volta al giorno. Se prevedete di chiamare questo flusso di lavoro più volte al giorno, utilizzate [!UICONTROL No aggregation].

1. Selezionate un tipo di e-mail. I tipi di e-mail sono ricavati dai modelli e-mail definiti nel menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** .
1. Immettete le proprietà generali del messaggio e-mail. Potete anche allegarlo a una campagna esistente. L&#39;etichetta dell&#39;attività di distribuzione del flusso di lavoro viene aggiornata con l&#39;etichetta e-mail.
1. Definite il contenuto dell’e-mail. Consultate la sezione sulla modifica dei [contenuti](../../designing/using/designing-content-in-adobe-campaign.md).
1. Per impostazione predefinita, l&#39; **[!UICONTROL Email delivery]** attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all&#39; **[!UICONTROL Email delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell&#39;attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: in questo modo potete generare una transizione in uscita contenente la popolazione a cui è stato inviato il messaggio e-mail. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, e-mail non valide, ecc.) sono escluse da questa transizione.

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

Quando riaprite l&#39;attività, viene portata direttamente alla dashboard e-mail. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L&#39;invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l&#39;avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l&#39; **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all&#39;interno di un flusso di lavoro sono accessibili nell&#39;elenco delle attività di marketing dell&#39;applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle e-mail consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre in caso di e-mail ricorrenti).

![](assets/wkf_display_recurrent_executions_2.png)

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. Per visualizzarli, seleziona l&#39; **[!UICONTROL Show recurring executions]** opzione nel pannello di ricerca delle attività di marketing.

![](assets/wkf_display_recurrent_executions.png)

Nelle consegne principali, a cui è possibile accedere dall&#39;elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell&#39; **[!UICONTROL Email delivery]** attività). A tal fine, aprire la visualizzazione dettagli del **[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Esempio {#example}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un&#39;email viene inviata a un profilo il cui compleanno è in quel giorno. Per eseguire questa operazione:

* Questo **[!UICONTROL Scheduler]** consente di avviare il flusso di lavoro ogni giorno alle 8 del mattino.

   ![](assets/wkf_delivery_example_2.png)

* L&#39; **[!UICONTROL Query]** attività consente di calcolare i profili che hanno fornito un&#39;e-mail e il cui compleanno è il giorno corrente, ogni volta che il flusso di lavoro viene eseguito. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

   ![](assets/wkf_delivery_example_3.png)

* Il **[!UICONTROL Email]** problema è ricorrente. Le mandate sono aggregate per mese. Pertanto, tutte le e-mail inviate in un mese vengono aggregate in una singola vista. In un anno, quindi, vengono eseguite 365 consegne, che vengono raggruppate in 12 viste (dette anche esecuzioni **** ricorrenti) nell&#39;interfaccia di Adobe Campaign. I dettagli della cronologia e del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_delivery_example_4.png)

**Argomenti correlati**

* [Caso di utilizzo: Creare una consegna di e-mail una volta alla settimana](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: Creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)