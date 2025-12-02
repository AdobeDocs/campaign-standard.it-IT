---
title: Sincronizzare i dati tra Campaign e Microsoft Dynamics
description: Sincronizzare i dati tra Campaign e Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1839'
ht-degree: 0%

---

# Sincronizzare i dati

Puoi sincronizzare le tabelle da Microsoft Dynamics 365 alle metriche di marketing di Campaign e Campaign a Microsoft Dynamics 365. La sincronizzazione viene eseguita tramite tre flussi di lavoro tecnici dedicati: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Fai riferimento a questa sezione per [ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>È necessario arrestare/avviare il flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per tenere conto delle modifiche. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## Mappare le tabelle da Microsoft Dynamics 365 a Campaign

La pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]** mostra un elenco di entità in Microsoft Dynamics 365 e le risorse personalizzate in Adobe Campaign con cui verranno sincronizzate. È possibile aggiungere nuove mappature, modificare o eliminare mappature esistenti.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

Segue una descrizione di ciascuna delle colonne della tabella:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: questa colonna identifica quale entità in Microsoft Dynamics 365 sarà l&#39;origine dei dati per la mappatura.

* **[!UICONTROL CAMPAIGN TABLE]**: questa colonna identifica quale risorsa in Adobe Campaign sarà la destinazione dei dati per la mappatura.

* **[!UICONTROL ACTIONS]**: le azioni possibili sono elencate di seguito:

   * Fare clic sull&#39;icona **[!UICONTROL Edit]** per modificare la mappatura.

   * Utilizzare l&#39;icona **[!UICONTROL Delete]** per eliminare un mapping di tabella.

   * Fare clic sull&#39;icona **[!UICONTROL Replay Data]** per risincronizzare tutti i dati nella tabella di Microsoft Dynamics 365. Normalmente l’applicazione di integrazione sincronizza solo i dati in Microsoft Dynamics 365 che sono stati modificati di recente.  Tuttavia, in alcuni casi (ad esempio, se hai apportato una modifica o commesso un errore) potresti voler risincronizzare tutti i dati.  In questi casi, fare clic su questo pulsante e, alla successiva interruzione o avvio del flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, i dati inizieranno a essere sincronizzati.

     Se si fa clic sul pulsante **[!UICONTROL Replay Data]** e i controlli hanno esito positivo, l&#39;icona verrà disabilitata: ciò indica che i dati per questa coppia di mapping della tabella verranno risincronizzati con la successiva esecuzione del flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**.

     Non è possibile scegliere di riprodurre nuovamente i dati quando si verificano le condizioni seguenti:

      * Se sono presenti 2.000.000 (o più) elementi nella metrica Backlog associata al flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (visualizzata nella pagina **[!UICONTROL Workflows]**)
      * Se nella tabella Microsoft Dynamics 365 sono presenti almeno 2.000.000 record

     Il numero di record da risincronizzare varia. Se il numero di record è elevato, il completamento del processo di sincronizzazione potrebbe richiedere del tempo. Fare riferimento alla metrica **[!UICONTROL Backlog]** nella pagina **[!UICONTROL Workflows]** poiché l&#39;applicazione di integrazione lavora per completare il processo di sincronizzazione.

     >[!IMPORTANT]
     >
     > Si consiglia vivamente di arrestare il flusso di lavoro di integrazione quando si pubblicano modifiche a Adobe Campaign Standard o Microsoft Dynamics 365. Le modifiche applicabili includono: aggiornamenti a risorse/entità (e ai relativi campi associati), collegamenti, colonne di identificatori e così via. attualmente in uso dall’integrazione.
     >

## Crea una nuova mappatura {#add-a-new-mapping}

Per creare una nuova mappatura, effettua le seguenti operazioni:

1. nella pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]** fare clic sul pulsante **[!UICONTROL Add New Mapping]**.

1. Utilizza gli elenchi a discesa per selezionare le tabelle Microsoft Dynamics 365 e Campaign da mappare.
La maggior parte degli altri input nella pagina dipenderà dalle tabelle scelte.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >Non è possibile mappare ogni tabella più di una volta. Pertanto, noterai che le selezioni a discesa non includeranno le tabelle già mappate.

1. Fare clic su **[!UICONTROL OK]** per confermare: l&#39;applicazione necessiterà di un breve momento per leggere le informazioni sul campo associate alle tabelle selezionate.

