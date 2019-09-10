---
title: Consegna SMS
seo-title: Consegna SMS
description: Consegna SMS
seo-description: L'attività di consegna SMS consente di configurare l'invio di un SMS singolo o di un SMS periodico in un flusso di lavoro.
page-status-flag: never-activated
uuid: 736078 c 6-ac 91-4440-825 b -4 a 6 ae 31894 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: channel-activity
discoiquuid: 978592 b 8-989 a -446 a -8 a 84-12 b 7 fecfc 130
context-tags: sms, main; delivery, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Consegna SMS{#sms-delivery}

## Descrizione {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

L' **[!UICONTROL SMS delivery]** attività consente di configurare l'invio di un SMS in un flusso di lavoro. Può trattarsi di **un singolo SMS inviato** e inviato una volta, oppure può essere un **SMS ricorrente** .

I messaggi SMS singolo sono SMS standard, inviati una volta.

I messaggi SMS ricorrenti consentono di inviare lo stesso SMS più volte a destinazioni diverse in un determinato periodo di tempo. Puoi aggregare le consegne per periodo per ottenere rapporti che corrispondono alle tue esigenze.

## Contesto di utilizzo {#context-of-use}

L **[!UICONTROL SMS delivery]** 'attività viene utilizzata in genere per automatizzare l'invio di SMS a una destinazione calcolata nello stesso flusso di lavoro.

Se collegati a un pianificatore, puoi definire messaggi SMS ricorrenti.

I destinatari SMS vengono definiti a monte dell'attività nello stesso flusso di lavoro, mediante attività di targeting quali query, intersezioni ecc.

La preparazione del messaggio viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal pannello del messaggio, potete selezionare se richiedere o meno una conferma manuale per inviare il messaggio (richiesto per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente oppure inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configurazione {#configuration}

1. Trascina un **[!UICONTROL SMS delivery]** 'attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante dalle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell'attività (e non della distribuzione stessa) tramite ![](assets/dlv_activity_params-24px.png) il pulsante nella barra delle azioni del flusso di lavoro. Questo pulsante è specifico dell' **[!UICONTROL SMS delivery]** attività. Le proprietà SMS sono accessibili tramite la barra delle azioni nel dashboard SMS.

1. Selezionate la modalità di invio SMS:

   * **[!UICONTROL SMS]**: l'SMS viene inviato una sola volta. Potete specificare qui se desiderate aggiungere una transizione in uscita all'attività. I diversi tipi di transizione sono descritti al punto 7 di questa procedura.
   * **[!UICONTROL Recurring SMS]**: il SMS viene inviato più volte, a seconda della frequenza definita in un **[!UICONTROL Scheduler]** 'attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di rigenerare tutte le invii che si verificano durante il periodo definito in una sola visualizzazione denominata **Esecuzione ricorrente** e accessibili dall'elenco delle attività di marketing dell'applicazione.

      Ad esempio, per un SMS ricorrente che viene inviato ogni giorno, potete scegliere di aggregare le mandate al mese. Questo consente di ricevere ogni giorno rapporti sulla distribuzione, anche se l'SMS viene inviato ogni giorno.

1. Selezionate un tipo di SMS. I tipi SMS provengono dai modelli SMS definiti nel menu **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** .
1. Immettete le proprietà generali dell'SMS. Potete allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta SMS.
1. Definire il contenuto SMS. Fare riferimento alla sezione [relativa alla creazione di un messaggio SMS](../../channels/using/creating-an-sms-message.md).
1. Per impostazione predefinita, l **[!UICONTROL SMS delivery]** 'attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all' **[!UICONTROL SMS delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell'attività), quindi controllate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: consente di generare una transizione in uscita contenente la stessa popolazione della transizione in ingresso.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato l'SMS. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, numero non valido, ecc.) sono esclusi da questa transizione.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, verrete indirizzati direttamente al dashboard SMS. Solo il relativo contenuto può essere modificato.

Per impostazione predefinita, l'avvio di un flusso di lavoro di consegna attiva solo la preparazione del messaggio. L'invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo che il flusso di lavoro è stato avviato. Tuttavia, dal pannello del messaggio, e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l' **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Commenti {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo SMS consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre nel caso di SMS periodico).

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. Per visualizzarle, controllate l' **[!UICONTROL Show recurring executions]** opzione nel pannello di ricerca delle attività di marketing.

Nelle consegne principali, accessibili dall'elenco delle attività di marketing o direttamente tramite le esecuzioni ricorrenti associate, potete visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato quando l' **[!UICONTROL SMS delivery]** attività è stata configurata). A tal fine, apri la visualizzazione Dettagli del **[!UICONTROL Deployment]** blocco della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

## Esempio {#example}

![](assets/wkf_sms_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno viene inviato un SMS a profili il cui compleanno si trova in quel giorno. A tal fine:

* Consente **[!UICONTROL Scheduler]** di avviare il flusso di lavoro ogni giorno alle 8.

   ![](assets/wkf_delivery_example_2.png)

* L' **[!UICONTROL Query]** attività consente di calcolare i profili che hanno fornito un numero di telefono mobile e il cui compleanno si trova nel giorno corrente, ogni volta che viene eseguito il flusso di lavoro. Il calcolo di compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica query.

   ![](assets/wkf_delivery_example_3.png)

* The **[!UICONTROL SMS]** recurring. Le mandate vengono aggregate per mese. Pertanto, tutti i messaggi SMS inviati in un mese vengono aggregati in una sola visualizzazione. In un anno, sono quindi eseguite 365 consegne, ma vengono suddivise in 12 visualizzazioni (dette **anche esecuzioni ricorrenti**) nell'interfaccia di Adobe Campaign. La cronologia e i dettagli del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_sms_example_4.png)

Per un altro esempio di consegna SMS in un flusso di lavoro, consultate [Casi d'uso: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md).
