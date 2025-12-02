---
title: Interfaccia per flussi di lavoro
description: Scopri l’interfaccia e le opzioni per creare, modificare ed eseguire un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 4%

---

# Interfaccia per flussi di lavoro{#workflow-interface}

Puoi creare flussi di lavoro per gestire interi processi nelle campagne e nei programmi.

La schermata di modifica del flusso di lavoro è composta dai seguenti elementi:

* La [palette](#palette), che fa riferimento alle attività disponibili.
* [Workspace](#workspace), in cui le attività sono configurate e organizzate.
* [Barra delle azioni](#action-bar), costituita da pulsanti che consentono di interagire con il flusso di lavoro e/o i relativi componenti.
* Le [Azioni rapide](#quick-actions), visualizzate intorno a un&#39;attività selezionata, consentono di interagire con essa.

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [Scopri come creare un flusso di lavoro nel video](#video)

## Palette {#palette}

La palette si trova sul lato sinistro dello schermo. Tutte le attività disponibili sono suddivise in diverse categorie:

* [Targeting](../../automating/using/about-targeting-activities.md): attività specifiche per il targeting, la manipolazione dei dati sulla popolazione e il filtraggio delle attività
* [Esecuzione](../../automating/using/about-execution-activities.md): attività specifiche per l&#39;organizzazione e l&#39;esecuzione di flussi di lavoro
* [Canali](../../automating/using/about-channel-activities.md): attività che rappresentano i diversi canali di comunicazione disponibili
* [Gestione dati (ETL)](../../automating/using/about-data-management-activities.md): attività specifiche per la manipolazione dei dati

Per utilizzare un’attività dalla palette nel flusso di lavoro, trascinala e rilasciala nell’area di lavoro.

Devi configurare ogni attività aggiunta dalla palette prima di avviare il flusso di lavoro.

![](assets/workflow_palette.png)

## Area di lavoro {#workspace}

L’area di lavoro è l’area centrale nell’editor del flusso di lavoro. È in quest’area che puoi rilasciare le attività, collegarle tramite transizioni e configurarle.

Per collegare due attività, sposta la fine della freccia dalla prima attività fino all’attività successiva fino a quando non si connettono. Puoi anche spostare l’attività verso il punto della freccia dietro di essa per collegarla all’attività precedente. Se sposti una qualsiasi delle attività, queste rimarranno collegate.

Le transizioni a seguito di attività che elaborano i dati contengono le popolazioni intermedie. Puoi accedervi se selezioni l&#39;opzione **[!UICONTROL Keep interim results]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.


Quando un’attività è selezionata, intorno ad essa vengono visualizzate azioni rapide che ti consentono di interagire con essa. Ad esempio, per configurare un&#39;attività, selezionala e aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px_table.png) nelle azioni rapide.

Alcune funzioni sono abilitate solo nell’area di lavoro:

* Seleziona diverse attività e transizioni disegnando una zona intorno a esse.
* Premi **Ctrl** + clic con il pulsante sinistro del mouse per selezionare diverse attività e/o transizioni.
* Premi **Invio** per visualizzare i dettagli dell&#39;attività o della transizione attualmente selezionata.
* Premi **Elimina** per eliminare l&#39;attività attualmente selezionata.
* Premi **Ctrl + C** per copiare le attività selezionate e **Ctrl + V** per incollarle nell&#39;area di lavoro.

![](assets/workflow_workspace.png)

## Barra delle azioni {#action-bar}

A seconda degli elementi selezionati nell’area di lavoro o dello stato di esecuzione del flusso di lavoro, i pulsanti disponibili nella barra delle azioni possono variare.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Consente di modificare le proprietà del flusso di lavoro.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Avvia il flusso di lavoro.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Sospende il flusso di lavoro.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrompe l&#39;esecuzione del flusso di lavoro. Impossibile riprendere dal punto in cui è stato interrotto.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Riavvia il flusso di lavoro.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Apre il registro di esecuzione del flusso di lavoro.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Attiva la modalità di selezione multipla. Il flusso di lavoro deve essere costituito da almeno due attività.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Disattiva la modalità di selezione multipla.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Apre la transizione selezionata.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Riattiva la selezione se è stata precedentemente disabilitata o contrassegnata come in pausa.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Sospende il flusso di lavoro nell&#39;attività selezionata.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disabilita l&#39;attività.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia le attività selezionate.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Incolla le attività copiate.

## Azioni rapide {#quick-actions}

Quando si seleziona un’attività, intorno ad essa vengono visualizzati pulsanti di azione rapida che consentono di interagire con essa.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Apre l&#39;attività selezionata.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia l&#39;attività selezionata.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Apre le opzioni avanzate dell&#39;attività di consegna e-mail o SMS selezionata.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Riattiva la selezione se è stata precedentemente disabilitata o contrassegnata come in pausa.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Sospende il flusso di lavoro per l&#39;attività selezionata.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Disattiva l&#39;attività.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Forza l&#39;elaborazione immediata della selezione. Questo pulsante è disponibile solo per le attività <span class="uicontrol">Scheduler</span> e <span class="uicontrol">Wait</span>.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina le attività selezionate.

## Duplicazione delle attività del flusso di lavoro {#duplicating-workflow-activities}

L’area di lavoro consente di duplicare le attività del flusso di lavoro copiandole e incollandole nello stesso flusso di lavoro o in un altro flusso di lavoro dalla stessa istanza di Campaign.

Una volta duplicata un’attività, viene mantenuta l’intera configurazione. Per le attività di consegna (e-mail, SMS, notifica push...), l’oggetto di consegna associato all’attività viene duplicato.

>[!NOTE]
>
>Le attività del flusso di lavoro non possono essere duplicate da un’istanza a un’altra. Le attività provenienti da flussi di lavoro tecnici non possono essere duplicate.

Per duplicare un’attività, effettua le seguenti operazioni:

1. Selezionare l&#39;attività, quindi fare clic sul pulsante **[!UICONTROL Copy selection]** dalle azioni rapide.

   È inoltre possibile utilizzare la scelta rapida da tastiera **Ctrl + C**.

   ![](assets/wkf_copypaste1.png)

1. Fare clic con il pulsante destro del mouse nell&#39;area di lavoro del flusso di lavoro di destinazione, quindi fare clic sul pulsante **[!UICONTROL Paste]**.

   È inoltre possibile utilizzare la scelta rapida da tastiera **CTRL + V**.

   ![](assets/wkf_copypaste2.png)

1. L’attività viene duplicata, con tutte le impostazioni configurate inizialmente.

È inoltre possibile copiare e incollare più attività, consentendo di duplicare un intero flusso di lavoro.

A questo scopo, seleziona le attività disegnando una zona intorno a esse. quindi fare clic sul pulsante **[!UICONTROL Copy selection]** nella barra delle azioni (oppure premere **Ctrl + C**). Puoi quindi incollarli nella posizione desiderata.

![](assets/wkf_copypaste3.png)

## Video tutorial {#video}

Questo video mostra come creare un flusso di lavoro.

>[!VIDEO](https://video.tv.adobe.com/v/329905?captions=ita&quality=12)

Ulteriori video dimostrativi di Campaign Standard sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
