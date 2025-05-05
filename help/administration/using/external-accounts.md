---
title: Account esterni
description: Scopri come configurare account esterni per impostare connessioni con sistemi esterni come i server SFTP
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 747e82ff-d3e6-4945-8f29-80e4a190c96f
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 77%

---

# Account esterni{#external-accounts}

Un account esterno è una configurazione che ti consente di configurare e testare l’accesso a un server esterno ad Adobe Campaign.

Questi account esterni possono essere utilizzati nei flussi di lavoro di Campaign per accedere ai dati e gestirli.

Puoi impostare i seguenti tipi di account esterni:

* SFTP. Per ulteriori informazioni, consulta [questa sezione](#sftp-external-account).
* Amazon Storage Service (S3). Per ulteriori informazioni, consulta [questa sezione](#amazon-s3-external-account).
* Adobe Experience Manager. Per ulteriori informazioni, consulta [questa sezione](#adobe-experience-manager-external-account).
* Adobe Analytics. Per ulteriori informazioni, consulta [questa sezione](../../integrating/using/configure-campaign-analytics-integration.md).
* Google reCAPTCHA. Per ulteriori informazioni, consulta [questa sezione](#google-recaptcha-external-account).
* Archiviazione BLOB di Microsoft Azure. Per ulteriori informazioni, consulta [questa sezione](#microsoft-azure-external-account).
* OAuth 2.0 Per ulteriori informazioni, consulta [questa sezione](#oauth-account).

>[!NOTE]
>
>Altri tipi di account esterni vengono utilizzati da Adobe durante il processo di provisioning dei prodotti. A partire dalla versione 17.9 di Campaign Standard, gli account esterni FTP possono ancora essere definiti ma non sono più utilizzabili nelle nuove attività del flusso di lavoro. Se avevi già configurato una connessione, essa rimane attivata.

Gli account esterni possono essere configurati dagli amministratori nel menu **[!UICONTROL Administration > Application settings > External accounts]**.

## Creazione di un account esterno {#creating-an-external-account}

Adobe Campaign è dotato di un set di account esterni predefiniti. Per impostare connessioni con sistemi esterni, come i server FTP utilizzati per i trasferimenti di file, puoi creare degli account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne. Quando imposti un trasferimento di file in un flusso di lavoro o uno scambio di dati con un’altra applicazione (Adobe Target, Experience Manager, ecc.), devi selezionare un account esterno.

1. Fai clic sul pulsante **[!UICONTROL Create]**.
1. Immetti un’etichetta. L’etichetta e l’ID verranno utilizzati per selezionare account esterni nei flussi di lavoro.
1. Seleziona il tipo di account da creare.
1. Configura l’accesso all’account specificando le credenziali, l’indirizzo del server, il numero della porta e/o le chiavi, se necessario.

   Le informazioni necessarie vengono in genere fornite dal provider del server a cui ti stai connettendo.

1. Salva l’account.

L’account esterno viene creato e aggiunto all’elenco degli account. È ora disponibile per i trasferimenti di dati/file o le configurazioni di indirizzamento nelle attività del flusso di lavoro e nelle proprietà di consegna.

## Account esterno SFTP {#sftp-external-account}

Diversi tipi di account esterni richiedono di specificare informazioni diverse.

Per un account esterno SFTP, fornisci i seguenti dettagli:

* Indirizzo del server. Ad esempio, **ftp.domain.com**.
* Numero della porta. Ad esempio, **22**.
* Credenziali del server SFTP: nome account e password utilizzati per connettersi al server.

### Adobe di consigli per server SFTP in hosting {#adobe-hosted-sftp-server-recommendations}

Quando gestisci file e dati per un processo di ETL, questi file vengono memorizzati in un server SFTP in hosting fornito da Adobe. Questo SFTP è progettato per essere uno spazio di archiviazione temporaneo su cui puoi controllare la conservazione e l’eliminazione dei file.

Se non utilizzato o monitorato correttamente, questo spazio può riempire rapidamente lo spazio fisico disponibile sul server e causare gravi problemi. Può causare perdita o danneggiamento di dati sulla piattaforma.

Per evitare tali problemi, Adobe consiglia di seguire le best practice riportate di seguito:

* Conserva la minore quantità possibile di dati.
* Utilizza l’autenticazione basata su chiave per evitare la scadenza delle password. I formati supportati sono solo **OpenSSH** e **SSH2**. Dovrai fornire la chiave pubblica al team di assistenza di Adobe per consentirne il caricamento sul server di Campaign.
* Conserva i dati solo per il tempo richiesto. 15 giorni è il limite massimo di tempo.
* Utilizza i flussi di lavoro per eliminare correttamente i dati (gestisci la conservazione dai flussi di lavoro che consumano i dati).
* Utilizza la suddivisione in batch nei caricamenti SFTP e nei flussi di lavoro.
* Gestisci gli errori/le eccezioni.
* Di tanto in tanto, effettua l’accesso a SFTP per verificare direttamente ciò che vi si trova.
* Ricorda che la gestione del disco SFTP è principalmente una tua responsabilità.

Inoltre, tieni presente che gli IP pubblici da cui stai tentando di avviare la connessione SFTP devono essere aggiunti al inserisco nell&#39;elenco Consentiti di sull’istanza Campaign. È possibile richiedere l&#39;aggiunta di indirizzi IP al inserisco nell&#39;elenco Consentiti di tramite un [ticket di supporto](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html) e fornire la chiave pubblica da utilizzare per l&#39;autenticazione.

I server SFTP possono essere gestiti dal Pannello di controllo. Per ulteriori informazioni, consulta la [documentazione del Pannello di controllo](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html).

>[!NOTE]
>
>Il Pannello di controllo è accessibile a tutti gli utenti amministratori. I passaggi per concedere a un utente l’accesso come amministratore sono descritti in[questa pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=it#discover-control-panel).

## Account OAuth 2.0 {#oauth-account}

Per un account esterno OAuth 2.0, fornisci i seguenti dettagli:

* Tipo di concessione **1&rbrace;: sono supportate solo** credenziali client **.**
* Un **URL API protetto**: immettere l&#39;endpoint di autorizzazione.
* **Credenziali sensibili OAuth 2.0**: questa sezione è destinata alle credenziali sensibili per natura. I valori delle credenziali vengono nascosti sullo schermo dopo che sono stati aggiunti; a questo punto, non saranno leggibili né modificabili. Se l&#39;endpoint di autorizzazione richiede l&#39;inserimento di una determinata credenziale nell&#39;intestazione dell&#39;autorizzazione HTTP anziché nel parametro del corpo del POST, è possibile selezionare l&#39;opzione Includi nell&#39;intestazione della credenziale.
* **Credenziali non riservate OAuth 2.0**: questa sezione è destinata alle credenziali di natura non sensibile. I valori delle credenziali saranno visibili sullo schermo dopo che sono stati aggiunti; saranno anche modificabili.  Se l&#39;endpoint di autorizzazione richiede l&#39;inserimento di una determinata credenziale nell&#39;intestazione dell&#39;autorizzazione HTTP anziché nel parametro del corpo del POST, è possibile selezionare l&#39;opzione Includi nell&#39;intestazione della credenziale.

Dopo aver immesso le informazioni sull&#39;account, fare clic su **Verifica connessione** per verificare che l&#39;account esterno sia stato configurato correttamente.

![](assets/external_accounts_OAuth.png)

>[!NOTE]
>
>Le credenziali &quot;Content-Type: application/x-www-form-urlencoded&quot; e &quot;grant_type=client_credentials&quot; verranno aggiunte automaticamente alla chiamata API; pertanto, non sarà necessario aggiungerle nella sezione delle credenziali.

## Account esterno Amazon S3 {#amazon-s3-external-account}

Il campo del server Amazon S3 deve essere compilato come segue:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Per memorizzare il file in modalità crittografata S3, seleziona la casella **[!UICONTROL Keep files in S3 encrypted]**.

![](assets/external_accounts_2.png)

Le informazioni necessarie vengono in genere fornite dal provider del server a cui ti stai connettendo.

Specifica la **[!UICONTROL AWS Region]** associata all’endpoint. Puoi consultare le aree geografiche supportate e le versioni della firma nella [documentazione ufficiale di Amazon S3](https://docs.aws.amazon.com/it_it/general/latest/gr/rande.html#s3_region).

>[!NOTE]
>
>Il **[!UICONTROL Receiver server]** deve essere immesso senza l’area geografica AWS, che in seguito verrà aggiunta automaticamente all’URL.

### Raccomandazioni per l’account Amazon S3 {#amazon-s3-account-recommendations}

Per facilitare l’impostazione dell’account Amazon S3, si consiglia di seguire le seguenti raccomandazioni:

* Crea policy di bucket rigide per limitare l’accesso ai bucket S3. La policy di bucket può essere configurata durante la creazione di un bucket. Per ulteriori informazioni, consulta la [documentazione su Amazon S3](https://docs.aws.amazon.com/it_it/AmazonS3/latest/dev/example-bucket-policies.html).
* Durante la creazione di un account esterno, abilita la crittografia per memorizzare dati sensibili nel bucket S3 selezionando la casella **[!UICONTROL Keep files in S3 encrypted]**.
* Concedi autorizzazioni di accesso ai bucket per specificare chi può accedere all’oggetto in un bucket. Per ulteriori informazioni sull’autorizzazione di accesso ai bucket, consulta la [documentazione di Amazon S3](https://docs.aws.amazon.com/it_it/AmazonS3/latest/dev/access-control-overview.html).

## Account esterno Adobe Experience Manager {#adobe-experience-manager-external-account}

Gli account esterni Adobe Experience Manager vengono utilizzati per l’integrazione di Campaign con Experience Manager.

I processi e i requisiti relativi a questa integrazione sono disponibili in [questo documento](../../integrating/using/get-started-campaign-integrations.md).

Durante la configurazione di questo nuovo account esterno, devi fornire i seguenti dettagli:

* Server: immetti l’URL del server Adobe Experience Manager. Ad esempio:

  ```
  http://aem.domain.com:4502
  ```

* Credenziali account AEM: utilizza l’account che accederà all’istanza di Adobe Experience Manager. Deve essere un account appartenente al gruppo remoto della campagna in Experience Manager.

## Account esterno Google reCAPTCHA {#google-recaptcha-external-account}

>[!NOTE]
>
>La configurazione di Google reCAPTCHA richiede un account Google.

Il meccanismo Google reCAPTCHA ti consente di proteggere la pagina di destinazione dallo spam e dagli abusi causati dai bot. Ciò non è intrusivo per i clienti in quanto non richiede alcuna interazione da parte loro e si basa sulle interazioni con il sito. Per registrare il sito, consulta questa [pagina](https://www.google.com/recaptcha/admin/create). Scegliere il tipo di reCAPTCHA V3.

Per aggiungere il Google reCAPTCHA V3 alla pagina di destinazione, configuralo nel tuo account esterno. Per ulteriori informazioni su come aggiungerlo alla pagina di destinazione, consulta questa [sezione](../../channels/using/configuring-landing-page.md#setting-google-recaptcha).

Per un account esterno Google reCAPTCHA V3, fornisci i seguenti dettagli:

* Un’**[!UICONTROL Label]** e un **[!UICONTROL ID]** dell’account esterno
* **[!UICONTROL Type]**: Google reCAPTCHA
* La **[!UICONTROL Site key]** e il **[!UICONTROL Site secret]**
* Una **[!UICONTROL Threshold]** tra 0 e 1

  Il valore di **[!UICONTROL Threshold]** 0,0 indica che probabilmente si tratta di un bot e 1,0 indica che probabilmente si tratta di una buona interazione. Per impostazione predefinita, puoi utilizzare una soglia di 0,5.

![](assets/external_accounts_3.png)

## Account esterno archiviazione BLOB di Microsoft Azure {#microsoft-azure-external-account}

>[!NOTE]
>
>Le informazioni necessarie per configurare l’account esterno in Adobe Campaign Standard sono disponibili nel portale di Azure selezionando **[!UICONTROL Settings]** > **[!UICONTROL Access keys]**.

Il connettore di archiviazione BLOB di Azure può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un’attività del flusso di lavoro **[!UICONTROL Transfer file]**. Per ulteriori informazioni, consulta questa [sezione](../../automating/using/transfer-file.md#azure-blob-configuration-wf).

Per un account esterno dell’archiviazione BLOB di Microsoft Azure, fornisci i seguenti dettagli:

* Un’**[!UICONTROL Label]** e un **[!UICONTROL ID]** dell’account esterno
* **[!UICONTROL Type]**: archiviazione BLOB di Microsoft Azure
* Il **[!UICONTROL Account name]** e la **[!UICONTROL Account key]**. Per sapere dove trovare il nome e la chiave dell’account, consulta questa [pagina](https://docs.microsoft.com/it-it/azure/storage/common/storage-account-keys-manage).
* Il **[!UICONTROL Endpoint suffix]**. È disponibile all’interno della **[!UICONTROL Connection string]** del menu **[!UICONTROL Access keys]** nel portale di Azure. Per ulteriori informazioni, consulta questa [pagina](https://docs.microsoft.com/it-it/azure/storage/common/storage-account-keys-manage).
* Il nome del **[!UICONTROL Container]**. Se prevedi di utilizzare più di un contenitore, crea un numero illimitato di account esterni come contenitori.
* L’opzione **[!UICONTROL Concurrency]** ti consente di ottimizzare la velocità dei trasferimenti di file.

![](assets/external_accounts_4.png)

Al termine della configurazione, fai clic su **[!UICONTROL Test connection]** per collegare Adobe Campaign all’archiviazione BLOB di Microsoft Azure.

### Raccomandazioni per l’archiviazione BLOB di Microsoft Azure {#azure-blob-recommendations}

**Crittografia**

Adobe Campaign utilizza una connessione protetta (HTTPS) per accedere all’account di archiviazione BLOB di Microsoft Azure.

**Chiave di accesso all’account**

Durante la configurazione dell’account esterno, devi utilizzare una delle **[!UICONTROL Account key]** disponibili nel portale di Azure. Per ulteriori informazioni su dove trovare le chiavi di accesso all’account, consulta questa [pagina](https://docs.microsoft.com/it-it/azure/storage/common/storage-account-keys-manage#view-access-keys-and-connection-string).

**Ottimizzazione della velocità di trasferimento dei file**

L’opzione **[!UICONTROL Concurrency]** ti consente di ottimizzare la velocità dei trasferimenti di file.
Rappresenta il numero di thread che verranno utilizzati per eseguire il trasferimento di file. Ognuno di questi thread scaricherà una porzione di circa 1 MB dal BLOB. Queste porzioni saranno quindi messe in coda per essere scritte su disco. Tieni presente che aumentando il numero di thread aumenterai anche il carico sulle risorse utilizzate dall’applicazione durante il trasferimento di file.

Al termine del trasferimento di file, puoi trovare le metriche delle prestazioni nei registri del flusso di lavoro.

**Nuovi tentativi**

Per impostazione predefinita, il trasferimento di file per BLOB di Azure effettuerà fino a quattro tentativi.  Se il servizio di archiviazione di Azure restituisce un codice di errore come 503 (server occupato) o 500 (timeout operazione), ciò potrebbe indicare che ti stai avvicinando o stai superando la scalabilità dell’account di archiviazione. Ciò può verificarsi quando si utilizza un nuovo account o si eseguono test.

Se l’errore persiste, puoi aumentare il numero di tentativi creando un’opzione nel menu avanzato **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

Se implementata, l’opzione deve essere creata come segue:

```
ID:        AzureBlob_Max_Retries
Date type: Integer
Default:   <the number of retries needed>
```
