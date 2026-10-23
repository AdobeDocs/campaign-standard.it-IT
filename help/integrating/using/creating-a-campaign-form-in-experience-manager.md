---
title: Creazione di un modulo Campaign in Experience Manager
description: Con l’integrazione di Adobe Experience Manager, puoi creare moduli direttamente in AEM per creare e aggiornare profili o gestire abbonamenti.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
TQID: 'https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 11%
---
# Creazione di un modulo Campaign in Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puoi creare &quot;moduli&quot; sui tuoi siti AEM e mappare i campi di un modulo ai campi del database Adobe Campaign. Questo consente di creare e aggiornare profili o gestire gli abbonamenti a un servizio.

Per creare un modulo Adobe Campaign sul sito AEM:

1. Nel tuo sito AEM, crea una nuova pagina basata sul modello **Adobe Campaign Profile**.

   ![](assets/aem_content_forms.png)

1. Nelle proprietà della pagina, seleziona **[!UICONTROL Cloud Service]** corrispondente alla tua istanza di Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Selezionare il tipo di modulo dal componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Salva profilo**
   * **Adobe Campaign: abbonati a servizi**
   * **Adobe Campaign: Annulla abbonamento a servizi**

1. Modifica il contenuto del modulo aggiungendo diversi campi e componenti che puoi mappare ai campi del database di Adobe Campaign.
1. Verifica e pubblica il modulo per renderlo accessibile sul tuo sito AEM.

Per ulteriori informazioni, consulta la [documentazione dettagliata](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=it).
