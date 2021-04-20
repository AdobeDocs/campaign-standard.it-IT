---
solution: Campaign Standard
product: campaign
title: 'Creazione di un modulo Campaign in Experience Manager '
description: Con l’integrazione di Adobe Experience Manager, puoi creare moduli direttamente in AEM per creare e aggiornare profili o gestire abbonamenti.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 11%

---


# Creazione di un modulo Campaign in Experience Manager {#creating-a-campaign-form-in-experience-manager}

È possibile creare &quot;moduli&quot; sui siti di AEM e mappare i campi di un modulo ai campi del database Adobe Campaign. Ciò ti consente di creare e aggiornare profili o gestire gli abbonamenti a un servizio.

Per creare un modulo Adobe Campaign sul sito AEM:

1. Nel sito AEM, crea una nuova pagina basata sul modello **Profilo Adobe Campaign** .

   ![](assets/aem_content_forms.png)

1. Nelle proprietà della pagina, seleziona il **[!UICONTROL Cloud Service]** corrispondente alla tua istanza Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Seleziona il tipo di modulo dal componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Salva profilo**
   * **Adobe Campaign: Iscriviti ai servizi**
   * **Adobe Campaign: Annulla sottoscrizione a servizi**

1. Modificare il contenuto del modulo aggiungendo campi e componenti diversi che è possibile mappare ai campi del database di Adobe Campaign.
1. Verificare e pubblicare il modulo per renderlo accessibile sul sito AEM.

Per ulteriori informazioni, consulta la [documentazione dettagliata](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
