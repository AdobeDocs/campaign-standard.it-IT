---
title: Creazione di contenuti e-mail in Adobe Experience Manager.
description: Con l’integrazione Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 2%

---

# Importazione di un contenuto Adobe Experience Manager in un’e-mail Adobe Campaign {#creating-email-aem}

Utilizzando questo documento, scoprirai come creare e gestire il contenuto delle e-mail in Adobe Experience Manager, quindi utilizzalo per le campagne di marketing importandole nelle e-mail in Adobe Campaign Standard.

Sussistono i seguenti prerequisiti:

* Accesso a un’istanza AEM configurata per l’integrazione.
* Accesso a un’istanza di Adobe Campaign configurata per l’integrazione.
* Un modello e-mail Adobe Campaign configurato per la ricezione AEM contenuto.

## Accesso alle e-mail in Adobe Experience Manager {#email-content-aem}

Accedi alla tua istanza di authoring Adobe Experience Manager e sfoglia il tuo sito per accedere alla cartella contenente il tuo contenuto e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creazione di nuovi contenuti e-mail in Adobe Experience Manager {#creating-email-content-aem}

Sono disponibili diversi modelli specifici di Adobe Campaign. È necessario utilizzare uno di questi modelli in quanto contengono componenti predefiniti supportati da Adobe Campaign.

Per impostazione predefinita, due modelli predefiniti consentono di creare contenuti e-mail per Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: questo modello contiene un contenuto standard che puoi personalizzare. Puoi scegliere tra Adobe Campaign Email (AC6.1) e Adobe Campaign Email (ACS).
* **[!UICONTROL Importer Page]**: questo modello ti consente di importare un file ZIP contenente un file HTML con contenuto che potrai quindi personalizzare.

1. In Adobe Experience Manager, crea una nuova **[!UICONTROL Page]**.

1. Seleziona la **[!UICONTROL Adobe Campaign Email]** modello. Per i passaggi dettagliati, fai riferimento al video seguente.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Apri il nuovo contenuto e-mail.

1. In **[!UICONTROL Page properties]**, set **[!UICONTROL Adobe Campaign]** come **[!UICONTROL Cloud Service Configuration]**. Questo consente la comunicazione tra il contenuto e l’istanza Adobe Campaign.

   Per ulteriori informazioni, guarda il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Modifica e invio di un’e-mail {#editing-email-aem}

Puoi modificare il contenuto dell’e-mail aggiungendo componenti e risorse. I campi di personalizzazione possono essere utilizzati per inviare un messaggio più pertinente in base ai dati dei destinatari in Adobe Campaign.

Per creare un contenuto e-mail in Adobe Experience Manager:

1. Modificare l’oggetto e **[!UICONTROL Plain text]** versione del messaggio e-mail mediante l’accesso al **[!UICONTROL Page properties]** > **[!UICONTROL Email]** scheda dalla barra laterale.

1. Aggiungi **[!UICONTROL Personalization fields]** attraverso **[!UICONTROL Text & Personalization]** componente. Ogni componente corrisponde a un utilizzo specifico: inserimento di immagini, aggiunta di personalizzazioni, ecc.

   Per ulteriori informazioni, guarda il seguente video:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Da **[!UICONTROL Workflow]** seleziona la scheda **[!UICONTROL Approve for Adobe Campaign]** flusso di lavoro di convalida. Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto non approvato.

1. Una volta definiti il contenuto e i parametri di invio, puoi procedere all’approvazione, alla preparazione e all’invio dell’e-mail in Adobe Campaign Standard.

   Per ulteriori informazioni, guarda il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
