---
title: Migrazione dell’app mobile SDK v4 all’SDK per Adobe Experience Platform
description: Scopri come migrare l’app mobile da SDK v4 a Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 620ae1adc6f804e90c10daeb5fa4df42ce106885
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 1%

---

# Migrazione dell’app mobile da SDK v4 ad Adobe Experience Platform SDK {#sdkv4-migration}


Il supporto per gli SDK Adobe Experience Platform Mobile versione 4 è terminato il 31 agosto 2021. Se utilizzi ancora questa versione legacy dell&#39;SDK, devi aggiornare l&#39;implementazione con Adobe Experience Platform SDK **prima della fine di giugno 2024**. Scopri come migrare all’SDK di Adobe Experience Platform in questo articolo.

>[!IMPORTANT]
>
> Leggi attentamente il documento prima di avviare la migrazione dell’app mobile SDK V4 all’SDK di Adobe Experience Platform.

## Informazioni sulla migrazione di SDK V4

Adobe Campaign Standard elabora le applicazioni mobili utilizzando SDK V4 come applicazioni separate da quelle che utilizzano l’SDK di Adobe Experience Platform.

Dopo aver aggiornato la versione dell’SDK Adobe dalla versione v4 alla versione Adobe Experience Platform, le app mobili devono continuare a utilizzare le campagne e i dati degli abbonati all’applicazione esistenti: è quindi necessaria una migrazione.

>[!NOTE]
>
> Questa pagina documenta la migrazione di un’app mobile SDK v4 a un’applicazione Adobe Experience Platform SDK di nuova creazione. Le tue app mobili SDK v4 non verranno unite a un&#39;app mobile Adobe Experience Platform SDK con **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Cosa non cambierà dopo la migrazione |
|:-:|
| Non vi sarà alcun effetto sulle consegne e campagne esistenti che utilizzano l’applicazione SDK V4 migrata. |
| Il nome dell’app mobile rimarrà invariato. |
| Le credenziali della piattaforma per iOS e Android verranno mantenute. |
| Tutti gli abbonati all’applicazione e i loro dati saranno conservati. |
| L’app mobile SDK v4 esistente continuerà a inviare dati (dati PII, informazioni abbonato e token) ad Adobe Campaign Standard. |
| Il **[!UICONTROL Organizational unit]** dell&#39;app mobile rimarrà invariato. |

| Cosa cambierà dopo la migrazione |
|:-:|
| L&#39;app mobile sarà disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Prima della migrazione, era disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| Il **[!UICONTROL Collect PII Endpoint]** dell&#39;applicazione verrà modificato. La cartella **[!UICONTROL Collect PII Endpoint]** precedente continuerà a funzionare. I dati inviati non andranno persi. |
| L&#39;applicazione verrà associata a un tag **[!UICONTROL Mobile Property]**. Verrà elaborata come app mobile appena creata. |
| L’applicazione Adobe Experience Platform SDK originale utilizzata nella migrazione non esiste come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata. |

## Migrare l’app mobile da SDK v4 a Adobe Experience Platform SDK {#how-to-migrate}

Prima di eseguire la migrazione, è necessario tenere conto dei seguenti consigli:

* La migrazione è irreversibile.
* Non eseguire la migrazione di più applicazioni contemporaneamente. È inoltre necessario assicurarsi che la migrazione di una stessa applicazione non venga attivata da più finestre contemporaneamente.
* Prima della migrazione, assicurati di aver assegnato **[!UICONTROL Organizational unit]** dell&#39;app mobile da migrare e dell&#39;applicazione Adobe Experience Platform utilizzata per la migrazione.
* Dopo la migrazione, l’applicazione diventerà un’applicazione Adobe Experience Platform SDK. Le modifiche verranno collegate al tag corrispondente **[!UICONTROL Mobile Property]**.

1. Crea un nuovo **[!UICONTROL Mobile property]** nell&#39;interfaccia utente di Data Collection. Per ulteriori informazioni, consulta la [documentazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** e apri il flusso di lavoro **[!UICONTROL syncWithLaunch]**. Controlla se il flusso di lavoro è terminato senza errori.

1. Dopo il completamento del flusso di lavoro, dal menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**, controlla se l&#39;app mobile è disponibile in Adobe Campaign Standard ed è nello stato **[!UICONTROL Ready to Configure]**.

   ![](assets/aep_v4_2.png)

1. In **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**, seleziona l&#39;applicazione SDK V4 di cui vuoi eseguire la migrazione.

1. Seleziona la scheda **[!UICONTROL Mobile application migration to AEP SDK]**.

   ![](assets/aep_v4_3.png)

1. Dall&#39;elenco a discesa **[!UICONTROL Select AEP SDK mobile application to merge current application with]**, seleziona l&#39;app mobile Adobe Experience Platform SDK creata in precedenza.

1. Fai clic su **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Dalla finestra **[!UICONTROL Migration application]**, fare clic su **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. Viene visualizzata la finestra di completamento, fare clic su **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. Dalla pagina dell&#39;elenco dei canali dell&#39;SDK di Adobe Experience Platform, verifica che l&#39;app mobile V4 precedente sia impostata su **[!UICONTROL Ready To Configure]**.

1. Seleziona l&#39;app mobile e fai clic su **[!UICONTROL Save]** per completare la migrazione.

