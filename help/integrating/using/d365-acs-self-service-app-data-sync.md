---
title: Sincronizzazione dei dati tra Campaign e Microsoft Dynamics
description: Sincronizzazione dei dati tra Campaign e Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---


# Sincronizza dati

Puoi sincronizzare le tabelle da Microsoft Dynamics 365 alle metriche di marketing Campaign e Campaign con Microsoft Dynamics 365. La sincronizzazione viene eseguita tramite tre flussi di lavoro tecnici dedicati: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Fare riferimento a questa sezione per [ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>Per tenere conto delle modifiche, è necessario arrestare/avviare il flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md)


## Mappare le tabelle da Microsoft Dynamics 365 a Campaign

La pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]** mostra un elenco di entità in Microsoft Dynamics 365 e le risorse personalizzate in  Adobe Campaign con cui verranno sincronizzate. È possibile aggiungere nuove mappature, modificare o eliminare mappature esistenti.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

Di seguito è riportata una descrizione di ciascuna colonna della tabella:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: questa colonna identifica quale entità in Microsoft Dynamics 365 sarà l&#39;origine dei dati per la mappatura.

* **[!UICONTROL CAMPAIGN TABLE]**: questa colonna identifica la risorsa in  Adobe Campaign che sarà la destinazione dei dati per la mappatura.

* **[!UICONTROL ACTIONS]**: le possibili azioni sono elencate di seguito:

   * Fate clic sull&#39;icona **[!UICONTROL Edit]** per modificare la mappatura.

   * Utilizzare l&#39;icona **[!UICONTROL Delete]** per eliminare una mappatura tabella.

   * Fare clic sull&#39;icona **[!UICONTROL Replay Data]** per sincronizzare nuovamente tutti i dati nella tabella di Microsoft Dynamics 365. Normalmente l&#39;applicazione di integrazione sincronizzerà solo i dati in Microsoft Dynamics 365 modificati di recente.  Tuttavia, in alcuni casi (ad esempio, se hai apportato una modifica o hai commesso un errore) potresti voler risincronizzare tutti i dati.  In questi casi, si faceva clic su questo pulsante e, al successivo arresto/avvio del flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, i dati iniziavano a sincronizzarsi.

      Se si fa clic sul pulsante **[!UICONTROL Replay Data]** e i controlli vengono eseguiti correttamente, l&#39;icona viene disattivata: indica che i dati per questa coppia di mappatura tabella verranno risincronizzati con la successiva esecuzione del flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**.

      Non è possibile selezionare di riprodurre nuovamente i dati quando le seguenti informazioni sono vere:

      * Se sono presenti 2.000.000 (o più) elementi nella metrica Backlog associata al flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (visualizzata nella pagina **[!UICONTROL Workflows]**)
      * Se sono presenti 2.000.000 o più record nella tabella di Microsoft Dynamics 365

      Il numero di record da risincronizzare varia. Se si dispone di un numero elevato di record, il completamento del processo di sincronizzazione potrebbe richiedere del tempo. Fare riferimento alla metrica **[!UICONTROL Backlog]** nella pagina **[!UICONTROL Workflows]** quando l&#39;applicazione di integrazione funziona per completare il processo di sincronizzazione.

      >[!IMPORTANT]
      >
      > Si consiglia vivamente di interrompere il flusso di lavoro di integrazione quando si pubblicano modifiche ad  Adobe Campaign Standard o Microsoft Dynamics 365. Le modifiche applicabili includono: aggiornamenti a risorse/entità (e relativi campi associati), collegamenti, colonne di identificatori, ecc. attualmente in uso nell&#39;integrazione.




## Creare una nuova mappatura {#add-a-new-mapping}

Per creare una nuova mappatura, effettuate le seguenti operazioni:

1. nella pagina **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, fare clic sul pulsante **[!UICONTROL Add New Mapping]**.

1. Utilizzare gli elenchi a discesa per selezionare le tabelle di Microsoft Dynamics 365 e Campaign da mappare.
La maggior parte degli altri input sulla pagina dipenderà dalle tabelle scelte.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >Non è possibile mappare ogni tabella più di una volta. Pertanto, noterete che le selezioni a discesa non includeranno tabelle già mappate.

1. Fare clic su **[!UICONTROL OK]** per confermare: l&#39;applicazione avrà bisogno di un breve momento per leggere le informazioni sul campo associate alle tabelle selezionate.

