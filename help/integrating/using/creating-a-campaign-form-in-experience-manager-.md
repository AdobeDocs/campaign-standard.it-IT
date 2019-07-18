---
title: 'Creazione di un modulo Campaign in Experience Manager '
seo-title: 'Creazione di un modulo Campaign in Experience Manager '
description: 'Creazione di un modulo Campaign in Experience Manager '
seo-description: Con l'integrazione di Adobe Experience Manager, potete creare moduli direttamente in AEM per creare e aggiornare profili o gestire iscrizioni.
page-status-flag: never-activated
uuid: 43057 f 81-d 47 d -4 b 96-b 150-217 c 289 cd 608
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4 a 8 b 5807-87 dd -4 db 4-bd 67-890 f 0 adae 932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a Campaign form in Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puoi creare i "moduli" nei siti AEM e mappare i campi di un modulo nei campi del database Adobe Campaign. Questo consente di creare e aggiornare i profili o di gestire le iscrizioni a un servizio.

Per creare un modulo Adobe Campaign sul sito AEM:

1. Nel sito AEM, crea una nuova pagina basata sul modello** Adobe Campaign Profile**.

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. Select the form type from the **[!UICONTROL Form Start]** component:

   * **Adobe Campaign: Salva profilo**
   * **Adobe Campaign: Iscrizione ai Servizi**
   * **Adobe Campaign: Annulla iscrizione ai servizi**

1. Modifica il contenuto del modulo aggiungendo campi e componenti diversi da mappare sui campi del database di Adobe Campaign.
1. Verificate e pubblicate il modulo per renderlo accessibile sul sito AEM.

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html).
