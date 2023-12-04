---
title: Migrazione dell’app mobile SDK v4 all’SDK per Adobe Experience Platform
description: Scopri come migrare l’app mobile da SDK v4 a Adobe Experience Platform SDK
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: 3b2f8d9b2b7a4ec9532917af3a0880400d98e636
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 1%

---

# Migrazione dell’app mobile da SDK v4 ad Adobe Experience Platform SDK {#sdkv4-migration}


Il supporto per gli SDK di Adobe Experience Platform Mobile versione 4 è terminato il **31 agosto 2021**. Scopri come migrare all’SDK di Adobe Experience Platform in questo articolo.

>[!IMPORTANT]
>
> La migrazione è irreversibile.
>
> Leggi attentamente il documento prima di avviare la migrazione dell’app mobile SDK V4 all’SDK di Adobe Experience Platform.

## Informazioni sulla migrazione di SDK V4

Adobe Campaign Standard elabora le applicazioni mobili utilizzando SDK V4 come applicazioni separate da quelle che utilizzano l’SDK di Adobe Experience Platform.
Dopo aver aggiornato la versione dell’SDK Adobe dalla versione v4 alla versione Adobe Experience Platform, le app mobili devono continuare a utilizzare le campagne e i dati degli abbonati all’applicazione esistenti: è quindi necessaria una migrazione.

>[!NOTE]
>
> Questa pagina documenta la migrazione di un’app mobile SDK v4 a un’applicazione Adobe Experience Platform SDK di nuova creazione. Le tue app mobili SDK v4 non verranno unite a un’app mobile SDK per Adobe Experience Platform con un **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Cosa non cambierà dopo la migrazione |
|:-:|
| Non vi sarà alcun effetto sulle consegne e campagne esistenti che utilizzano l’applicazione SDK V4 migrata. |
| Il nome dell’app mobile rimarrà invariato. |
| Le credenziali della piattaforma per iOS e Android verranno mantenute. |
| Tutti gli abbonati all’applicazione e i loro dati saranno conservati. |
| L’app mobile SDK v4 esistente continuerà a inviare dati (dati PII, informazioni abbonato e token) ad Adobe Campaign Standard. |
| Il **[!UICONTROL Organizational unit]** dell’app mobile rimarrà invariata. |

| Cosa cambierà dopo la migrazione |
|:-:|
| L’app mobile sarà disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Prima della migrazione, era disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| Il **[!UICONTROL Collect PII Endpoint]** dell’applicazione cambierà. Il più vecchio **[!UICONTROL Collect PII Endpoint]** continuerà a funzionare, i dati inviati non andranno persi. |
| L’applicazione verrà associata a un tag **[!UICONTROL Mobile Property]**. Verrà elaborata come app mobile appena creata. |
| L’applicazione Adobe Experience Platform SDK originale utilizzata nella migrazione non esiste come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata. |

## Migrare l’app mobile da SDK v4 a Adobe Experience Platform SDK {#how-to-migrate}

Prima di eseguire la migrazione, è necessario tenere conto dei seguenti consigli:

* La migrazione è irreversibile.
* Non eseguire la migrazione di più applicazioni contemporaneamente. È inoltre necessario assicurarsi che la migrazione di una stessa applicazione non venga attivata da più finestre contemporaneamente.
* Prima della migrazione, assicurati di aver assegnato **[!UICONTROL Organizational unit]** dell’app mobile di cui desideri eseguire la migrazione e dell’applicazione Adobe Experience Platform di cui stai utilizzando la migrazione.
* Dopo la migrazione, l’applicazione diventerà un’applicazione Adobe Experience Platform SDK. Le modifiche verranno collegate al tag corrispondente **[!UICONTROL Mobile Property]**.

1. Crea un nuovo **[!UICONTROL Mobile property]** nell’interfaccia utente di Data Collection. Per ulteriori informazioni, consulta [documentazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** e apri **[!UICONTROL syncWithLaunch]** flusso di lavoro. Controlla se il flusso di lavoro è terminato senza errori.

1. Dopo il completamento del flusso di lavoro, da **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** , controlla se l’app mobile è disponibile in Adobe Campaign Standard ed è in **[!UICONTROL Ready to Configure]** stato.

   ![](assets/aep_v4_2.png)

1. In entrata **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**, seleziona l’applicazione SDK V4 di cui vuoi eseguire la migrazione.

1. Seleziona la scheda **[!UICONTROL Mobile application migration to AEP SDK]**.

   ![](assets/aep_v4_3.png)

1. Dalla sezione **[!UICONTROL Select AEP SDK mobile application to merge current application with]** a discesa, seleziona l’app mobile Adobe Experience Platform SDK creata in precedenza.

1. Fai clic su **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Dalla sezione **[!UICONTROL Migration application]** finestra, fai clic su **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. Viene visualizzata la finestra di completamento, fare clic su **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. Dalla pagina dell’elenco dei canali dell’SDK di Adobe Experience Platform, verifica che l’app mobile V4 precedente sia impostata su **[!UICONTROL Ready To Configure]**.

1. Seleziona la tua app mobile e fai clic su **[!UICONTROL Save]** per completare la migrazione.

Dopo questa migrazione, gli abbonati raccolti dalla versione V4 dell’app mobile e i nuovi abbonati raccolti dalla versione AEP dell’app mobile saranno disponibili nell’applicazione migrata.

Per distinguere i due diversi tipi di abbonati, puoi aggiungere un nuovo campo personalizzato di **[!UICONTROL Text]** digita quando estendi la risorsa personalizzata **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** as `sdkversion` o `appVersion` ad esempio. Per ulteriori informazioni su come estendere una risorsa personalizzata, consulta questa [pagina](../../developing/using/creating-or-extending-the-resource.md).
Sarà quindi necessario configurare il tag associato **[!UICONTROL Mobile property]** per inviare questo valore di campo personalizzato nella chiamata Raccogli PII e modificare di conseguenza la configurazione dell’app mobile.

## Domande frequenti {#faq}

### D: nell’app mobile SDK v4, la scheda Migrazione dell’app mobile all’SDK di Adobe Experience Platform non è visibile. {#tab-not-visible}

R: Dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**, controlla il valore di **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]** opzione. Deve essere impostato su 1 e attivato per impostazione predefinita. L&#39;amministratore potrebbe averlo disabilitato manualmente.

