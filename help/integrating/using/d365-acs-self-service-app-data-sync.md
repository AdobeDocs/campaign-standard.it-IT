---
title: Sincronizzare i dati tra Campaign e Microsoft Dynamics
description: Sincronizzare i dati tra Campaign e Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# Sincronizzare i dati

È possibile sincronizzare le tabelle da Microsoft Dynamics 365 alle metriche di marketing di Campaign e Campaign a Microsoft Dynamics 365. La sincronizzazione viene eseguita tramite tre flussi di lavoro tecnici dedicati: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Fai riferimento a questa sezione per [ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>È necessario interrompere/avviare il **[!UICONTROL Microsoft Dynamics 365 to Campaign]** affinché le modifiche vengano prese in considerazione. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## Mappare le tabelle da Microsoft Dynamics 365 a Campaign

Il **[!UICONTROL Microsoft Dynamics 365 to Campaign]** Questa pagina mostra un elenco di entità in Microsoft Dynamics 365 e le risorse personalizzate in Adobe Campaign con cui verranno sincronizzate. È possibile aggiungere nuove mappature, modificare o eliminare mappature esistenti.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

Segue una descrizione di ciascuna delle colonne della tabella:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: questa colonna identifica quale entità in Microsoft Dynamics 365 sarà l’origine dei dati per la mappatura.

* **[!UICONTROL CAMPAIGN TABLE]**: questa colonna identifica quale risorsa in Adobe Campaign sarà la destinazione dei dati per la mappatura.

* **[!UICONTROL ACTIONS]**: le azioni possibili sono elencate di seguito:

   * Fai clic su **[!UICONTROL Edit]** per modificare la mappatura.

   * Utilizza il  **[!UICONTROL Delete]** per eliminare una mappatura tabella.

   * Fai clic su **[!UICONTROL Replay Data]** per risincronizzare tutti i dati nella tabella Microsoft Dynamics 365. Normalmente l’applicazione di integrazione sincronizzerà solo i dati in Microsoft Dynamics 365 che sono stati modificati di recente.  Tuttavia, in alcuni casi (ad esempio, se hai apportato una modifica o commesso un errore) potresti voler risincronizzare tutti i dati.  In questi casi, fare clic su questo pulsante e, la volta successiva che si arresta/avvia il **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flusso di lavoro, i dati inizierebbero a essere sincronizzati.

     Se si fa clic sul pulsante **[!UICONTROL Replay Data]** e i controlli hanno esito positivo, l’icona si disabilita: indica che i dati per questa coppia di mappatura tabella saranno risincronizzati con l’esecuzione successiva della **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flusso di lavoro.

     Non è possibile scegliere di riprodurre nuovamente i dati quando si verificano le condizioni seguenti:

      * Se la metrica Backlog è associata a 2.000.000 (o più) elementi, **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flusso di lavoro (visualizzato nella **[!UICONTROL Workflows]** page)
      * Se nella tabella Microsoft Dynamics 365 sono presenti almeno 2.000.000 record

     Il numero di record da risincronizzare varia. Se il numero di record è elevato, il completamento del processo di sincronizzazione potrebbe richiedere del tempo. Consulta la sezione **[!UICONTROL Backlog]** metrica in **[!UICONTROL Workflows]** come l’applicazione di integrazione lavora per completare il processo di sincronizzazione.

     >[!IMPORTANT]
     >
     > Si consiglia vivamente di arrestare il flusso di lavoro di integrazione quando si pubblicano modifiche su Adobe Campaign Standard o Microsoft Dynamics 365. Le modifiche applicabili includono: aggiornamenti a risorse/entità (e ai relativi campi associati), collegamenti, colonne di identificatori e così via. attualmente in uso dall’integrazione.
     >

## Crea una nuova mappatura {#add-a-new-mapping}

Per creare una nuova mappatura, effettua le seguenti operazioni:

1. nel **[!UICONTROL Microsoft Dynamics 365 to Campaign]** , fare clic su **[!UICONTROL Add New Mapping]** pulsante.

1. Utilizza gli elenchi a discesa per selezionare le tabelle di Microsoft Dynamics 365 e Campaign da mappare.
La maggior parte degli altri input nella pagina dipenderà dalle tabelle scelte.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >Non è possibile mappare ogni tabella più di una volta. Pertanto, noterai che le selezioni a discesa non includeranno le tabelle già mappate.

1. Clic **[!UICONTROL OK]** per confermare: l’applicazione avrà bisogno di un breve momento per leggere le informazioni sul campo associate alle tabelle selezionate.

Puoi quindi procedere con la configurazione della mappatura. [Ulteriori informazioni](#new-mapping-settings)

>[!IMPORTANT]
>
>È possibile scegliere le tabelle in questa pagina solo quando si aggiunge la mappatura per la prima volta. Accertati di aver selezionato le tabelle corrette prima di fare clic su **[!UICONTROL Save]** una volta salvati, i campi di selezione della tabella saranno **sola lettura**.

### Modificare una mappatura esistente

Se modifichi una mappatura esistente, vedrai che le selezioni della tabella non sono modificabili.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Questo è per progettazione perché gli input più in basso nella pagina sono basati sui campi associati a queste tabelle. La modifica delle tabelle renderebbe non validi tutti i campi associati a tali tabelle.  Se desideri modificare la tabella da mappare a, dovrai tornare alla pagina precedente, eliminare la mappatura che desideri modificare e aggiungere una nuova mappatura.

### Configurare una mappatura di tabella singola {#new-mapping-settings}

In questa sezione imparerai a configurare una **singolo** mappatura di una tabella Microsoft Dynamics 365 a una tabella Adobe Campaign.

Puoi definire le seguenti impostazioni:

* **[!UICONTROL Tables]**: in questa sezione vengono elencati il nome della tabella Microsoft Dynamics 365 e della tabella Campaign a cui verrà mappata.
* **[!UICONTROL Field Mappings]**: ulteriori informazioni in [questa sezione](#field-mappings)
* **[!UICONTROL Field Replacements]**: ulteriori informazioni in [questa sezione](#field-replacements)
* **[!UICONTROL Filters]**: ulteriori informazioni in [questa sezione](#filters)
* **[!UICONTROL Advanced Settings]**: ulteriori informazioni in [questa sezione](#advanced-settings)

### Mappature campi {#field-mappings}

#### Chiavi primarie

Quando aggiungi una nuova mappatura di tabella Microsoft Dynamics 365 a Campaign, devi identificare il campo ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La chiave primaria di Microsoft Dynamics 365 è di sola lettura perché verrà rilevata dall&#39;applicazione.

Per Campaign, devi selezionare quale campo sarà la chiave univoca. Deve essere configurato come [Risorsa personalizzata ID CRM](../../developing/using/uc-calling-resource-id-key.md) e non devono avere duplicati.

>[!NOTE]
>
>Potrai scegliere il campo ID sulla tabella solo dopo aver selezionato **[!UICONTROL Add New Mapping]**. Se fai clic sul pulsante Modifica per modificare una mappatura tabella esistente, il campo ID sarà di sola lettura.

Le chiavi primarie saranno sempre i primi nomi di campo elencati nel **[!UICONTROL Field Mappings]** sezione. La seguente icona è elencata a destra per ricordarti che si tratta delle chiavi primarie.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Aggiungi altre mappature campi

Il **[!UICONTROL Field Mappings]** consente di aggiungere mappature di campi diverse da Chiavi primarie. Per aggiungere una nuova mappatura di un campo da Microsoft Dynamics 365 ad Adobe Campaign, fai clic sul pulsante **[!UICONTROL Add new field mapping]** pulsante.

Seleziona i campi Microsoft Dynamics 365 e Campaign negli elenchi:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Questi elenchi contengono i nomi dei campi associati alle tabelle Microsoft Dynamics 365 e Campaign selezionate nella parte superiore della pagina.

Il **[!UICONTROL Apply updates]** Il selettore consente di controllare se gli aggiornamenti a questo campo verranno propagati da Microsoft Dynamics 365 a Campaign:
* Se è acceso ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), gli aggiornamenti ai valori in Microsoft Dynamics 365 verranno propagati ad Adobe Campaign man mano che si verificano gli aggiornamenti.

* Se si è spento ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), il valore verrà propagato quando i dati vengono inizialmente caricati (o riprodotti), ma gli aggiornamenti incrementali al campo in Microsoft Dynamics 365 non verranno propagati.

>[!NOTE]
>
>Fai clic sul pulsante **[!UICONTROL Apply updates]** intestazione di colonna da aggiornare **tutto** degli interruttori su on o off.
>

Quando si selezionano i valori dei campi, sotto i menu a discesa viene visualizzato il tipo di dati.   È un aspetto da tenere presente quando si mappano i valori da un campo all’altro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> Non è possibile mappare più campi Microsoft Dynamics 365 a un singolo campo Campaign.

### Sostituzioni di campi {#field-replacements}

Utilizza il **[!UICONTROL Add New Field Replacement]** per definire una nuova sostituzione di campo.

Le sostituzioni dei campi consentono di identificare:

* un nome di campo di Microsoft Dynamics 365 (aggiunto in precedenza nella sezione mappature campi),
* un valore esistente (esistente in Microsoft Dynamics 365) e
* un nuovo valore da scrivere in Adobe Campaign

Verrà fornito un elenco a discesa per i valori di elenco a discesa, enumerazione e booleano. Verrà utilizzata una casella di testo per altri tipi di stringa e numerici.

### Filtri {#filters}

Utilizza il **[!UICONTROL Add New Filter]** per selezionare i record di Microsoft Dynamics 365 che verranno propagati a Campaign. Puoi scegliere qualsiasi campo associato a un record da aggiungere ai filtri (non è necessario aggiungere il nome del campo ai mapping dei campi).

È possibile specificare un filtro compilando le informazioni seguenti:

* Nome campo Microsoft Dynamics 365
* un valore di confronto, e
* un valore (da Microsoft Dynamics 365) Se il nome, il confronto e il valore del campo restituiscono true per un determinato record, il record verrà propagato ad Adobe Campaign.

Puoi scegliere come valutare questi filtri impostando l’input etichettato **[!UICONTROL Choose the filter comparison operator]**.  Se si sceglie **E**, tutti i filtri devono essere true affinché un record possa essere propagato a Campaign. Se si sceglie **Oppure**, il record verrà propagato se uno di essi restituisce true.

Opzione **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controlla se desideri che i record esclusi vengano eliminati da Campaign. Se si seleziona **No** quindi i record rimarranno in Adobe Campaign. Seleziona **Sì** per eliminarli mediante la logica di integrazione.

>[!NOTE]
>
> Se non vengono aggiunti filtri, tutti i record modificati verranno propagati ad Adobe Campaign.
>

### Impostazioni avanzate {#advanced-settings}

Durante la configurazione di una mappatura, puoi impostare le seguenti opzioni aggiuntive:

* Imposta il **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** opzione per **Sì**, se desideri propagare le eliminazioni che si verificano in Microsoft Dynamics 365 al campo corrispondente in Adobe Campaign (in base alla mappatura del nome del campo). Seleziona **No** per ignorare le eliminazioni in Microsoft Dynamics 365.

* Imposta il **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** opzione per **No** se desideri propagare a Campaign il valore visualizzato associato a un elenco a discesa di Microsoft Dynamics 365. Seleziona **Sì** per propagare il valore tecnico.

## Sincronizzare gli eventi di marketing di Campaign con Microsoft Dynamics 365

Il **[!UICONTROL Campaign to Microsoft Dynamics 365]** consente di identificare gli eventi di e-mail marketing da Adobe Campaign a Microsoft Dynamics 365.

Le quattro metriche che puoi controllare sono: **Invia**, **Clic**, **Aperture**, e **Mancati recapiti**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Seleziona **Sì** per confermare che desideri che gli eventi di quel tipo vengano trasmessi a Microsoft Dynamics 365.

Clic [qui](../../integrating/using/d365-acs-self-service-app-workflows.md) per ulteriori informazioni su questi flussi di eventi e-mail.

## Flusso di lavoro di consenso/rinuncia {#opt-in-out-wf}

Il **Consenso/rinuncia** Il flusso di lavoro consente di identificare il flusso di informazioni di consenso/diniego tra Microsoft Dynamics 365 e Adobe Campaign. Ciò presuppone che i dati siano associati al &quot;contatto&quot; dell’entità Microsoft Dynamics 365 e alla risorsa Adobe Campaign &quot;profilo&quot;.

Ulteriori informazioni sulla gestione delle rinunce in [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Ricorda che devi fare clic su &quot;Salva&quot; per salvare le selezioni. Ricorda inoltre che è necessario interrompere **Campaign a Microsoft Dynamics 365** flusso di lavoro, quindi fai clic su play per l’integrazione per incorporare le modifiche.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Direzione di sincronizzazione consenso/rinuncia

Di seguito è riportato l’elenco delle opzioni disponibili per la sincronizzazione dei dati:

* **[!UICONTROL Disabled]**: quando questa opzione è selezionata, tra Adobe Campaign e Microsoft Dynamics 365 non verranno spostate informazioni di consenso/rinuncia.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: questa opzione viene utilizzata per eseguire il flusso di consenso/rinuncia solo da Microsoft Dynamics 365 ad Adobe Campaign. L’applicazione di integrazione non consente di configurare il flusso in questa schermata; fai clic sul pulsante **[!UICONTROL Save button]**, e passare al **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flusso di lavoro. In questo flusso di lavoro, puoi modificare la mappatura della tabella contatti/profilo per identificare come mappare i campi di consenso/rinuncia.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: questa opzione rende visibile il **Mappature** sezione. Questi input ti consentono di definire quali campi di Adobe Campaign mapperanno i dati in base a quali campi in Microsoft Dynamics 365. Ciò significa che se si aggiorna manualmente un valore in Microsoft Dynamics 365, il relativo valore, in caso di modifica, verrebbe sovrascritto dal valore di Adobe Campaign.

* **[!UICONTROL Bidirectional]**: questa opzione rende visibile il **Mappature** sezione. Queste coppie identificheranno quali campi in Microsoft Dynamics 365 e Adobe Campaign verranno mappati tra loro. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Mappature

Questa sezione si applica solo quando il campo Opt-in/out direzione di sincronizzazione è impostato su **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. È possibile definire quali campi in Microsoft Dynamics 365 vengono mappati a quali input in Adobe Campaign.

I nomi dei campi di Microsoft Dynamics 365 includono tutti quelli di tipo **booleano**.

I nomi dei campi di Adobe Campaign sono un set fisso di valori specifici per il consenso/la rinuncia. I nomi dei campi di Adobe Campaign sono un set fisso di valori specifici per il consenso/la rinuncia. **Impossibile modificare il set di valori in questo elenco**.
