---
title: Importazione di dati con modelli di importazione
description: Scopri come raccogliere i dati per alimentare il database Campaign.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Importazione di dati con modelli di importazione{#importing-data-with-import-templates}

L&#39;importazione di dati consente di raccogliere dati per alimentare il database Campaign.

In alternativa ai [flussi di lavoro](../../automating/using/get-started-workflows.md), Adobe Campaign offre una funzione di importazione semplificata che consente all&#39;utente di gestire alcuni tipi di importazione definiti da un amministratore.

Il principio di funzionamento è il seguente: un **amministratore** definisce e gestisce i modelli di importazione (consultate [Definizione dei modelli](../../automating/using/defining-import-templates.md)di importazione). Questi modelli di importazione vengono quindi resi disponibili agli utenti con viste semplificate nel menu **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Questi utenti devono quindi semplicemente selezionare il tipo di importazione che desiderano eseguire e caricare il file con i dati da importare. Il flusso di lavoro definito dall’amministratore viene eseguito in modo trasparente per l’utente, che potrà accedere ai dettagli del risultato dell’importazione una volta completata.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Per ulteriori informazioni sui ruoli, consulta [questa sezione](../../administration/using/list-of-roles.md).

Le importazioni possono essere filtrate in base al modello da cui sono state eseguite, alla data di esecuzione e allo stato di esecuzione.

1. Dalla panoramica delle importazioni, fate clic sul **[!UICONTROL Create]** pulsante. Viene aperta la procedura guidata.
1. Selezionare il tipo di importazione che si desidera eseguire. I tipi di importazione corrispondono ai modelli di importazione disponibili.
1. Se necessario, scaricate nel computer il file di esempio collegato al modello per visualizzare i tipi di dati previsti nel file da importare.
1. Scaricate il file contenente i dati da importare nella procedura guidata.
1. Avviate l’importazione. La procedura guidata si chiude e si torna all’elenco delle importazioni effettuate con il modello utilizzato.
1. Aggiorna la pagina e seleziona l’importazione appena eseguita per visualizzare i dettagli dell’esecuzione.

   ![](assets/simplified_import1.png)

I dettagli dell&#39;esecuzione dell&#39;importazione sono ora disponibili. È possibile scaricare nel computer sia il file importato, sia il file contenente i dati rifiutati (dati non importati).
