---
title: Sincronizzazione dei dati tra Campaign e Microsoft Dynamics
description: Sincronizzazione dei dati tra Campaign e Dynamics
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
source-wordcount: '1795'
ht-degree: 0%

---

# Sincronizzare i dati

Puoi sincronizzare le tabelle da Microsoft Dynamics 365 alle metriche di marketing Campaign e Campaign con Microsoft Dynamics 365. La sincronizzazione viene eseguita tramite tre flussi di lavoro tecnici dedicati: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Fai riferimento a questa sezione per [ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>È necessario arrestare/avviare il **[!UICONTROL Microsoft Dynamics 365 to Campaign]** per tenere conto delle modifiche. [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Mappare tabelle da Microsoft Dynamics 365 a Campaign

La **[!UICONTROL Microsoft Dynamics 365 to Campaign]** in questa pagina viene visualizzato un elenco delle entità in Microsoft Dynamics 365 e delle risorse personalizzate in Adobe Campaign con cui verranno sincronizzate. Puoi aggiungere nuove mappature, modificare o eliminare mappature esistenti.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

Segue una descrizione di ciascuna colonna di questa tabella:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: questa colonna identifica quale entità in Microsoft Dynamics 365 sarà l’origine dei dati per la mappatura.

* **[!UICONTROL CAMPAIGN TABLE]**: questa colonna identifica la risorsa in Adobe Campaign che sarà la destinazione dei dati per la mappatura.

* **[!UICONTROL ACTIONS]**: di seguito sono elencate le possibili azioni:

   * Fai clic sul pulsante **[!UICONTROL Edit]** per modificare la mappatura.

   * Utilizza la  **[!UICONTROL Delete]** per eliminare una mappatura tabella.

   * Fai clic sul pulsante **[!UICONTROL Replay Data]** per sincronizzare nuovamente tutti i dati della tabella Microsoft Dynamics 365. Normalmente l’applicazione di integrazione sincronizza solo i dati in Microsoft Dynamics 365 che sono stati modificati di recente.  Tuttavia, in alcuni casi (ad esempio, se hai apportato una modifica o hai commesso un errore) potresti voler risincronizzare tutti i dati.  In questi casi, fai clic su questo pulsante e, alla successiva interruzione/avvio del **[!UICONTROL Microsoft Dynamics 365 to Campaign]** workflow, i tuoi dati inizierebbero a sincronizzarsi.

      Se fai clic sul pulsante **[!UICONTROL Replay Data]** e i controlli hanno esito positivo. L’icona verrà disabilitata: indica che i dati per questa coppia di mappatura tabella verranno risincronizzati con l&#39;esecuzione successiva del **[!UICONTROL Microsoft Dynamics 365 to Campaign]** workflow.

      Non è possibile selezionare di riprodurre nuovamente i dati quando sono soddisfatte le seguenti condizioni:

      * Se ci sono 2.000.000 (o più) elementi nella metrica Backlog associata al **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (visualizzato nel **[!UICONTROL Workflows]** page)
      * Se nella tabella Microsoft Dynamics 365 sono presenti almeno 2.000.000 record

      Il numero di record da risincronizzare varia. Se disponi di un numero elevato di record, può essere necessario un po&#39; di tempo per completare il processo di sincronizzazione. Fai riferimento a **[!UICONTROL Backlog]** nella metrica **[!UICONTROL Workflows]** mentre l&#39;applicazione di integrazione funziona per completare il processo di sincronizzazione.

      >[!IMPORTANT]
      >
      > Si consiglia vivamente di interrompere il flusso di lavoro di integrazione quando si pubblicano le modifiche ad Adobe Campaign Standard o Microsoft Dynamics 365. Le modifiche applicabili includono: aggiornamenti a risorse/entità (e relativi campi associati), collegamenti, colonne di identificatore, ecc. che sono attualmente in uso dall’integrazione.


## Creare una nuova mappatura {#add-a-new-mapping}

Per creare una nuova mappatura, effettua le seguenti operazioni:

1. in **[!UICONTROL Microsoft Dynamics 365 to Campaign]** fai clic su **[!UICONTROL Add New Mapping]** pulsante .

1. Utilizza gli elenchi a discesa per selezionare le tabelle Microsoft Dynamics 365 e Campaign da mappare.
La maggior parte degli altri input sulla pagina dipenderà dalle tabelle selezionate.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >Non è possibile mappare ogni tabella più di una volta. Pertanto, noterai che le selezioni del menu a discesa non includeranno tabelle già mappate.

1. Fai clic su **[!UICONTROL OK]** per confermare: l&#39;applicazione avrà bisogno di un breve momento per leggere le informazioni sul campo associate alle tabelle selezionate.

Puoi quindi procedere con la configurazione della mappatura. [Ulteriori informazioni](#new-mapping-settings)

>[!IMPORTANT]
>
>Puoi scegliere le tabelle in questa pagina solo quando aggiungi la mappatura per la prima volta. Prima di fare clic sul pulsante **[!UICONTROL Save]** pulsante: una volta salvati, i campi di selezione della tabella verranno **sola lettura**.

### Modificare una mappatura esistente

Se modifichi una mappatura esistente, noterai che le selezioni della tabella non sono modificabili.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Questo avviene in base alla progettazione, in quanto gli input più giù nella pagina sono basati sui campi associati a queste tabelle. La modifica delle tabelle renderebbe non validi tutti i campi associati a queste tabelle.  Se desideri modificare la tabella per la mappatura, dovrai tornare alla pagina precedente, eliminare la mappatura da modificare e aggiungere una nuova mappatura.

### Configurare una mappatura tabella singola {#new-mapping-settings}

In questa sezione viene illustrato come configurare un **singolo** mappatura di una tabella Microsoft Dynamics 365 a una tabella Adobe Campaign.

Puoi definire le seguenti impostazioni:

* **[!UICONTROL Tables]**: in questa sezione sono elencati il nome della tabella Microsoft Dynamics 365 e della tabella Campaign a cui verrà mappata.
* **[!UICONTROL Field Mappings]**: ulteriori informazioni in [questa sezione](#field-mappings)
* **[!UICONTROL Field Replacements]**: ulteriori informazioni in [questa sezione](#field-replacements)
* **[!UICONTROL Filters]**: ulteriori informazioni in [questa sezione](#filters)
* **[!UICONTROL Advanced Settings]**: ulteriori informazioni in [questa sezione](#advanced-settings)

### Mappature dei campi {#field-mappings}

#### Chiavi principali

Quando aggiungi una nuova Microsoft Dynamics 365 alla mappatura tabella Campaign, devi identificare il campo ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La chiave primaria di Microsoft Dynamics 365 è di sola lettura perché l’applicazione la rileverà.

Per Campaign, devi selezionare quale campo sarà la chiave univoca. Deve essere configurato come [Risorsa personalizzata ID CRM](../../developing/using/uc-calling-resource-id-key.md) e non devono avere duplicati.

>[!NOTE]
>
>Puoi scegliere il campo ID sulla tabella solo dopo aver selezionato **[!UICONTROL Add New Mapping]**. Se fai clic sul pulsante Modifica per modificare una mappatura tabella esistente, il campo ID sarà di sola lettura.

Le chiavi primarie saranno sempre i nomi dei campi elencati in **[!UICONTROL Field Mappings]** sezione . Come promemoria, la seguente icona è elencata a destra per ricordarti che sono le chiavi principali.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Aggiungi altre mappature campo

La **[!UICONTROL Field Mappings]** La sezione ti consente di aggiungere mappature campo diverse dalle chiavi primarie. Per aggiungere una nuova mappatura di un campo da Microsoft Dynamics 365 ad Adobe Campaign, fai clic sul pulsante **[!UICONTROL Add new field mapping]** pulsante .

Seleziona i campi Microsoft Dynamics 365 e Campaign negli elenchi:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Questi elenchi contengono i nomi dei campi associati alle tabelle Microsoft Dynamics 365 e Campaign selezionate nella parte superiore della pagina.

La **[!UICONTROL Apply updates]** il commutatore ti consente di controllare se gli aggiornamenti a questo campo verranno propagati da Microsoft Dynamics 365 a Campaign:
* Se è acceso ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), gli aggiornamenti ai valori in Microsoft Dynamics 365 verranno propagati ad Adobe Campaign man mano che si verificano gli aggiornamenti.

* Se si spegne ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), il valore viene propagato al caricamento o alla riproduzione iniziale dei dati, ma gli aggiornamenti incrementali al campo in Microsoft Dynamics 365 non verranno propagati.

>[!NOTE]
>
>Fai clic sul pulsante **[!UICONTROL Apply updates]** intestazione di colonna da aggiornare **tutto** degli interruttori di accensione o spegnimento.

Quando si selezionano i valori dei campi, il tipo di dati viene visualizzato sotto i menu a discesa.   Questo è un aspetto da tenere presente durante la mappatura dei valori da un campo all’altro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> Non è possibile mappare più campi Microsoft Dynamics 365 su un singolo campo Campaign.

### Sostituzioni di campi {#field-replacements}

Utilizza la **[!UICONTROL Add New Field Replacement]** per definire una nuova sostituzione del campo.

Le sostituzioni dei campi consentono di identificare:

* un nome di campo Microsoft Dynamics 365 (aggiunto sopra nella sezione mappature campi),
* un valore esistente (presente in Microsoft Dynamics 365), e
* un nuovo valore da scrivere in Adobe Campaign

Verrà fornito un elenco a discesa per i valori picklist, enumeration e booleani. Per altri tipi di stringa e numerici viene utilizzata una casella di testo.

### Filtri {#filters}

Utilizza la **[!UICONTROL Add New Filter]** per selezionare i record di Microsoft Dynamics 365 che verranno propagati a Campaign. Puoi scegliere qualsiasi campo associato a un record da aggiungere ai filtri (il nome del campo non deve essere aggiunto alle mappature dei campi).

Per specificare un filtro, compila le seguenti informazioni:

* Nome campo Microsoft Dynamics 365
* un valore di confronto, e
* un valore (da Microsoft Dynamics 365) Se il nome del campo, il confronto e il valore risultano true per un dato record, il record verrà propagato ad Adobe Campaign.

Puoi scegliere come valutare questi filtri impostando l’input etichettato **[!UICONTROL Choose the filter comparison operator]**.  Se scegli **E**, tutti i filtri devono essere true affinché un record venga propagato a Campaign. Se scegli **Oppure**, il record viene propagato se uno qualsiasi di essi valuta true.

Opzione **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controlla se desideri eliminare i record filtrati da Campaign. Se si seleziona **No** quindi i record rimarranno in Adobe Campaign. Seleziona **Sì** per eliminarli dalla logica di integrazione.

>[!NOTE]
>
> Se non vengono aggiunti filtri, tutti i record modificati verranno propagati ad Adobe Campaign.

### Impostazioni avanzate {#advanced-settings}

Puoi impostare le seguenti opzioni aggiuntive durante la configurazione di una mappatura:

* Imposta la **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** opzione per **Sì**, se desideri propagare le eliminazioni che si verificano in Microsoft Dynamics 365 al campo corrispondente in Adobe Campaign (in base al mapping dei nomi dei campi). Seleziona **No** per ignorare le eliminazioni in Microsoft Dynamics 365.

* Imposta la **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** opzione per **No** se desideri propagare a Campaign il valore di visualizzazione associato a un elenco di selezione di Microsoft Dynamics 365. Seleziona **Sì** propagare il valore tecnico.

## Sincronizzazione degli eventi di marketing di Campaign con Microsoft Dynamics 365

La **[!UICONTROL Campaign to Microsoft Dynamics 365]** consente di identificare gli eventi di marketing e-mail che verranno mappati da Adobe Campaign a Microsoft Dynamics 365.

Le quattro metriche che puoi controllare sono: **Invio**, **Clic**, **Aperture** e **Rimbalzi**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Seleziona **Sì** per confermare che desideri che gli eventi di quel tipo passino a Microsoft Dynamics 365.

Fai clic su [qui](../../integrating/using/d365-acs-self-service-app-workflows.md) per ulteriori informazioni su questi flussi di eventi e-mail.

## Flusso di lavoro di Opt-in/out {#opt-in-out-wf}

La **Consenso/rinuncia** il flusso di lavoro ti consente di identificare il flusso di informazioni di consenso/rinuncia tra Microsoft Dynamics 365 e Adobe Campaign. Ciò presuppone che i dati siano associati all’entità Microsoft Dynamics 365 &quot;contact&quot; e alla risorsa Adobe Campaign &quot;profile&quot;.

Ulteriori informazioni sulla gestione delle rinunce in [questa sezione](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Ricordare che è necessario fare clic su &quot;Salva&quot; per salvare le selezioni. Inoltre ricorda che devi interrompere il **Campaign a Microsoft Dynamics 365** , quindi fai clic su play for the integration (Riproduci per l’integrazione) per incorporare le modifiche.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Direzione di sincronizzazione in/out Opt

Di seguito è riportato l’elenco delle opzioni disponibili per la sincronizzazione dei dati:

* **[!UICONTROL Disabled]**: quando questa opzione è selezionata, tra Adobe Campaign e Microsoft Dynamics 365 non verranno spostate informazioni di consenso/rinuncia.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: questa opzione viene utilizzata solo per lo scorrimento della funzionalità opt-in/out da Microsoft Dynamics 365 ad Adobe Campaign. L&#39;applicazione di integrazione non ti consentirà di configurare il flusso in questa schermata; fai clic su **[!UICONTROL Save button]** e naviga fino al **[!UICONTROL Microsoft Dynamics 365 to Campaign]** workflow. In questo flusso di lavoro, puoi modificare la mappatura della tabella contatti/profili per identificare la modalità di associazione dei campi di consenso/rinuncia.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: questa opzione renderà visibile il **Mappature** sezione . Questi input ti consentono di definire quali campi di Adobe Campaign mapperanno i dati su quali campi in Microsoft Dynamics 365. Questo significa che se aggiorni manualmente un valore in Microsoft Dynamics 365, il suo valore viene sovrascritto dal valore Adobe Campaign se viene modificato.

* **[!UICONTROL Bidirectional]**: questa opzione renderà visibile il **Mappature** sezione . Queste coppie identificano i campi in Microsoft Dynamics 365 e Adobe Campaign da mappare tra loro. [Ulteriori informazioni](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Mappature

Questa sezione si applica solo quando il campo della direzione di sincronizzazione Opt-in/out è impostato su **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. Puoi definire quali campi in Microsoft Dynamics 365 mappano in base agli input in Adobe Campaign.

I nomi dei campi Microsoft Dynamics 365 includono tutti quelli di tipo **booleano**.

I nomi dei campi Adobe Campaign sono un set fisso di valori specifici di opt-in/out. I nomi dei campi Adobe Campaign sono un set fisso di valori specifici di opt-in/out. **Impossibile modificare l&#39;insieme di valori dell&#39;elenco**.
