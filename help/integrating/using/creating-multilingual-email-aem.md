---
title: Creazione di un messaggio e-mail multilingue con l’integrazione Adobe Experience Manager.
description: Con l’integrazione di Adobe Experience Manager, puoi creare contenuti direttamente nell’AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 3%

---

# Creazione di un’e-mail multilingue con l’integrazione Adobe Experience Manager {#creating-multilingual-email-aem}

Questo documento illustra come creare un messaggio e-mail multilingue utilizzando copie in lingua e contenuto di Adobe Experience Manager.

Sussistono i seguenti prerequisiti:

* Accesso a un’istanza AEM configurata per l’integrazione.
* Accesso a un’istanza di Adobe Campaign configurata per l’integrazione.
* Modello e-mail multilingue Adobe Campaign configurato per ricevere contenuti AEM.

## Creazione di nuovi contenuti e-mail in Adobe Experience Manager {#creating-email-content-aem}

1. Dalla home page di Adobe Experience Manager, selezionare **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Selezionare la cartella in cui creare la pagina e fare clic su **[!UICONTROL Create]** e quindi su **[!UICONTROL Page]**. In questo caso, la pagina viene creata nella cartella en_us che sarà la lingua predefinita.

   ![](assets/aem_acs_2.png)

1. Selezionare il modello **[!UICONTROL Adobe Campaign Email (ACS)]**.

1. Compila le proprietà dell&#39;e-mail e fai clic su **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Apri i nuovi contenuti e-mail e personalizzali in base alle esigenze. Per ulteriori informazioni, consulta questa [pagina](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. Dalla scheda **[!UICONTROL Workflow]**, selezionare il flusso di lavoro di convalida **[!UICONTROL Approve for Adobe Campaign]**. Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto non approvato.

   ![](assets/aem_acs_7.png)

1. Fare clic su **[!UICONTROL Complete]** e quindi su **[!UICONTROL Newsletter review]** nella finestra **[!UICONTROL Complete work item]**.

1. Fare clic su **[!UICONTROL Complete]** e quindi su **[!UICONTROL Newsletter approval]**. Una volta definiti il contenuto e i parametri di invio, puoi procedere all’approvazione, alla preparazione e all’invio dell’e-mail in Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Creazione di copie per lingua {#creating-language-copies}

Dopo aver progettato il contenuto delle e-mail, ora è necessario creare le copie per lingua che verranno sincronizzate con Adobe Campaign Standard come varianti.

1. Seleziona la pagina creata in precedenza, fai clic su **[!UICONTROL Create]** e quindi su **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Seleziona il contenuto dell&#39;e-mail creato in precedenza che verrà tradotto nelle lingue scelte, quindi fai clic su **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. Nel menu a discesa **[!UICONTROL Target language(s)]**, seleziona la lingua in cui tradurre il contenuto, quindi fai clic su **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Fai clic su **[!UICONTROL Create]**.

Ora che sono state create le copie per lingua, puoi modificare il contenuto in base alla lingua scelta.

>[!CAUTION]
>
>Ogni copia in lingua deve essere approvata tramite il flusso di lavoro di convalida **[!UICONTROL Approve for Adobe Campaign]**. Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto non approvato.

![](assets/aem_acs_11.png)

## Creazione di contenuti multilingue in Adobe Campaign Standard {#multilingual-acs}

1. Dalla home page di Adobe Campaign Standard, fare clic su **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Seleziona il modello di e-mail multilingue Adobe Campaign configurato per ricevere contenuti Adobe Experience Manager. Per ulteriori informazioni su come creare un modello collegato alla tua istanza di Adobe Experience Manager, consulta questa [pagina](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >In questo caso, per poter inviare l&#39;e-mail multilingue, è necessario duplicare il modello predefinito **[!UICONTROL Multilingual email (mailMultiLang)]**.

   ![](assets/aem_acs_13.png)

1. Compila **[!UICONTROL Properties]** e **[!UICONTROL Audience]** dell&#39;e-mail e fai clic su **[!UICONTROL Create]**.

1. In **[!UICONTROL Edit properties]**, assicurati che l&#39;account Adobe Experience Manager sia impostato correttamente nel menu a discesa **[!UICONTROL Content]**.

   ![](assets/aem_acs_20.png)

1. Fai clic su **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Selezionare il contenuto Adobe Experience Manager creato in precedenza e fare clic su **[!UICONTROL Confirm]**. I contenuti di Adobe Experience Manager visualizzati qui sono solo contenuti convalidati e possono essere filtrati sui loro **[!UICONTROL Label]** e **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >La copia per lingua selezionata verrà impostata come predefinita. Sarà possibile modificarla in seguito nel blocco **[!UICONTROL Content variant]**.

   ![](assets/aem_acs_17.png)

1. Fai clic su **[!UICONTROL Create variants]** per collegare il tuo contenuto multilingue. Adobe Campaign Standard collegherà quindi automaticamente le copie per altre lingue a questo contenuto. Le varianti create avranno la stessa etichetta e lo stesso linguaggio di codice di quelle scelte in Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Fai clic sul blocco **[!UICONTROL Content variant]** per modificare la variante predefinita, se necessario, e fai clic su **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Se il contenuto o le varianti vengono aggiornati in Adobe Experience Manager, puoi sincronizzarli direttamente in Adobe Campaign Standard con il pulsante **[!UICONTROL Refresh AEM contents]**.

1. L’e-mail è ora pronta per essere inviata. Per ulteriori informazioni, consulta questa [pagina](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto AEM che non è stato approvato.

Il pubblico riceverà l&#39;e-mail a seconda di **[!UICONTROL Preferred languages]** impostati in **[!UICONTROL Profiles]**. Per ulteriori informazioni su come modificare profili e lingue preferite, consulta questa [pagina](../../audiences/using/editing-profiles.md).
