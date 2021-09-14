---
title: Migrazione dell’SDK v4 per applicazioni mobili all’SDK per Adobe Experience Platform
description: Questo documento consente di migrare l’app mobile da SDK v4 a Adobe Experience Platform SDK
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 1%

---

# Migrazione dell’app mobile da SDK v4 ad Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> Il processo di migrazione è irreversibile.
>
> Leggi attentamente il documento prima di avviare la migrazione dell’app mobile SDK V4 all’SDK di Adobe Experience Platform.

## Informazioni sulla migrazione SDK V4

Adobe Campaign Standard elabora le applicazioni mobili utilizzando l’SDK V4 come applicazioni separate da quelle che utilizzano l’SDK Adobe Experience Platform.
Dopo aver aggiornato la versione SDK di Adobe dalla versione v4 a Adobe Experience Platform, le applicazioni mobili devono continuare a utilizzare i dati e le campagne degli abbonati alle applicazioni esistenti: è pertanto necessaria una migrazione.

>[!NOTE]
>
> Questa pagina documenta la migrazione di un’app mobile SDK v4 a una nuova applicazione SDK Adobe Experience Platform. Le applicazioni mobili SDK v4 non verranno unite a un’app mobile Adobe Experience Platform SDK con un **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Cosa non cambierà dopo la migrazione |
|:-:|
| Non ci sarà alcun effetto sulle consegne e campagne esistenti che utilizzano l’applicazione SDK V4 migrata. |
| Il nome dell’app mobile rimarrà invariato. |
| Le credenziali della piattaforma per iOS e Android verranno mantenute. |
| Tutti gli abbonati all&#39;applicazione e i loro dati saranno conservati. |
| L’app mobile SDK v4 esistente continuerà a inviare dati (dati PII, informazioni del sottoscrittore e del token) ad Adobe Campaign Standard. |
| Il **[!UICONTROL Organizational unit]** dell’app mobile rimarrà lo stesso. |

| Cosa cambierà dopo la migrazione |
|:-:|
| L’app mobile sarà disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Prima della migrazione, era disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| L’ **[!UICONTROL Collect PII Endpoint]** dell’applicazione verrà modificato. La cartella **[!UICONTROL Collect PII Endpoint]** continuerà a funzionare, i dati inviati non andranno persi. |
| L&#39;applicazione verrà associata a un Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**. Sarà elaborato come nuova app mobile creata. |
| L&#39;applicazione Adobe Experience Platform SDK originale utilizzata nella migrazione non esisterà come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata. |

## Migrazione dell’app mobile dall’SDK v4 a Adobe Experience Platform SDK {#how-to-migrate}

Prima di eseguire la migrazione, è necessario tenere conto dei seguenti consigli:

* Il processo di migrazione è irreversibile.
* Non è consigliabile eseguire la migrazione di più applicazioni contemporaneamente. È inoltre necessario assicurarsi che la migrazione di una stessa applicazione non venga attivata contemporaneamente da più finestre.
* Prima della migrazione, accertati di ricevere l’ **[!UICONTROL Organizational unit]** dell’app mobile da migrare e dell’applicazione Adobe Experience Platform che stai utilizzando per la migrazione.
* Dopo la migrazione, l’applicazione diventerà un’applicazione Adobe Experience Platform SDK. Le modifiche saranno collegate al lancio corrispondente **[!UICONTROL Mobile Property]**.

1. Crea un nuovo **[!UICONTROL Mobile property]** in Adobe Experience Platform Launch. Per ulteriori informazioni, consulta la [documentazione Adobe Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property).

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** e apri il flusso di lavoro **[!UICONTROL syncWithLaunch]**. Controlla se il flusso di lavoro è terminato senza errori.

1. Al termine del flusso di lavoro, dal menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** controlla se l’app mobile è disponibile in Adobe Campaign Standard ed è nello stato **[!UICONTROL Ready to Configure]**.

   ![](assets/aep_v4_2.png)

1. In **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**, seleziona l’applicazione SDK V4 da migrare.

1. Seleziona la scheda **[!UICONTROL Mobile application migration to AEP SDK]**.

   ![](assets/aep_v4_3.png)

1. Dal menu a discesa **[!UICONTROL Select AEP SDK mobile application to merge current application with]** , seleziona l’app mobile Adobe Experience Platform SDK creata in precedenza.

1. Fai clic su **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Dalla finestra **[!UICONTROL Migration application]**, fai clic su **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. Viene visualizzata la finestra di completamento corretta, fare clic su **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. Dalla pagina dell’elenco dei canali SDK per Adobe Experience Platform , controlla che la tua precedente app mobile V4 sia impostata su **[!UICONTROL Ready To Configure]**.

1. Seleziona l’app mobile e fai clic su **[!UICONTROL Save]** per completare la migrazione.

Dopo questa migrazione, gli abbonati raccolti dalla versione V4 dell’app mobile e i nuovi abbonati raccolti dalla versione AEP dell’app mobile saranno disponibili nell’applicazione migrata.

