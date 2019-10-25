---
title: Conti esterni
seo-title: Conti esterni
description: Conti esterni
seo-description: Configurate gli account esterni per configurare le connessioni con sistemi esterni come i server SFTP.
page-status-flag: mai attivato
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,principale;extAccount,panoramica
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Conti esterni{#external-accounts}

Un account esterno è una configurazione che consente di configurare e verificare l'accesso a un server esterno ad Adobe Campaign.

Questi account esterni possono essere utilizzati nei flussi di lavoro Campaign per accedere e gestire i dati.

Puoi impostare i seguenti tipi di account esterni:

* SFTP. For more on this, refer to [this section](#sftp-external-account).
* Amazon Storage Service (S3). For more on this, refer to [this section](#amazon-s3-external-account).
* Adobe Experience Manager. For more on this, refer to [this section](#adobe-experience-manager-external-account).
* Adobe Analytics. For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google reCAPTCHA. For more on this, refer to [this section](#google-recaptcha-external-account).

>[!NOTE]
>
>Altri tipi di account esterni vengono utilizzati da Adobe durante il processo di provisioning dei prodotti. Dalla versione Campaign Standard 17.9, gli account esterni FTP possono ancora essere definiti ma non sono più utilizzabili nelle nuove attività del flusso di lavoro. Se è già stata configurata una connessione, questa rimane attivata.

Gli account esterni possono essere configurati dagli amministratori nel **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creazione di un account esterno {#creating-an-external-account}

Adobe Campaign viene fornito con un set di account esterni predefiniti. Per configurare le connessioni con i sistemi esterni, come i server FTP utilizzati per i trasferimenti di file, potete creare i vostri account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro delle campagne. Quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un'altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

1. Fate clic sul **[!UICONTROL Create]** pulsante.
1. Immettere un'etichetta. L'etichetta e l'ID verranno utilizzati per selezionare account esterni nei flussi di lavoro.
1. Selezionate il tipo di account da creare.
1. Configurate l'accesso all'account specificando le credenziali, l'indirizzo del server, il numero di porta e le chiavi, se necessario.

   Le informazioni necessarie vengono in genere fornite dal provider del server a cui ci si sta connettendo.

1. Salvate l’account.

L'account esterno viene creato e aggiunto all'elenco degli account. È ora disponibile per trasferimenti di dati/file o configurazioni di routing nelle attività del flusso di lavoro e nelle proprietà di consegna.

## Account esterno SFTP {#sftp-external-account}

Diversi tipi di account esterni richiedono informazioni diverse per essere specificati.

Per un account esterno SFTP, fornisci i seguenti dettagli:

* Indirizzo del server. Ad esempio, **ftp.domain.com**.
* Numero porta. Ad esempio, **22**.
* Credenziali server SFTP: nome account e password utilizzati per connettersi al server.

### Consigli del server SFTP ospitato da Adobe {#adobe-hosted-sftp-server-recommendations}

Quando gestite file e dati a scopo ETL, questi file vengono memorizzati in un server SFTP ospitato fornito da Adobe. Questo SFTP è progettato per essere uno spazio di archiviazione temporaneo su cui è possibile controllare la conservazione e l'eliminazione dei file.

Se non utilizzato o monitorato correttamente, questo spazio può riempire rapidamente lo spazio fisico disponibile sul server e causare gravi problemi. Può causare perdita di dati o danneggiamento sulla piattaforma.

Per evitare tali problemi, Adobe consiglia di seguire le procedure ottimali riportate di seguito:

* Mantenere i dati minimi possibili.
* Utilizzate l'autenticazione basata su chiave per evitare la scadenza della password. I formati supportati sono solo **OpenSSH** e **SSH2** . Dovrete fornire la chiave pubblica al team di supporto Adobe per consentirne il caricamento sul server Campaign.
* Conservare i dati per il tempo necessario. 15 giorni è il limite massimo.
* Utilizzare i flussi di lavoro per eliminare correttamente i dati (gestire la conservazione dai flussi di lavoro che consumano i dati).
* Utilizzare i batch nei caricamenti SFTP e nei flussi di lavoro.
* Gestire errori/eccezioni.
* Talvolta, effettuate l’accesso a SFTP per verificare direttamente ciò che vi si trova.
* Ricorda che la gestione del disco SFTP è principalmente una tua responsabilità.

Inoltre, gli IP pubblici da cui si sta tentando di avviare la connessione SFTP devono essere inseriti nella white list dell'istanza Campaign. La whitelist degli indirizzi IP può essere richiesta tramite un ticket [di](https://support.neolane.net)supporto, insieme alla fornitura della chiave pubblica da utilizzare per l'autenticazione.

I server SFTP possono essere gestiti dal Pannello di controllo. Per ulteriori informazioni, consultare la documentazione [del Pannello di](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html)controllo.

>[!NOTE]
>
>Il Pannello di controllo è disponibile solo per gli utenti Admin dei clienti ospitati su AWS.
Verifica se l’istanza è ospitata su AWS [qui](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Account esterno Amazon S3 {#amazon-s3-external-account}

Il campo del server Amazon S3 deve essere compilato come segue:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Per memorizzare il file in modalità crittografata S3, selezionare la **[!UICONTROL Keep files in S3 encrypted]** casella.

![](assets/external_accounts_2.png)

Le informazioni necessarie vengono in genere fornite dal provider del server a cui ci si sta connettendo.

Specificate l' **[!UICONTROL AWS Region]** endpoint associato. È possibile controllare le regioni supportate e le versioni delle firme nella documentazione [ufficiale di](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) Amazon S3.

### Consigli account Amazon S3 {#amazon-s3-account-recommendations}

Per facilitare l'impostazione del vostro account Amazon S3, vi consigliamo di seguire le seguenti raccomandazioni:

* Crea criteri fissi rigidi per limitare l'accesso ai bucket S3. È possibile configurare il criterio del bucket durante la creazione di un bucket. Per ulteriori informazioni, consultate la documentazione [di](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html)Amazon S3.
* Durante la creazione di un account esterno, abilitare la crittografia per memorizzare dati sensibili nel bucket S3 selezionando la **[!UICONTROL Keep files in S3 encrypted]** casella.
* Concedere autorizzazioni bucket per specificare chi può accedere all'oggetto in un bucket. Per ulteriori informazioni sull'autorizzazione bucket, fare riferimento alla documentazione [Amazon S3](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Account esterno di Adobe Experience Manager {#adobe-experience-manager-external-account}

Gli account esterni di Adobe Experience Manager vengono utilizzati per l'integrazione di Campaign con Experience Manager.

I processi e i requisiti relativi a questa integrazione sono disponibili in [questo documento](../../integrating/using/about-campaign-integrations.md).

Mentre configurate questo nuovo account esterno, dovete fornire i seguenti dettagli:

* Server: immettete l'URL del server Adobe Experience Manager. Ad esempio, **http://aem.domain.com:4502**.
* Credenziali account AEM: utilizzate l'account che potrà accedere all'istanza di Adobe Experience Manager. Deve essere un account appartenente al gruppo remoto della campagna in Experience Manager.

## Account esterno Google reCAPTCHA {#google-recaptcha-external-account}

>[!NOTE]
>
>La configurazione Google reCAPTCHA richiede un account Google.

Il meccanismo Google reCAPTCHA consente di proteggere la pagina di destinazione dallo spam e dagli abusi causati dai bot. Questo non è intrusivo per i clienti in quanto non richiede alcuna interazione da parte loro ed è basato sulle interazioni con il tuo sito. Per registrare il sito, fare riferimento a questa [pagina](https://www.google.com/recaptcha/admin/create). È necessario scegliere il tipo V3 reCAPTCHA.

Per aggiungere Google reCAPTCHA V3 alla pagina di destinazione, è necessario prima configurarla nel tuo account esterno. Per ulteriori informazioni su come aggiungerlo alla pagina di destinazione, consulta questa [sezione](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

Per un account esterno Google reCAPTCHA V3, fornite i seguenti dettagli:

* A **[!UICONTROL Label]** e **[!UICONTROL ID]** del tuo account esterno
* **[!UICONTROL Type]**: Google reCAPTCHA
* Your **[!UICONTROL Site key]** and **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** tra 0 e 1

   Il valore 0,0 **[!UICONTROL Threshold]** indica che probabilmente si tratta di un bot e 1,0 probabilmente una buona interazione. Per impostazione predefinita, è possibile utilizzare una soglia pari a 0,5.

![](assets/external_accounts_3.png)

