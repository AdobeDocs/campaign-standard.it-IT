---
title: Interfaccia del flusso di lavoro
seo-title: Interfaccia del flusso di lavoro
description: Interfaccia del flusso di lavoro
seo-description: Scopri l'interfaccia e le opzioni per creare, modificare ed eseguire un flusso di lavoro.
page-status-flag: never-activated
uuid: aafe 33 ed-fa 07-4 dd 9-825 e -242099334 f 1 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: about-workflows-and-data-management
discoiquuid: 147 fbb 0 d -17 d 2-444 b-a 215-9 ad 14179 c 549
context-tags: flusso di lavoro, principale; flusso di lavoro, panoramica
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Workflow interface{#workflow-interface}

Puoi creare flussi di lavoro per gestire interi processi nelle campagne e nei programmi.

La schermata di modifica del flusso di lavoro è composta dai seguenti elementi:

* [Palette,](../../automating/using/workflow-interface.md#palette)che fa riferimento alle attività disponibili.
* The [Workspace](../../automating/using/workflow-interface.md#workspace), in which the activities are configured and organized.
* The [Action bar](../../automating/using/workflow-interface.md#action-bar), which is made up of buttons that allow you to interact with the workflow and/or its components.
* The [Quick actions](../../automating/using/workflow-interface.md#quick-actions), which appear around a selected activity, allow you to interact with it.

![](assets/wkf_overview.png)

## Palette {#palette}

La palette si trova sul lato sinistro della schermata. Tutte le attività disponibili sono ordinate in diverse categorie:

* [Targeting](../../automating/using/about-targeting-activities.md): attività specifiche per il targeting, manipolazione di dati sulla popolazione e attività di filtro
* [Esecuzione](../../automating/using/about-execution-activities.md): attività specifiche per organizzare ed eseguire flussi di lavoro
* [Canali](../../automating/using/about-channel-activities.md): attività che rappresentano i diversi canali di comunicazione disponibili
* [Gestione dati (ETL)](../../automating/using/about-data-management-activities.md): attività specifiche per la manipolazione dei dati

Per usare un'attività dalla palette nel flusso di lavoro, trascinatela nell'area di lavoro.

È necessario configurare ogni attività aggiunta dalla palette prima di avviare il flusso di lavoro.

![](assets/workflow_palette.png)

## Workspace {#workspace}

L'area di lavoro è la zona centrale dell'editor di workflow. È in questo zona che potete rilasciare le attività, collegarle insieme utilizzando le transizioni e configurarle.

Per collegare due attività, sposta la fine della freccia dalla prima attività fino alla prima attività fino alla loro connessione. Potete anche spostare l'attività verso il punto della freccia dietro di essa per collegarla all'attività precedente. Se spostate una qualsiasi attività, queste rimarranno collegate.

Le transizioni seguono le attività che il processo elabora per le popolazioni di intermediari. You can access them if you check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

Quando un'attività è selezionata, le azioni rapide vengono visualizzate attorno all'attività, consentendo di interagire con essa. For example, to configure an activity, select it then open it using the ![](assets/edit_darkgrey-24px_table.png) button in the quick actions.

Alcune funzioni sono abilitate solo nell'area di lavoro:

* Selezionate più attività e transizioni disegnando un'area intorno a essi.
* Press **Ctrl** + left click to select several activities and/or transitions.
* Press **Enter** to view the detail of the currently selected activity or transition.
* Press **Delete** to delete the currently selected activity.
* Press **Ctrl + C** to copy the selected activities, and **Ctrl + V** to paste them into the workspace.

![](assets/workflow_workspace.png)

## Action bar {#action-bar}

In base agli elementi selezionati nell'area di lavoro o allo stato di esecuzione del flusso di lavoro, i pulsanti disponibili nella barra delle azioni possono variare.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Consente di modificare le proprietà del flusso di lavoro.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Avvia il flusso di lavoro.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Mette in pausa il flusso di lavoro.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe l'esecuzione del flusso di lavoro. Non può essere ripristinato da dove è stato interrotto.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Riavvia il flusso di lavoro.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Apre il registro dell'esecuzione del flusso di lavoro.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Attiva la modalità di selezione multipla. Il flusso di lavoro deve essere composto da almeno due attività.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Disattiva la modalità di selezione multipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Apre la transizione selezionata.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Riattiva la selezione se in precedenza è stata disattivata o contrassegnata come messa in pausa.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Mette in pausa il flusso di lavoro nell'attività selezionata.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l'attività.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia le attività selezionate.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Incolla le attività che sono state copiate.

## Quick actions {#quick-actions}

Quando un'attività è selezionata, i pulsanti di azione rapida appaiono attorno all'attività e consentono di interagire con esso.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Apre l'attività selezionata.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia l'attività selezionata.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Consente di aprire le opzioni avanzate dell'attività di consegna e-mail o SMS selezionata.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Riattiva la selezione se in precedenza è stata disattivata o contrassegnata come messa in pausa.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Mette in pausa il flusso di lavoro nell'attività selezionata.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l'attività.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Forza l'elaborazione immediata della selezione. This button is only available for the <span class="uicontrol">Scheduler</span> and <span class="uicontrol">Wait</span> activities.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.

## Duplicating workflow activities {#duplicating-workflow-activities}

L'area di lavoro consente di duplicare le attività del flusso di lavoro copiandole nello stesso flusso di lavoro o in un altro flusso di lavoro dalla stessa istanza Campaign.

Una volta ottenuta la duplicazione dell'attività, viene mantenuta la relativa configurazione intera. Per le attività di consegna (E-mail, SMS, Notifica push…), l'oggetto di consegna associato all'attività viene duplicato.

>[!NOTE]
>
>Le attività del flusso di lavoro non possono essere duplicate da un'istanza all'altra. Le attività dai flussi di lavoro tecnici non possono essere duplicate.

Per duplicare un'attività, effettuate le operazioni seguenti:

1. Select the activity, then click the **[!UICONTROL Copy selection]** button from the quick actions.

   You can also use the **Ctrl + C** keyboard shortcut.

   ![](assets/wkf_copypaste1.png)

1. Right-click in the target workflow workspace, then click the **[!UICONTROL Paste]** button.

   You can also use the **CTRL + V** keyboard shortcut.

   ![](assets/wkf_copypaste2.png)

1. L'attività viene duplicata, con tutte le impostazioni configurate inizialmente.

Potete anche copiare e incollare più attivazioni, per duplicare un intero worflow.

A tal fine, seleziona le attività disegnando un'area intorno a loro. then click the **[!UICONTROL Copy selection]** button from the action bar (or press **Ctrl + C**). Potete quindi incollarli nella posizione desiderata.

![](assets/wkf_copypaste3.png)

