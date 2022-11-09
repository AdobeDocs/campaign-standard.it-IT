---
title: Creazione di un messaggio e-mail multilingue
description: Segui questi passaggi per creare un’e-mail con targeting multilingue per i destinatari con diverse lingue preferite.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: d234d7fab039b602eff06c03ba0d8f7ce2a0cf3f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# Creazione di un messaggio e-mail multilingue{#creating-a-multilingual-email}

Puoi inviare un’e-mail multilingue a profili con diverse lingue preferite: ogni profilo riceverà una variante dell’e-mail nella lingua preferita.

A questo scopo, verifica di disporre di un modello e-mail multilingue. In caso contrario, scopri come crearne uno in [questa sezione](../../channels/using/multilingual-messages-template.md).

Il pubblico si basa su profili con informazioni sulla lingua preferita completate.

1. Crea un nuovo messaggio e-mail in base a un [modello multilingue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Definisci le proprietà generali e il pubblico target dell’e-mail, come per un’e-mail standard. Consulta la sezione [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).

1. Al quarto passaggio della procedura guidata di creazione, definisci le opzioni della variante. Se la [modello multilingue](../../channels/using/multilingual-messages-template.md) contiene già tutti i parametri giusti, puoi fare clic direttamente sul pulsante **[!UICONTROL Create]** pulsante .

   ![](assets/multi_create4.png)

   Se necessario, aggiungi varianti utilizzando la variabile **[!UICONTROL Add an element]** pulsante . **[!UICONTROL Default]** la variante non deve essere eliminata. Quando è impostato su **[!UICONTROL default]**, [la lingua preferita del profilo](../../audiences/using/creating-profiles.md) viene utilizzato per scegliere la variante. È inoltre possibile impostare **[!UICONTROL Default]** variante di qualsiasi altra lingua.

1. Conferma la creazione dell’e-mail: viene quindi visualizzato il dashboard e-mail.
1. Definisci il contenuto dell’e-mail per ogni variante. A seconda del modello scelto, puoi definire diversi oggetti, diversi nomi di mittenti o diversi contenuti differenti. Utilizza il menu a discesa per navigare tra le diverse varianti dell’elemento. Per ulteriori informazioni, consulta la sezione [editor di contenuti](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Verifica e convalida il messaggio. Fai riferimento a [Invio della bozza](../../sending/using/sending-proofs.md) sezione .
1. Pianifica l’invio con il **[!UICONTROL Send after confirmation option]**.
1. Una volta inviata l’e-mail, puoi accedere ai relativi registri e rapporti per misurare il successo della campagna. Per ulteriori informazioni sul reporting, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

