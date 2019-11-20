---
title: '"Workflow use-case: Gruppo di controllo"'
seo-title: '"Workflow use-case: Gruppo di controllo"'
description: '"Workflow use-case: Gruppo di controllo"'
seo-description: '"Workflow use-case: Gruppo di controllo"'
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
source-git-commit: 2912e3b75b817347b832f9c89ca2320868cbc355

---


# Caso di utilizzo del flusso di lavoro: Creazione di un gruppo di controllo {#building-control-group}

Per misurare l'impatto di una consegna, potresti voler escludere alcuni profili dalla destinazione in modo che non ricevano un messaggio specifico. Questo gruppo di controllo può essere utilizzato per fare un confronto con il comportamento della popolazione di destinazione che ha ricevuto il messaggio.

A tal fine, in Adobe Campaign Standard, puoi creare un flusso di lavoro che include le seguenti attività:
* Un'attività di query per eseguire il targeting di una determinata popolazione.
* Un'attività di segmentazione per isolare un gruppo di controllo casuale da questa popolazione.
* Un'attività di consegna tramite e-mail per inviare un messaggio alla destinazione principale.
* Un'attività di aggiornamento dei dati per aggiornare i profili esclusi dalla destinazione (il gruppo di controllo casuale).

![](assets/wkf_control-group.png)

## Estensione della risorsa Profilo {#extending-profile}

Innanzitutto, è necessario estendere la **[!UICONTROL Profile]** risorsa con un nuovo campo corrispondente al gruppo di controllo. Una volta eseguito il flusso di lavoro, questo campo viene controllato per individuare i profili esclusi dalla destinazione.

1. Da **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, fate clic su **[!UICONTROL Create]**.
1. Se non lo avete ancora esteso, selezionate **[!UICONTROL Extend an existing resource]** e scegliete la **[!UICONTROL Profile]** risorsa.
1. Nella **[!UICONTROL Data structure]** scheda, aggiungere un nuovo campo per il gruppo di controllo e selezionare **[!UICONTROL Boolean]** il campo **[!UICONTROL Type]** .

   ![](assets/wkf_control-group-profile-field.png)

1. Dalla **[!UICONTROL Screen definition]** scheda, aprire la **[!UICONTROL Detail screen configuration]** sezione e selezionare il campo appena creato in modo che venga visualizzato per ciascun profilo.

   ![](assets/wkf_control-group-profile-field-screen.png)

1.  Salvare le modifiche.
1. Aggiornate la struttura del database per pubblicare la risorsa **[!UICONTROL Profile]** estesa. Consultate [Pubblicazione di una risorsa](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizzata.

Per ulteriori informazioni sull'estensione di una risorsa personalizzata, consultate Procedura [chiave per aggiungere una risorsa](../../developing/using/key-steps-to-add-a-resource.md).

## Creazione di un flusso di lavoro {#creating-a-workflow}

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

I passaggi dettagliati per creare un flusso di lavoro sono descritti nella sezione [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md) .

## Creazione di un'attività Query {#create-a-query-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, trascina e rilascia un **[!UICONTROL Query activity]**.
1. Fate doppio clic sull'attività per definire la destinazione.
1. Ad esempio, in **[!UICONTROL Shortcuts]**, trascinare **[!UICONTROL Profile]**, selezionare **[!UICONTROL Age]** con l'operatore **[!UICONTROL Greater than]** e digitare 25 nel **[!UICONTROL Value]** campo.
1. Click **[!UICONTROL Confirm]**.

I passaggi dettagliati per creare un'attività Query sono descritti nella sezione [Query](../../automating/using/query.md) .

## Creazione di un'attività di segmentazione {#creating-a-segmentation-activity}

1. Trascinate e rilasciate un' **[!UICONTROL Segmentation]** attività e fate doppio clic su di essa.
1. Nella **[!UICONTROL Segments]** scheda, seleziona un segmento da modificare.
1. Nella **[!UICONTROL Configuration]** scheda di quel segmento, selezionate l' **[!UICONTROL Limit the population of this segment]** opzione.

   ![](assets/wkf_control-segment-configuration.png)

1. Nella **[!UICONTROL Limitation]** scheda, accertatevi che l' **[!UICONTROL Random sampling]** opzione sia selezionata.

   ![](assets/wkf_control-segment-limitation.png)

1. Definire una percentuale della popolazione iniziale, ad esempio 10% e fare clic su **[!UICONTROL Confirm]**. Il gruppo di controllo sarà composto del 10% dalla popolazione interessata, selezionata in modo casuale.
1. Nella **[!UICONTROL Advanced options]** scheda, selezionare l' **[!UICONTROL Generate complement]** opzione e compilare i campi **[!UICONTROL Transition label]** e **[!UICONTROL Segment code]** .

   ![](assets/wkf_control-segment-advanced.png)

1. Click **[!UICONTROL Confirm]**.

I passaggi dettagliati per creare un'attività di segmentazione sono descritti nella sezione [Segmentazione](../../automating/using/segmentation.md) .

## Creazione di un'attività e-mail {#creating-an-email-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, trascinate e rilasciate un elemento **[!UICONTROL Email Delivery]** dopo il segmento di destinazione principale.
1. Fate clic sull'attività e selezionate ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Selezionate **[!UICONTROL Single send email]** e fate clic su **[!UICONTROL Next]**.
1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, fate clic su **[!UICONTROL Use the Email Designer]**.
1. Modificate e salvate il contenuto.
1. Nella **[!UICONTROL Schedule]** sezione del dashboard dei messaggi, deselezionate l'opzione **[!UICONTROL Request Confirm before sent messages}** (Conferma richiesta CONTROL prima dell'invio dei messaggi).