Per distinguere i due diversi tipi di abbonati, puoi aggiungere un nuovo campo personalizzato di tipo **[!UICONTROL Text]** quando estendi la risorsa personalizzata **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** come ad esempio `sdkversion` o `appVersion`. Per ulteriori informazioni su come estendere una risorsa personalizzata, consulta questa [pagina](../../developing/using/creating-or-extending-the-resource.md).
Sarà quindi necessario configurare il Launch associato **[!UICONTROL Mobile property]** per inviare questo valore di campo personalizzato nella chiamata Raccogli PII e modificare di conseguenza la configurazione dell’app mobile.

## Domande frequenti {#faq}

### D: Nell’app mobile SDK v4, la scheda Migrazione dell’applicazione mobile all’SDK Adobe Experience Platform non è visibile. {#tab-not-visible}

R: Dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**, controlla il valore dell’opzione **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**. Deve essere impostato su 1 e abilitato per impostazione predefinita. L&#39;amministratore potrebbe averlo disabilitato manualmente.

![](assets/aep_v4_1.png)

### D: Dalla scheda Migrazione dell’applicazione mobile all’SDK di Adobe Experience Platform, viene visualizzato il messaggio Nessun dato. {#no-data}

R: Nell’elenco viene visualizzata solo l’applicazione idonea del **[!UICONTROL Organizational unit]**. Assicurati di disporre dell’applicazione Adobe Experience Platform corretta per la migrazione. Il valore **[!UICONTROL Property Status]** dell&#39;applicazione Adobe Experience Platform deve essere impostato su **[!UICONTROL Ready to Configure]** e il valore **[!UICONTROL Mobile app migration status]** deve essere impostato su **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### D: Perché l’applicazione Adobe Experience Platform SDK con lo stato della proprietà configurata non può essere utilizzata per la migrazione? {#property-status}

R: Il processo di migrazione mantiene gli abbonati e gli attributi SDK v4. Mantiene solo le informazioni relative a Launch dall’applicazione SDK di Adobe Experience Platform. Gli abbonati e altri dati dell’applicazione SDK Adobe Experience Platform andranno persi. Per evitare perdite di dati, solo le applicazioni Adobe Experience Platform SDK con **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** sono idonee alla migrazione.

### D: Dopo la migrazione, dove posso trovare la mia precedente app mobile SDK v4? {#v4-app-not-visible}

R: L’app mobile dopo la migrazione sarà visibile dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** .

### D: Dopo la migrazione, dove posso trovare la mia nuova applicazione SDK Adobe Experience Platform? {#aep-not-visible}

R: L’applicazione Adobe Experience Platform SDK appena creata utilizzata per la migrazione non esisterà come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata.

### D: Se l&#39;unità organizzativa dell&#39;applicazione mobile SDK v4 è impostata su A (un elemento figlio dell&#39;unità organizzativa ALL) e l&#39;SDK Adobe Experience Platform è impostato su ALL. Come posso eseguire la migrazione della mia app mobile? {#v4-org-unit}

R: Gli amministratori di **[!UICONTROL Organizational unit]** ALL avranno i diritti per gestire entrambe le applicazioni mobili e saranno responsabili della migrazione.

### D: Se l&#39;unità organizzativa dell&#39;applicazione mobile SDK v4 è impostata su A e l&#39;applicazione SDK Adobe Experience Platform è impostata su B (un livello di pari livello dell&#39;unità organizzativa A). Come posso eseguire la migrazione della mia app mobile? {#aep-org-unit}

R: L’applicazione SDK Adobe Experience Platform, essendo la risorsa di pari livello **[!UICONTROL Organizational unit]**, non sarà visibile agli utenti dell’ **[!UICONTROL Organizational unit]** A. L’app mobile sarà disponibile per gli amministratori del **[!UICONTROL Organizational unit]** ALL ma si sconsiglia agli amministratori di eseguire la migrazione dell’app mobile.
In questo caso, devi spostare le tue applicazioni mobili nello stesso **[!UICONTROL Organizational unit]** o in un **[!UICONTROL Organizational unit]** con un collegamento principale.
Per ulteriori informazioni su **[!UICONTROL Organizational unit]**, consulta questa [sezione](../../administration/using/organizational-units.md).

### D: Dalla pagina dell’app mobile Adobe Experience Platform SDK (migrata dall’app mobile v4), nel menu a discesa delle impostazioni del canale push , non vengono visualizzate informazioni come data/nome caricati per la chiave Android o il certificato iOS {#no-information-v5}

R: Il sistema non memorizza queste informazioni quando viene creata l&#39;applicazione mobile SDK V4. Durante la migrazione dell’app mobile SDK V4 a un’app mobile Adobe Experience Platform SDK, l’app mobile migrata non avrà questo tipo di informazioni. Non appena un utente carica un nuovo certificato iOS o una nuova chiave Android, i diversi dettagli della chiave o del certificato verranno memorizzati e visualizzati correttamente nel menu a discesa **[!UICONTROL Push channel settings]** .
