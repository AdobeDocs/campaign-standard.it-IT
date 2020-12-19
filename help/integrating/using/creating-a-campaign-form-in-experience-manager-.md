---
solution: Campaign Standard
product: campaign
title: 'Creazione di un modulo Campaign in Experience Manager '
description: Con l'integrazione di Adobe Experience Manager, è possibile creare moduli direttamente in AEM per creare e aggiornare profili o gestire iscrizioni.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# Creazione di un modulo Campaign in Experience Manager {#creating-a-campaign-form-in-experience-manager}

È possibile creare &quot;moduli&quot; sui siti AEM e mappare i campi di un modulo sui campi del database Adobe Campaign . Questo consente di creare e aggiornare profili o gestire le iscrizioni a un servizio.

Per creare un modulo Adobe Campaign  sul sito AEM:

1. Nel sito AEM, create una nuova pagina basata sul modello **profilo Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. Nelle proprietà della pagina, selezionate la **[!UICONTROL Cloud Service]** corrispondente all&#39;istanza di Adobe Campaign .

   ![](assets/aem_content_forms_2.png)

1. Selezionare il tipo di modulo dal componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Salva profilo**
   * **Adobe Campaign: Iscriviti ai servizi**
   * **Adobe Campaign: Annulla sottoscrizione a servizi**

1. Modificare il contenuto del modulo aggiungendo campi e componenti diversi che è possibile mappare ai campi del database Adobe Campaign .
1. Verificare e pubblicare il modulo per renderlo accessibile sul sito AEM.

Per ulteriori informazioni, consulta la [documentazione dettagliata](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
