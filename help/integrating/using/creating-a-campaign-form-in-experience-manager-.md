---
title: 'Creazione di un modulo Campaign in Experience Manager '
description: Con l'integrazione di Adobe Experience Manager, è possibile creare moduli direttamente in AEM per creare e aggiornare profili o gestire iscrizioni.
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# Creazione di un modulo Campaign in Experience Manager {#creating-a-campaign-form-in-experience-manager}

È possibile creare &quot;moduli&quot; sui siti AEM e mappare i campi di un modulo sui campi del database Adobe Campaign . Questo consente di creare e aggiornare profili o gestire le iscrizioni a un servizio.

Per creare un modulo Adobe Campaign  sul sito AEM:

1. Nel sito AEM, create una nuova pagina basata sul modello di profilo **Adobe Campaign** .

   ![](assets/aem_content_forms.png)

1. Nelle proprietà della pagina, selezionate la **[!UICONTROL Cloud Service]** corrispondente all’istanza di Adobe Campaign .

   ![](assets/aem_content_forms_2.png)

1. Selezionate il tipo di modulo dal **[!UICONTROL Form Start]** componente:

   * **Adobe Campaign: Salva profilo**
   * **Adobe Campaign: Iscriviti ai servizi**
   * **Adobe Campaign: Annulla sottoscrizione a servizi**

1. Modificare il contenuto del modulo aggiungendo campi e componenti diversi che è possibile mappare ai campi del database Adobe Campaign .
1. Verificare e pubblicare il modulo per renderlo accessibile sul sito AEM.

Per ulteriori informazioni, consulta la [documentazione dettagliata](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
