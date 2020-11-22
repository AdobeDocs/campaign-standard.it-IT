---
solution: Campaign Standard
product: campaign
title: Aggiunta di contenuto dinamico Target
description: Scoprite come aggiungere  contenuto dinamico Adobe Target in una delle vostre  di distribuzione Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 5%

---


# Aggiunta di contenuto dinamico Target{#adding-target-dynamic-content}

&#39;integrazione con Adobe Target, è possibile aggiungere immagini dinamiche a una distribuzione per personalizzare i contenuti in base alle esperienze.

Durante la modifica di un messaggio e-mail, potete inserire un’immagine dinamica da  Adobe Target che verrà modificata a seconda dei destinatari.

Prima di accedere all’immagine in  Adobe Campaign, è necessario eseguire le seguenti operazioni in  Adobe Target:

* Create una o più offerte [di](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)reindirizzamento, nelle quali dovete specificare l&#39;URL dell&#39;immagine che state utilizzando.
* Create una o più [audience](https://docs.adobe.com/content/help/en/target/using/audiences/create-audiences/audiences.html), per definire il target dell&#39;attività.
* Create un&#39;attività di composer [esperienza basata su](https://docs.adobe.com/content/help/en/target/using/experiences/form-experience-composer.html) modulo, in cui dovete selezionare una rawbox e specificare diverse esperienze, a seconda del numero di offerte di reindirizzamento create. Per ogni esperienza, dovete selezionare una delle offerte di reindirizzamento create.
* Crea segmenti utilizzando le informazioni di  Adobe Campaign per specificare le esperienze. Per utilizzare i dati di  Adobe Campaign nelle regole di selezione dell&#39;offerta, è necessario specificare i dati nella rawbox in  Adobe Target.

1. Creare una consegna tramite e-mail.
1. Durante la modifica del contenuto di un&#39;e-mail o di una pagina di destinazione, passare a un blocco immagine, quindi selezionarlo **[!UICONTROL Dynamic image from Adobe Target]** tramite il menu contestuale.

   ![](assets/tar_insert_dynamic_image.png)

1. Selezionate l’immagine che verrà visualizzata per impostazione predefinita nel messaggio e-mail. Potete specificare direttamente l’URL dell’immagine o selezionare un’immagine condivisa tramite [Risorse](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   L&#39;integrazione supporta solo immagini statiche. Il resto del contenuto non è personalizzabile.

1. Inserite il nome della rawbox specificata in  Adobe Target.
1. Se utilizzate le autorizzazioni Enterprise nelle impostazioni in  Adobe Target, aggiungete la proprietà corrispondente in questo campo. Ulteriori informazioni sulle autorizzazioni di Target Enterprise in [questa pagina](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/properties-overview.html). Questo campo è facoltativo e non obbligatorio se non utilizzate le autorizzazioni Enterprise in Target.
1. In **[!UICONTROL Additional decision parameters]**, specificate la mappatura tra i campi definiti nei segmenti Adobe Target  e i campi Adobe Campaign .

   I campi Adobe Campaign  utilizzati devono essere stati specificati nella rawbox. In questo caso, definiremo esperienze diverse in base al genere del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Visualizzate l&#39;anteprima del messaggio e-mail per verificare se, quando selezionate profili diversi, l&#39;immagine inserita cambia a seconda dei parametri specificati nell&#39;attività di Adobe Target  e in  Adobe Campaign.

È ora possibile inviare l&#39;invio contenente l&#39;immagine dinamica. I suoi risultati sono reperibili  Adobe Target.

**Argomenti correlati:**

* [Adobe Target Portal](https://docs.adobe.com/content/help/it-IT/target/using/integrate/campaign-and-target.html)
* [Informazioni sulla progettazione del contenuto delle e-mail](../../designing/using/designing-content-in-adobe-campaign.md)
* [Personalizzare le immagini delle e-mail in video in tempo](https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html) reale

