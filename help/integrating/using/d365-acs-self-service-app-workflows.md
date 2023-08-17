---
title: Flussi di lavoro dell’applicazione di integrazione
description: Flussi di lavoro di integrazione di Campaign e Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---

# Flussi di lavoro di integrazione di Campaign - Microsoft Dynamics 365

Il **[!UICONTROL Workflows]** elenca i flussi di lavoro tecnici e il loro stato.

L’applicazione di integrazione è dotata di tre flussi di lavoro:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Da Microsoft Dynamics 365 a Campaign**
* Invia *contatti* da Microsoft Dynamics 365 ad Adobe Campaign
* *Entità personalizzate*: porta tabelle personalizzate da Microsoft Dynamics 365 a Adobe Campaign. [Ulteriori informazioni](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Questo è anche noto come **Ingresso** (con riferimento all’ingresso di dati da Microsoft Dynamics 365 ad Adobe Campaign)

**Campaign a Microsoft Dynamics 365**
* Gli eventi di marketing e-mail da Adobe Campaign Standard vengono inviati a Dynamics 365 (invio e-mail, apertura, clic, mancato recapito). [Ulteriori informazioni](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Questo è anche noto come **Uscita** (con riferimento all’uscita dei dati da Adobe Campaign a Microsoft Dynamics 365)

**Consenso/rinuncia**

Gli stati di rinuncia (ad esempio, inserisco nell&#39;elenco Bloccati di rinuncia a un’opzione) possono essere sincronizzati da Microsoft Dynamics 365 a Adobe Campaign o da Adobe Campaign a Microsoft Dynamics 365. I dati possono anche essere sincronizzati bidirezionalmente (ossia flussi di dati in entrambe le direzioni). [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Si consiglia vivamente di interrompere **Da Microsoft Dynamics 365 a Campaign** flusso di lavoro prima di pubblicare le modifiche apportate a Adobe Campaign Standard o Microsoft Dynamics 365. Queste modifiche includono aggiornamenti a risorse/entità (e ai relativi campi associati), collegamenti, colonne di identificatori e così via, attualmente in uso dall’integrazione. In caso contrario, si potrebbe verificare una perdita di dati e/o l’arresto imprevisto del flusso di lavoro.

## Backlog del flusso di lavoro

Questa applicazione di integrazione legge prima i dati e quindi li scrive nella destinazione. Il **[!UICONTROL Backlog]** colonna indica il numero di record che sono stati messi in coda e sono in attesa di essere scritti. Questo valore dovrebbe aumentare quando si dispone di una grande quantità di dati da elaborare (ad esempio, si esegue l’integrazione per la prima volta, si riproducono i dati, ecc.).

>[!NOTE]
>Se i record di Microsoft Dynamics 365 e/o Campaign non vengono aggiornati, è innanzitutto necessario verificare se è presente un numero elevato di record in attesa di essere scritti nella destinazione.
>

## Stato del flusso di lavoro {#workflow-status}

Il **[!UICONTROL Status]** indica lo stato dei processi in background associati al flusso di lavoro. I valori possibili sono:

* **IN ESECUZIONE**: il processo è attualmente in esecuzione e i dati devono essere sincronizzati.
* **INTERROTTO**: il processo non è attualmente in esecuzione, pertanto non è previsto che i dati vengano sincronizzati.
* **AVVIO**: hai richiesto l’avvio dei processi del flusso di lavoro. L’applicazione non ha ancora iniziato a sincronizzare i dati associati a questo flusso di lavoro, ma se ne prevede uno dopo alcuni minuti, quando verrà visualizzato lo stato **IN ESECUZIONE**)
* **NON RIUSCITO**: i processi del flusso di lavoro erano in esecuzione ma si sono verificati errori che non sono stati recuperati.

## Azioni disponibili

Le azioni possibili sono elencate di seguito.

* **Modifica**: facendo clic sull’icona della matita verrai indirizzato a un’altra pagina che ti consentirà di apportare aggiornamenti al flusso di lavoro. Eventuali modifiche apportate NON avranno effetto finché il flusso di lavoro non verrà interrotto e riavviato.

* **Inizio**: un pulsante Start richiede l’avvio di un flusso di lavoro interrotto. Questo pulsante viene visualizzato solo quando i processi associati al flusso di lavoro sono attualmente interrotti. I processi passeranno prima a &quot;START&quot; (AVVIO) e poi a &quot;RUNNING&quot; (ESECUZIONE). I dati associati al flusso di lavoro non iniziano la sincronizzazione finché il flusso di lavoro non si trova nello stato &quot;IN ESECUZIONE&quot;.

  Il pulsante di avvio è un interruttore. Se i processi del flusso di lavoro sono già stati avviati, il pulsante diventa **Interrompi** pulsante.

* **Interrompi**: A **Interrompi** richiede l&#39;interruzione di un flusso di lavoro in esecuzione. Questo pulsante viene visualizzato solo quando i processi associati al flusso di lavoro sono attualmente in esecuzione.

Quando modifichi un flusso di lavoro, gli aggiornamenti NON vengono incorporati immediatamente nelle regole dei processi in esecuzione, fino a quando non interrompi il flusso di lavoro e fai clic su **Inizio** pulsante. Gli aggiornamenti vengono quindi incorporati nei processi in esecuzione (una volta che il processo torna a **IN ESECUZIONE** state).

Un&#39;indicazione di avvertenza viene aggiunta al **Interrompi** per comunicare quando a) sono stati apportati aggiornamenti al flusso di lavoro, ma b) non è stato eseguito un arresto/inizio del flusso di lavoro.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
