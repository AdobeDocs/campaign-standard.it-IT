---
title: Informazioni sui messaggi SMS
seo-title: Informazioni sui messaggi SMS
description: Informazioni sui messaggi SMS
seo-description: Scopri le principali specificità del canale SMS in Adobe Campaign.
page-status-flag: mai attivato
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,procedura guidata;consegna,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 96001355220a9dd0cd3851d3f7de9f4dc8ea2782

---


# Informazioni sui messaggi SMS{#about-sms-messages}

Adobe Campaign consente di inviare messaggi SMS (Short Message Service).

>[!NOTE]
>
>Canale SMS è un add-on. Controllare il contratto di licenza.

Per i messaggi SMS, potete creare, modificare e personalizzare i messaggi solo in formato testo. Potete anche visualizzare l'anteprima dei messaggi SMS prima che vengano inviati.

La lunghezza di un messaggio SMS è limitata a 160 caratteri se è in codifica GSM e solo a 70 caratteri se è in Unicode. Tuttavia, alcuni caratteri speciali possono influenzare la lunghezza del messaggio. Per ulteriori informazioni, consulta la sezione Codifica [](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) SMS.

I messaggi SMS possono essere creati dal **[!UICONTROL Marketing activities]** menu, da una campagna o in un flusso di lavoro; vedete [Creazione di un messaggio](../../channels/using/creating-an-sms-message.md)SMS.

Per inviare messaggi SMS a un telefono cellulare è necessario:

* Account **[!UICONTROL Routing]** esterno configurato sul **[!UICONTROL Mobile (SMS)]** canale con la **[!UICONTROL Bulk delivery]** modalità. Per ulteriori informazioni, vedere la sezione [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) .
* Un modello di consegna correttamente collegato a questo account esterno.

**Argomenti correlati:**

* [Gestione dei modelli](../../start/using/about-templates.md)
* [Configurazione SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [SMS report](../../reporting/using/sms-report.md)

## Modello di consegna SMS {#sms-delivery-template}

Adobe Campaign offre un modello di consegna per i dispositivi mobili. Questo modello deve essere collegato correttamente all'account esterno utilizzato per il **[!UICONTROL Mobile (SMS)]** canale. Per accedervi e modificarlo:

1. Selezionate **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** dal menu avanzato.
1. Passate il puntatore del mouse sul **[!UICONTROL Send via SMS]** modello e selezionate l'opzione **Duplica elemento** .
1. Selezionate il nuovo modello.
1. Fate clic sul **[!UICONTROL Edit properties]** pulsante.
1. Nella **[!UICONTROL Advanced parameters]** sezione delle proprietà del modello, accertatevi che il modello sia collegato all'account esterno da utilizzare per la distribuzione di SMS.

   ![](assets/sms_template.png)

**Argomenti correlati:**

* [Gestione dei modelli](../../start/using/about-templates.md)

