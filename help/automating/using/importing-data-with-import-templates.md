---
title: Importazione di dati con modelli di importazione
seo-title: Importazione di dati con modelli di importazione
description: Importazione di dati con modelli di importazione
seo-description: Scopri come raccogliere dati per fornire feed al tuo database Campaign.
page-status-flag: never-activated
uuid: bfc 03235-2032-448 a-a 9 ed -21 ff 2 a 83 fa 09
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: import-and-exporting-data
discoiquuid: fb 511 bb 8-6 be 7-43 f 6-86 ab -94 d 5 cfa 3 efc 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Importing data with import templates{#importing-data-with-import-templates}

L'importazione di dati consente di raccogliere dati per fornire feed al database di Campaign.

Alternatively to [Workflows](../../automating/using/discovering-workflows.md), Adobe Campaign offers a simplified import function that allows the user to manage certain types of import that were defined by an administrator.

The operating principle is as follows: an **administrator** defines and manages import templates (see [Defining import templates](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** menu.

Pertanto, questi utenti devono semplicemente selezionare il tipo di importazione da importare e caricare il file con i dati da importare. Il flusso di lavoro definito dall'amministratore viene eseguito in modo trasparente per l'utente, che può accedere ai dettagli del risultato dell'importazione una volta terminato.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Per ulteriori informazioni sui ruoli, consulta [questa sezione](../../administration/using/list-of-roles.md).

Le importazioni possono essere filtrate in base al modello da cui sono stati eseguiti, alla data di esecuzione e al relativo stato di esecuzione.

1. From the imports overview, click the **[!UICONTROL Create]** button. Viene aperta la procedura guidata.
1. Selezionate il tipo di importazione da eseguire. I tipi di importazione corrispondono ai modelli di importazione disponibili.
1. Se necessario, scaricate il file di esempio collegato al modello per visualizzare i tipi di dati previsti nel file da importare.
1. Scaricate il file contenente i dati da importare nella procedura guidata.
1. Avviate l'importazione. La procedura guidata viene chiusa e vi riporterà all'elenco delle importazioni eseguite con il modello utilizzato.
1. Aggiornate la pagina e selezionate l'importazione che avete appena eseguito per visualizzare i dettagli sull'esecuzione.

   ![](assets/simplified_import1.png)

Sono ora disponibili i dettagli dell'esecuzione di importazione. È possibile scaricare nel computer sia il file importato, che quello contenente i dati rifiutati (i dati non importati).
