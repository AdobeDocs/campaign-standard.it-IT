---
title: SMS delivery
description: L’attività SMS delivery consente di configurare l’invio di un SMS singolo o ricorrente in un flusso di lavoro.
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
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '784'
ht-degree: 100%

---


# SMS delivery{#sms-delivery}

## Descrizione {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

L’attività **[!UICONTROL SMS delivery]** consente di configurare l’invio di un SMS in un flusso di lavoro. Può trattarsi di un SMS singolo e inviato solo una volta o di un SMS ricorrente.

* **I messaggi SMS singoli sono SMS standard, inviati una sola volta.**
* **I messaggi SMS ricorrenti consentono di inviare lo stesso SMS più volte a destinazioni diverse in un determinato periodo di tempo.** Puoi aggregare le consegne per periodo in modo da ottenere report che corrispondano alle tue esigenze.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL SMS delivery]** viene generalmente utilizzata per automatizzare l’invio di un SMS a una destinazione calcolata nello stesso flusso di lavoro.

Se collegata a una pianificazione, ti consente di definire messaggi SMS ricorrenti.

I destinatari degli SMS sono definiti a monte dell’attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni, ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL SMS delivery]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) nella barra delle azioni del flusso di lavoro. Questo pulsante è specifico per l’attività **[!UICONTROL SMS delivery]**. Le proprietà dell’SMS sono accessibili tramite la barra delle azioni nel dashboard SMS.

1. Seleziona la modalità di invio dell’SMS:

   * **[!UICONTROL SMS]**: l’SMS viene inviato una sola volta. Puoi specificare qui se desideri aggiungere o meno una transizione in uscita all’attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring SMS]**: l’SMS viene inviato diverse volte, in base alla frequenza definita in un’attività **[!UICONTROL Scheduler]**. Seleziona il periodo di aggregazione degli invii. Ciò consente di raggruppare tutti gli invii che avvengono durante il periodo definito in un’unica vista, denominata anche **Esecuzione ricorrente**, a cui è possibile accedere dall’elenco delle attività di marketing dell’applicazione.

      Ad esempio, per un SMS di compleanno ricorrente, inviato ogni giorno, puoi scegliere di aggregare gli invii al mese. Ciò consente di ricevere report sulla consegna su base mensile, anche se l’SMS viene inviato ogni giorno.

1. Seleziona un tipo di SMS. I tipi di SMS provengono dai modelli SMS definiti nel menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Inserisci le proprietà generali dell’SMS. Puoi anche allegarlo a una campagna esistente. L’etichetta dell’attività di consegna del flusso di lavoro viene aggiornata con l’etichetta SMS.
1. Definisci il contenuto dell’SMS. Consulta la sezione relativa alla [Creazione di un messaggio SMS](../../channels/using/creating-an-sms-message.md).
1. Per impostazione predefinita, l’attività **[!UICONTROL SMS delivery]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL SMS delivery]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato l’SMS. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, numero non valido, ecc.) sono esclusi da questa transizione.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riapri l’attività, accedi direttamente al dashboard SMS. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo degli SMS ti consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna principale in caso di SMS ricorrenti).

Tuttavia, le esecuzioni delle consegne ricorrenti sono nascoste per impostazione predefinita. Per visualizzarle, seleziona l’opzione **[!UICONTROL Show recurring executions]** nel pannello di ricerca delle attività di marketing.

Nelle consegne principali, accessibili dall’elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, puoi visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell’attività **[!UICONTROL SMS delivery]**). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
