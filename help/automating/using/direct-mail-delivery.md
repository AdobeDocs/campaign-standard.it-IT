---
title: Spedizione diretta
seo-title: Spedizione diretta
description: Spedizione diretta
seo-description: L'attività di consegna diretta della posta consente di configurare l'invio di una singola e-mail di invio diretto o periodico in un flusso di lavoro.
page-status-flag: mai attivato
uuid: bfa7b176-a17c-4079-a073-64b8ce4788ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di canale
discoiquuid: b9ddb2a0-54ff-4ada-be6f-8109fa06d461
context-tags: directMail,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Spedizione diretta{#direct-mail-delivery}

## Descrizione {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

L' **[!UICONTROL Direct mail delivery]** attività consente di configurare e preparare un file contenente i dati del profilo che si desidera utilizzare per una campagna di posta diretta. Può trattarsi di una posta diretta utilizzata una sola volta, o di una posta diretta **ricorrente** .

Le e-mail dirette standard vengono inviate una volta.

Le e-mail ricorrenti consentono di inviare la stessa posta diretta più volte a destinazioni diverse in un determinato periodo di tempo. È possibile aggregare le consegne per periodo al fine di ottenere rapporti che corrispondano alle proprie esigenze.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Direct mail delivery]** attività viene in genere utilizzata per automatizzare la preparazione di un file che contiene dati di profilo. Questo file può essere inviato a un partner/fornitore incaricato della spedizione.

Se collegato a un pianificatore, potete definire e-mail dirette ricorrenti.

I destinatari della posta diretta sono definiti a monte dell'attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc. I profili il cui indirizzo di posta non è specificato vengono automaticamente esclusi durante la preparazione della posta diretta.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l'invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Direct mail delivery]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell'attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante dalle azioni rapide dell'attività. Questo pulsante è specifico per le attività del canale. È possibile accedere alle proprietà della posta diretta tramite la barra delle azioni nel dashboard della posta diretta.

1. Selezionate la modalità di invio della posta diretta:

   * **[!UICONTROL Direct mail]**: la posta diretta viene inviata una sola volta. Potete specificare qui se desiderate aggiungere o meno una transizione in uscita all'attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring direct mail]**: la posta diretta viene inviata più volte, in base alla frequenza definita in un' **[!UICONTROL Scheduler]** attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di raggruppare tutte le invii che si verificano durante il periodo definito in un'unica posta diretta denominata anche esecuzione **** ricorrente e a cui è possibile accedere dall'elenco delle attività di marketing dell'applicazione.

      Ad esempio, per un messaggio di compleanno periodico, elaborato ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla consegna mensile anche se la posta viene elaborata ogni giorno.

      >[!NOTE]
      >
      >Per le e-mail dirette ricorrenti, viene generato un nuovo file a ogni esecuzione del flusso di lavoro. Il periodo di aggregazione selezionato non ha alcun impatto su questo comportamento.

1. Selezionare un tipo di posta diretta. I tipi di posta diretta sono ricavati dai modelli definiti nel menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Immettere le proprietà generali per la posta diretta. Potete anche allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta di posta diretta.
1. Definire il contenuto della posta diretta. Consultate la sezione sulla modifica dei [contenuti](../../designing/using/personalization.md).
1. Per impostazione predefinita, l' **[!UICONTROL Direct mail delivery]** attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all' **[!UICONTROL Direct mail delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell'attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata. Questa transizione contiene il file generato dall'attività di posta diretta e dalla popolazione non elaborata ricevuta dall'attività di posta diretta.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui verrà inviata la posta diretta. I membri della destinazione esclusi durante la preparazione diretta per posta (quarantena, indirizzo non valido, ecc.) sono escluse da questa transizione. La transizione contiene anche il file generato dalla posta diretta.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, viene portata direttamente al dashboard della posta diretta. È possibile modificare solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L'invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l'avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l' **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo della posta diretta consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre in caso di posta diretta ricorrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

Per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. Per visualizzarli, seleziona l' **[!UICONTROL Show recurring executions]** opzione nel pannello di ricerca delle attività di marketing.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

Nelle consegne principali, a cui è possibile accedere dall'elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, è possibile visualizzare il numero totale di messaggi di posta elettronica che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell' **[!UICONTROL Direct mail delivery]** attività). A tal fine, aprire la visualizzazione dettagli del **[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Esempio {#example}

Un esempio **[!UICONTROL Direct mail delivery]** è disponibile nel capitolo [Posta](../../channels/using/example-of-direct-mail-in-a-workflow.md) diretta.
