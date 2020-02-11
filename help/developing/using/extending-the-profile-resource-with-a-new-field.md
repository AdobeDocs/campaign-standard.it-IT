---
title: Estensione della risorsa profilo con un nuovo campo
description: Scopri come estendere la risorsa del profilo.
page-status-flag: never-activated
uuid: 9b99e95c-93ff-4187-90f7-db0baf5369ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 1e0f8945-fc3c-46a9-a8e5-b181a1f5ffcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Estensione della risorsa profilo con un nuovo campo{#extending-the-profile-resource-with-a-new-field}

## Informazioni sull&#39;estensione dei profili {#about-extending-profiles}

Questo caso d’uso descrive come estendere un profilo e un profilo di test con un campo dedicato.

In questo caso, vogliamo aggiornare i nostri profili con il nuovo campo utilizzando una pagina di destinazione e quindi con i profili di destinazione con una newsletter specifica per i loro interessi.

A tale scopo, attenetevi alla procedura seguente:

* [Passaggio 1: Estendi la risorsa del profilo](#step-1--extend-the-profile-resource)
* [Passaggio 2: Estendere il profilo di test](#step-2--extend-the-test-profile)
* [Passaggio 3: Pubblicare la risorsa personalizzata](#step-3--publish-your-custom-resource)
* [Passaggio 4: Aggiornamento e targeting dei profili con un flusso di lavoro](#step-4--update-and-target-profiles-with-a-workflow)

Il seguente campo verrà aggiunto ai nostri profili e potrà essere mirato in una consegna:

![](assets/schema_extension_uc20.png)

Argomenti correlati:

* [Informazioni sulle risorse personalizzate](../../developing/using/data-model-concepts.md)
* [Gestione dei profili](../../audiences/using/about-profiles.md)
* [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)

## Passaggio 1: Estendi la risorsa del profilo {#step-1--extend-the-profile-resource}

Per creare il nuovo campo **Interesse** per i nostri profili, devi innanzitutto estendere la risorsa out-of-the-box **[!UICONTROL Profiles (profile)]** .

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]**, quindi **[!UICONTROL Custom resources]**.
1. Se non avete ancora esteso la **[!UICONTROL Profiles]** risorsa, fate clic su **[!UICONTROL Create]**.
1. Scegliete l’ **[!UICONTROL Extend an existing resource]** opzione.
1. Selezionate la **[!UICONTROL Profile (profile)]** risorsa.
1. Clic **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc5.png)

1. Nella **[!UICONTROL Fields]** categoria della **[!UICONTROL Data structure]** scheda, fare clic su **[!UICONTROL Create element]**.

   >[!NOTE]
   >
   >Se avete già esteso la **[!UICONTROL Profile]** risorsa per scopi precedenti, potete iniziare da questo passaggio facendo clic su **[!UICONTROL Add field]**.

   ![](assets/schema_extension_uc6.png)

1. Aggiungete un **[!UICONTROL Label]** e un **[!UICONTROL ID]**. Selezionate il **[!UICONTROL Text]** tipo e fate clic su **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc9.png)

1. Per configurare il campo, nella scheda **[!UICONTROL Data structure]** sotto al menu a discesa **[!UICONTROL Fields]**, fai clic su ![](assets/schema_extension_uc8.png) e quindi su ![](assets/schema_extension_uc7.png) dal campo creato in precedenza.
1. In questo esempio vogliamo aggiungere valori specifici, per fare clic su **[!UICONTROL Specify a list of authorized values]**.

   ![](assets/schema_extension_uc10.png)

1. Fate clic su **[!UICONTROL Add an element]** e aggiungete il numero desiderato aggiungendo un **[!UICONTROL Label]** e un **[!UICONTROL ID]** clic **[!UICONTROL Add]**.

   Qui, creeremo i valori Books, Exhibitions, Movies e N/D per i profili da scegliere tra queste opzioni.

   ![](assets/schema_extension_uc11.png)

1. Per aggiungere questo campo nella **[!UICONTROL Profile]** schermata, fare clic sulla **[!UICONTROL Screen definition]** scheda.
1. Nell’ **[!UICONTROL Detail screen configuration]** elenco a discesa, fate clic **[!UICONTROL Add a personalized fields section]** e fate clic su **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc12.png)

1. Selezionate una **[!UICONTROL Type]**. Qui si desidera aggiungere un campo di immissione. Quindi, selezionate il campo creato in precedenza e fate clic su **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc2.png)

