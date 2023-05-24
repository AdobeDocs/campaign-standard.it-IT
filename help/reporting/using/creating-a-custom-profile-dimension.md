---
title: Creazione di una dimensione di profilo personalizzata
description: Scopri come creare una dimensione di profilo personalizzata basata sui dati di profilo personalizzati.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---

# Creazione di una dimensione di profilo personalizzata{#creating-a-custom-profile-dimension}

I rapporti possono anche essere creati e gestiti in base ai dati di profilo personalizzati creati durante l’estensione della risorsa personalizzata profilo.

In questo esempio, desideri creare il campo del profilo personalizzato **Programmi fedeltà** che sarà diviso in tre livelli: oro, argento e bronzo. Questo profilo personalizzato verrà quindi esteso per poterlo utilizzare come dimensione di profilo personalizzata nei rapporti dinamici.

* [Passaggio 1: creare un nuovo campo profilo](#step-1--create-a-new-profile-field)
* [Passaggio 2: estendere i registri di invio con il campo del profilo](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Passaggio 3: creare una consegna con targeting per i destinatari iscritti al programma fedeltà](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Passaggio 4: creare un rapporto dinamico per filtrare i destinatari con la dimensione di profilo personalizzata](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Passaggio 1: creare un nuovo campo profilo {#step-1--create-a-new-profile-field}

Innanzitutto devi creare il nuovo campo del profilo **Programma fedeltà** che assegnerà il livello di fedeltà ai destinatari: oro, argento o bronzo.

>[!NOTE]
>
>Le risorse personalizzate possono essere gestite solo da un amministratore.

Per eseguire questa operazione:

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** quindi il **[!UICONTROL Profile (profile)]** risorsa personalizzata.

   ![](assets/custom_profile_1.png)

1. Dalla sezione **[!UICONTROL Data structure]** , nella scheda **[!UICONTROL Fields]** categoria, fai clic su **[!UICONTROL Add field]** pulsante.

   ![](assets/custom_profile_2.png)

1. Inserisci il **[!UICONTROL Label]**, **[!UICONTROL ID]** e seleziona la risorsa personalizzata **[!UICONTROL Type]**. In questo caso abbiamo selezionato **[!UICONTROL Text]** poiché i destinatari potranno scegliere tra oro, argento e bronzo.

   ![](assets/custom_profile_3.png)

1. Fai clic su ![](assets/custom_profile_22.png) per definire il campo.

   ![](assets/custom_profile_12.png)

1. In questo caso, è necessario specificare i valori autorizzati verificando **[!UICONTROL Specify a list of authorized valued]** e crea ciascun valore facendo clic su **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Inserisci il **[!UICONTROL Label]** e **[!UICONTROL Value]** quindi fai clic su **[!UICONTROL Add]**. Per questo esempio, dobbiamo creare il valore oro, argento e bronzo. Al termine della configurazione, fai clic su **[!UICONTROL Confirm]**.

   ![](assets/custom_profile_14.png)

1. Seleziona la scheda **[!UICONTROL Screen definition]**. In **[!UICONTROL Detail screen configuration]** a discesa, spunta **[!UICONTROL Add personalized fields]** per creare una nuova sezione nel nostro profilo.

   ![](assets/custom_profile_4.png)

1. Fai clic su **[!UICONTROL Add an element]** per creare la nuova sezione. Seleziona la **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** o **[!UICONTROL List]**, quindi il campo da aggiungere in questa nuova sezione.

   ![](assets/custom_profile_5.png)

1. Puoi anche aggiungere un titolo alla sezione nel campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Clic **[!UICONTROL Save]** al termine della configurazione.

   ![](assets/custom_profile_6.png)

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** per iniziare a pubblicare la risorsa personalizzata.
1. Clic **[!UICONTROL Prepare publication]** al termine della preparazione, fai clic su **[!UICONTROL Publish]** pulsante.

   ![](assets/custom_profile_7.png)

Il nuovo campo del profilo è ora pronto per essere utilizzato e selezionato dai destinatari.

![](assets/custom_profile_8.png)

## Passaggio 2: estendere i registri di invio con il campo del profilo {#step-2--extend-the-sending-logs-with-the-profile-field}

Ora che il campo del profilo è stato creato, è necessario estendere i registri di invio con il campo del profilo per creare la dimensione di profilo personalizzata associata nei rapporti dinamici.

Prima di estendere il registro con il campo del profilo, assicurati che la finestra PII sia stata accettata per avere accesso a **[!UICONTROL Sending logs extension]** scheda. Per ulteriori informazioni, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>I registri possono essere estesi solo con i campi del profilo dall’amministratore.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** quindi il **[!UICONTROL Profile (profile)]** risorsa personalizzata.
1. Apri **[!UICONTROL Sending logs extension]** a discesa.
1. Fai clic sul pulsante **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Seleziona il campo creato in precedenza e fai clic su **[!UICONTROL Confirm]**.
1. Verifica **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** per creare la dimensione di profilo personalizzata.

   ![](assets/custom_profile_10.png)

   Questa opzione è disponibile solo se la finestra PII è stata accettata. Per ulteriori informazioni, consulta questa [pagina](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Clic **[!UICONTROL Add]** quindi salva la risorsa personalizzata.
1. Poiché la risorsa personalizzata è stata modificata, è necessario pubblicarla per implementare le nuove modifiche.

   Dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** per iniziare a pubblicare la risorsa personalizzata.

1. Clic **[!UICONTROL Prepare publication]** al termine della preparazione, fai clic su **[!UICONTROL Publish]** pulsante.

   ![](assets/custom_profile_7.png)

Il profilo personalizzato è ora disponibile come dimensione di profilo personalizzata nei rapporti.

Ora che il campo è stato creato e i registri di invio sono stati estesi con questo campo del profilo, puoi iniziare a eseguire il targeting dei destinatari nelle consegne.

## Passaggio 3: creare una consegna con targeting per i destinatari iscritti al programma fedeltà {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Una volta pubblicato il campo del profilo, puoi avviare la consegna. In questo esempio, vogliamo eseguire il targeting per ogni destinatario iscritto al programma fedeltà.

1. Dalla scheda **[!UICONTROL Marketing activities]**, fai clic su **[!UICONTROL Create]** e quindi seleziona **[!UICONTROL Email]**.
1. Scegli un **[!UICONTROL Email type]** quindi inserisci le proprietà dell’e-mail.
1. Per eseguire il targeting dei destinatari iscritti al programma fedeltà, trascina e rilascia la **[!UICONTROL Profiles (attributes)]** attività.
1. Seleziona il campo creato in precedenza da **[!UICONTROL Field]** a discesa.

   ![](assets/custom_profile_16.png)

1. Seleziona il **[!UICONTROL Filter conditions]**. In questo caso, vogliamo eseguire il targeting dei destinatari che fanno parte di uno dei tre livelli del programma fedeltà.

   ![](assets/custom_profile_17.png)

1. Clic **[!UICONTROL Confirm]** quindi, al termine del filtro, fai clic su **[!UICONTROL Next]**.
1. Definisci e personalizza il contenuto del messaggio, il nome del mittente e l’oggetto. Per ulteriori informazioni sulla creazione di e-mail, consulta questa [pagina](../../designing/using/designing-content-in-adobe-campaign.md).

   Quindi, fai clic su **[!UICONTROL Create]**.

1. Al termine dell’operazione, potrai visualizzare in anteprima e inviare il messaggio. Per ulteriori informazioni su come preparare e inviare il messaggio, consulta questa [pagina](../../sending/using/preparing-the-send.md).

Una volta inviata correttamente l’e-mail ai destinatari selezionati, puoi iniziare a filtrare i dati e monitorare il successo della consegna tramite i rapporti.

## Passaggio 4: creare un rapporto dinamico per filtrare i destinatari con la dimensione di profilo personalizzata {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Dopo aver inviato la consegna, puoi suddividere i rapporti utilizzando la dimensione di profilo personalizzata dal **[!UICONTROL Profile]** tabella.

1. Dalla sezione **[!UICONTROL Reports]** , seleziona un rapporto predefinito o fai clic sulla scheda **[!UICONTROL Create]** per iniziare da zero.

   ![](assets/custom_profile_18.png)

1. In **[!UICONTROL Dimensions]** categoria, fai clic su **[!UICONTROL Profile]** quindi trascina e rilascia il **Programma fedeltà** dimensione profilo nella tabella a forma libera.

   ![](assets/custom_profile_19.png)

1. Trascina la **[!UICONTROL Processed/Sent]** e **[!UICONTROL Open]** metriche per iniziare a filtrare i dati.

   ![](assets/custom_profile_20.png)

1. Se necessario, trascina e rilascia una visualizzazione nell’area di lavoro.

   ![](assets/custom_profile_21.png)

**Argomento correlato:**

* [Utilizzo di dati di profilo personalizzati per creare rapporti dettagliati](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
