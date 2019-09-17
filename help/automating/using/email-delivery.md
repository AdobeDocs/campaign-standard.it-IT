---
title: Invio e-mail
seo-title: Invio e-mail
description: Invio e-mail
seo-description: L'attività di distribuzione e-mail consente di configurare l'invio di un'e-mail singola o ricorrente in un flusso di lavoro.
page-status-flag: mai attivato
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di canale
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: consegna,flusso di lavoro,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Invio e-mail{#email-delivery}

## Descrizione {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

L' **[!UICONTROL Email delivery]** attività consente di configurare l'invio di un'e-mail in un flusso di lavoro. Può trattarsi di un'e-mail di invio **** singolo e inviata una sola volta, oppure di un'e-mail **ricorrente** .

Le e-mail singole sono e-mail standard, inviate una volta.

Le e-mail ricorrenti consentono di inviare la stessa e-mail più volte a destinazioni diverse in un determinato periodo di tempo. È possibile aggregare le consegne per periodo al fine di ottenere rapporti che corrispondano alle proprie esigenze.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Email delivery]** attività viene in genere utilizzata per automatizzare l'invio di un'e-mail a una destinazione calcolata nello stesso flusso di lavoro.

Se collegato a un pianificatore, puoi definire e-mail ricorrenti.

I destinatari e-mail sono definiti a monte dell'attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l'invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Email delivery]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell'attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante dalle azioni rapide dell'attività. Questo pulsante è specifico per l' **[!UICONTROL Email delivery]** attività. Le proprietà dell’e-mail sono accessibili tramite la barra delle azioni nel dashboard e-mail.

1. Selezionate la modalità di invio e-mail:

   * **[!UICONTROL Email]**: l’e-mail viene inviata una sola volta. Potete specificare qui se desiderate aggiungere o meno una transizione in uscita all'attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring email]**: l'e-mail viene inviata più volte, in base alla frequenza definita in un' **[!UICONTROL Scheduler]** attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di raggruppare tutte le invii che si verificano durante il periodo definito in un'unica e-mail denominata anche esecuzione **** ricorrente e accessibile dall'elenco delle attività di marketing dell'applicazione.

      Ad esempio, per un'e-mail di compleanno ricorrente, inviata ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla consegna mensile anche se l'e-mail viene inviata ogni giorno.

1. Selezionate un tipo di e-mail. I tipi di e-mail sono ricavati dai modelli e-mail definiti nel menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Immettete le proprietà generali del messaggio e-mail. Potete anche allegarlo a una campagna esistente. L'etichetta dell'attività di distribuzione del flusso di lavoro viene aggiornata con l'etichetta e-mail.
1. Definite il contenuto dell’e-mail. Consultate la sezione sulla modifica dei [contenuti](../../designing/using/overview.md).
1. Per impostazione predefinita, l' **[!UICONTROL Email delivery]** attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all' **[!UICONTROL Email delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell'attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato il messaggio e-mail. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, e-mail non valide, ecc.) sono escluse da questa transizione.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, viene portata direttamente alla dashboard e-mail. È possibile modificare solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L'invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l'avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l' **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro del riepilogo delle e-mail consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre in caso di e-mail ricorrenti).

![](assets/wkf_display_recurrent_executions_2.png)

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. Per visualizzarli, seleziona l' **[!UICONTROL Show recurring executions]** opzione nel pannello di ricerca delle attività di marketing.

![](assets/wkf_display_recurrent_executions.png)

Nelle consegne principali, a cui è possibile accedere dall'elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell' **[!UICONTROL Email delivery]** attività). A tal fine, aprire la visualizzazione dettagli del **[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Esempio {#example}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un'email viene inviata a un profilo il cui compleanno è in quel giorno. Per eseguire questa operazione:

* Questo **[!UICONTROL Scheduler]** consente di avviare il flusso di lavoro ogni giorno alle 8 del mattino.

   ![](assets/wkf_delivery_example_2.png)

* L' **[!UICONTROL Query]** attività consente di calcolare i profili che hanno fornito un'e-mail e il cui compleanno è il giorno corrente, ogni volta che il flusso di lavoro viene eseguito. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

   ![](assets/wkf_delivery_example_3.png)

* Il **[!UICONTROL Email]** problema è ricorrente. Le mandate sono aggregate per mese. Pertanto, tutte le e-mail inviate in un mese vengono aggregate in una singola vista. In un anno, vengono quindi eseguite 365 consegne, che vengono raggruppate in 12 viste (dette anche esecuzioni **** ricorrenti) nell'interfaccia di Adobe Campaign. I dettagli della cronologia e del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_delivery_example_4.png)

**Argomenti correlati**

* [Caso di utilizzo: Creare una consegna di e-mail una volta alla settimana](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: Creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)