1. Per aggiungere un separatore per organizzare meglio la finestra del profilo, fare clic su **[!UICONTROL Create an element]** e selezionare **[!UICONTROL Separator]** dal **[!UICONTROL Type]** menu a discesa.

   ![](assets/schema_extension_uc19.png)

Il campo è ora configurato. Ora dobbiamo estenderlo al profilo di prova.

>[!NOTE]
>
>Se non è necessario estendere la risorsa del profilo di test, potete passare al passaggio Pubblicazione.

## Passaggio 2: Estendere il profilo di test {#step-2--extend-the-test-profile}

Per verificare se il nuovo campo creato è configurato correttamente, potete verificarlo inviando la consegna ai profili di test. In primo luogo, il nuovo campo deve anche essere eseguito sui profili di prova.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]**, quindi **[!UICONTROL Custom resources]**.
1. Se non avete ancora esteso la **[!UICONTROL Profiles]** risorsa, fate clic su **[!UICONTROL Create]**.
1. Scegliete l’ **[!UICONTROL Extend an existing resource]** opzione.
1. Selezionate la **[!UICONTROL Test profile (seedMember)]** risorsa.
1. Clic **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc13.png)

1. Nella **[!UICONTROL Data structure]** scheda fare clic su **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc15.png)

1. Selezionate il campo delle risorse creato in precedenza e fate clic su **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc16.png)

1. Effettuate gli stessi passaggi dal passaggio 11 al 13, in quanto il profilo di estensione descritto sopra consente di aggiungere questo campo nella **[!UICONTROL Test profile]** schermata.
1. Clic **[!UICONTROL Save]**.

Entrambi i profili e i profili di test avranno a disposizione il nuovo campo. Affinché sia configurato correttamente, è necessario pubblicare la risorsa personalizzata.

## Passaggio 3: Pubblicare la risorsa personalizzata {#step-3--publish-your-custom-resource}

Per applicare le modifiche eseguite sulle risorse e utilizzarle, è necessario eseguire un aggiornamento del database.

1. Dal menu avanzato, selezionate **Amministrazione** > **Sviluppo**, quindi **Pubblicazione**.
1. Per impostazione predefinita, l&#39;opzione **[!UICONTROL Determine modifications since the last publication]** è selezionata, il che significa che verranno applicate solo le modifiche eseguite dall&#39;ultimo aggiornamento.

   ![](assets/schema_extension_uc14.png)

1. Fare clic **[!UICONTROL Prepare publication]** per avviare l&#39;analisi che aggiornerà il database.
1. Una volta completata la pubblicazione, fate clic sul pulsante **Pubblica** per applicare le nuove configurazioni.

   ![](assets/schema_extension_uc17.png)

1. Dopo la pubblicazione, il riquadro **Riepilogo** di ciascuna risorsa indica che lo stato è **Pubblicato** e specifica la data dell’ultima pubblicazione.

   ![](assets/schema_extension_uc18.png)

1. Selezionate la **[!UICONTROL Profiles]** scheda e fate clic **[!UICONTROL New]** per verificare se le modifiche sono state implementate correttamente.

   ![](assets/schema_extension_uc20.png)

Il nuovo campo delle risorse è ora pronto per essere utilizzato e mirato in una distribuzione, ad esempio.

## Passaggio 4: Aggiornamento e targeting dei profili con un flusso di lavoro {#step-4--update-and-target-profiles-with-a-workflow}

Per aggiornare i profili con i dati per il nuovo campo personalizzato, puoi creare una pagina di destinazione utilizzando il **[!UICONTROL Profile acquisition]** modello. Per ulteriori informazioni sulle pagine di destinazione, consultare questa [pagina](../../channels/using/getting-started-with-landing-pages.md).

