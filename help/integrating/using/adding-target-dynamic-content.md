---
title: Aggiunta di contenuto dinamico Target
description: Scopri come aggiungere contenuto dinamico Adobe Target in una delle distribuzioni di Adobe Campaign.
page-status-flag: mai attivato
uuid: b3cc045f-7924-480e-8c61-8246510f3adb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: con campagna e destinazione
discoiquuid: 45ddf7b7-98f7-4fdd-bb4a-49ec8490e877
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Aggiunta di contenuto dinamico Target{#adding-target-dynamic-content}

Grazie all'integrazione con Adobe Target, è possibile aggiungere immagini dinamiche a una distribuzione per personalizzare i contenuti in base alle esperienze.

Durante la modifica di un messaggio e-mail, puoi inserire un'immagine dinamica da Adobe Target che verrà modificata a seconda dei destinatari.

Prima di accedere all'immagine in Adobe Campaign, è necessario effettuare le seguenti operazioni in Adobe Target:

* Create una o più offerte [di](https://docs.adobe.com/content/help/en/target/using/experiences/offers/offer-redirect.html)reindirizzamento, nelle quali dovete specificare l'URL dell'immagine che state utilizzando.
* Create una o più [audience](https://marketing.adobe.com/resources/help/en_US/target/ov/c_about_segments.html), per definire il target dell'attività.
* Create un'attività di composer [esperienza basata su](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html) modulo, in cui dovete selezionare una rawbox e specificare diverse esperienze, a seconda del numero di offerte di reindirizzamento create. Per ogni esperienza, dovete selezionare una delle offerte di reindirizzamento create.
* Crea segmenti utilizzando le informazioni di Adobe Campaign per specificare le esperienze. Per utilizzare i dati di Adobe Campaign nelle regole di selezione dell'offerta, devi specificare i dati nella rawbox in Adobe Target.

1. Creare una consegna tramite e-mail.
1. Durante la modifica del contenuto di un'e-mail o di una pagina di destinazione, passare a un blocco immagine, quindi selezionarlo **[!UICONTROL Dynamic image from Adobe Target]** tramite il menu contestuale.

   ![](assets/tar_insert_dynamic_image.png)

1. Selezionate l’immagine che verrà visualizzata per impostazione predefinita nel messaggio e-mail. Potete specificare direttamente l’URL dell’immagine o selezionare un’immagine condivisa tramite [Risorse](../../integrating/using/working-with-campaign-and-assets-core-service.md).

   L'integrazione supporta solo immagini statiche. Il resto del contenuto non è personalizzabile.

1. Immettete il nome della rawbox specificata in Adobe Target.
1. Se utilizzate le autorizzazioni Enterprise nelle impostazioni in Adobe Target, aggiungete la proprietà corrispondente in questo campo. Ulteriori informazioni sulle autorizzazioni di Target Enterprise in [questa pagina](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html). Questo campo è facoltativo e non obbligatorio se non utilizzate le autorizzazioni Enterprise in Target.
1. In **[!UICONTROL Additional decision parameters]**, specificate la mappatura tra i campi definiti nei segmenti di Adobe Target e i campi di Adobe Campaign.

   I campi di Adobe Campaign utilizzati devono essere stati specificati nella rawbox. In questo caso, definiremo esperienze diverse in base al genere del destinatario.

   ![](assets/tar_additional_decisionning_parameters.png)

1. Visualizzate l'anteprima del messaggio e-mail per verificare se, quando selezionate profili diversi, l'immagine inserita cambia in base ai parametri specificati nell'attività Adobe Target e in Adobe Campaign.

È ora possibile inviare la distribuzione contenente l'immagine dinamica. I risultati sono disponibili in Adobe Target.

**Argomenti correlati:**

* [Adobe Target Portal](https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html)
* [Informazioni sulla progettazione del contenuto delle e-mail](../../designing/using/overview.md)
* [Personalizzare le immagini delle e-mail in video in tempo](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html) reale

