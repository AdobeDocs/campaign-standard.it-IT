---
title: Email delivery
description: L’attività Email delivery ti consente di configurare l’invio di un’e-mail singola o ricorrente in un flusso di lavoro.
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
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 94%

---


# Email delivery{#email-delivery}

## Descrizione {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

L’attività **[!UICONTROL Email delivery]** ti consente di configurare l’invio di un’e-mail in un flusso di lavoro. Può trattarsi di un’e-mail **singola** e inviata solo una volta o di un’e-mail **ricorrente**.

Le e-mail singole sono e-mail standard, inviate una sola volta.

Le e-mail ricorrenti ti consentono di inviare la stessa e-mail più volte a destinazioni diverse in un determinato periodo di tempo. Puoi aggregare le consegne per periodo in modo da ottenere report che corrispondano alle tue esigenze.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Email delivery]** viene generalmente utilizzata per automatizzare l’invio di un’e-mail a una destinazione calcolata nello stesso flusso di lavoro.

Se collegata a una pianificazione, ti consente di definire e-mail ricorrenti.

I destinatari delle e-mail sono definiti a monte dell’attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni, ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

**Argomenti correlati:**

* [Caso di utilizzo: creare una consegna e-mail settimanale](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: invio di una nuova consegna a non-opener tramite un flusso di lavoro di retargeting](../../automating/using/workflow-cross-channel-retargeting.md)
* [Caso di utilizzo: Consegna compleanno](../../automating/using/birthday-delivery.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Email delivery]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività. Questo pulsante è specifico per l’attività **[!UICONTROL Email delivery]**. Le proprietà dell’e-mail sono accessibili tramite la barra delle azioni nel dashboard e-mail.

1. Seleziona la modalità di invio dell’e-mail:

   * **[!UICONTROL Email]**: l’e-mail viene inviata una sola volta. Puoi specificare qui se desideri aggiungere o meno una transizione in uscita all’attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring email]**: l’e-mail viene inviata diverse volte, in base alla frequenza definita in un’attività **[!UICONTROL Scheduler]**. Seleziona il periodo di aggregazione degli invii. Ciò ti consente di raggruppare tutti gli invii che avvengono durante il periodo definito in un’unica e-mail, denominata anche **Esecuzione ricorrente**, e a cui è possibile accedere dall’elenco delle attività di marketing dell’applicazione.

      Ad esempio, per un’e-mail di compleanno ricorrente, inviata ogni giorno, puoi scegliere di aggregare gli invii al mese. Ciò ti consente di ricevere report sulla consegna su base mensile, anche se l’e-mail viene inviata ogni giorno.
   >[!NOTE]
   >
   >Le consegne ricorrenti vengono preparate in base al periodo **di** aggregazione. Ad esempio, se il periodo di aggregazione è &quot;per giorno&quot;, la consegna verrà preparata solo una volta al giorno. Se prevedete di chiamare questo flusso di lavoro più volte al giorno, utilizzate [!UICONTROL No aggregation].

1. Seleziona un tipo di e-mail. I tipi di e-mail provengono dai modelli e-mail definiti nel menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Immetti le proprietà generali per l’e-mail. Puoi anche allegarla a una campagna esistente. L’etichetta dell’attività di consegna del flusso di lavoro viene aggiornata con l’etichetta e-mail.
1. Definisci il contenuto dell’e-mail. Consulta la sezione relativa alla [modifica dei contenuti](../../designing/using/designing-content-in-adobe-campaign.md).
1. Per impostazione predefinita, l’attività **[!UICONTROL Email delivery]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL Email delivery]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stata inviata l’e-mail. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, e-mail non valida, ecc.) sono esclusi da questa transizione.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riapri l’attività, accedi direttamente al dashboard e-mail. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle e-mail ti consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna principale in caso di e-mail ricorrenti).

![](assets/wkf_display_recurrent_executions_2.png)

Tuttavia, le esecuzioni delle consegne ricorrenti sono nascoste per impostazione predefinita. Per visualizzarle, seleziona l’opzione **[!UICONTROL Show recurring executions]** nel pannello di ricerca delle attività di marketing.

![](assets/wkf_display_recurrent_executions.png)

Nelle consegne principali, accessibili dall’elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, puoi visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell’attività **[!UICONTROL Email delivery]**). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)