I passaggi dettagliati per creare un'attività e-mail sono descritti nella sezione relativa alla consegna [](../../automating/using/email-delivery.md) delle e-mail.

## Creazione di un'attività di aggiornamento dei dati {#creating-update-data-activity}

1. Trascinare un' **[!UICONTROL Update data]** attività dopo il segmento del gruppo di controllo.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Nella **[!UICONTROL General]** scheda, selezionare **[!UICONTROL Update]** dall'elenco a **[!UICONTROL Operation type]** discesa.
1. Nella **[!UICONTROL Identification]** scheda, selezionare l' **[!UICONTROL Directly using the targeting dimension]** opzione.
1. Selezionate la risorsa precedentemente **[!UICONTROL Profile]** estesa come dimensione da aggiornare.

   ![](assets/wkf_control-update-identification.png)

1. Nella **[!UICONTROL Fields to update]** scheda, selezionare come condizione il campo del gruppo di controllo aggiunto alla **[!UICONTROL Profile]** risorsa **[!UICONTROL Destination]** e immettere true.

   ![](assets/wkf_control-update-fields-to-update.png)

1. Click **[!UICONTROL Confirm]**.

I passaggi dettagliati per creare un'attività di aggiornamento dei dati sono descritti nella sezione [Aggiorna dati](../../automating/using/update-data.md) .

## Esecuzione del flusso di lavoro {#running-the-workflow}

Fare clic **[!UICONTROL Start]** per eseguire il flusso di lavoro.

Una volta eseguito il flusso di lavoro, la popolazione del gruppo di controllo viene esclusa e il messaggio viene inviato alla destinazione principale rimanente.

La **[!UICONTROL Profile]** risorsa viene aggiornata come segue: se un profilo si trova nel gruppo di controllo, il campo corrispondente viene selezionato.

![](assets/wkf_control-group-profile-checked.png)

Ora puoi confrontare il modo in cui i destinatari del messaggio reagiranno rispetto al gruppo di dimensioni ridotte che è stato escluso dal messaggio e non lo ha ricevuto.

## Riutilizzo dello stesso gruppo di controllo {#reusing-same-control-group}

L'esempio precedente consente di creare un gruppo di controllo globale, in quanto memorizzato come attributo di profilo indipendentemente dalle consegne. In effetti, il nuovo campo "Gruppo di controllo" creato come parte dell’estensione della **[!UICONTROL Profile]** risorsa viene aggiornato dopo l’esecuzione del flusso di lavoro precedente.

Di conseguenza, la prossima volta che si desidera utilizzare lo stesso gruppo di controllo, è possibile segmentare il nuovo campo "Gruppo di controllo" anziché eseguire una segmentazione casuale.

Per eseguire questa operazione:
1. Quando create l' **[!UICONTROL Segmentation]** attività, selezionate il segmento da modificare nella **[!UICONTROL Segments]** scheda.
1. Nella **[!UICONTROL Configuration]** scheda del segmento, accertatevi di non selezionare l' **[!UICONTROL Limit the population of this segment]** opzione.
1. Nella **[!UICONTROL Filtering]** scheda, trascinare fino **[!UICONTROL Profiles (attributes)]** all’area di lavoro principale.

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. Nella **[!UICONTROL Add a rule - Profiles (attributes)]** finestra, selezionate "Gruppo di controllo" (il campo aggiunto alla **[!UICONTROL Profile]** risorsa) e selezionate **[!UICONTROL Yes]** come condizione del filtro.

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)