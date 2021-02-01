---
title: Flussi di lavoro delle applicazioni di integrazione
description: Flussi di lavoro di integrazione di Campaign e Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: efa30d7ed4a0caf929da6f485681078318849cda
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 0%

---


# Campaign - Flussi di lavoro di integrazione di Microsoft Dynamics 365

Nella pagina **[!UICONTROL Workflows]** sono elencati i flussi di lavoro tecnici e il relativo stato.

L&#39;applicazione di integrazione include tre flussi di lavoro:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Da Microsoft Dynamics 365 a Campaign**
* Invia *contatti* da Microsoft Dynamics 365 a  Adobe Campaign
* *Entità* personalizzate: Inserire tabelle personalizzate da Microsoft Dynamics 365 a  Adobe Campaign. [Ulteriori informazioni](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Questo è noto anche come **Ingress** (con riferimento all&#39;ingresso di dati da Microsoft Dynamics 365 a  Adobe Campaign)

**Campaign to Microsoft Dynamics 365**
* Gli eventi di marketing e-mail da  Adobe Campaign Standard vengono inviati a Dynamics 365 (invio e-mail, apertura, clic, rimbalzo). [Ulteriori informazioni](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Questo è noto anche come **Egress** (con riferimento alla portata dei dati da  Adobe Campaign a Microsoft Dynamics 365)

**Opt-In/Out**

Gli stati di rifiuto (ad esempio, elenco Bloccati) possono essere sincronizzati da Microsoft Dynamics 365 a  Adobe Campaign o da  Adobe Campaign a Microsoft Dynamics 365. I dati possono anche essere sincronizzati bidirezionalmente (cioè con flussi di dati in entrambe le direzioni). [Ulteriori informazioni](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>È vivamente consigliato arrestare il flusso di lavoro **Microsoft Dynamics 365 in Campaign** prima di pubblicare le modifiche in  Adobe Campaign Standard o Microsoft Dynamics 365. Queste modifiche includono aggiornamenti a risorse/entità (e relativi campi associati), collegamenti, colonne di identificatori, ecc. attualmente in uso nell&#39;integrazione. In caso contrario si potrebbe verificare una perdita di dati e/o l&#39;arresto imprevisto del flusso di lavoro.

## Backlog del flusso di lavoro

Questa applicazione di integrazione legge prima i dati e quindi li scrive nella destinazione. La colonna **[!UICONTROL Backlog]** indica il numero di record che sono stati messi in coda e sono in attesa di essere scritti. Questo valore dovrebbe aumentare quando si dispone di una grande quantità di dati da elaborare (ad esempio, si esegue l&#39;integrazione per la prima volta, si stanno riproducendo i dati, ecc.).

>[!NOTE]
>Se i record di Microsoft Dynamics 365 e/o Campaign non si aggiornano, è innanzitutto necessario verificare se è presente un numero elevato di record in attesa di scrittura nella destinazione.


## Stato del flusso di lavoro {#workflow-status}

La colonna **[!UICONTROL Status]** indica lo stato dei processi in background associati al flusso di lavoro. I valori possibili sono:

* **ESECUZIONE**: Il processo è attualmente in esecuzione e i dati devono essere sincronizzati.
* **ARRESTATO**: Il processo non è attualmente in esecuzione, pertanto non è necessario che i dati vengano sincronizzati.
* **INIZIO**: È stato richiesto l&#39;avvio dei processi del flusso di lavoro. L&#39;applicazione non ha ancora iniziato a sincronizzare i dati associati a questo flusso di lavoro, ma è probabile che lo sarà dopo alcuni minuti (quando verrà visualizzato lo stato di **RUNNING**)
* **ERRORE**: I processi del flusso di lavoro erano in esecuzione ma hanno rilevato errori e non è stato possibile ripristinarli.

## Azioni disponibili

Le azioni possibili sono elencate di seguito.

* **Modifica**: Facendo clic sull’icona a forma di matita potrete passare a un’altra pagina per aggiornare il flusso di lavoro. Eventuali modifiche apportate AVRANNO EFFETTO SOLO dopo l’arresto del flusso di lavoro e il successivo riavvio.

* **Inizio**: Un pulsante Start richiede l’avvio di un flusso di lavoro interrotto. Questo pulsante viene visualizzato solo quando i processi associati al flusso di lavoro sono attualmente interrotti. I processi verranno prima modificati in &quot;AVVIO&quot; e poi in &quot;ESECUZIONE&quot;. I dati associati al flusso di lavoro non avvieranno la sincronizzazione finché il flusso di lavoro non sarà in stato &quot;RUNNING&quot;.

   Il pulsante di avvio è un interruttore. Se i processi del flusso di lavoro sono già stati avviati, il pulsante si trasformerà in un pulsante **Stop**.

* **Interrompi**: Un  **** pulsante Interrompi richiede che venga interrotto un flusso di lavoro in esecuzione. Questo pulsante viene visualizzato solo quando sono in esecuzione i processi associati al flusso di lavoro.

Quando si modifica un flusso di lavoro, gli aggiornamenti NON vengono immediatamente incorporati nelle regole dei processi in esecuzione, finché non si interrompe il flusso di lavoro e quindi si fa clic sul pulsante **Start**. Gli aggiornamenti vengono quindi incorporati nei processi in esecuzione (una volta che il processo ritorna allo stato **RUNNING**).

Al pulsante **Stop** viene aggiunta un&#39;indicazione di avviso per segnalare all&#39;utente quando (a) sono stati eseguiti aggiornamenti al flusso di lavoro, ma (b) non è stato eseguito un arresto/avvio del flusso di lavoro.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
