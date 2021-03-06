---
title: Integrazione dei flussi di lavoro delle applicazioni
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

# Campaign - Flussi di lavoro di integrazione Microsoft Dynamics 365

La **[!UICONTROL Workflows]** in questa pagina sono elencati i flussi di lavoro tecnici e il loro stato.

L’applicazione di integrazione viene fornita con tre flussi di lavoro:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 in Campaign**
* Invia *contatti* da Microsoft Dynamics 365 ad Adobe Campaign
* *Entità personalizzate*: Puoi importare tabelle personalizzate da Microsoft Dynamics 365 in Adobe Campaign. [Ulteriori informazioni](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Questo è noto anche come **Ingresso** (riferimento all’ingresso di dati da Microsoft Dynamics 365 ad Adobe Campaign)

**Campaign a Microsoft Dynamics 365**
* Gli eventi di marketing e-mail da Adobe Campaign Standard vengono inviati a Dynamics 365 (invio e-mail, apertura, clic, mancato recapito). [Ulteriori informazioni](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Questo è noto anche come **Egresso** (riferimento all’uscita di dati da Adobe Campaign a Microsoft Dynamics 365)

**Consenso/rinuncia**

Gli stati di rinuncia (ad esempio, elenco Bloccati) possono essere sincronizzati da Microsoft Dynamics 365 ad Adobe Campaign o da Adobe Campaign a Microsoft Dynamics 365. I dati possono anche essere sincronizzati bidirezionalmente (cioè flussi di dati in entrambe le direzioni). [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Si consiglia vivamente di interrompere la **Microsoft Dynamics 365 in Campaign** prima di pubblicare le modifiche ad Adobe Campaign Standard o Microsoft Dynamics 365. Queste modifiche includono aggiornamenti a risorse/entità (e relativi campi associati), collegamenti, colonne di identificatore, ecc. attualmente in uso nell’integrazione. In caso contrario, potrebbe verificarsi una perdita di dati e/o l’arresto imprevisto del flusso di lavoro.

## Backlog del flusso di lavoro

Questa applicazione di integrazione legge prima i dati e quindi scrive i dati nella destinazione. La **[!UICONTROL Backlog]** la colonna indica il numero di record che sono stati messi in coda e sono in attesa di essere scritti. Questo valore dovrebbe aumentare quando si dispone di una grande quantità di dati da elaborare (ad esempio, si esegue l’integrazione per la prima volta, si riproducono i dati, ecc.).

>[!NOTE]
>Se i record Microsoft Dynamics 365 e/o Campaign non vengono aggiornati, verifica innanzitutto se è presente un numero elevato di record in attesa di scrittura nella destinazione.

## Stato del flusso di lavoro {#workflow-status}

La **[!UICONTROL Status]** La colonna indica lo stato dei processi in background associati al flusso di lavoro. I valori possibili sono:

* **IN ESECUZIONE**: Il processo è attualmente in esecuzione e i dati devono essere sincronizzati.
* **ARRESTATO**: Il processo non è attualmente in esecuzione, pertanto non è necessario che i dati vengano sincronizzati.
* **INIZIO**: Hai richiesto l’avvio dei processi del flusso di lavoro. L&#39;applicazione non ha ancora iniziato a sincronizzare i dati associati a questo flusso di lavoro, ma si può prevedere che lo sarà dopo alcuni minuti (quando mostrerà lo stato di **IN ESECUZIONE**)
* **NON RIUSCITO**: I processi del flusso di lavoro erano in esecuzione ma hanno rilevato errori e non è stato possibile ripristinarli.

## Azioni disponibili

Le azioni possibili sono elencate di seguito.

* **Modifica**: Facendo clic sull’icona a forma di matita potrai passare a un’altra pagina per apportare aggiornamenti al flusso di lavoro. Tieni presente che le modifiche apportate NON avranno effetto finché non interrompi il flusso di lavoro e lo riavvii.

* **Inizio**: Un pulsante Start richiede l’avvio di un flusso di lavoro interrotto. Questo pulsante viene visualizzato solo quando i processi associati al flusso di lavoro vengono attualmente interrotti. I processi verranno prima modificati in &quot;AVVIO&quot; e poi in &quot;ESECUZIONE&quot;. I dati associati al flusso di lavoro non avvieranno la sincronizzazione finché il flusso di lavoro non sarà in uno stato &quot;IN ESECUZIONE&quot;.

   Il pulsante di avvio è un interruttore. Se i processi del flusso di lavoro sono già stati avviati, il pulsante diventa un **Interrompi** pulsante .

* **Interrompi**: A **Interrompi** richiede l’arresto di un flusso di lavoro in esecuzione. Questo pulsante viene visualizzato solo quando i processi associati al flusso di lavoro sono attualmente in esecuzione.

Quando modifichi un flusso di lavoro, gli aggiornamenti NON vengono immediatamente incorporati nelle regole dei processi in esecuzione, fino a quando non interrompi il flusso di lavoro e quindi fai clic sul pulsante **Inizio** pulsante . Quindi gli aggiornamenti vengono incorporati nei processi in esecuzione (una volta che il processo ritorna a un **IN ESECUZIONE** stato).

Viene aggiunta un’indicazione di avviso al **Interrompi** per comunicare quando hai (a) effettuato aggiornamenti al flusso di lavoro, ma (b) non hai eseguito un arresto/avvio del flusso di lavoro.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
