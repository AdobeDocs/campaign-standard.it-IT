---
title: Account esterni
seo-title: Account esterni
description: Account esterni
seo-description: Configurate account esterni per impostare connessioni con sistemi esterni come i server SFTP.
page-status-flag: never-activated
uuid: 5 d 2 e 2 e 3 d -5 d 1 f -4466-97 e 5-842 c 50390146
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: application-settings
discoiquuid: d 5 c 6 a 3 d 4-f 767-46 c 1-a 8 c 0-3 b 9 dc 52 dcea 8
internal: n
snippet: y
context-tags: Extaccount, main; Extaccount, panoramica
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# External accounts{#external-accounts}

Un account esterno è una configurazione che consente di configurare e verificare l'accesso a un server esterno ad Adobe Campaign.

Questi account esterni possono essere utilizzati nei flussi di lavoro Campagna per accedere e gestire i dati.

Potete configurare i seguenti tipi di account esterni:

* SFTP. For more on this, refer to [this section](../../administration/using/external-accounts.md#sftp-external-account).
* Amazon Storage Service (S 3). For more on this, refer to [this section](../../administration/using/external-accounts.md#amazon-s3-external-account).
* Adobe Experience Manager. For more on this, refer to [this section](../../administration/using/external-accounts.md#adobe-experience-manager-external-account).
* Adobe Analytics. For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google recaptcha. For more on this, refer to [this section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

>[!NOTE]
>
>Altri tipi di account esterni vengono utilizzati da Adobe durante il processo di provisioning dei prodotti. Dalla release Campaign Standard 17.9, gli account esterni FTP possono ancora essere definiti ma non sono più utilizzabili nelle nuove attività del flusso di lavoro. Se è già stata impostata una connessione, questa viene comunque attivata.

External accounts can be configured by administrators under the **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creating an external account {#creating-an-external-account}

Adobe Campaign viene fornito con un insieme di account esterni preconfigurati. Per impostare connessioni con sistemi esterni quali server FTP utilizzati per i trasferimenti di file, potete creare account esterni.

Gli account esterni sono utilizzati da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro della campagna. Quando configurate un trasferimento di file in un flusso di lavoro o uno scambio di dati con qualsiasi altra applicazione (Adobe Target, Experience Manager, ecc.), dovete selezionare un account esterno.

1. Click the **[!UICONTROL Create]** button.
1. Immettete un'etichetta. L'etichetta e l'ID saranno utilizzati quando si selezionano account esterni nei flussi di lavoro.
1. Selezionate il tipo di account che desiderate creare.
1. Configurare l'accesso all'account specificando le credenziali, l'indirizzo server, il numero di porta e o le chiavi quando pertinente.

   Le informazioni necessarie sono in genere fornite dal fornitore del server a cui ci si sta connettendo.

1. Salvate l'account.

L'account esterno viene creato e aggiunto all'elenco degli account. Ora è disponibile per i trasferimenti di dati/file o di routing nelle attività del flusso di lavoro e nelle proprietà di consegna.

## SFTP external account {#sftp-external-account}

Diversi tipi di account esterni richiedono informazioni diverse da specificare.

Per un account esterno SFTP, fornisci i seguenti dettagli:

* Indirizzo server. For example, **ftp.domain.com**.
* Numero porta. For example, **22**.
* Credenziali server SFTP: nome account e password utilizzata per connettersi al server.

### Adobe hosted SFTP server recommendations {#adobe-hosted-sftp-server-recommendations}

Quando si gestiscono file e dati per ETL, questi file vengono memorizzati in un server SFTP ospitato fornito da Adobe. Questo SFTP è uno spazio di archiviazione temporaneo su cui potete controllare la conservazione e l'eliminazione dei file.

Se non viene utilizzato o monitorato correttamente, questo spazio può riempire rapidamente lo spazio fisico disponibile sul server e causare problemi gravi. Può causare una perdita di dati o un danneggiamento sulla piattaforma.

Per evitare tali problemi, Adobe consiglia di seguire le best practice seguenti:

* Mantenere i dati minimi possibili.
* Utilizzate l'autenticazione basata su chiave per evitare la scadenza della password. Supported formats are **OpenSSH** and **SSH2** only. Dovrai fornire la chiave pubblica al team di assistenza Adobe per caricarlo sul server Campaign.
* Mantenete i dati solo se necessario. 15 giorni è il limite massimo di tempo.
* Utilizza flussi di lavoro per eliminare correttamente i dati (gestisci il mantenimento da flussi di lavoro che consumano i dati).
* Utilizzo di batch in caricamenti SFTP e nei flussi di lavoro.
* Gestione di errori/eccezioni.
* A volte, accedete a SFTP per controllare direttamente ciò che vi appartiene.
* Tenere presente che la gestione del disco SFTP è prevalentemente responsabile.

Inoltre, gli IP pubblici da cui si sta tentando di avviare la connessione SFTP devono essere inseriti nella white list dell'istanza Campaign. Whitelisting of IP addresses can be requested via a [support ticket](https://support.neolane.net), along with providing the public key to use for authentication.

I server Sftp possono essere gestiti dal Pannello di controllo. For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>Il Pannello di controllo è disponibile solo per gli utenti Admin dei clienti ospitati su AWS.
Check if your instance is hosted on AWS [here](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Amazon S3 external account {#amazon-s3-external-account}

Il campo del server Amazon S 3 deve essere compilato come segue:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

To store your file in S3 encrypted mode, check the **[!UICONTROL Keep files in S3 encrypted]** box.

![](assets/external_accounts_2.png)

Le informazioni necessarie sono in genere fornite dal fornitore del server a cui ci si sta connettendo.

Specify the **[!UICONTROL AWS Region]** associated to your endpoint. You can check the supported regions and signature versions in the official [Amazon S3 documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) .

### Amazon S3 account recommendations {#amazon-s3-account-recommendations}

Per configurare l'account Amazon S 3, vi consigliamo di seguire le seguenti raccomandazioni:

* Create criteri rigorosi per limitare l'accesso ai bucket S 3. Il criterio secchiello può essere configurato durante la creazione di un bucket. For more information, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* While creating an external account, enable the encryption to store sensitive data in the S3 bucket by checking the **[!UICONTROL Keep files in S3 encrypted]** box.
* Concedete le autorizzazioni di bucket per specificare chi può accedere all'oggetto in un bucket. For more information on bucket permission, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

Gli account esterni di Adobe Experience Manager vengono utilizzati quando si integra Campaign con Experience Manager.

Process and requirements related to this integration are available in [this document](../../integrating/using/about-campaign-integrations.md).

Quando state configurando il nuovo account esterno, dovete fornire i seguenti dettagli:

* Server: immettete l'URL del server Adobe Experience Manager. For example, **http://aem.domain.com:4502**.
* Credenziali account AEM: utilizzare l'account che accederà all'istanza Adobe Experience Manager. Deve essere un account del gruppo remoto della campagna in Experience Manager.

## Google reCAPTCHA external account {#google-recaptcha-external-account}

>[!NOTE]
>
>La configurazione Google recaptcha richiede un account Google.

Il meccanismo Google recaptcha consente di proteggere la pagina di destinazione da spam e abusi causati da bot. Questo non è intrusivo per i clienti perché non richiede alcuna interazione da loro e si basa sulle interazioni con il sito. To register your site, refer to this [page](https://www.google.com/recaptcha/admin/create). È necessario scegliere il tipo V 3 recaptcha.

Per aggiungere Google recaptcha V 3 alla pagina di destinazione, occorre prima configurarlo nell'account esterno. For more information on how to add it to your landing page, refer to this [section](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

Per un account esterno Google recaptcha V 3, fornite i seguenti dettagli:

* A **[!UICONTROL Label]** and **[!UICONTROL ID]** of your external account
* **[!UICONTROL Type]**: Google recaptcha
* Your **[!UICONTROL Site key]** and **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   The 0.0 **[!UICONTROL Threshold]** value means that it is likely a bot and 1.0 likely a good interaction. Per impostazione predefinita, potete utilizzare una soglia di 0.5.

![](assets/external_accounts_3.png)

