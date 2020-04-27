---
title: Configurare l'integrazione Unifi per Microsoft Dynamics 365
description: Scoprite come configurare l'integrazione Unifi per Microsoft Dynamics 365
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 37e86c6143c52841e69d610fa9db35dff70a3587

---



# Configurare l&#39;integrazione Unifi per Microsoft Dynamics 365

Configurare Unifi per configurare e attivare l&#39;integrazione di Microsoft Dynamics 365 - Adobe Campaign.

## Prerequisiti

Prima di eseguire i passaggi di post-provisioning in questo articolo, si presume che i passaggi di [post-provisioning per Campaign](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) e [per Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)siano già stati completati correttamente.  Se non è successo, dovrai seguire questi passaggi per completare il post-provisioning di Campaign Standard e Dynamics 365.

Si presume inoltre di aver contattato Unifi, di aver creato un account Unifi per voi e di aver potuto effettuare l&#39;accesso.  Se ciò non è avvenuto, seguite i passaggi descritti in [questo articolo](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!CAUTION]
>
>È fortemente consigliato lavorare con Unifi e/o Adobe Consulting (contattare Adobe CSM) durante la configurazione di Unifi.

## Configura integrazione con Campaign

Alla prima connessione, fate clic **[!UICONTROL Adobe Campaign Standard]** per immettere le credenziali della campagna.

La maggior parte di queste credenziali proviene dall&#39;integrazione creata nella console di I/O di Adobe durante i passaggi [di configurazione di](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)Campaign Standard.

>[!NOTE]
>
>Per garantire la sicurezza e la privacy, i campi delle credenziali sensibili vengono visualizzati vuoti durante la revisione di queste schermate di configurazione.

1. Per l&#39;URL autenticazione Adobe, immettete `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Inserisci il tuo **[!UICONTROL Adobe IO Organization ID]** e il tuo **[!UICONTROL Adobe IO Integration ID]**.

Per ottenere gli ID organizzazione e integrazione Adobe IO, accedi all’integrazione della console Adobe I/O sullo schermo e prendi nota dell’URL Web.

Dovrebbe assomigliare a questo: `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`, dove ID organizzazione e ID interno sono numeri.

1. Inserisci il tuo **[!UICONTROL Tenant ID]**

Per ottenere il tuo ID tenant, segui i passaggi seguenti:

