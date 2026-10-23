---
title: Informazioni sui messaggi SMS
description: Scopri le principali specificità del canale SMS in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
TQID: 'https://experienceleague.adobe.com/d0IcWAf5j-JUAKKeC84Fxm-mZsfuMJ2k6GmhQfdQeFk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 29%
---
# Informazioni sui messaggi SMS{#about-sms-messages}

Adobe Campaign consente di inviare messaggi SMS (Short Message Service).

>[!NOTE]
>
>Il canale SMS è un componente aggiuntivo. Controlla il contratto di licenza.

Per i messaggi SMS, puoi creare, modificare e personalizzare i messaggi solo in formato testo. Puoi anche visualizzare in anteprima i messaggi SMS prima che vengano inviati.

La lunghezza di un messaggio SMS è limitata a 160 caratteri se è in codifica GSM e a 70 caratteri se è in Unicode. Tuttavia, alcuni caratteri speciali possono influenzare la lunghezza del messaggio. Per ulteriori informazioni, consulta la sezione [Codifica SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

I messaggi SMS possono essere creati dal menu **[!UICONTROL Marketing activities]**, da una campagna o in un flusso di lavoro. Vedere [Creazione di un messaggio SMS](../../channels/using/creating-an-sms-message.md).

Per inviare messaggi SMS a un telefono cellulare è necessario:

* Un account esterno di **[!UICONTROL Routing]** configurato sul canale **[!UICONTROL Mobile (SMS)]** con la modalità **[!UICONTROL Bulk delivery]**. Per ulteriori informazioni, consulta la sezione [Indirizzamento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Un modello di consegna correttamente collegato a questo account esterno.

**Argomenti correlati:**

* [Gestione dei modelli](../../start/using/marketing-activity-templates.md)
* [Configurazione SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Rapporto SMS](../../reporting/using/sms-report.md)
* [Guida di Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Modello di consegna SMS {#sms-delivery-template}

Adobe Campaign offre un modello di consegna per dispositivi mobili. Questo modello deve essere collegato correttamente all&#39;account esterno utilizzato per il canale **[!UICONTROL Mobile (SMS)]**. Per accedervi e modificarlo:

1. Selezionare **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** dal menu avanzato.
1. Passa il puntatore del mouse sul modello **[!UICONTROL Send via SMS]** e seleziona l&#39;opzione **Duplica elemento**.
1. Seleziona il nuovo modello.
1. Fai clic sul pulsante **[!UICONTROL Edit properties]**.
1. Nella sezione **[!UICONTROL Advanced parameters]** delle proprietà del modello, assicurati che il modello sia collegato all’account esterno da utilizzare per la consegna di SMS.

   ![](assets/sms_template.png)

**Argomenti correlati:**

* [Gestione dei modelli](../../start/using/marketing-activity-templates.md)
