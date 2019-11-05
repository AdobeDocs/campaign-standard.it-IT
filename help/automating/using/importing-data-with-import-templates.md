---
title: Importazione di dati con modelli di importazione
description: Scopri come raccogliere i dati per alimentare il database Campaign.
page-status-flag: mai attivato
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: importazione ed esportazione di dati
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Importazione di dati con modelli di importazione{#importing-data-with-import-templates}

L'importazione di dati consente di raccogliere dati per alimentare il database Campaign.

In alternativa ai [flussi di lavoro](../../automating/using/discovering-workflows.md), Adobe Campaign offre una funzione di importazione semplificata che consente all'utente di gestire alcuni tipi di importazione definiti da un amministratore.

Il principio di funzionamento è il seguente: un **amministratore** definisce e gestisce i modelli di importazione (consultate [Definizione dei modelli](../../automating/using/defining-import-templates.md)di importazione). Questi modelli di importazione vengono quindi resi disponibili agli utenti con viste semplificate nel menu **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** .

Questi utenti devono quindi semplicemente selezionare il tipo di importazione che desiderano eseguire e caricare il file con i dati da importare. Il flusso di lavoro definito dall’amministratore viene eseguito in modo trasparente per l’utente, che potrà accedere ai dettagli del risultato dell’importazione una volta completata.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Per ulteriori informazioni sui ruoli, consulta [questa sezione](../../administration/using/list-of-roles.md).

Le importazioni possono essere filtrate in base al modello da cui sono state eseguite, alla data di esecuzione e allo stato di esecuzione.

1. Dalla panoramica delle importazioni, fate clic sul **[!UICONTROL Create]** pulsante. Viene aperta la procedura guidata.
1. Selezionare il tipo di importazione da effettuare. I tipi di importazione corrispondono ai modelli di importazione disponibili.
1. Se necessario, scaricate nel computer il file di esempio collegato al modello per visualizzare i tipi di dati previsti nel file da importare.
1. Scaricate il file contenente i dati da importare nella procedura guidata.
1. Avviare l’importazione. La procedura guidata viene chiusa e riporta all'elenco delle importazioni effettuate con il modello utilizzato.
1. Aggiorna la pagina e seleziona l’importazione appena eseguita per visualizzare i dettagli dell’esecuzione.

   ![](assets/simplified_import1.png)

I dettagli dell'esecuzione dell'importazione sono ora disponibili. È possibile scaricare nel computer sia il file importato, sia il file contenente i dati rifiutati (dati non importati).
