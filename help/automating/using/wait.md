---
title: Attendi
seo-title: Attendi
description: Attendi
seo-description: L'attività di attesa interrompe momentaneamente l'esecuzione di una parte di un flusso di lavoro.
page-status-flag: never-activated
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: wait, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Wait{#wait}

## Description {#description}

![](assets/wait.png)

**[!UICONTROL Wait]** L'attività interrompe momentaneamente l'esecuzione di una parte di un flusso di lavoro. La transizione in uscita viene attivata dopo un ritardo che potrebbe variare da alcuni secondi a più mesi, in modo da eseguire le attività successivamente inserite.

## Context of use {#context-of-use}

The **[!UICONTROL Wait]** activity is used to allow a certain amount of time to pass between two activities being executed. Ad esempio, per attendere diversi giorni dopo un'attività di consegna e-mail, quindi analizzare le aperture e i clic generati durante questo periodo prima di eseguire operazioni di follow-up (e-mail promemoria, creazione di un pubblico ecc.).

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Wait]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Duration]** of the wait between when the inbound and outbound transitions of the activity are activated.

   È possibile immettere manualmente la durata o utilizzare il selettore disponibile nel campo.

   ![](assets/wait_duration.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

The following example illustrates the **[!UICONTROL Wait]** activity in a typical use case. Viene inviato un invito e-mail a un evento. 24 ore dopo l'invio, i registri di consegna e-mail vengono analizzati e un messaggio e-mail viene inviato alle persone che hanno ricevuto la prima e-mail ma non sono state registrate.

Il flusso di lavoro viene presentato come segue:

![](assets/wait_example_workflow.png)

* A first **[!UICONTROL Query]** targets the profiles that will be sent the email invitation.
* An **[!UICONTROL Email delivery]** sends the invitation for the first time to the profiles selected.
* A **[!UICONTROL Wait]** activity of 24h places a pause between when the invitation was sent and the rest of the workflow.
* A second **[!UICONTROL Query]** targets the profiles that received the first email but did not click on the subscription link inside.
* A second **[!UICONTROL Email delivery]** sends a reminder of the invitation to the people selected.