Puoi quindi procedere con la configurazione della mappatura. [Ulteriori informazioni](#new-mapping-settings)

>[!IMPORTANT]
>
>È possibile scegliere le tabelle in questa pagina solo quando si aggiunge la mappatura per la prima volta. Assicurarsi di aver selezionato le tabelle corrette prima di fare clic sul pulsante **[!UICONTROL Save]**: una volta salvate, i campi di selezione della tabella saranno **di sola lettura**.

### Modificare una mappatura esistente

Se modifichi una mappatura esistente, vedrai che le selezioni della tabella non sono modificabili.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Questo è per progettazione perché gli input più in basso nella pagina sono basati sui campi associati a queste tabelle. La modifica delle tabelle renderebbe non validi tutti i campi associati a tali tabelle.  Se desideri modificare la tabella da mappare a, dovrai tornare alla pagina precedente, eliminare la mappatura che desideri modificare e aggiungere una nuova mappatura.

### Configurare una mappatura di tabella singola {#new-mapping-settings}

In questa sezione verrà illustrato come configurare una mappatura **singola** di una tabella Microsoft Dynamics 365 in una tabella Adobe Campaign.

Puoi definire le seguenti impostazioni:

* **[!UICONTROL Tables]**: questa sezione elenca il nome della tabella Microsoft Dynamics 365 e della tabella Campaign a cui verrà mappata.
* **[!UICONTROL Field Mappings]**: ulteriori informazioni in [questa sezione](#field-mappings)
* **[!UICONTROL Field Replacements]**: ulteriori informazioni in [questa sezione](#field-replacements)
* **[!UICONTROL Filters]**: ulteriori informazioni in [questa sezione](#filters)
* **[!UICONTROL Advanced Settings]**: ulteriori informazioni in [questa sezione](#advanced-settings)

### Mappature campi {#field-mappings}

#### Chiavi primarie

Quando aggiungi un nuovo Microsoft Dynamics 365 alla mappatura della tabella di Campaign, devi identificare il campo ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La chiave primaria di Microsoft Dynamics 365 è di sola lettura perché verrà rilevata dall&#39;applicazione.

Per Campaign, devi selezionare quale campo sarà la chiave univoca. Deve essere configurato come [risorsa personalizzata ID CRM](../../developing/using/uc-calling-resource-id-key.md) e non deve contenere duplicati.

>[!NOTE]
>
>Potrai scegliere il campo ID nella tabella solo dopo aver selezionato **[!UICONTROL Add New Mapping]**. Se fai clic sul pulsante Modifica per modificare una mappatura tabella esistente, il campo ID sarà di sola lettura.

Le chiavi primarie saranno sempre i primi nomi di campo elencati nella sezione **[!UICONTROL Field Mappings]**. La seguente icona è elencata a destra per ricordarti che si tratta delle chiavi primarie.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Aggiungi altre mappature campi

La sezione **[!UICONTROL Field Mappings]** consente di aggiungere mappature di campi diverse dalle chiavi primarie. Per aggiungere una nuova mappatura di un campo da Microsoft Dynamics 365 ad Adobe Campaign, fare clic sul pulsante **[!UICONTROL Add new field mapping]**.

Seleziona i campi Microsoft Dynamics 365 e Campaign negli elenchi:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Questi elenchi contengono i nomi dei campi associati alle tabelle Microsoft Dynamics 365 e Campaign selezionate nella parte superiore della pagina.

Il commutatore **[!UICONTROL Apply updates]** consente di controllare se gli aggiornamenti a questo campo verranno propagati da Microsoft Dynamics 365 a Campaign:
* Se è attivato ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), gli aggiornamenti ai valori in Microsoft Dynamics 365 verranno propagati ad Adobe Campaign man mano che si verificano gli aggiornamenti.

* Se si disattiva ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), il valore verrà propagato al caricamento iniziale (o alla ripetizione) dei dati, ma gli aggiornamenti incrementali al campo in Microsoft Dynamics 365 non verranno propagati.

>[!NOTE]
>
>Fai clic sull&#39;intestazione della colonna **[!UICONTROL Apply updates]** per aggiornare **all** dei passaggi a attivato o disattivato.
>

Quando si selezionano i valori dei campi, sotto i menu a discesa viene visualizzato il tipo di dati.   È un aspetto da tenere presente quando si mappano i valori da un campo all’altro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> Non è possibile mappare più campi Microsoft Dynamics 365 a un singolo campo Campaign.

### Sostituzioni di campi {#field-replacements}

Utilizza il pulsante **[!UICONTROL Add New Field Replacement]** per definire una nuova sostituzione di campo.

Le sostituzioni dei campi consentono di identificare:

* un nome di campo Microsoft Dynamics 365 (aggiunto in precedenza nella sezione mappature campi),
* un valore esistente (esistente in Microsoft Dynamics 365), e
* un nuovo valore da scrivere in Adobe Campaign

Verrà fornito un elenco a discesa per i valori di elenco a discesa, enumerazione e booleano. Verrà utilizzata una casella di testo per altri tipi di stringa e numerici.

### Filtri {#filters}

Utilizza il pulsante **[!UICONTROL Add New Filter]** per selezionare i record di Microsoft Dynamics 365 che verranno propagati a Campaign. Puoi scegliere qualsiasi campo associato a un record da aggiungere ai filtri (non è necessario aggiungere il nome del campo ai mapping dei campi).

È possibile specificare un filtro compilando le informazioni seguenti:

* Nome campo Microsoft Dynamics 365
* un valore di confronto, e
* un valore (da Microsoft Dynamics 365)
Se il nome, il confronto e il valore del campo sono pari a true per un determinato record, il record verrà propagato ad Adobe Campaign.

È possibile scegliere come valutare questi filtri impostando l&#39;input con etichetta **[!UICONTROL Choose the filter comparison operator]**.  Se scegli **And**, tutti i filtri devono essere true affinché un record possa essere propagato a Campaign. Se si sceglie **Or**, il record verrà propagato se uno di essi restituisce true.

L&#39;opzione **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controlla se si desidera eliminare da Campaign i record filtrati. Se si seleziona **No**, i record rimarranno in Adobe Campaign. Seleziona **Sì** per eliminarli dalla logica di integrazione.

>[!NOTE]
>
> Se non vengono aggiunti filtri, tutti i record modificati verranno propagati ad Adobe Campaign.
>

### Impostazioni avanzate {#advanced-settings}

Durante la configurazione di una mappatura, puoi impostare le seguenti opzioni aggiuntive:

* Impostare l&#39;opzione **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** su **Sì** se si desidera propagare le eliminazioni che si verificano in Microsoft Dynamics 365 al campo corrispondente in Adobe Campaign (in base alla mappatura del nome del campo). Selezionare **No** per ignorare le eliminazioni in Microsoft Dynamics 365.

* Impostare l&#39;opzione **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** su **No** se si desidera propagare a Campaign il valore di visualizzazione associato a un elenco di selezione di Microsoft Dynamics 365. Selezionare **Sì** per propagare il valore tecnico.

## Sincronizzare gli eventi di marketing di Campaign con Microsoft Dynamics 365

La pagina **[!UICONTROL Campaign to Microsoft Dynamics 365]** consente di identificare gli eventi di e-mail marketing da mappare da Adobe Campaign a Microsoft Dynamics 365.

Le quattro metriche che puoi controllare sono: **Invii**, **Clic**, **Aperture** e **Rimbalzi**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Selezionare **Sì** per confermare che si desidera che gli eventi di quel tipo vengano indirizzati a Microsoft Dynamics 365.

Fai clic [qui](../../integrating/using/d365-acs-self-service-app-workflows.md) per ulteriori informazioni su questi flussi di eventi e-mail.

## Flusso di lavoro di consenso/rinuncia {#opt-in-out-wf}

Il flusso di lavoro **Opt-in/Out** ti consente di identificare il flusso di informazioni di consenso/diniego tra Microsoft Dynamics 365 e Adobe Campaign. Ciò presuppone che i dati siano associati al &quot;contatto&quot; dell’entità Microsoft Dynamics 365 e alla risorsa Adobe Campaign &quot;profilo&quot;.

Ulteriori informazioni sulla gestione delle rinunce in [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Ricorda che devi fare clic su &quot;Salva&quot; per salvare le selezioni. Ricorda inoltre che devi arrestare il flusso di lavoro **Campaign to Microsoft Dynamics 365** e quindi fare clic su Riproduci per l&#39;integrazione per incorporare le modifiche.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Direzione di sincronizzazione consenso/rinuncia

Di seguito è riportato l’elenco delle opzioni disponibili per la sincronizzazione dei dati:

* **[!UICONTROL Disabled]**: quando questa opzione è selezionata, nessuna informazione di consenso/rinuncia verrà spostata tra Adobe Campaign e Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: questa opzione viene utilizzata per eseguire il flusso di consenso/rinuncia da Microsoft Dynamics 365 solo ad Adobe Campaign. L&#39;applicazione di integrazione non consente di configurare il flusso in questa schermata. Fare clic su **[!UICONTROL Save button]** e passare al flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. In questo flusso di lavoro, puoi modificare la mappatura della tabella contatti/profilo per identificare come mappare i campi di consenso/rinuncia.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: questa opzione renderà visibile la sezione **Mappature**. Questi input ti consentiranno di definire quali campi di Adobe Campaign mapperanno i dati in quali campi in Microsoft Dynamics 365. Ciò significa che se si aggiorna manualmente un valore in Microsoft Dynamics 365, il suo valore, in caso di modifica, verrebbe sovrascritto dal valore di Adobe Campaign.

* **[!UICONTROL Bidirectional]**: questa opzione renderà visibile la sezione **Mappature**. Queste coppie identificheranno quali campi in Microsoft Dynamics 365 e Adobe Campaign verranno mappati tra loro. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Mappature

Questa sezione si applica solo quando il campo Direzione di sincronizzazione Opt-in/Out è impostato su **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. Puoi definire quali campi in Microsoft Dynamics 365 mappano agli input in Adobe Campaign.

I nomi dei campi di Microsoft Dynamics 365 includono tutti quelli di tipo **booleano**.

I nomi dei campi di Adobe Campaign sono un set fisso di valori specifici per il consenso/la rinuncia. I nomi dei campi di Adobe Campaign sono un set fisso di valori specifici per il consenso/la rinuncia. **Impossibile modificare il set di valori in questo elenco**.
