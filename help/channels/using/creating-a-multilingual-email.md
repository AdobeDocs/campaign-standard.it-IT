---
title: Creazione di un messaggio e-mail multilingue
description: Segui questi passaggi per creare un’e-mail multilingue indirizzata a destinatari con lingue preferite diverse.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
TQID: 'https://experienceleague.adobe.com/dz14KptzZtyP8Oo-RaYvZKP5D3L4akcJJmY2f-p1nuE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: 50d1fd2e-0fc9-5627-bbc9-02dbc9d15e08
    internal-label: Email
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 24%
---
# Creazione di un messaggio e-mail multilingue{#creating-a-multilingual-email}

Puoi inviare un’e-mail multilingue a profili con diverse lingue preferite: ogni profilo riceverà una variante dell’e-mail nella lingua preferita.

A questo scopo, verifica di disporre di un modello e-mail multilingue. In caso contrario, scopri come crearne uno in [questa sezione](../../channels/using/multilingual-messages-template.md).

Il pubblico si basa su profili con informazioni complete sulla lingua preferita.

1. Crea un nuovo messaggio e-mail basato su un [modello multilingue](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Definisci le proprietà generali e il pubblico target dell’e-mail, come per un’e-mail standard. Consulta la sezione [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md).

1. Nel quarto passaggio della procedura guidata di creazione, definisci le opzioni di variante. Se il [modello multilingue](../../channels/using/multilingual-messages-template.md) contiene già tutti i parametri corretti, è possibile fare clic direttamente sul pulsante **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Se necessario, aggiungere varianti utilizzando il pulsante **[!UICONTROL Add an element]**. La variante **[!UICONTROL Default]** non deve essere eliminata. Se è impostato su **[!UICONTROL default]**, [per scegliere la variante viene utilizzata la lingua preferita del profilo](../../audiences/using/creating-profiles.md). È inoltre possibile impostare la variante **[!UICONTROL Default]** su qualsiasi altra lingua.

1. Conferma creazione e-mail: viene quindi visualizzato il dashboard e-mail.
1. Definisci il contenuto dell’e-mail per ogni variante. A seconda del modello scelto, puoi definire diversi oggetti, diversi nomi di mittenti o diversi contenuti differenti. Utilizza il menu a discesa per spostarti tra le diverse varianti dell’elemento. Per ulteriori informazioni, consulta la sezione [editor di contenuti](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Verifica e convalida il messaggio. Consulta la sezione [Invio della bozza](../../sending/using/sending-proofs.md).
1. Pianifica l&#39;invio con **[!UICONTROL Send after confirmation option]**.
1. Una volta inviata l’e-mail, puoi accedere ai relativi registri e rapporti per misurare il successo della campagna. Per ulteriori informazioni sul reporting, consulta [questa sezione](../../reporting/using/about-dynamic-reports.md).

