---
solution: Campaign Standard
product: campaign
title: SDK v4 per la migrazione dell'applicazione mobile all'SDK Adobe Experience Platform
description: Questo documento consente di migrare l’applicazione mobile dall’SDK v4 all’SDK Adobe Experience Platform
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 6c171d45d655e4055d4a3c7927f1dd8e0913eeaa
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 0%

---


# Come migrare l&#39;applicazione mobile da SDK v4 a Adobe Experience Platform SDK {#sdkv4-migration}

>[!IMPORTANT]
>
> Il processo di migrazione è irreversibile.
>
> Leggi attentamente il documento prima di avviare la migrazione dell’applicazione SDK V4 per dispositivi mobili all’SDK Adobe Experience Platform.

## Informazioni sulla migrazione SDK V4

 Adobe Campaign Standard elabora applicazioni mobili utilizzando l’SDK V4 come applicazioni separate da quelle che utilizzano l’SDK Adobe Experience Platform.
Dopo aver aggiornato la versione dell’SDK del Adobe  dalla versione v4 a Adobe Experience Platform, le applicazioni mobili devono continuare a utilizzare i dati e le campagne dell’utente iscritto all’applicazione esistente: è quindi necessaria una migrazione.

>[!NOTE]
>
> Questa pagina documenta la migrazione di un’applicazione SDK v4 per dispositivi mobili a un’applicazione SDK Adobe Experience Platform appena creata. Le applicazioni SDK v4 per dispositivi mobili non verranno unite a un&#39;applicazione mobile Adobe Experience Platform SDK con un **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Cosa non cambia dopo la migrazione |
|:-:|
| Non si verificherà alcun effetto sulle consegne e le campagne esistenti che utilizzano l’applicazione SDK V4 migrata. |
| Il nome dell’applicazione mobile rimarrà invariato. |
| Le credenziali della piattaforma per iOS e Android verranno mantenute. |
| Tutti gli abbonati dell&#39;applicazione e i loro dati verranno conservati. |
| L’applicazione mobile SDK v4 esistente continuerà a inviare dati (dati PII, informazioni utente iscritto e token) a  Adobe Campaign Standard. |
| La **[!UICONTROL Organizational unit]** dell&#39;applicazione mobile rimarrà la stessa. |

| Cosa cambierà dopo la migrazione |
|:-:|
| L&#39;applicazione mobile sarà disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Prima della migrazione, era disponibile in **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| La **[!UICONTROL Collect PII Endpoint]** dell&#39;applicazione verrà modificata. La vecchia **[!UICONTROL Collect PII Endpoint]** continuerà a funzionare, i dati inviati non andranno persi. |
| L&#39;applicazione verrà legata a un Adobe Experience Platform Launch  **[!UICONTROL Mobile Property]**. Sarà elaborata come applicazione mobile appena creata. |
| L’applicazione SDK Adobe Experience Platform originale utilizzata per la migrazione non esisterà come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata. |

## Migra l’applicazione mobile da SDK v4 a Adobe Experience Platform SDK {#how-to-migrate}

Prima di eseguire la migrazione, è necessario tenere conto delle seguenti raccomandazioni:

* Il processo di migrazione è irreversibile.
* Non è consigliabile eseguire la migrazione di più applicazioni contemporaneamente. È inoltre necessario assicurarsi che la migrazione di una stessa applicazione non venga attivata contemporaneamente da più finestre.
* Prima della migrazione, accertatevi di disporre delle **[!UICONTROL Organizational unit]** applicazioni mobili da migrare e dell&#39;applicazione Adobe Experience Platform utilizzata per la migrazione.
* Dopo la migrazione, l’applicazione diventerà un’applicazione Adobe Experience Platform SDK. Le modifiche apportate verranno collegate al lancio **[!UICONTROL Mobile Property]** corrispondente.

1. Create un nuovo **[!UICONTROL Mobile property]** nell&#39;Adobe Experience Platform Launch . Per ulteriori informazioni, consultare la [ documentazione Adobe Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property).

1. In  Adobe Campaign Standard, dal menu avanzato, selezionare **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** e aprire il flusso di lavoro **[!UICONTROL syncWithLaunch]**. Verificate che il flusso di lavoro sia terminato senza errori.

1. Al termine del flusso di lavoro, dal menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** verificare se l&#39;applicazione mobile è disponibile in  Adobe Campaign Standard ed è nello stato **[!UICONTROL Ready to Configure]**.

   ![](assets/aep_v4_2.png)

1. In **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**, selezionare l&#39;applicazione SDK V4 da migrare.

1. Seleziona la scheda **[!UICONTROL Mobile application migration to AEP SDK]**.

   ![](assets/aep_v4_3.png)

1. Dall&#39;elenco a discesa **[!UICONTROL Select AEP SDK mobile application to merge current application with]**, seleziona l&#39;applicazione mobile Adobe Experience Platform SDK creata in precedenza.

1. Fai clic su **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. Dalla finestra **[!UICONTROL Migration application]**, fare clic su **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. Viene visualizzata la finestra di completamento, fare clic su **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. Dalla pagina dell&#39;elenco dei canali SDK per Adobe Experience Platform, verifica che l&#39;applicazione mobile V4 precedente sia impostata su **[!UICONTROL Ready To Configure]**.

1. Selezionate l&#39;applicazione mobile e fate clic su **[!UICONTROL Save]** per completare la migrazione.

