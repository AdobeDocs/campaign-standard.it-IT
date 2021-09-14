---
title: Creazione di un’e-mail multilingue con l’integrazione Adobe Experience Manager.
description: Con l’integrazione Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 5%

---

# Creazione di un’e-mail multilingue con l’integrazione Adobe Experience Manager {#creating-multilingual-email-aem}

Questo documento illustra come creare un’e-mail multilingue utilizzando contenuti e copie per lingua di Adobe Experience Manager.

Sussistono i seguenti prerequisiti:

* Accesso a un’istanza AEM configurata per l’integrazione.
* Accesso a un’istanza di Adobe Campaign configurata per l’integrazione.
* Un modello e-mail multilingue di Adobe Campaign configurato per la ricezione AEM contenuto.

## Creazione di nuovi contenuti e-mail in Adobe Experience Manager {#creating-email-content-aem}

1. Dalla home page di Adobe Experience Manager, seleziona **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Seleziona la cartella in cui desideri creare la pagina e fai clic su **[!UICONTROL Create]** , quindi **[!UICONTROL Page]**. In questo caso, creiamo la nostra pagina nella cartella en_us che sarà la nostra lingua predefinita.

   ![](assets/aem_acs_2.png)

1. Selezionare il modello **[!UICONTROL Adobe Campaign Email (ACS)]**.

1. Inserisci le proprietà dell’e-mail e fai clic su **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Apri il nuovo contenuto e-mail e personalizzalo in base alle esigenze. Per ulteriori informazioni, consulta questa [pagina](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. Dalla scheda **[!UICONTROL Workflow]** , seleziona il flusso di lavoro di convalida **[!UICONTROL Approve for Adobe Campaign]** . Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto non approvato.

   ![](assets/aem_acs_7.png)

1. Fare clic su **[!UICONTROL Complete]**, quindi su **[!UICONTROL Newsletter review]** dalla finestra **[!UICONTROL Complete work item]**.

1. Fai clic su **[!UICONTROL Complete]**, quindi su **[!UICONTROL Newsletter approval]**. Una volta definiti il contenuto e i parametri di invio, puoi procedere all’approvazione, alla preparazione e all’invio dell’e-mail in Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Creazione di copie per lingua {#creating-language-copies}

Dopo aver progettato il contenuto dell’e-mail, ora devi creare le copie della lingua che saranno sincronizzate con Adobe Campaign Standard come varianti.

1. Seleziona la pagina creata in precedenza, fai clic su **[!UICONTROL Create]**, quindi **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Seleziona il contenuto dell’e-mail creato in precedenza che verrà tradotto nelle lingue selezionate, quindi fai clic su **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. Nel menu a discesa **[!UICONTROL Target language(s)]** , seleziona la lingua in cui il contenuto verrà tradotto, quindi fai clic su **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Fai clic su **[!UICONTROL Create]**.

Le copie per lingua vengono ora create e ora puoi modificare il contenuto in base alla lingua scelta.

>[!CAUTION]
>
>Ogni copia in lingua deve essere approvata tramite il flusso di lavoro di convalida **[!UICONTROL Approve for Adobe Campaign]** . Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto non approvato.

![](assets/aem_acs_11.png)

## Creazione di contenuti multilingue in Adobe Campaign Standard {#multilingual-acs}

1. Nella home page di Adobe Campaign Standard, fai clic su **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Seleziona il modello e-mail multilingue di Adobe Campaign configurato per la ricezione del contenuto Adobe Experience Manager. Per ulteriori informazioni su come creare un modello collegato alla tua istanza Adobe Experience Manager, consulta questa [pagina](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >In questo caso, dovrai duplicare il modello incorporato **[!UICONTROL Multilingual email (mailMultiLang)]** per poter inviare il tuo messaggio e-mail multilingue.

   ![](assets/aem_acs_13.png)

1. Compila i **[!UICONTROL Properties]** e **[!UICONTROL Audience]** del tuo indirizzo e-mail e fai clic su **[!UICONTROL Create]**.

1. Nel menu a discesa **[!UICONTROL Edit properties]** , accertati che l&#39;account Adobe Experience Manager sia impostato correttamente nel menu a discesa **[!UICONTROL Content]** .

   ![](assets/aem_acs_20.png)

1. Fai clic su **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Seleziona il contenuto Adobe Experience Manager creato in precedenza e fai clic su **[!UICONTROL Confirm]**. I contenuti Adobe Experience Manager visualizzati qui sono solo contenuti convalidati e possono essere filtrati sui rispettivi **[!UICONTROL Label]** e **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >La copia in lingua selezionata verrà impostata come predefinita; in seguito potrai modificarla nel blocco **[!UICONTROL Content variant]**.

   ![](assets/aem_acs_17.png)

1. Fai clic su **[!UICONTROL Create variants]** per collegare i contenuti multilingue. Adobe Campaign Standard quindi collegherà automaticamente al contenuto le altre copie in lingua. Le varianti create avranno la stessa etichetta e la stessa lingua di codice di quelle scelte in Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Fai clic sul blocco **[!UICONTROL Content variant]** per modificare la variante predefinita, se necessario, e fai clic su **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Se il contenuto o le varianti sono aggiornati in Adobe Experience Manager, puoi sincronizzarli direttamente in Adobe Campaign Standard con il pulsante **[!UICONTROL Refresh AEM contents]** .

1. L’e-mail è ora pronta per l’invio. Per ulteriori informazioni, consulta questa [pagina](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >Non potrai inviare un’e-mail in Adobe Campaign se utilizza un contenuto AEM non approvato.

Il pubblico riceverà il tuo messaggio e-mail a seconda del **[!UICONTROL Preferred languages]** impostato nel relativo **[!UICONTROL Profiles]**. Per ulteriori informazioni su come modificare profili e lingue preferite, consulta questa [pagina](../../audiences/using/editing-profiles.md).
