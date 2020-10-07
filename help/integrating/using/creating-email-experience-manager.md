---
title: Creazione di contenuti e-mail in Adobe Experience Manager.
description: Con l'integrazione Adobe Experience Manager, potete creare contenuti direttamente in AEM e usarli successivamente in  Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---


# Importazione di un contenuto Adobe Experience Manager in un messaggio e-mail Adobe Campaign  {#creating-email-aem}

Questo documento illustra come creare e gestire i contenuti delle e-mail in Adobe Experience Manager, quindi utilizzarli per le campagne di marketing importandoli nelle e-mail in  Adobe Campaign Standard.

Sussistono i seguenti prerequisiti:

* Accesso a un&#39;istanza AEM configurata per l&#39;integrazione.
* Accesso a un&#39;istanza Adobe Campaign  configurata per l&#39;integrazione.
* Un modello e-mail Adobe Campaign  configurato per la ricezione AEM contenuto.

## Accesso alle e-mail in Adobe Experience Manager {#email-content-aem}

Accedete all’istanza di authoring Adobe Experience Manager e sfogliate il sito per accedere alla cartella che contiene il contenuto dell’e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creating new email content in Adobe Experience Manager {#creating-email-content-aem}

Sono disponibili diversi modelli specifici per  Adobe Campaign. È necessario utilizzare uno di questi modelli poiché contengono componenti predefiniti supportati da  Adobe Campaign.

Per impostazione predefinita, due modelli predefiniti consentono di creare contenuti e-mail per  Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: questo modello contiene un contenuto standard che potete personalizzare. Potete scegliere tra  e-mail Adobe Campaign (AC6.1) e  e-mail Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**: questo modello consente di importare un file ZIP contenente un file HTML con contenuto che sarà quindi possibile personalizzare.

1. In Adobe Experience Manager, create una nuova **[!UICONTROL Page]**.

1. Selezionate il **[!UICONTROL Adobe Campaign Email]** modello. Per informazioni dettagliate, consultate il seguente video.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Aprite il nuovo contenuto e-mail.

1. In **[!UICONTROL Page properties]**, impostate **[!UICONTROL Adobe Campaign]** come **[!UICONTROL Cloud Service Configuration]**. Questo consente la comunicazione tra il contenuto e l&#39;istanza Adobe Campaign .

   Per ulteriori informazioni, guardate il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Modifica e invio di un messaggio e-mail {#editing-email-aem}

Potete modificare il contenuto dell’e-mail aggiungendo componenti e risorse. I campi di personalizzazione possono essere utilizzati per inviare un messaggio più rilevante in base ai dati dei destinatari in  Adobe Campaign.

Per creare un contenuto e-mail in Adobe Experience Manager:

1. Modificate l’oggetto e la **[!UICONTROL Plain text]** versione del messaggio e-mail accedendo alla scheda **[!UICONTROL Page properties]** > **[!UICONTROL Email]** dalla barra laterale.

1. Aggiungi **[!UICONTROL Personalization fields]** tramite il **[!UICONTROL Text & Personalization]** componente. Ciascun componente corrisponde a un utilizzo specifico: inserimento di immagini, aggiunta di personalizzazione, ecc.

   Per ulteriori informazioni, guardate il seguente video:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Dalla **[!UICONTROL Workflow]** scheda, selezionare il flusso di lavoro di **[!UICONTROL Approve for Adobe Campaign]** convalida. Non potrete inviare un&#39;e-mail in  Adobe Campaign se utilizza un contenuto non approvato.

1. Una volta definiti il contenuto e i parametri di invio, potete procedere all’approvazione, alla preparazione e all’invio dell’e-mail in  Adobe Campaign Standard.

   Per ulteriori informazioni, guardate il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
