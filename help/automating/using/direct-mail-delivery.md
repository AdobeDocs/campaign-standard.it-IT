---
title: Direct mail delivery
description: L’attività Direct mail delivery ti consente di configurare l’invio di una direct mailing singola o ricorrente in un flusso di lavoro.
page-status-flag: never-activated
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 99%

---


# Direct mail delivery{#direct-mail-delivery}

## Descrizione {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

L’attività **[!UICONTROL Direct mail delivery]** ti consente di configurare e preparare un file contenente i dati di profilo che desideri utilizzare per una campagna di direct mailing. Può trattarsi di una direct mailing utilizzata una sola volta, o di una direct mailing ricorrente.

* **Le direct mailing standard vengono inviate una volta.**
* **Le mail ricorrenti ti consentono di inviare la stessa direct mailing più volte a destinazioni diverse in un determinato periodo di tempo.** Puoi aggregare le consegne per periodo in modo da ottenere report che corrispondano alle tue esigenze.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Direct mail delivery]** viene generalmente utilizzata per automatizzare la preparazione di un file che contiene dati di profilo. Questo file può quindi essere inviato a un partner/fornitore incaricato della spedizione.

Se collegata a una pianificazione, ti consente di definire direct mailing ricorrenti.

I destinatari delle direct mailing sono definiti a monte dell’attività nello stesso flusso di lavoro tramite attività di targeting come query, intersezioni, ecc. I profili il cui indirizzo di posta non è specificato vengono automaticamente esclusi durante la preparazione della direct mailing.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

**Argomenti correlati:**

* [Caso di utilizzo: Accoppiamento delle consegne e-mail e della posta diretta](../../automating/using/coupling-email-direct-mail.md)
* [Informazioni sulla direct mailing](../../channels/using/about-direct-mail.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Direct mail delivery]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività. Questo pulsante è specifico per le attività del canale. Le proprietà della direct mailing sono accessibili tramite la barra delle azioni nel dashboard direct mailing.

1. Seleziona la modalità di invio della direct mailing:

   * **[!UICONTROL Direct mail]**: la direct mailing viene inviata una sola volta. Puoi specificare qui se desideri aggiungere o meno una transizione in uscita all’attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring direct mail]**: la direct mailing viene inviata diverse volte, in base alla frequenza definita in un’attività **[!UICONTROL Scheduler]**. Seleziona il periodo di aggregazione degli invii. Ciò ti consente di raggruppare tutti gli invii che avvengono durante il periodo definito in un’unica direct mailing, denominata anche **Esecuzione ricorrente**, e a cui è possibile accedere dall’elenco delle attività di marketing dell’applicazione.

      Ad esempio, per una mail di compleanno ricorrente, elaborata ogni giorno, puoi scegliere di aggregare gli invii al mese. Ciò ti consente di ricevere report sulla consegna su base mensile, anche se la mail viene elaborata ogni giorno.

      >[!NOTE]
      >
      >Per le direct mailing ricorrenti, viene generato un nuovo file a ogni esecuzione del flusso di lavoro. Il periodo di aggregazione selezionato non ha alcun impatto su questo comportamento.

1. Seleziona un tipo di direct mailing. I tipi di direct mailing provengono dai modelli definiti nel menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Immetti le proprietà generali per la direct mailing. Puoi anche allegarla a una campagna esistente. L’etichetta dell’attività di consegna del flusso di lavoro viene aggiornata con l’etichetta direct mailing.
1. Definisci il contenuto della direct mailing. Consulta la sezione relativa alla [modifica dei contenuti](../../designing/using/personalization.md).
1. Per impostazione predefinita, l’attività **[!UICONTROL Direct mail delivery]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL Direct mail delivery]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata. Questa transizione contiene il file generato dall’attività di direct mailing e la popolazione non elaborata ricevuta dall’attività di direct mailing.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui verrà inviata la direct mailing. I membri della destinazione esclusi durante la preparazione della direct mailing (quarantena, indirizzo non valido, ecc.) sono esclusi da questa transizione. La transizione contiene inoltre il file generato dalla direct mailing.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riapri l’attività, accedi direttamente alla dashboard direct mailing. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo della direct mailing ti consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna principale in caso di direct mailing ricorrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

Le esecuzioni delle consegne ricorrenti sono nascoste per impostazione predefinita. Per visualizzarle, seleziona l’opzione **[!UICONTROL Show recurring executions]** nel pannello di ricerca delle attività di marketing.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

Nelle consegne principali, accessibili dall’elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, puoi visualizzare il numero totale di mail che sono state elaborate (in base al periodo di aggregazione specificato al momento della configurazione dell’attività **[!UICONTROL Direct mail delivery]**). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando il pulsante ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)
