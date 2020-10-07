---
title: Informazioni sui messaggi SMS
description: Scopri le principali specificità del canale SMS in  Adobe Campaign.
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 23%

---


# Informazioni sui messaggi SMS{#about-sms-messages}

 Adobe Campaign consente di inviare messaggi SMS (Short Message Service).

>[!NOTE]
>
>Canale SMS è un add-on. Controlla il contratto di licenza.

Per i messaggi SMS, potete creare, modificare e personalizzare i messaggi solo in formato testo. È inoltre possibile visualizzare l&#39;anteprima dei messaggi SMS prima dell&#39;invio.

La lunghezza di un messaggio SMS è limitata a 160 caratteri se è in codifica GSM e solo a 70 caratteri se è in Unicode. Tuttavia, alcuni caratteri speciali possono influenzare la lunghezza del messaggio. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

I messaggi SMS possono essere creati dal **[!UICONTROL Marketing activities]** menu, da una campagna o in un flusso di lavoro; vedete [Creazione di un messaggio](../../channels/using/creating-an-sms-message.md)SMS.

Per inviare messaggi SMS a un telefono cellulare è necessario:

* Un account esterno di **[!UICONTROL Routing]** configurato sul canale **[!UICONTROL Mobile (SMS)]** con la modalità **[!UICONTROL Bulk delivery]**. Per ulteriori informazioni, consulta la sezione [Indirizzamento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Un modello di consegna correttamente collegato a questo account esterno.

**Argomenti correlati:**

* [Gestione dei modelli](../../start/using/marketing-activity-templates.md)
* [Configurazione SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Report SMS](../../reporting/using/sms-report.md)
* [Guida a Campaign Standard per dispositivi mobili](https://helpx.adobe.com/it/campaign/kb/acs-mobile.html)

## Modello di consegna SMS {#sms-delivery-template}

 Adobe Campaign offre un modello di consegna per dispositivi mobili. Questo modello deve essere collegato correttamente all&#39;account esterno utilizzato per il **[!UICONTROL Mobile (SMS)]** canale. Per accedervi e modificarlo:

1. Selezionate **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** dal menu avanzato.
1. Passate il puntatore del mouse sul **[!UICONTROL Send via SMS]** modello e selezionate l&#39;opzione **Duplica elemento** .
1. Selezionate il nuovo modello.
1. Fai clic sul pulsante **[!UICONTROL Edit properties]**.
1. Nella **[!UICONTROL Advanced parameters]** sezione delle proprietà del modello, accertatevi che il modello sia collegato all&#39;account esterno da utilizzare per la distribuzione di SMS.

   ![](assets/sms_template.png)

**Argomenti correlati:**

* [Gestione dei modelli](../../start/using/marketing-activity-templates.md)
