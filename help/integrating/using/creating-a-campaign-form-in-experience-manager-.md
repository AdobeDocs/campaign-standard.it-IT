---
title: 'Creazione di un modulo Campaign in Experience Manager '
description: Con l'integrazione di Adobe Experience Manager, puoi creare moduli direttamente in AEM per creare e aggiornare profili o gestire iscrizioni.
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Creazione di un modulo Campaign in Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puoi creare &quot;moduli&quot; sui tuoi siti AEM e mappare i campi di un modulo sui campi del database Adobe Campaign. Questo consente di creare e aggiornare profili o gestire le iscrizioni a un servizio.

Per creare un modulo Adobe Campaign sul sito AEM:

1. Nel tuo sito AEM, crea una nuova pagina basata sul modello di profilo **di** Adobe Campaign.

   ![](assets/aem_content_forms.png)

1. Nelle proprietà della pagina, seleziona il **[!UICONTROL Cloud Service]**corrispondente all’istanza di Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Selezionate il tipo di modulo dal **[!UICONTROL Form Start]**componente:

   * **Adobe Campaign: Salva profilo**
   * **Adobe Campaign: Iscriviti ai servizi**
   * **Adobe Campaign: Annulla sottoscrizione a servizi**

1. Modifica il contenuto del modulo aggiungendo campi e componenti diversi che puoi mappare ai campi del database di Adobe Campaign.
1. Sottoponete a test e pubblicate il modulo per renderlo accessibile sul sito AEM.

Per ulteriori informazioni, consulta la documentazione [](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html)dettagliata.