Potete quindi procedere con la configurazione della mappatura. [Ulteriori informazioni](#new-mapping-settings)

>[!IMPORTANT]
>
>È possibile scegliere le tabelle in questa pagina solo quando si aggiunge la mappatura per la prima volta. Assicurarsi di aver selezionato le tabelle corrette prima di fare clic sul pulsante **[!UICONTROL Save]**: una volta salvati, i campi di selezione della tabella saranno **di sola lettura**.

### Modificare una mappatura esistente

Se modificate una mappatura esistente, le selezioni delle tabelle non saranno modificabili.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Questo avviene in base alla progettazione, in quanto gli input nella pagina sono basati sui campi associati a tali tabelle. La modifica delle tabelle renderebbe non validi tutti i campi associati a tali tabelle.  Se si desidera modificare la tabella in cui eseguire la mappatura, sarà necessario tornare alla pagina precedente, eliminare la mappatura che si desidera modificare e aggiungere una nuova mappatura.

### Configurare una mappatura tabella singola {#new-mapping-settings}

In questa sezione verrà illustrato come configurare una mappatura **singola** di una tabella di Microsoft Dynamics 365 su una  tabella Adobe Campaign.

Potete definire le seguenti impostazioni:

* **[!UICONTROL Tables]**: in questa sezione sono elencati il nome della tabella di Microsoft Dynamics 365 e la tabella Campaign a cui verrà mappato.
* **[!UICONTROL Field Mappings]**: ulteriori informazioni in  [questa sezione](#field-mappings)
* **[!UICONTROL Field Replacements]**: ulteriori informazioni in  [questa sezione](#field-replacements)
* **[!UICONTROL Filters]**: ulteriori informazioni in  [questa sezione](#filters)
* **[!UICONTROL Advanced Settings]**: ulteriori informazioni in  [questa sezione](#advanced-settings)

### Mappature campi {#field-mappings}

#### Chiavi principali

Quando aggiungi una nuova Microsoft Dynamics 365 alla mappatura della tabella Campaign, devi identificare il campo ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La chiave primaria di Microsoft Dynamics 365 è di sola lettura perché verrà rilevata dall&#39;applicazione.

Per Campaign, devi selezionare quale campo sarà la chiave univoca. Deve essere configurato come risorsa personalizzata [ID CRM](../../developing/using/uc-calling-resource-id-key.md) e non deve avere duplicati.

>[!NOTE]
>
>Potrai scegliere il campo ID nella tabella solo se hai selezionato **[!UICONTROL Add New Mapping]**. Se fai clic sul pulsante Modifica per modificare una mappatura tabella esistente, il campo ID sarà di sola lettura.

Le chiavi primarie saranno sempre i nomi dei campi elencati nella sezione **[!UICONTROL Field Mappings]**. Come promemoria, la seguente icona è elencata a destra per ricordare che queste sono le chiavi principali.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Aggiungere altri mapping di campi

La sezione **[!UICONTROL Field Mappings]** consente di aggiungere mappature di campi diverse dalle chiavi primarie. Per aggiungere una nuova mappatura di un campo da Microsoft Dynamics 365 a  Adobe Campaign, fare clic sul pulsante **[!UICONTROL Add new field mapping]**.

Seleziona i campi di Microsoft Dynamics 365 e Campaign negli elenchi:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Questi elenchi contengono i nomi dei campi associati alle tabelle di Microsoft Dynamics 365 e Campaign selezionate nella parte superiore della pagina.

Il commutatore **[!UICONTROL Apply updates]** consente di controllare se gli aggiornamenti a questo campo verranno propagati da Microsoft Dynamics 365 a Campaign:
* Se è attivato ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), gli aggiornamenti ai valori in Microsoft Dynamics 365 verranno propagati ad  Adobe Campaign non appena si verificano gli aggiornamenti.

* Se si spegne ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), il valore verrà propagato quando i dati vengono inizialmente caricati (o riprodotti), ma gli aggiornamenti incrementali al campo in Microsoft Dynamics 365 non verranno propagati.

>[!NOTE]
>
>Fare clic sull&#39;intestazione di colonna **[!UICONTROL Apply updates]** per aggiornare **all** degli switch attivati o disattivati.


Quando si selezionano i valori dei campi, sotto i menu a discesa viene visualizzato il tipo di dati.   Questo è qualcosa da tenere presente quando si mappano i valori da un campo all&#39;altro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> Non è possibile mappare più campi di Microsoft Dynamics 365 su un singolo campo Campaign.

### Sostituzioni campo {#field-replacements}

Utilizzare il pulsante **[!UICONTROL Add New Field Replacement]** per definire una nuova sostituzione di campo.

Le sostituzioni dei campi consentono di identificare:

* un nome di campo di Microsoft Dynamics 365 (aggiunto sopra nella sezione delle mappature dei campi),
* un valore esistente (presente in Microsoft Dynamics 365), e
* un nuovo valore da scrivere in  Adobe Campaign

Verrà fornito un elenco a discesa per i valori di elenco di selezione, enumerazione e booleano. Per altri tipi di stringa e numerici viene utilizzata una casella di testo.

### Filtri {#filters}

Utilizzate il pulsante **[!UICONTROL Add New Filter]** per selezionare quali record di Microsoft Dynamics 365 verranno propagati a Campaign. È possibile scegliere qualsiasi campo associato a un record da aggiungere ai filtri (il nome del campo non deve essere aggiunto alle mappature dei campi).

Potete specificare un filtro compilando le seguenti informazioni:

* Nome campo di Microsoft Dynamics 365
* un valore di confronto e
* un valore (da Microsoft Dynamics 365)
Se il nome, il confronto e il valore del campo corrispondono a true per un dato record, il record verrà propagato a  Adobe Campaign.

È possibile scegliere come valutare questi filtri impostando l&#39;input con etichetta **[!UICONTROL Choose the filter comparison operator]**.  Se scegli **And**, tutti i filtri devono essere veri affinché un record venga propagato a Campaign. Se si sceglie **O**, il record verrà propagato se uno di essi restituisce true.

L&#39;opzione **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controlla se i record filtrati devono essere eliminati da Campaign. Se si seleziona **No**, i record resteranno in  Adobe Campaign. Selezionare **Sì** per fare in modo che vengano eliminati dalla logica di integrazione.

>[!NOTE]
>
> Se non vengono aggiunti filtri, tutti i record modificati verranno propagati  Adobe Campaign.


### Impostazioni avanzate {#advanced-settings}

Durante la configurazione di una mappatura è possibile impostare le seguenti opzioni aggiuntive:

* Impostate l&#39;opzione **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** su **Sì**, se desiderate estendere le eliminazioni che si verificano in Microsoft Dynamics 365 al campo corrispondente in  Adobe Campaign (in base al mapping dei nomi dei campi). Selezionare **No** per ignorare le eliminazioni in Microsoft Dynamics 365.

* Impostate l&#39;opzione **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** su **No** se desiderate estendere a Campaign il valore di visualizzazione associato a un elenco di selezione di Microsoft Dynamics 365. Selezionare **Sì** per estendere il valore tecnico.

## Sincronizzare gli eventi di marketing delle campagne con Microsoft Dynamics 365

La pagina **[!UICONTROL Campaign to Microsoft Dynamics 365]** consente di identificare gli eventi di e-mail marketing che verranno mappati da  Adobe Campaign a Microsoft Dynamics 365.

Le quattro metriche che puoi controllare sono: **Invia**, **Clic**, **Apre** e **Blocchi**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Selezionare **Yes** per confermare che gli eventi di quel tipo devono scorrere in Microsoft Dynamics 365.

Fare clic [qui](../../integrating/using/d365-acs-self-service-app-workflows.md) per ulteriori informazioni su questi flussi di eventi e-mail.

## Flusso di lavoro di rifiuto {#opt-in-out-wf}

Il flusso di lavoro **Opt-In/Out** consente di identificare il flusso delle informazioni di opt in/out tra Microsoft Dynamics 365 e  Adobe Campaign. Si parte dal presupposto che i dati siano associati all&#39;entità &quot;contact&quot; di Microsoft Dynamics 365 e al &quot;profile&quot; della risorsa Adobe Campaign .

Ulteriori informazioni sulla gestione del rifiuto in [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Ricorda che devi fare clic su &quot;Salva&quot; per salvare le selezioni. È inoltre necessario arrestare il flusso di lavoro **Campaign to Microsoft Dynamics 365**, quindi fare clic su play per l&#39;integrazione per includere le modifiche.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Direzione sincronizzazione consenso/uscita

Di seguito è riportato l&#39;elenco delle opzioni disponibili per la sincronizzazione dei dati:

* **[!UICONTROL Disabled]**: quando questa opzione è selezionata, tra  Adobe Campaign e Microsoft Dynamics 365 non verranno spostate le informazioni relative al rifiuto.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: questa opzione viene utilizzata per far scorrere l&#39;opzione di rifiuto da Microsoft Dynamics 365 a  solo Adobe Campaign. L&#39;applicazione di integrazione non consente di configurare il flusso in questa schermata; fare clic su **[!UICONTROL Save button]** e passare al flusso di lavoro **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. In questo flusso di lavoro, puoi modificare la mappatura della tabella contatti/profili per identificare la mappatura desiderata per i campi di rinuncia.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: questa opzione renderà visibile la  **** sezione Mappingseection. Questi input consentono di definire quali  campi Adobe Campaign mapperanno i dati sui campi in Microsoft Dynamics 365. Ciò significa che se si aggiorna manualmente un valore in Microsoft Dynamics 365, in caso di modifica il suo valore viene sovrascritto dal valore Adobe Campaign .

* **[!UICONTROL Bidirectional]**: questa opzione renderà visibile la  **** sezione Mappingseection. Queste coppie identificheranno i campi in Microsoft Dynamics 365 e  Adobe Campaign verranno mappati tra loro. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Mappature

Questa sezione si applica solo quando il campo della direzione di sincronizzazione Opt-in/out è impostato su **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. È possibile definire quali campi in Microsoft Dynamics 365 vengono mappati sugli input in  Adobe Campaign.

I nomi dei campi di Microsoft Dynamics 365 includono tutti quelli di tipo **booleano**.

I nomi dei campi Adobe Campaign  sono un insieme fisso di valori specifici per l&#39;opzione di rifiuto. I nomi dei campi Adobe Campaign  sono un insieme fisso di valori specifici per l&#39;opzione di rifiuto. **Impossibile modificare** l&#39;insieme di valori in questo elenco.