Qui vogliamo eseguire il targeting in un profilo di flusso di lavoro che non ha compilato questo campo. Riceveranno un&#39;e-mail con la richiesta di aggiornare il profilo per ricevere newsletter e offerte personalizzate. Ogni profilo riceverà quindi una newsletter personalizzata in base ai loro interessi.

Innanzitutto, è necessario creare una pagina di destinazione che aggiorni i campi **Interesse** dei profili di destinazione:

1. Dal menu **[!UICONTROL Marketing activities]**, fate clic **[!UICONTROL Create]** quindi selezionate **[!UICONTROL Landing page]**.
1. Selezionare un tipo di pagina di destinazione. Qui, dal momento che vogliamo aggiornare i nostri profili, seleziona **[!UICONTROL Profile acquisition]**.
1. Clic **[!UICONTROL Create]**.
1. Fare clic sul **[!UICONTROL Content]** blocco per iniziare a modificare il contenuto della pagina di destinazione.

   ![](assets/schema_extension_uc21.png)

1. Personalizzate la pagina di destinazione come necessario.
1. Fai clic sul campo configurato per i profili per scegliere tra la selezione di Interessi. Nel riquadro a sinistra, seleziona la risorsa personalizzata **Interesse** precedentemente creata.

   ![](assets/schema_extension_uc22.png)

1. Salvare la pagina di destinazione e testarla per verificare che i campi siano configurati correttamente.
1. Fate clic **[!UICONTROL Publish]** quando la pagina di destinazione è pronta.

La pagina di destinazione è ora pronta. Per aggiornare i profili, puoi creare un flusso di lavoro che invierà un&#39;offerta speciale in base all&#39;interesse scelto.

1. Dalla **[!UICONTROL Marketing activities]** scheda, fare clic **[!UICONTROL Create]** quindi selezionare **[!UICONTROL Workflow]**.
1. Trascinate e rilasciate un&#39; **[!UICONTROL Query]** attività per definire i profili o le audience di cui avete bisogno.
1. Trascinate e rilasciate un&#39; **[!UICONTROL Email delivery]** attività per iniziare a configurare l&#39;e-mail che conterrà un collegamento alla pagina di destinazione. Selezionare il **[!UICONTROL Add an outbound transition with the population]**.

   ![](assets/schema_extension_uc3.png)

1. Create e progettate le e-mail in base alle vostre esigenze. Per ulteriori informazioni sulla personalizzazione delle e-mail, consultate questa [pagina](../../designing/using/quick-start.md).
1. Aggiungi un pulsante all’e-mail per reindirizzare i profili alla pagina di destinazione.
1. Selezionate il pulsante aggiunto e fate clic ![](assets/schema_extension_uc7.png) nella **[!UICONTROL Link]** sezione del riquadro a sinistra.

   ![](assets/schema_extension_uc23.png)

1. Nella **[!UICONTROL Insert link]** finestra, selezionate **[!UICONTROL Landing page]** dal menu a **[!UICONTROL Link type]** discesa, quindi selezionate la pagina di destinazione creata in precedenza.

   ![](assets/schema_extension_uc24.png)

1. Clic **[!UICONTROL Save]**. L&#39;e-mail è ora pronta. Potete tornare al flusso di lavoro.
1. Aggiungete un&#39; **[!UICONTROL Wait]** attività per consentire ai vostri profili di riempire la pagina di destinazione con un certo tempo.
1. Aggiungete un&#39; **[!UICONTROL Segmentation]** attività per dividere la transizione in uscita in base ai loro **interessi**.
1. Crea un segmento in uscita per ogni **interesse**.

   ![](assets/schema_extension_uc4.png)

1. Aggiungete un&#39; **[!UICONTROL Email delivery]** attività dopo ogni transizione e create un&#39;e-mail personalizzata in base all&#39; **interesse** scelto.
1. Avviate il flusso di lavoro al termine della configurazione.

   ![](assets/schema_extension_uc25.png)

I profili riceveranno ora l&#39;e-mail con la richiesta di compilare il campo Interesse seguito da un messaggio e-mail personalizzato in base al valore scelto.
