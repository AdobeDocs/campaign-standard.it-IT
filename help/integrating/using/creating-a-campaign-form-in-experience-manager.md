---
title: Creazione di un modulo Campaign in Experience Manager
description: Con l’integrazione di Adobe Experience Manager, puoi creare moduli direttamente nell’AEM per creare e aggiornare profili o gestire abbonamenti.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---

# Creazione di un modulo Campaign in Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puoi creare &quot;moduli&quot; sui siti AEM e mappare i campi di un modulo ai campi del database di Adobe Campaign. Questo consente di creare e aggiornare profili o gestire gli abbonamenti a un servizio.

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
1. Testare e pubblicare il modulo per renderlo accessibile sul sito AEM.

Per ulteriori informazioni, consulta la [documentazione dettagliata](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html?lang=it).
