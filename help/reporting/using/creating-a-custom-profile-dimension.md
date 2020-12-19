---
solution: Campaign Standard
product: campaign
title: Creazione di una dimensione di profilo personalizzata
description: Scoprite come creare una dimensione di profilo personalizzata basata sui dati di profilo personalizzati.
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---


# Creazione di una dimensione di profilo personalizzata{#creating-a-custom-profile-dimension}

È inoltre possibile creare e gestire i rapporti in base ai dati di profilo personalizzati creati durante l&#39;estensione della risorsa personalizzata del profilo.

In questo esempio, vogliamo creare il campo profilo personalizzato **Programmi fedeltà** che verrà diviso in tre livelli: oro, argento e bronzo. Questo profilo personalizzato verrà quindi esteso in modo da poterlo utilizzare come dimensione di profilo personalizzata nei report dinamici.

* [Passaggio 1: Creare un nuovo campo profilo](#step-1--create-a-new-profile-field)
* [Passaggio 2: Estendi i registri di invio con il campo del profilo](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Passaggio 3: Creazione di un targeting per la consegna dei destinatari iscritti al programma fedeltà](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Passaggio 4: Creare un rapporto dinamico per filtrare i destinatari con la dimensione del profilo personalizzato](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Passaggio 1: Creare un nuovo campo profilo {#step-1--create-a-new-profile-field}

Prima di tutto è necessario creare il nuovo campo profilo **Programma fedeltà** che assegnerà il livello di fedeltà ai destinatari: oro, argento o bronzo.

>[!NOTE]
>
>Le risorse personalizzate possono essere gestite solo da un amministratore.

Per eseguire questa operazione:

1. Dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, quindi la risorsa **[!UICONTROL Profile (profile)]** personalizzata.

   ![](assets/custom_profile_1.png)

1. Dalla scheda **[!UICONTROL Data structure]**, nella categoria **[!UICONTROL Fields]** fare clic sul pulsante **[!UICONTROL Add field]**.

   ![](assets/custom_profile_2.png)

1. Immettere **[!UICONTROL Label]**, **[!UICONTROL ID]** e selezionare la risorsa personalizzata **[!UICONTROL Type]**. Qui abbiamo selezionato **[!UICONTROL Text]** perché i destinatari avranno la scelta tra oro, argento e bronzo.

   ![](assets/custom_profile_3.png)

1. Fare clic sull&#39;icona ![](assets/custom_profile_22.png) per definire il campo.

   ![](assets/custom_profile_12.png)

1. Qui è necessario specificare i valori autorizzati selezionando **[!UICONTROL Specify a list of authorized valued]** e creare ciascun valore facendo clic su **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Immettere **[!UICONTROL Label]** e **[!UICONTROL Value]**, quindi fare clic su **[!UICONTROL Add]**. Per questo esempio, dobbiamo creare il valore oro, argento e bronzo. Fare clic su **[!UICONTROL Confirm]** al termine.

   ![](assets/custom_profile_14.png)

1. Seleziona la scheda **[!UICONTROL Screen definition]**. Nel menu a discesa **[!UICONTROL Detail screen configuration]**, seleziona la sezione **[!UICONTROL Add personalized fields]** per creare una nuova sezione nel nostro profilo.

   ![](assets/custom_profile_4.png)

1. Fate clic sul pulsante **[!UICONTROL Add an element]** per creare la nuova sezione. Selezionare **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** o **[!UICONTROL List]**, quindi il campo da aggiungere in questa nuova sezione.

   ![](assets/custom_profile_5.png)

1. È inoltre possibile aggiungere un titolo alla sezione nel campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Fare clic su **[!UICONTROL Save]** al termine della configurazione.

   ![](assets/custom_profile_6.png)

1. Dal menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** per avviare la pubblicazione della risorsa personalizzata.
1. Fare clic su **[!UICONTROL Prepare publication]**, quindi, al termine della preparazione, fare clic sul pulsante **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

Il nuovo campo del profilo è ora pronto per essere utilizzato e selezionato dai destinatari.

![](assets/custom_profile_8.png)

## Passaggio 2: Estendi i registri di invio con il campo profilo {#step-2--extend-the-sending-logs-with-the-profile-field}

Dopo aver creato il campo del profilo, è necessario estendere i log di invio con il campo del profilo per creare la dimensione del profilo personalizzato associata nei report dinamici.

Prima di estendere il registro con il campo del profilo, assicurarsi che la finestra PII sia stata accettata per avere accesso alla scheda **[!UICONTROL Sending logs extension]**. Per ulteriori informazioni, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>I registri possono essere estesi solo con i campi del profilo dall’amministratore.

1. Dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, quindi la risorsa **[!UICONTROL Profile (profile)]** personalizzata.
1. Aprite il menu a discesa **[!UICONTROL Sending logs extension]**.
1. Fai clic sul pulsante **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Selezionate il campo creato in precedenza e fate clic su **[!UICONTROL Confirm]**.
1. Selezionare **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** per creare una dimensione di profilo personalizzata.

   ![](assets/custom_profile_10.png)

   Questa opzione è disponibile solo se è stata accettata la finestra PII. Per ulteriori informazioni, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Fate clic su **[!UICONTROL Add]**, quindi salvate la risorsa personalizzata.
1. Poiché la risorsa personalizzata è stata modificata, è necessario pubblicarla per implementare le nuove modifiche.

   Dal menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** per avviare la pubblicazione della risorsa personalizzata.

1. Fare clic su **[!UICONTROL Prepare publication]**, quindi, al termine della preparazione, fare clic sul pulsante **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

Il profilo personalizzato è ora disponibile come dimensione di profilo personalizzata nei rapporti.

Ora che il campo è stato creato e che i registri di invio sono stati estesi con questo campo del profilo, puoi avviare il targeting dei destinatari nelle consegne.

## Passaggio 3: Creare un targeting di distribuzione dei destinatari iscritti al programma fedeltà {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Dopo aver pubblicato il campo del profilo, puoi iniziare la consegna. In questo esempio, vogliamo indirizzare tutti i destinatari iscritti al programma fedeltà.

1. Dalla scheda **[!UICONTROL Marketing activities]**, fai clic su **[!UICONTROL Create]** e quindi seleziona **[!UICONTROL Email]**.
1. Scegliete un **[!UICONTROL Email type]**, quindi immettete le proprietà del messaggio e-mail.
1. Per eseguire il targeting del destinatario iscritto al programma fedeltà, trascinate e rilasciate l&#39;attività **[!UICONTROL Profiles (attributes)]**.
1. Seleziona il campo creato in precedenza dall&#39;elenco a discesa **[!UICONTROL Field]**.

   ![](assets/custom_profile_16.png)

1. Selezionare il **[!UICONTROL Filter conditions]**. In questo caso, vogliamo indirizzare i destinatari che fanno parte di uno dei tre livelli del programma fedeltà.

   ![](assets/custom_profile_17.png)

1. Fare clic su **[!UICONTROL Confirm]**, quindi, al termine del filtraggio, fare clic su **[!UICONTROL Next]**.
1. Definisci e personalizza il contenuto del messaggio, il nome del mittente e l&#39;oggetto. Per ulteriori informazioni sulla creazione di e-mail, fare riferimento a questa [pagina](../../designing/using/designing-content-in-adobe-campaign.md).

   Quindi, fare clic su **[!UICONTROL Create]**.

1. Una volta pronti, potete visualizzare l&#39;anteprima e inviare il messaggio. Per ulteriori informazioni su come preparare e inviare il messaggio, fare riferimento a questa [pagina](../../sending/using/preparing-the-send.md).

Una volta che l’e-mail è stata inviata correttamente ai destinatari selezionati, potete iniziare a filtrare i dati e a monitorare il successo della distribuzione con i rapporti.

## Passaggio 4: Creare un rapporto dinamico per filtrare i destinatari con la dimensione del profilo personalizzato {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Dopo l&#39;invio della consegna, puoi suddividere i rapporti utilizzando la dimensione del profilo personalizzata dalla tabella **[!UICONTROL Profile]**.

1. Dalla scheda **[!UICONTROL Reports]**, selezionare un report out-of-the-box o fare clic sul pulsante **[!UICONTROL Create]** per iniziare da zero.

   ![](assets/custom_profile_18.png)

1. Nella categoria **[!UICONTROL Dimensions]**, fare clic su **[!UICONTROL Profile]**, quindi trascinare e rilasciare la dimensione del profilo **Programma fedeltà** personalizzata nella tabella a forma libera.

   ![](assets/custom_profile_19.png)

1. Trascina e rilascia le metriche **[!UICONTROL Processed/Sent]** e **[!UICONTROL Open]** per iniziare a filtrare i dati.

   ![](assets/custom_profile_20.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/custom_profile_21.png)

**Argomento correlato:**

* [Utilizzo di dati di profilo personalizzati per creare rapporti approfonditi](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