1. Accedi ad [Adobe Admin Console](https://adminconsole.adobe.com/) e seleziona la tua organizzazione IMS dal menu a discesa in alto a destra.
1. Seleziona il prodotto Adobe Campaign Standard, quindi seleziona l&#39;istanza Campaign Standard (se ne hai più).  Verrà visualizzato un elenco dei profili di prodotto.

   Le descrizioni del profilo di prodotto vengono generalmente visualizzate in uno dei seguenti formati, dove `<tenantID>` è l&#39;ID tenant dell&#39;istanza.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>In caso di problemi con l&#39;identificazione dell&#39;ID tenant, contatta l&#39;Assistenza clienti Adobe o l&#39;Assistenza clienti Adobe.
>
>Gli ID tenant dell&#39;istanza sandbox partner seguono in genere il pattern `https://<tenantId>`, dove `tenantId` si trova `tbd.campaign-sandbox.adobe.com`.

1. Inserisci il tuo **[!UICONTROL Campaign Instance ID]**.

Per ottenere l’ID istanza, segui i passaggi seguenti:

    1. Digitate `https://&lt;acs-instance-url>/r/test` in un browser Web, sostituendo `&lt;acs-instance-url>` con l&#39;URL dell&#39;istanza Campaign Standard.
    1. La risposta conterrà `instance=`, seguita dall&#39;ID dell&#39;istanza.

1. Seleziona l&#39;area dell&#39;istanza Campaign.

1. Puoi lasciare **[!UICONTROL Base Directory]** vuoto.

1. Selezionate l’ **[!UICONTROL Allow as Output Destination]** opzione.

Dopo aver impostato i parametri, fare clic **[!UICONTROL CONNECT]** e controllare la connessione ha esito positivo.

In caso contrario, fate clic **[!UICONTROL CLOSE]** e verificate i parametri.

>[!NOTE]
>
>Se non riesci a completare questo passaggio, contatta il servizio [clienti](mailto:support@unifisoftware.atlassian.net)Unifi.

## Configurare l&#39;integrazione di Dynamics 365

Fate clic su Microsoft Dynamics CRM per configurare le credenziali di Dynamics 365. La maggior parte di queste credenziali proviene dall&#39;integrazione creata in Microsoft Dynamics 365 durante i passaggi di configurazione di Microsoft Dynamics 365.

>[!NOTE]
>
>Per garantire la sicurezza e la privacy, i campi delle credenziali sensibili vengono visualizzati vuoti durante la revisione di queste schermate di configurazione.

1. Ad **[!UICONTROL URL]** esempio, immetti l’URL dell’istanza Dynamics 365, avendo cura di inserire &quot;.api&quot; prima di &quot;.crm&quot; (ad es. `https://mydynamicsinstance.api.crm.dynamics.com`)

1. Ad **[!UICONTROL clientid]** esempio, utilizzerete l&#39;ID applicazione generato al momento della creazione della registrazione dell&#39;app come [configurazione di Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Ad **[!UICONTROL clientsecret]** esempio, utilizzerai il segreto client generato quando hai aggiunto un segreto client alla registrazione dell&#39;app come [configurazione di Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Ad **[!UICONTROL callbackurl]** esempio, aggiungi `http://localhost:33333`.

1. Ad **[!UICONTROL refresh token]** esempio, lasciate vuoto.

1. Per l&#39;ID **** tenant, utilizza l&#39;ID tenant ottenuto da Portal.azure.com per [configurare Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Infine, selezionare la casella per **[!UICONTROL Allow as Output Destination]**.

Dopo aver immesso i parametri, fare clic **[!UICONTROL CONNECT]** e controllare la connessione ha esito positivo.

In caso contrario, fate clic **[!UICONTROL CLOSE]** e verificate i parametri.

>[!NOTE]
>
>Se non riesci a completare questo passaggio, contatta il servizio [clienti](mailto:support@unifisoftware.atlassian.net)Unifi.

## Completamento configurazione Unifi

Una volta configurate le credenziali, è necessario inviare una notifica ad Unifi in quanto è necessario eseguire alcuni passaggi aggiuntivi prima di completare la configurazione dell&#39;integrazione.  Rivolgiti alle informazioni di contatto di Unifi fornite per segnalare che hai impostato le tue credenziali.

È necessario selezionare un&#39;opzione di rifiuto e inviare una notifica all&#39;Unifi al completamento (indicando a Unifi quale opzione di rifiuto è selezionata).  Una spiegazione delle opzioni di rifiuto si trova nella Guida [utente](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn)Unifi.

Una volta che Unifi completa il loro lavoro, ti avviseranno e forniranno ulteriori informazioni per aiutarti a configurare la tua istanza Unifi, eseguire l&#39;ingresso dati una volta e poi, una volta completato il completamento, puoi abilitare le pianificazioni.

Per diversi casi di utilizzo si consiglia la frequenza seguente:

* Ingresso: Ogni 15 minuti
* Egress: Ogni 15 minuti
* Elimina: Ogni giorno
* Rifiuto: Ogni giorno

>[!NOTE]
>
>Per impostazione predefinita, gli eventi di marketing SEND vengono filtrati fuori dal processo di uscita.  Se desideri visualizzare gli eventi di marketing SEND in Dynamics 365, devi modificare il filtro (passaggio 5) del processo di uscita in Unifi.

Unifi dispone di due ruoli separati, un utente proprietario e un utente di analisi di sola lettura. Un utente proprietario ha la capacità di modificare processi e pianificazioni, mentre l&#39;analista di sola lettura non lo è.  Per una determinata istanza di cliente può essere presente un solo utente proprietario.  Se il cliente deve cambiare il singolo assegnato come utente proprietario, può inviare un messaggio e-mail a [adobe-support@unifisoftware.com](mailto:adobe-support@unifisoftware.com) con la modifica richiesta.

La configurazione, i dettagli del processo, la configurazione e il monitoraggio di Unifi sono presentati nei video seguenti.

## Processi Unifi

### Panoramica dei processi Unifi

>[!VIDEO](https://video.tv.adobe.com/v/27392)

Questo video illustra i diversi processi Unifi richiesti per l&#39;integrazione di Adobe Campaign Standard con Microsoft Dynamics 365 (02:10 min)

### Dettagli processo Unifi: Ingress &amp; Egress

>[!VIDEO](https://video.tv.adobe.com/v/27396)

Questo video spiega i processi di ingresso e uscita in Unifi (04:27 min)

### Operazionalizzazione e monitoraggio

>[!VIDEO](https://video.tv.adobe.com/v/27391)

Questo video illustra i flussi di lavoro e le pianificazioni (03:03 min)

Più simile
* [Utilizzo di Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configurare Microsoft Dynamics 365 per l&#39;integrazione con Campaign](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Configurare Adobe IO per Microsoft Dynamics 365 - Integrazione con Campaign Standard](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Pagina delle funzionalità di integrazione di Microsoft Dynamics 365](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)