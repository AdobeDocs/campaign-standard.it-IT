---
solution: Campaign Standard
product: campaign
title: Interfaccia dei flussi di lavoro
description: Scopri l’interfaccia e le opzioni per creare, modificare ed eseguire un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Flussi di lavoro
role: Architetto dati
level: Principiante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 4%

---


# Interfaccia dei flussi di lavoro{#workflow-interface}

Puoi creare flussi di lavoro per gestire interi processi nelle campagne e nei programmi.

La schermata di modifica del flusso di lavoro è composta dai seguenti elementi:

* La [Palette](#palette), che fa riferimento alle attività disponibili.
* L’ [Area di lavoro](#workspace), in cui le attività sono configurate e organizzate.
* La [barra delle azioni](#action-bar), costituita da pulsanti che consentono di interagire con il flusso di lavoro e/o i relativi componenti.
* Le [Azioni rapide](#quick-actions), visualizzate intorno a un&#39;attività selezionata, consentono di interagire con essa.

![](assets/wkf_overview.png)

## Palette {#palette}

La palette si trova sul lato sinistro dello schermo. Tutte le attività disponibili sono suddivise in diverse categorie:

* [Targeting](../../automating/using/about-targeting-activities.md): attività specifiche per il targeting, la manipolazione dei dati sulla popolazione e le attività di filtraggio
* [Esecuzione](../../automating/using/about-execution-activities.md): attività specifiche per l’organizzazione e l’esecuzione dei flussi di lavoro
* [Canali](../../automating/using/about-channel-activities.md): attività che rappresentano i diversi canali di comunicazione disponibili
* [Gestione dati (ETL)](../../automating/using/about-data-management-activities.md): attività specifiche per la manipolazione dei dati

Per utilizzare un’attività dalla palette nel flusso di lavoro, trascinala nell’area di lavoro.

Devi configurare ogni attività aggiunta dalla palette prima di avviare il flusso di lavoro.

![](assets/workflow_palette.png)

## Area di lavoro {#workspace}

L’area di lavoro è la zona centrale nell’editor del flusso di lavoro. È in questa zona che puoi rilasciare le tue attività, collegarle utilizzando le transizioni e configurarle.

Per collegare due attività, sposta la fine della freccia dalla prima attività all’attività seguente fino a quando non si connettono. Puoi anche spostare l’attività verso il punto della freccia dietro di essa per collegarla all’attività precedente. Se sposti una delle attività, queste rimarranno collegate.

Transizioni successive alle attività che elaborano i dati contenenti le popolazioni intermedie. Puoi accedervi selezionando l’opzione **[!UICONTROL Keep interim results]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.


Quando un’attività viene selezionata, intorno all’attività vengono visualizzate azioni rapide, che consentono di interagire con essa. Ad esempio, per configurare un’attività, selezionala e aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px_table.png) nelle azioni rapide.

Alcune funzioni sono abilitate solo nell’area di lavoro:

* Seleziona diverse attività e transizioni disegnando una zona intorno a loro.
* Premi **Ctrl** + clic a sinistra per selezionare diverse attività e/o transizioni.
* Premi **Invio** per visualizzare i dettagli dell&#39;attività o della transizione attualmente selezionata.
* Premi **Elimina** per eliminare l&#39;attività attualmente selezionata.
* Premere **Ctrl + C** per copiare le attività selezionate e **Ctrl + V** per incollarle nell&#39;area di lavoro.

![](assets/workflow_workspace.png)

## Barra delle azioni {#action-bar}

A seconda degli elementi selezionati nell’area di lavoro o dello stato di esecuzione del flusso di lavoro, i pulsanti disponibili nella barra delle azioni possono variare.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Consente di modificare le proprietà del flusso di lavoro.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Avvia il flusso di lavoro.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Sospende il flusso di lavoro.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe l’esecuzione del flusso di lavoro. Impossibile riprendere da dove è stato interrotto.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Riavvia il flusso di lavoro.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Apre il registro di esecuzione del flusso di lavoro.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Abilita la modalità di selezione multipla. Il flusso di lavoro deve essere composto da almeno due attività.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Disattiva la modalità di selezione multipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Apre la transizione selezionata.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Abilita nuovamente la selezione se in precedenza è stata disabilitata o contrassegnata come sospesa.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Sospende il flusso di lavoro nell’attività selezionata.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l’attività.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia le attività selezionate.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Incolla le attività che sono state copiate.

## Azioni rapide {#quick-actions}

Quando un’attività è selezionata, intorno all’attività vengono visualizzati i pulsanti di azione rapida, che consentono di interagire con essa.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Apre l’attività selezionata.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia l’attività selezionata.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Apre le opzioni avanzate dell’attività Email o SMS delivery selezionata.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Abilita nuovamente la selezione se in precedenza è stata disabilitata o contrassegnata come sospesa.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Sospende il flusso di lavoro nell’attività selezionata.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l’attività.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Forza l&#39;elaborazione immediata della selezione. Questo pulsante è disponibile solo per le attività <span class="uicontrol">Scheduler</span> e <span class="uicontrol">Wait</span> .

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.

## Duplicazione delle attività del flusso di lavoro {#duplicating-workflow-activities}

L’area di lavoro ti consente di duplicare le attività del flusso di lavoro copiandole e incollandole nello stesso flusso di lavoro o in un altro flusso di lavoro dalla stessa istanza Campaign.

Una volta duplicata un’attività, viene mantenuta l’intera configurazione. Per le attività di consegna (e-mail, SMS, notifica push..), l’oggetto di consegna allegato all’attività viene duplicato.

>[!NOTE]
>
>Le attività del flusso di lavoro non possono essere duplicate da un’istanza a un’altra. Non è possibile duplicare le attività dai flussi di lavoro tecnici.

Per duplicare un’attività, segui i passaggi seguenti:

1. Seleziona l’attività, quindi fai clic sul pulsante **[!UICONTROL Copy selection]** dalle azioni rapide.

   È inoltre possibile utilizzare la scelta rapida da tastiera **Ctrl + C**.

   ![](assets/wkf_copypaste1.png)

1. Fai clic con il pulsante destro del mouse nell’area di lavoro del flusso di lavoro di destinazione, quindi fai clic sul pulsante **[!UICONTROL Paste]** .

   È inoltre possibile utilizzare la scelta rapida da tastiera **CTRL+V**.

   ![](assets/wkf_copypaste2.png)

1. L’attività viene duplicata, con tutte le impostazioni inizialmente configurate.

È inoltre possibile copiare e incollare più attività, consentendo di duplicare un intero flusso di lavoro.

A questo scopo, seleziona le attività disegnando una zona intorno a esse. quindi fai clic sul pulsante **[!UICONTROL Copy selection]** dalla barra delle azioni (oppure premi **Ctrl + C**). Puoi quindi incollarli nella posizione desiderata.

![](assets/wkf_copypaste3.png)

