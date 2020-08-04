---
title: Wait
description: L’attività Wait sospende momentaneamente l’esecuzione di una parte di un flusso di lavoro.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '296'
ht-degree: 100%

---


# Wait{#wait}

## Descrizione {#description}

![](assets/wait.png)

L’attività **[!UICONTROL Wait]** sospende momentaneamente l’esecuzione di una parte di un flusso di lavoro. Attiva la relativa transizione in uscita dopo un ritardo che può variare da pochi secondi a diversi mesi, che esegue le attività inserite in seguito.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Wait]** viene utilizzata per consentire il trascorrere di un certo periodo di tempo tra due attività eseguite. Ad esempio, per attendere diversi giorni dopo un’attività di consegna e-mail, quindi per analizzare le aperture e i clic generati durante questo periodo prima di eseguire eventuali operazioni di follow-up (promemoria e-mail, creazione di un pubblico, ecc.).

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Wait]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Specifica la **[!UICONTROL Duration]** dell’attesa tra l’attivazione delle transizioni in entrata e in uscita dell’attività.

   Puoi immettere manualmente la durata o utilizzare il selettore disponibile nel campo.

   ![](assets/wait_duration.png)

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

L’esempio seguente illustra l’attività **[!UICONTROL Wait]** in un caso d’uso tipico. Viene inviato un invito e-mail a un evento. 24 ore dopo l’invio, i log di consegna e-mail vengono analizzati e viene inviato un messaggio e-mail di promemoria alle persone che hanno ricevuto la prima e-mail ma non si sono registrate.

Il flusso di lavoro viene presentato come segue:

![](assets/wait_example_workflow.png)

* Una prima **[!UICONTROL Query]** esegue il targeting dei profili ai quali viene inviato l’invito e-mail.
* Una **[!UICONTROL Email delivery]** invia l’invito per la prima volta ai profili selezionati.
* Un’attività **[!UICONTROL Wait]** pari a 24 ore inserisce una pausa tra il momento dell’invio dell’invito e il resto del flusso di lavoro.
* Una seconda **[!UICONTROL Query]** esegue il targeting dei profili che hanno ricevuto il primo messaggio e-mail ma non hanno fatto clic sul collegamento di abbonamento all’interno.
* Una seconda **[!UICONTROL Email delivery]** invia un promemoria dell’invito alle persone selezionate.