Dopo questa migrazione, gli abbonati raccolti dalla versione V4 dell’app mobile e i nuovi abbonati raccolti dalla versione AEP dell’app mobile saranno disponibili nell’applicazione migrata.

Per distinguere i due diversi tipi di sottoscrittori, è possibile aggiungere un nuovo campo personalizzato di tipo **[!UICONTROL Text]** durante l&#39;estensione della risorsa personalizzata **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**, ad esempio `sdkversion` o `appVersion`. Per ulteriori informazioni su come estendere una risorsa personalizzata, consulta questa [pagina](../../developing/using/creating-or-extending-the-resource.md).
Sarà quindi necessario configurare il tag associato **[!UICONTROL Mobile property]** per inviare il valore del campo personalizzato nella chiamata Raccolta PII e modificare di conseguenza la configurazione dell&#39;app mobile.

## Domande frequenti {#faq}

### D: nell’app mobile SDK v4, la scheda Migrazione dell’app mobile all’SDK di Adobe Experience Platform non è visibile. {#tab-not-visible}

R: Dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**, controllare il valore dell&#39;opzione **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**. Deve essere impostato su 1 e attivato per impostazione predefinita. L&#39;amministratore potrebbe averlo disabilitato manualmente.

![](assets/aep_v4_1.png)

### D: Dalla scheda Migrazione dell’applicazione mobile all’SDK di Adobe Experience Platform, viene visualizzato il messaggio No data (Nessun dato). {#no-data}

R: Nell&#39;elenco viene visualizzata solo l&#39;applicazione idonea di **[!UICONTROL Organizational unit]**. Assicurarsi di disporre dell&#39;applicazione Adobe Experience Platform corretta per la migrazione. **[!UICONTROL Property Status]** dell&#39;applicazione Adobe Experience Platform deve essere impostato su **[!UICONTROL Ready to Configure]** e **[!UICONTROL Mobile app migration status]** su **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### D: Perché non è possibile utilizzare per la migrazione l’applicazione Adobe Experience Platform SDK con Stato proprietà configurato? {#property-status}

R: Il processo di migrazione mantiene i sottoscrittori e gli attributi dell’SDK v4. Conserva solo le informazioni relative al tag dell’applicazione Adobe Experience Platform SDK. Gli abbonati e altri dati provenienti dall’applicazione Adobe Experience Platform SDK andranno persi. Per evitare perdite di dati, solo le applicazioni Adobe Experience Platform SDK con **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** sono idonee per la migrazione.

### D: Dopo la migrazione, dove posso trovare la mia precedente app mobile SDK v4? {#v4-app-not-visible}

R: L&#39;app mobile dopo la migrazione sarà visibile dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### D: Dopo la migrazione, dove posso trovare l’applicazione Adobe Experience Platform SDK appena creata? {#aep-not-visible}

R: L’applicazione Adobe Experience Platform SDK appena creata e utilizzata per la migrazione non esisterà come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata.

### D: se l’unità organizzativa dell’applicazione mobile SDK v4 è impostata su A (un elemento secondario dell’unità organizzativa ALL) e l’SDK di Adobe Experience Platform è impostato su ALL. Come posso eseguire la migrazione della mia app mobile? {#v4-org-unit}

R: Gli amministratori di **[!UICONTROL Organizational unit]** ALL avranno i diritti per gestire entrambe le applicazioni mobili e saranno responsabili della migrazione.

### D: se l’unità organizzativa dell’applicazione mobile SDK v4 è impostata su A e l’applicazione Adobe Experience Platform SDK è impostata su B (un elemento di pari livello dell’unità organizzativa A). Come posso eseguire la migrazione della mia app mobile? {#aep-org-unit}

R: l&#39;applicazione Adobe Experience Platform SDK è la risorsa di un elemento di pari livello **[!UICONTROL Organizational unit]**, pertanto l&#39;applicazione mobile non sarà visibile agli utenti dell&#39;elemento A **[!UICONTROL Organizational unit]**. L&#39;app mobile sarà disponibile per gli amministratori di **[!UICONTROL Organizational unit]** ALL, ma si sconsiglia agli amministratori di eseguire la migrazione dell&#39;app mobile.
In questo caso, è necessario spostare le applicazioni mobili nello stesso **[!UICONTROL Organizational unit]** o in un **[!UICONTROL Organizational unit]** con un collegamento padre.
Per ulteriori informazioni su **[!UICONTROL Organizational unit]**, fare riferimento a questa [sezione](../../administration/using/organizational-units.md).

### D: dalla pagina dell’app mobile Adobe Experience Platform SDK (migrata dall’app mobile v4), sotto il menu a discesa delle impostazioni del canale push, non viene visualizzata alcuna informazione come data/nome caricato per la chiave Android o il certificato iOS {#no-information-v5}

R: Il sistema non memorizza queste informazioni quando viene creata l’app mobile SDK V4. Quando esegui la migrazione dell’app mobile SDK V4 a un’app mobile Adobe Experience Platform SDK, nemmeno l’app mobile migrata disporrà di questo tipo di informazioni. Non appena un utente carica un nuovo certificato iOS o una nuova chiave Android, i diversi dettagli della chiave o del certificato verranno memorizzati e visualizzati correttamente nel menu a discesa **[!UICONTROL Push channel settings]**.