![](assets/aep_v4_1.png)

### D: Dalla scheda Migrazione dell’applicazione mobile all’SDK di Adobe Experience Platform, viene visualizzato il messaggio No data (Nessun dato). {#no-data}

R: Solo applicazione idonea del tuo **[!UICONTROL Organizational unit]** viene visualizzato nell&#39;elenco. Assicurarsi di disporre dell&#39;applicazione Adobe Experience Platform corretta per la migrazione. Il **[!UICONTROL Property Status]** dell’applicazione Adobe Experience Platform deve essere impostato su **[!UICONTROL Ready to Configure]**  e **[!UICONTROL Mobile app migration status]** imposta su **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### D: Perché non è possibile utilizzare per la migrazione l’applicazione Adobe Experience Platform SDK con Stato proprietà configurato? {#property-status}

R: Il processo di migrazione mantiene i sottoscrittori e gli attributi dell’SDK v4. Conserva solo le informazioni relative al tag dell’applicazione Adobe Experience Platform SDK. Gli abbonati e altri dati provenienti dall’applicazione Adobe Experience Platform SDK andranno persi. Per evitare perdite di dati, solo le applicazioni SDK Adobe Experience Platform con **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** sono idonei per la migrazione.

### D: Dopo la migrazione, dove posso trovare la mia precedente app mobile SDK v4? {#v4-app-not-visible}

R: L’app mobile dopo la migrazione sarà visibile dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### D: Dopo la migrazione, dove posso trovare l’applicazione Adobe Experience Platform SDK appena creata? {#aep-not-visible}

R: L’applicazione Adobe Experience Platform SDK appena creata e utilizzata per la migrazione non esisterà come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata.

### D: se l’unità organizzativa dell’applicazione mobile SDK v4 è impostata su A (un elemento secondario dell’unità organizzativa ALL) e l’SDK di Adobe Experience Platform è impostato su ALL. Come posso eseguire la migrazione della mia app mobile? {#v4-org-unit}

R: Amministratori di **[!UICONTROL Organizational unit]** ALL avrà i diritti per gestire entrambe le applicazioni mobili e sarà responsabile della migrazione.

### D: se l’unità organizzativa dell’applicazione mobile SDK v4 è impostata su A e l’applicazione Adobe Experience Platform SDK è impostata su B (un elemento di pari livello dell’unità organizzativa A). Come posso eseguire la migrazione della mia app mobile? {#aep-org-unit}

A: l’applicazione Adobe Experience Platform SDK è la risorsa di un elemento di pari livello **[!UICONTROL Organizational unit]**, l’app mobile non sarà visibile agli utenti di **[!UICONTROL Organizational unit]** A. L’app mobile sarà disponibile per gli amministratori del **[!UICONTROL Organizational unit]** TUTTI ma non consigliamo a questi amministratori di eseguire la migrazione dell’app mobile.
In questo caso, è necessario spostare le applicazioni mobili nello stesso **[!UICONTROL Organizational unit]** o in un **[!UICONTROL Organizational unit]** con un collegamento principale.
Per ulteriori informazioni su **[!UICONTROL Organizational unit]**, fare riferimento a questo [sezione](../../administration/using/organizational-units.md).

### D: dalla pagina dell’app mobile Adobe Experience Platform SDK (migrata dall’app mobile v4), sotto il menu a discesa delle impostazioni del canale push, non viene visualizzata alcuna informazione come data/nome caricato per la chiave Android o il certificato iOS {#no-information-v5}

R: Il sistema non memorizza queste informazioni quando viene creata l’app mobile SDK V4. Quando esegui la migrazione dell’app mobile SDK V4 a un’app mobile Adobe Experience Platform SDK, nemmeno l’app mobile migrata disporrà di questo tipo di informazioni. Non appena un utente carica un nuovo certificato iOS o una nuova chiave Android, i diversi dettagli della chiave o del certificato vengono memorizzati e visualizzati correttamente in **[!UICONTROL Push channel settings]** a discesa.
