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
TQID: https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 187
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
