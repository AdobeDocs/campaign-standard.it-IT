---
title: Creazione di un gruppo di controllo
description: Questo esempio di utilizzo mostra come creare un gruppo di controllo.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 73a91344ada17d6eb0da0335e08ea27a1019b4fb
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 14%

---


# Creazione di un gruppo di controllo {#building-control-group}

Per misurare l&#39;impatto di una consegna, potresti voler escludere alcuni profili dalla destinazione in modo che non ricevano un messaggio specifico. Questo gruppo di controllo può essere utilizzato per fare un confronto con il comportamento della popolazione di destinazione che ha ricevuto il messaggio.

Per eseguire questa operazione in  Adobe Campaign Standard, potete creare un flusso di lavoro che includa le seguenti attività:
* Un&#39;attività [Query](../../automating/using/query.md) per eseguire il targeting di una popolazione specifica.
* Un&#39;attività di [segmentazione](../../automating/using/segmentation.md) per isolare un gruppo di controllo casuale da questa popolazione.
* Un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail per inviare un messaggio alla destinazione principale.
* Un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) per aggiornare i profili esclusi dalla destinazione (il gruppo di controllo casuale).

![](assets/wkf_control-group.png)

## Estensione della risorsa Profilo {#extending-profile}

Innanzitutto, è necessario estendere la **[!UICONTROL Profile]** risorsa con un nuovo campo corrispondente al gruppo di controllo. Una volta eseguito il flusso di lavoro, questo campo viene controllato per individuare i profili esclusi dalla destinazione.

1. Da **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, fate clic su **[!UICONTROL Create]**.
1. Se non l’avete ancora esteso, selezionate **[!UICONTROL Extend an existing resource]** e scegliete la **[!UICONTROL Profile]** risorsa.
1. Nella **[!UICONTROL Data structure]** scheda, aggiungere un nuovo campo per il gruppo di controllo e selezionare **[!UICONTROL Boolean]** il campo **[!UICONTROL Type]** .

   ![](assets/wkf_control-group-profile-field.png)

1. Dalla **[!UICONTROL Screen definition]** scheda, aprire la **[!UICONTROL Detail screen configuration]** sezione e selezionare il campo appena creato in modo che venga visualizzato per ciascun profilo.

   ![](assets/wkf_control-group-profile-field-screen.png)

1. Salva le modifiche.
1. Aggiornate la struttura del database per pubblicare la risorsa **[!UICONTROL Profile]** estesa. See [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

Per ulteriori informazioni sull&#39;estensione di una risorsa personalizzata, consultate Procedura [chiave per aggiungere una risorsa](../../developing/using/key-steps-to-add-a-resource.md).

## Creazione di un flusso di lavoro {#creating-a-workflow}

1. In **[!UICONTROL Marketing Activities]**, fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL Workflow]**.
1. Seleziona **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fai clic su **[!UICONTROL Next]**.
1. Inserisci le proprietà del flusso di lavoro e fai clic su **[!UICONTROL Create]**.

I passaggi dettagliati per la creazione di un flusso di lavoro sono descritti nella sezione [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md).

## Creazione di un’attività query {#create-a-query-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, trascinate e rilasciate un&#39;attività [Query](../../automating/using/query.md) .
1. Fate doppio clic sull&#39;attività per definire la destinazione.
1. Ad esempio, in **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profile]**, selezionare **[!UICONTROL Age]** con l&#39;operatore **[!UICONTROL Greater than]** e digitare 25 nel **[!UICONTROL Value]** campo.
1. Fai clic su **[!UICONTROL Confirm]**.

## Creazione di un’attività di segmentazione {#creating-a-segmentation-activity}

1. Drag and drop a [Segmentation](../../automating/using/segmentation.md) activity and double-click it.
1. Nella **[!UICONTROL Segments]** scheda, seleziona un segmento da modificare.
1. Nella **[!UICONTROL Configuration]** scheda di quel segmento, selezionate l&#39; **[!UICONTROL Limit the population of this segment]** opzione.

   ![](assets/wkf_control-segment-configuration.png)

1. Nella **[!UICONTROL Limitation]** scheda, accertatevi che l&#39; **[!UICONTROL Random sampling]** opzione sia selezionata.

   ![](assets/wkf_control-segment-limitation.png)

