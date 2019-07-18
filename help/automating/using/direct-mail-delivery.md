---
title: Consegna posta diretta
seo-title: Consegna posta diretta
description: Consegna posta diretta
seo-description: L'attività di consegna Posta diretta consente di configurare l'invio di una posta diretta diretta o di una posta diretta ricorrente in un flusso di lavoro.
page-status-flag: never-activated
uuid: bfa 7 b 176-a 17 c -4079-a 073-64 b 8 ce 4788 ed
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: channel-activity
discoiquuid: b 9 ddb 2 a 0-54 ff -4 ada-be 6 f -8109 fa 06 d 461
context-tags: Directmail, workflow, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Direct mail delivery{#direct-mail-delivery}

## Description {#description}

![](assets/paper.png)

![](assets/recurrentpaper.png)

The **[!UICONTROL Direct mail delivery]** activity allows you to configure and prepare a file containing profile data that you want to use for a direct mail campaign. This can be a direct mail that is used just once, or it can be a **recurring** direct mail.

I messaggi diretti standard vengono inviati una volta.

I messaggi e-mail periodici consentono di inviare lo stesso direct mail più volte a destinazioni diverse in un determinato periodo di tempo. Puoi aggregare le consegne per periodo per ottenere rapporti che corrispondono alle tue esigenze.

## Context of use {#context-of-use}

The **[!UICONTROL Direct mail delivery]** activity is generally used to automate preparing a file that contains profile data. Questo file può essere inviato a un partner/fornitore incaricato della mailing list.

Se collegati a un pianificatore, potete definire e-mail dirette ricorrenti.

I destinatari di posta diretta vengono definiti a monte dell'attività nello stesso flusso di lavoro, mediante attività di targeting quali query, intersezioni ecc. I profili il cui indirizzo di posta non è specificato vengono automaticamente esclusi quando la posta diretta è preparata.

La preparazione del messaggio viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal pannello del messaggio, potete selezionare se richiedere o meno una conferma manuale per inviare il messaggio (richiesto per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente oppure inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Direct mail delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. Questo pulsante è specifico delle attività dei canali. Potete accedere alle proprietà della posta diretta tramite la barra delle azioni nel dashboard Direct Mail.

1. Selezionate la modalità di invio posta diretta:

   * **[!UICONTROL Direct mail]**: la posta diretta viene inviata una sola volta. Potete specificare qui se desiderate aggiungere una transizione in uscita all'attività. I diversi tipi di transizione sono descritti al punto 7 di questa procedura.
   * **[!UICONTROL Recurring direct mail]**: il messaggio diretto viene inviato più volte, a seconda della frequenza definita in un **[!UICONTROL Scheduler]** 'attività. Selezionare il periodo di aggregazione delle mandate. This allows you to regroup all the sends that occur during the defined period in one single direct mail that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Ad esempio, per una posta di compleanno ricorrente elaborata ogni giorno, potete scegliere di aggregare le mandate al mese. Questo consente di ricevere rapporti sulla distribuzione mensile, anche se il messaggio viene elaborato ogni giorno.

      >[!NOTE]
      >
      >Per le comunicazioni dirette ricorrenti, a ogni esecuzione del flusso di lavoro viene generato un nuovo file. Il periodo di aggregazione selezionato non ha alcun impatto su questo comportamento.

1. Selezionate un tipo di posta diretta. The direct mail types come from templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Inserite le proprietà generali della posta diretta. Potete allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta posta diretta.
1. Definite il contenuto di posta diretta. Refer to the section concerning [content editing](../../designing/using/about-personalization.md).
1. By default, the **[!UICONTROL Direct mail delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Direct mail delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: consente di generare una transizione in uscita contenente la stessa popolazione della transizione in ingresso. Questa transizione contiene il file generato dall'attività di posta diretta e dalla popolazione non elaborato ricevuta dall'attività posta diretta.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui verrà inviato il messaggio diretto. I membri della destinazione sono esclusi durante la preparazione diretta della posta (quarantena, indirizzo non valido, ecc.) sono esclusi da questa transizione. La transizione contiene anche il file generato dalla posta diretta.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, viene portato direttamente al dashboard Direct Mail. Solo il relativo contenuto può essere modificato.

Per impostazione predefinita, l'avvio di un flusso di lavoro di consegna attiva solo la preparazione del messaggio. L'invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo che il flusso di lavoro è stato avviato. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Remarks {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo Direct Mail consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre nel caso di una posta diretta ricorrente).

![](assets/wkf_display_parent_elements_direct_mail.png)

Per impostazione predefinita, le esecuzioni di consegne ricorrenti vengono mascherate. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions_direct_mail.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of mails that have been processed (according to the aggregation period specified when the **[!UICONTROL Direct mail delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3_direct_mail.png)

## Example {#example}

An example of **[!UICONTROL Direct mail delivery]** is available in the [Direct Mail](../../channels/using/example-of-direct-mail-in-a-workflow.md) chapter.
