---
solution: Campaign Standard
product: campaign
title: Creazione di un messaggio e-mail multilingue
description: Per creare un'e-mail di destinazione multilingue con diverse lingue preferite, effettuate le seguenti operazioni.
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 25%

---


# Creazione di un messaggio e-mail multilingue{#creating-a-multilingual-email}

Potete inviare un messaggio e-mail in più lingue a profili con diverse lingue preferite: ogni profilo riceverà una variante dell&#39;e-mail nella sua lingua preferita.

A questo scopo, verificate di disporre di un modello e-mail in più lingue. In caso contrario, scopri come crearne uno in [questa sezione](../../channels/using/multilingual-messages-template.md).

L&#39;audience è basata su profili con informazioni sulla lingua preferita completate.

1. Create un nuovo messaggio e-mail basato su un [modello multilingue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Definisci le proprietà generali e il pubblico target dell’e-mail, come per un’e-mail standard. Consulta la sezione [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).
1. Al quarto passaggio della procedura guidata di creazione, definite le opzioni della variante. Se il [modello multilingue](../../channels/using/multilingual-messages-template.md) contiene già tutti i parametri giusti, è possibile fare clic direttamente sul pulsante **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Se necessario, aggiungere varianti utilizzando il pulsante **[!UICONTROL Add an element]**. **[!UICONTROL Default]** la variante non deve essere eliminata. Quando è impostato su **[!UICONTROL default]**, [la lingua preferita del profilo](../../audiences/using/creating-profiles.md) viene utilizzata per scegliere la variante. È inoltre possibile impostare la variante **[!UICONTROL Default]** su qualsiasi altra lingua.

1. Conferma creazione e-mail: viene visualizzata la dashboard e-mail.
1. Definite il contenuto dell&#39;e-mail per ogni variante. A seconda del modello scelto, puoi definire diversi oggetti, diversi nomi di mittenti o diversi contenuti differenti. Utilizzate il menu a discesa per navigare tra le diverse varianti dell&#39;elemento. Per ulteriori informazioni, consulta la sezione [editor di contenuti](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Verifica e convalida del messaggio. Fare riferimento alla sezione [Invio della prova](../../sending/using/sending-proofs.md).
1. Pianificare l&#39;invio con il **[!UICONTROL Send after confirmation option]**.
1. Una volta inviato il messaggio e-mail, potete accedere ai registri e ai rapporti relativi per misurare il successo della campagna. Per ulteriori informazioni sul reporting, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

**Argomento correlato:**

* [Raggiungere audience in più lingue con un unico flusso di lavoro](https://helpx.adobe.com/it/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
