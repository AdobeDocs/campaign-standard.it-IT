---
title: Interfaccia dei flussi di lavoro
description: Scopri l’interfaccia e le opzioni per creare, modificare ed eseguire un flusso di lavoro.
page-status-flag: never-activated
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: workflow,main;workflow,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 4%

---


# Interfaccia dei flussi di lavoro{#workflow-interface}

Puoi creare flussi di lavoro per gestire interi processi nelle campagne e nei programmi.

La schermata di modifica del flusso di lavoro è composta dai seguenti elementi:

* La [palette](#palette), che fa riferimento alle attività disponibili.
* L&#39; [area di lavoro](#workspace), in cui le attività sono configurate e organizzate.
* La barra [](#action-bar)Azioni, composta da pulsanti che consentono di interagire con il flusso di lavoro e/o i relativi componenti.
* Le azioni [](#quick-actions)rapide, visualizzate intorno a un&#39;attività selezionata, consentono di interagire con essa.

![](assets/wkf_overview.png)

## Palette {#palette}

La palette si trova sul lato sinistro dello schermo. Tutte le attività disponibili sono suddivise in diverse categorie:

* [Targeting](../../automating/using/about-targeting-activities.md): attività specifiche per il targeting, la manipolazione dei dati sulla popolazione e le attività di filtraggio
* [Esecuzione](../../automating/using/about-execution-activities.md): attività specifiche per l&#39;organizzazione e l&#39;esecuzione di flussi di lavoro
* [Canali](../../automating/using/about-channel-activities.md): attività che rappresentano i diversi canali di comunicazione disponibili
* [Gestione dei dati (ETL)](../../automating/using/about-data-management-activities.md): attività specifiche per la manipolazione dei dati

Per utilizzare un&#39;attività dalla palette nel flusso di lavoro, trascinatela nell&#39;area di lavoro.

È necessario configurare ogni attività aggiunta dalla palette prima di avviare il flusso di lavoro.

![](assets/workflow_palette.png)

## Area di lavoro {#workspace}

L’area di lavoro è l’area centrale nell’editor del flusso di lavoro. È in questa zona che puoi rilasciare le tue attività, collegarle utilizzando le transizioni e configurarle.

Per collegare due attività, spostate la fine della freccia dalla prima attività fino alla seguente fino alla connessione. Potete anche spostare l&#39;attività verso il punto della freccia dietro di essa per collegarla all&#39;attività precedente. Se spostate una delle attività, queste rimarranno collegate.

Transizioni successive alle attività che elaborano i dati contenenti le popolazioni intermedie. Potete accedervi selezionando l&#39; **[!UICONTROL Keep interim results]** opzione nella **[!UICONTROL Execution]** sezione delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.


Quando un&#39;attività è selezionata, intorno all&#39;attività vengono visualizzate azioni rapide che consentono di interagire con essa. Ad esempio, per configurare un&#39;attività, selezionatela e apritela utilizzando il ![](assets/edit_darkgrey-24px_table.png) pulsante nelle azioni rapide.

Alcune funzioni sono abilitate solo nell’area di lavoro:

* Seleziona diverse attività e transizioni disegnando una zona intorno a esse.
* Premere **Ctrl** + clic con il pulsante sinistro del mouse per selezionare diverse attività e/o transizioni.
* Premere **Invio** per visualizzare il dettaglio dell&#39;attività o della transizione attualmente selezionata.
* Premere **Elimina** per eliminare l&#39;attività attualmente selezionata.
* Premere **Ctrl + C** per copiare le attività selezionate, quindi **Ctrl + V** per incollarle nell&#39;area di lavoro.

![](assets/workflow_workspace.png)

## Barra delle azioni {#action-bar}

A seconda degli elementi selezionati nell’area di lavoro o dello stato di esecuzione del flusso di lavoro, i pulsanti disponibili nella barra delle azioni possono variare.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Consente di modificare le proprietà del flusso di lavoro.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Avvia il flusso di lavoro.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Mette in pausa il flusso di lavoro.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe l&#39;esecuzione del flusso di lavoro. Impossibile riprendere da dove è stato interrotto.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Riavvia il flusso di lavoro.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Apre il registro di esecuzione del flusso di lavoro.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Abilita la modalità di selezione multipla. Il flusso di lavoro deve essere composto da almeno due attività.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Disattiva la modalità di selezione multipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Apre la transizione selezionata.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Abilita di nuovo la selezione se è stata precedentemente disabilitata o contrassegnata come messa in pausa.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Mette in pausa il flusso di lavoro nell&#39;attività selezionata.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l&#39;attività.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia le attività selezionate.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Incolla le attività che sono state copiate.

## Azioni rapide {#quick-actions}

Quando un&#39;attività è selezionata, intorno all&#39;attività vengono visualizzati pulsanti di azione rapida, che consentono di interagire con essa.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Apre l&#39;attività selezionata.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia l&#39;attività selezionata.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Apre le opzioni avanzate dell&#39;attività di consegna e-mail o SMS selezionata.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Abilita di nuovo la selezione se è stata precedentemente disabilitata o contrassegnata come messa in pausa.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Mette in pausa il flusso di lavoro nell&#39;attività selezionata.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l&#39;attività.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Impone l&#39;elaborazione immediata della selezione. Questo pulsante è disponibile solo per le attività<span class="uicontrol">Scheduler</span>e<span class="uicontrol">Wait</span>.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.

## Duplicazione delle attività del flusso di lavoro {#duplicating-workflow-activities}

L&#39;area di lavoro consente di duplicare le attività del flusso di lavoro copiandole e incollandole nello stesso flusso di lavoro o in un altro flusso di lavoro dalla stessa istanza Campaign.

Una volta duplicata un&#39;attività, l&#39;intera configurazione viene mantenuta. Per le attività di consegna (E-mail, SMS, Push Notification...), l&#39;oggetto di consegna allegato all&#39;attività viene duplicato.

>[!NOTE]
>
>Le attività del flusso di lavoro non possono essere duplicate da un&#39;istanza all&#39;altra. Le attività dei flussi di lavoro tecnici non possono essere duplicate.

Per duplicare un&#39;attività, effettuate le operazioni seguenti:

1. Selezionate l&#39;attività, quindi fate clic sul **[!UICONTROL Copy selection]** pulsante delle azioni rapide.

   È inoltre possibile utilizzare la scelta rapida da tastiera **Ctrl + C** .

   ![](assets/wkf_copypaste1.png)

1. Fare clic con il pulsante destro del mouse nell&#39;area di lavoro del flusso di lavoro di destinazione, quindi fare clic sul **[!UICONTROL Paste]** pulsante.

   È inoltre possibile utilizzare la scelta rapida da tastiera **CTRL + V** .

   ![](assets/wkf_copypaste2.png)

1. L&#39;attività viene duplicata, con tutte le impostazioni che sono state configurate inizialmente.

È inoltre possibile copiare e incollare più attività, per duplicare un intero flusso di lavoro.

A tal fine, selezionate le attività disegnando una zona intorno a esse. quindi fate clic sul **[!UICONTROL Copy selection]** pulsante dalla barra delle azioni (oppure premete **Ctrl + C**). Potete quindi incollarli nella posizione desiderata.

![](assets/wkf_copypaste3.png)

