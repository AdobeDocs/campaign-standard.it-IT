---
solution: Campaign Standard
product: campaign
title: Creazione di contenuti e-mail in Adobe Experience Manager.
description: Con l'integrazione Adobe Experience Manager, potete creare contenuti direttamente in AEM e usarli successivamente in  Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---


# Importazione di un contenuto Adobe Experience Manager in un  e-mail Adobe Campaign {#creating-email-aem}

Questo documento illustra come creare e gestire i contenuti delle e-mail in Adobe Experience Manager, quindi utilizzarli per le campagne di marketing importandoli nelle e-mail in  Adobe Campaign Standard.

Sussistono i seguenti prerequisiti:

* Accesso a un&#39;istanza AEM configurata per l&#39;integrazione.
* Accesso a un&#39;istanza Adobe Campaign  configurata per l&#39;integrazione.
* Un modello e-mail Adobe Campaign  configurato per la ricezione AEM contenuto.

## Accesso alle e-mail in Adobe Experience Manager {#email-content-aem}

Accedete all’istanza di authoring Adobe Experience Manager e sfogliate il sito per accedere alla cartella che contiene il contenuto dell’e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creazione di nuovo contenuto e-mail in Adobe Experience Manager {#creating-email-content-aem}

Sono disponibili diversi modelli specifici per  Adobe Campaign. È necessario utilizzare uno di questi modelli poiché contengono componenti predefiniti supportati da  Adobe Campaign.

Per impostazione predefinita, due modelli predefiniti consentono di creare contenuti e-mail per  Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: questo modello contiene un contenuto standard che potete personalizzare. Potete scegliere tra  e-mail Adobe Campaign (AC6.1) e  e-mail Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**: questo modello consente di importare un file ZIP contenente un file HTML con contenuto che sarà quindi possibile personalizzare.

1. In Adobe Experience Manager, create un nuovo **[!UICONTROL Page]**.

1. Selezionare il modello **[!UICONTROL Adobe Campaign Email]**. Per informazioni dettagliate, consultate il seguente video.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Aprite il nuovo contenuto e-mail.

1. In **[!UICONTROL Page properties]**, impostare **[!UICONTROL Adobe Campaign]** come **[!UICONTROL Cloud Service Configuration]**. Questo consente la comunicazione tra il contenuto e l&#39;istanza Adobe Campaign .

   Per ulteriori informazioni, guardate il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Modifica e invio di un&#39;e-mail {#editing-email-aem}

Potete modificare il contenuto dell’e-mail aggiungendo componenti e risorse. I campi di personalizzazione possono essere utilizzati per inviare un messaggio più rilevante in base ai dati dei destinatari in  Adobe Campaign.

Per creare un contenuto e-mail in Adobe Experience Manager:

1. Modificate l&#39;oggetto e la versione **[!UICONTROL Plain text]** del messaggio e-mail accedendo alla scheda **[!UICONTROL Page properties]** > **[!UICONTROL Email]** dalla barra laterale.

1. Aggiungete **[!UICONTROL Personalization fields]** al componente **[!UICONTROL Text & Personalization]**. Ciascun componente corrisponde a un utilizzo specifico: inserimento di immagini, aggiunta di personalizzazione, ecc.

   Per ulteriori informazioni, guardate il seguente video:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Dalla scheda **[!UICONTROL Workflow]**, selezionare il flusso di lavoro di convalida **[!UICONTROL Approve for Adobe Campaign]**. Non potrete inviare un&#39;e-mail in  Adobe Campaign se utilizza un contenuto non approvato.

1. Una volta definiti il contenuto e i parametri di invio, potete procedere all’approvazione, alla preparazione e all’invio dell’e-mail in  Adobe Campaign Standard.

   Per ulteriori informazioni, guardate il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