1. Definire una percentuale della popolazione iniziale, ad esempio 10% e fare clic su **[!UICONTROL Confirm]**. Il gruppo di controllo sarà composto del 10% dalla popolazione interessata, selezionata in modo casuale.
1. Nella **[!UICONTROL Advanced options]** scheda, selezionare l&#39; **[!UICONTROL Generate complement]** opzione e compilare i campi **[!UICONTROL Transition label]** e **[!UICONTROL Segment code]** .

   ![](assets/wkf_control-segment-advanced.png)

1. Fai clic su **[!UICONTROL Confirm]**.

## Creating an Email activity {#creating-an-email-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, trascinate e rilasciate un&#39;attività di consegna [](../../automating/using/email-delivery.md) e-mail dopo il segmento di destinazione principale.
1. Click the activity and select ![](assets/edit_darkgrey-24px.png) to edit it.
1. Seleziona **[!UICONTROL Single send email]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di e-mail e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’e-mail e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’e-mail, fai clic su **[!UICONTROL Use the Email Designer]**.
1. Modifica e salva il contenuto.
1. Nella **[!UICONTROL Schedule]** sezione del dashboard dei messaggi, deseleziona l’ **[!UICONTROL Request confirmation before sending messages]** opzione.

## Creazione di un&#39;attività di aggiornamento dei dati {#creating-update-data-activity}

1. Trascinare e rilasciare un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) dopo il segmento del gruppo di controllo.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Nella **[!UICONTROL General]** scheda, selezionare **[!UICONTROL Update]** dall&#39;elenco a **[!UICONTROL Operation type]** discesa.
1. In the **[!UICONTROL Identification]** tab, select the **[!UICONTROL Directly using the targeting dimension]** option.
1. Selezionate la risorsa precedentemente **[!UICONTROL Profile]** estesa come dimensione da aggiornare.

   ![](assets/wkf_control-update-identification.png)

1. Nella **[!UICONTROL Fields to update]** scheda, selezionare come condizione il campo del gruppo di controllo aggiunto alla **[!UICONTROL Profile]** risorsa **[!UICONTROL Destination]** e immettere true.

   ![](assets/wkf_control-update-fields-to-update.png)

1. Fai clic su **[!UICONTROL Confirm]**.

## Esecuzione del flusso di lavoro {#running-the-workflow}

Fare clic **[!UICONTROL Start]** per eseguire il flusso di lavoro.

Una volta eseguito il flusso di lavoro, la popolazione del gruppo di controllo viene esclusa e il messaggio viene inviato alla destinazione principale rimanente.

La **[!UICONTROL Profile]** risorsa viene aggiornata come segue: se un profilo si trova nel gruppo di controllo, il campo corrispondente viene selezionato.

![](assets/wkf_control-group-profile-checked.png)

Ora puoi confrontare il modo in cui i destinatari del messaggio reagiranno rispetto al gruppo di dimensioni ridotte che è stato escluso dal messaggio e non lo ha ricevuto.

## Riutilizzo dello stesso gruppo di controllo {#reusing-same-control-group}

L&#39;esempio precedente consente di creare un gruppo di controllo globale, in quanto memorizzato come attributo di profilo indipendentemente dalle consegne. In effetti, il nuovo campo &quot;Gruppo di controllo&quot; creato come parte dell’estensione della **[!UICONTROL Profile]** risorsa viene aggiornato dopo l’esecuzione del flusso di lavoro precedente.

Di conseguenza, la prossima volta che si desidera utilizzare lo stesso gruppo di controllo, è possibile segmentare il nuovo campo &quot;Gruppo di controllo&quot; anziché eseguire una segmentazione casuale.

Per eseguire questa operazione:
1. Quando create l&#39; **[!UICONTROL Segmentation]** attività, selezionate il segmento da modificare nella **[!UICONTROL Segments]** scheda.
1. Nella **[!UICONTROL Configuration]** scheda di quel segmento, accertatevi di non selezionare l&#39; **[!UICONTROL Limit the population of this segment]** opzione.
1. Nella **[!UICONTROL Filtering]** scheda, trascinare fino **[!UICONTROL Profiles (attributes)]** all’area di lavoro principale.

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. Nella **[!UICONTROL Add a rule - Profiles (attributes)]** finestra, selezionate &quot;Gruppo di controllo&quot; (il campo aggiunto alla **[!UICONTROL Profile]** risorsa) e selezionate **[!UICONTROL Yes]** come condizione del filtro.

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)
