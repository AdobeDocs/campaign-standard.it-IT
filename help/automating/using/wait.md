---
title: Attendi
description: L'attività Wait sospende momentaneamente l'esecuzione di una parte di un flusso di lavoro.
page-status-flag: mai attivato
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Attendi{#wait}

## Descrizione {#description}

![](assets/wait.png)

L' **[!UICONTROL Wait]** attività interrompe momentaneamente l'esecuzione di una parte di un flusso di lavoro. Attiva la sua transizione in uscita dopo un ritardo che può variare da pochi secondi a diversi mesi, che esegue le attività poste in seguito.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Wait]** attività viene utilizzata per consentire il passaggio di un certo periodo di tempo tra due attività eseguite. Ad esempio, per attendere diversi giorni dopo un'attività di consegna delle e-mail, analizzare le aperture e i clic generati durante questo periodo prima di eseguire eventuali operazioni di follow-up (promemoria e-mail, creazione di un'audience, ecc.).

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Wait]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Specificate l'intervallo **[!UICONTROL Duration]** di attesa tra l'attivazione delle transizioni in entrata e in uscita dell'attività.

   È possibile immettere manualmente la durata o utilizzare il selettore disponibile nel campo.

   ![](assets/wait_duration.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'esempio seguente illustra l' **[!UICONTROL Wait]** attività in un caso d'uso tipico. Viene inviato un invito e-mail a un evento. 24 ore dopo l’invio, i registri di consegna delle e-mail vengono analizzati e viene inviato un messaggio e-mail di promemoria alle persone che hanno ricevuto la prima e-mail ma non si sono registrate.

Il flusso di lavoro viene presentato come segue:

![](assets/wait_example_workflow.png)

* Un primo **[!UICONTROL Query]** esegue il targeting dei profili che verranno inviati all’invito e-mail.
* L'invito **[!UICONTROL Email delivery]** viene inviato per la prima volta ai profili selezionati.
* Un’ **[!UICONTROL Wait]** attività pari a 24 ore interrompe il passaggio dall’invio dell’invito al resto del flusso di lavoro.
* Un secondo **[!UICONTROL Query]** esegue il targeting dei profili che hanno ricevuto il primo messaggio e-mail ma non hanno fatto clic sul collegamento di iscrizione all'interno.
* Un secondo **[!UICONTROL Email delivery]** invia un promemoria dell’invito alle persone selezionate.