Dopo questa migrazione, gli abbonati raccolti dalla versione V4 dell&#39;applicazione mobile e i nuovi abbonati raccolti dalla versione AEP dell&#39;applicazione mobile saranno disponibili nell&#39;applicazione migrata.

Per distinguere i due diversi tipi di sottoscrittori, è possibile aggiungere un nuovo campo personalizzato di tipo **[!UICONTROL Text]** durante l&#39;estensione della risorsa personalizzata **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** come ad esempio `sdkversion` o `appVersion`. Per ulteriori informazioni su come estendere una risorsa personalizzata, fare riferimento a questa [pagina](../../developing/using/creating-or-extending-the-resource.md).
Sarà quindi necessario configurare il lancio associato **[!UICONTROL Mobile property]** per inviare questo valore campo personalizzato nella chiamata Collect PII e modificare di conseguenza la configurazione dell&#39;applicazione mobile.

## Domande frequenti {#faq}

### D: Nell’applicazione SDK v4 per dispositivi mobili, la migrazione dell’applicazione Mobile all’SDK per Adobe Experience Platform non è visibile. {#tab-not-visible}

A: Dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**, verificare il valore dell&#39;opzione **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**. Deve essere impostato su 1 e attivato per impostazione predefinita. L&#39;amministratore potrebbe averlo disattivato manualmente.

![](assets/aep_v4_1.png)

### D: Dalla migrazione dell&#39;applicazione Mobile alla scheda SDK Adobe Experience Platform, viene visualizzato il messaggio Nessun dato. {#no-data}

A: Nell&#39;elenco viene visualizzata solo l&#39;applicazione idonea della **[!UICONTROL Organizational unit]**. Verificare di disporre dell&#39;applicazione Adobe Experience Platform corretta per la migrazione. È necessario impostare **[!UICONTROL Property Status]** dell&#39;applicazione Adobe Experience Platform su **[!UICONTROL Ready to Configure]** e **[!UICONTROL Mobile app migration status]** su **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### D: Perché l’applicazione Adobe Experience Platform SDK con lo stato della proprietà configurata non può essere utilizzata per la migrazione? {#property-status}

A: Il processo di migrazione mantiene gli abbonati e gli attributi SDK v4. Mantiene solo le informazioni relative a Launch dall’applicazione SDK di Adobe Experience Platform. Gli utenti iscritti e altri dati dell’applicazione SDK Adobe Experience Platform andranno persi. Per evitare perdite di dati, solo le applicazioni SDK Adobe Experience Platform con **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** sono idonee alla migrazione.

### D: Dopo la migrazione, dove posso trovare la mia precedente applicazione mobile SDK v4? {#v4-app-not-visible}

A: L&#39;applicazione mobile dopo la migrazione sarà visibile dal menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### D: Dopo la migrazione, dove si trova la mia nuova applicazione SDK Adobe Experience Platform? {#aep-not-visible}

A: L’applicazione SDK Adobe Experience Platform appena creata utilizzata per la migrazione non esisterà come applicazione separata. Sarà disponibile solo l’applicazione SDK v4 migrata.

### D: Se l’unità organizzativa dell’applicazione mobile SDK v4 è impostata su A (un elemento secondario dell’unità organizzativa ALL) e l’SDK per Adobe Experience Platform è impostato su ALL. Come si effettua la migrazione dell’applicazione mobile? {#v4-org-unit}

A: Gli amministratori di **[!UICONTROL Organizational unit]** ALL avranno i diritti per gestire entrambe le applicazioni mobili e saranno responsabili della migrazione.

### D: Se l’unità organizzativa dell’applicazione mobile SDK v4 è impostata su A e l’applicazione SDK Adobe Experience Platform è impostata su B (un elemento di pari livello dell’unità organizzativa A). Come si effettua la migrazione dell’applicazione mobile? {#aep-org-unit}

A: Applicazione SDK Adobe Experience Platform, essendo la risorsa di un elemento di pari livello **[!UICONTROL Organizational unit]**, l&#39;applicazione mobile non sarà visibile agli utenti della **[!UICONTROL Organizational unit]** A. L&#39;applicazione mobile sarà disponibile agli amministratori di **[!UICONTROL Organizational unit]** ALL, ma non consigliamo a questi amministratori di eseguire la migrazione dell&#39;applicazione mobile.
In questo caso, è necessario spostare le applicazioni mobili nello stesso **[!UICONTROL Organizational unit]** o in un **[!UICONTROL Organizational unit]** con un collegamento principale.
Per ulteriori informazioni su **[!UICONTROL Organizational unit]**, fare riferimento alla sezione [](../../administration/using/organizational-units.md).

### D: Dalla pagina dell’applicazione mobile Adobe Experience Platform SDK (migrata dall’applicazione mobile v4), nel menu a discesa delle impostazioni del canale push, per la chiave Android o il certificato iOS non vengono visualizzate informazioni come data/nome caricato {#no-information-v5}

A: Il sistema non memorizza queste informazioni quando viene creata l&#39;applicazione SDK V4 per dispositivi mobili. Durante la migrazione dell’applicazione SDK V4 per dispositivi mobili a un’applicazione Adobe Experience Platform SDK per dispositivi mobili, l’applicazione mobile migrata non avrà questo tipo di informazioni. Non appena un utente carica un nuovo certificato iOS o una nuova chiave Android, i diversi dettagli della chiave o del certificato saranno memorizzati e visualizzati correttamente nel menu a discesa **[!UICONTROL Push channel settings]**.
