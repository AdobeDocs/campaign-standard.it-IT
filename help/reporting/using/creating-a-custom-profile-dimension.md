---
solution: Campaign Standard
product: campaign
title: Creazione di una dimensione di profilo personalizzata
description: Scopri come creare una dimensione di profilo personalizzata basata sui dati di profilo personalizzati.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Generazione rapporti
role: Leader
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---


# Creazione di una dimensione di profilo personalizzata{#creating-a-custom-profile-dimension}

Puoi anche creare e gestire i rapporti in base ai dati di profilo personalizzati creati durante l’estensione della risorsa personalizzata del profilo.

In questo esempio, vogliamo creare il campo del profilo personalizzato **Programmi fedeltà** che verrà suddiviso in tre livelli: oro, argento e bronzo. Questo profilo personalizzato verrà quindi esteso in modo da poterlo utilizzare come dimensione di profilo personalizzata nei rapporti dinamici.

* [Passaggio 1: Creare un nuovo campo del profilo](#step-1--create-a-new-profile-field)
* [Passaggio 2: Estendi i registri di invio con il campo del profilo](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Passaggio 3: Creare un targeting di consegna dei destinatari iscritti al programma fedeltà](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Passaggio 4: Creare un rapporto dinamico per filtrare i destinatari con la dimensione di profilo personalizzata](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Passaggio 1: Crea un nuovo campo profilo {#step-1--create-a-new-profile-field}

Innanzitutto, devi creare il nuovo campo profilo **Programma fedeltà** che assegnerà il livello di fedeltà ai destinatari: oro, argento o bronzo.

>[!NOTE]
>
>Le risorse personalizzate possono essere gestite solo da un amministratore.

Per eseguire questa operazione:

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** , quindi la risorsa personalizzata **[!UICONTROL Profile (profile)]**.

   ![](assets/custom_profile_1.png)

1. Dalla scheda **[!UICONTROL Data structure]**, nella categoria **[!UICONTROL Fields]**, fai clic sul pulsante **[!UICONTROL Add field]** .

   ![](assets/custom_profile_2.png)

1. Inserisci **[!UICONTROL Label]**, **[!UICONTROL ID]** e seleziona la risorsa personalizzata **[!UICONTROL Type]**. Qui abbiamo selezionato **[!UICONTROL Text]** poiché i destinatari avranno la scelta tra oro, argento e bronzo.

   ![](assets/custom_profile_3.png)

1. Fai clic sull’icona ![](assets/custom_profile_22.png) per definire il campo.

   ![](assets/custom_profile_12.png)

1. Qui, è necessario specificare i valori autorizzati selezionando **[!UICONTROL Specify a list of authorized valued]** e creare ogni valore facendo clic su **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Inserisci i valori **[!UICONTROL Label]** e **[!UICONTROL Value]**, quindi fai clic su **[!UICONTROL Add]**. Per questo esempio, dobbiamo creare il valore oro, argento e bronzo. Al termine, fai clic su **[!UICONTROL Confirm]** .

   ![](assets/custom_profile_14.png)

1. Seleziona la scheda **[!UICONTROL Screen definition]**. Nel menu a discesa **[!UICONTROL Detail screen configuration]** , seleziona la sezione **[!UICONTROL Add personalized fields]** per creare una nuova sezione nel nostro profilo.

   ![](assets/custom_profile_4.png)

1. Fai clic sul pulsante **[!UICONTROL Add an element]** per creare la nuova sezione. Seleziona il **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** o **[!UICONTROL List]**, quindi il campo da aggiungere in questa nuova sezione.

   ![](assets/custom_profile_5.png)

1. Puoi anche aggiungere un titolo alla sezione nel campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Al termine della configurazione, fai clic su **[!UICONTROL Save]** .

   ![](assets/custom_profile_6.png)

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** per iniziare a pubblicare la risorsa personalizzata.
1. Fai clic su **[!UICONTROL Prepare publication]**, quindi al termine della preparazione, fai clic sul pulsante **[!UICONTROL Publish]** .

   ![](assets/custom_profile_7.png)

Il nuovo campo del profilo è ora pronto per essere utilizzato e selezionato dai destinatari.

![](assets/custom_profile_8.png)

## Passaggio 2: Estendi i registri di invio con il campo del profilo {#step-2--extend-the-sending-logs-with-the-profile-field}

Dopo la creazione del campo del profilo, è necessario estendere i registri di invio con il campo del profilo per creare la dimensione del profilo personalizzato associata nei rapporti dinamici.

Prima di estendere il registro con il campo del profilo, accertati che la finestra PII sia stata accettata per avere accesso alla scheda **[!UICONTROL Sending logs extension]** . Per ulteriori informazioni, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>I registri possono essere estesi solo con i campi del profilo dall’amministratore.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** , quindi la risorsa personalizzata **[!UICONTROL Profile (profile)]**.
1. Apri il menu a discesa **[!UICONTROL Sending logs extension]** .
1. Fai clic sul pulsante **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Seleziona il campo creato in precedenza e fai clic su **[!UICONTROL Confirm]**.
1. Seleziona **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** per creare la dimensione di profilo personalizzata.

   ![](assets/custom_profile_10.png)

   Questa opzione è disponibile solo se è stata accettata la finestra PII. Per ulteriori informazioni, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Fai clic su **[!UICONTROL Add]**, quindi salva la risorsa personalizzata.
1. Poiché la risorsa personalizzata è stata modificata, è necessario pubblicarla per implementare le nuove modifiche.

   Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** per iniziare a pubblicare la risorsa personalizzata.

1. Fai clic su **[!UICONTROL Prepare publication]**, quindi al termine della preparazione, fai clic sul pulsante **[!UICONTROL Publish]** .

   ![](assets/custom_profile_7.png)

Il profilo personalizzato è ora disponibile come dimensione di profilo personalizzata nei rapporti.

Dopo aver creato il campo e aver esteso i registri di invio con questo campo di profilo, puoi iniziare a eseguire il targeting dei destinatari nelle consegne.

## Passaggio 3: Creare un target di consegna iscritto al programma fedeltà {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Una volta pubblicato il campo del profilo, puoi avviare la consegna. In questo esempio, vogliamo eseguire il targeting di ogni destinatario iscritto al programma fedeltà.

1. Dalla scheda **[!UICONTROL Marketing activities]**, fai clic su **[!UICONTROL Create]** e quindi seleziona **[!UICONTROL Email]**.
1. Scegli un **[!UICONTROL Email type]** e immetti le proprietà del messaggio e-mail.
1. Per eseguire il targeting del destinatario iscritto al programma fedeltà, trascina e rilascia l’attività **[!UICONTROL Profiles (attributes)]** .
1. Seleziona il campo creato in precedenza dal menu a discesa **[!UICONTROL Field]** .

   ![](assets/custom_profile_16.png)

1. Seleziona il tuo **[!UICONTROL Filter conditions]**. In questo caso, vogliamo eseguire il targeting dei destinatari che fanno parte di uno dei tre livelli del programma fedeltà.

   ![](assets/custom_profile_17.png)

1. Fai clic su **[!UICONTROL Confirm]**, quindi al termine del filtro, fai clic su **[!UICONTROL Next]**.
1. Definisci e personalizza il contenuto del messaggio, il nome del mittente e l’oggetto. Per ulteriori informazioni sulla creazione di e-mail, consulta questa [pagina](../../designing/using/designing-content-in-adobe-campaign.md).

   Quindi, fai clic su **[!UICONTROL Create]**.

1. Quando sei pronto, puoi visualizzare l’anteprima e inviare il messaggio. Per ulteriori informazioni su come preparare e inviare il messaggio, consulta questa [pagina](../../sending/using/preparing-the-send.md).

Una volta inviata correttamente l’e-mail ai destinatari selezionati, puoi iniziare a filtrare i dati e a tenere traccia del successo della consegna con i rapporti.

## Passaggio 4: Creare un rapporto dinamico per filtrare i destinatari con la dimensione di profilo personalizzata {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Dopo aver inviato la consegna, puoi suddividere i rapporti utilizzando la dimensione di profilo personalizzata dalla tabella **[!UICONTROL Profile]** .

1. Dalla scheda **[!UICONTROL Reports]** , seleziona un rapporto predefinito o fai clic sul pulsante **[!UICONTROL Create]** per iniziare da zero.

   ![](assets/custom_profile_18.png)

1. Nella categoria **[!UICONTROL Dimensions]** , fai clic su **[!UICONTROL Profile]**, quindi trascina e rilascia la dimensione di profilo **Programma fedeltà** personalizzata nella tabella a forma libera.

   ![](assets/custom_profile_19.png)

1. Trascina e rilascia le metriche **[!UICONTROL Processed/Sent]** e **[!UICONTROL Open]** per iniziare a filtrare i dati.

   ![](assets/custom_profile_20.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/custom_profile_21.png)

**Argomento correlato:**

* [Utilizzo di dati di profilo personalizzati per creare rapporti approfonditi](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
