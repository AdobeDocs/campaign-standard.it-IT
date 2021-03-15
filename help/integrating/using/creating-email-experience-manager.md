---
solution: Campaign Standard
product: campaign
title: Creazione di contenuti e-mail in Adobe Experience Manager.
description: Con l’integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 2%

---


# Importazione di contenuti Adobe Experience Manager in un messaggio e-mail Adobe Campaign {#creating-email-aem}

Utilizzando questo documento, scoprirai come creare e gestire i contenuti delle e-mail in Adobe Experience Manager, quindi utilizzarli per le campagne di marketing importandoli nelle e-mail in Adobe Campaign Standard.

Sussistono i seguenti prerequisiti:

* Accesso a un’istanza AEM configurata per l’integrazione.
* Accesso a un’istanza di Adobe Campaign configurata per l’integrazione.
* Un modello e-mail Adobe Campaign configurato per la ricezione AEM contenuto.

## Accesso alle e-mail in Adobe Experience Manager {#email-content-aem}

Accedi alla tua istanza di authoring Adobe Experience Manager e sfoglia il tuo sito per accedere alla cartella contenente il tuo contenuto e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Creazione di nuovo contenuto e-mail in Adobe Experience Manager {#creating-email-content-aem}

Sono disponibili diversi modelli specifici di Adobe Campaign. È necessario utilizzare uno di questi modelli in quanto contengono componenti predefiniti supportati da Adobe Campaign.

Per impostazione predefinita, due modelli predefiniti consentono di creare contenuti e-mail per Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: questo modello contiene un contenuto standard che puoi personalizzare. Puoi scegliere tra Adobe Campaign Email (AC6.1) e Adobe Campaign Email (ACS).
* **[!UICONTROL Importer Page]**: questo modello ti consente di importare un file ZIP contenente un file HTML con contenuto che potrai quindi personalizzare.

1. In Adobe Experience Manager, crea un nuovo **[!UICONTROL Page]**.

1. Selezionare il modello **[!UICONTROL Adobe Campaign Email]**. Per i passaggi dettagliati, fai riferimento al video seguente.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Apri il nuovo contenuto e-mail.

1. In **[!UICONTROL Page properties]**, imposta **[!UICONTROL Adobe Campaign]** come **[!UICONTROL Cloud Service Configuration]**. Questo consente la comunicazione tra il contenuto e l’istanza Adobe Campaign.

   Per ulteriori informazioni, guarda il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Modifica e invio di un messaggio e-mail {#editing-email-aem}

Puoi modificare il contenuto dell’e-mail aggiungendo componenti e risorse. I campi di personalizzazione possono essere utilizzati per inviare un messaggio più pertinente in base ai dati dei destinatari in Adobe Campaign.

Per creare un contenuto e-mail in Adobe Experience Manager:

1. Modifica l’oggetto e la versione **[!UICONTROL Plain text]** del messaggio e-mail accedendo alla scheda **[!UICONTROL Page properties]** > **[!UICONTROL Email]** dalla barra laterale.

1. Aggiungi **[!UICONTROL Personalization fields]** tramite il componente **[!UICONTROL Text & Personalization]** . Ogni componente corrisponde a un utilizzo specifico: inserimento di immagini, aggiunta di personalizzazioni, ecc.

   Per ulteriori informazioni, guarda il seguente video:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Dalla scheda **[!UICONTROL Workflow]** , seleziona il flusso di lavoro di convalida **[!UICONTROL Approve for Adobe Campaign]** . Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto non approvato.

1. Una volta definiti il contenuto e i parametri di invio, puoi procedere all’approvazione, alla preparazione e all’invio dell’e-mail in Adobe Campaign Standard.

   Per ulteriori informazioni, guarda il seguente video:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
