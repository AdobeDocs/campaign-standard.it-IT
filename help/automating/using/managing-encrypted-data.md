---
title: Gestione dei dati crittografati
description: Scopri come gestire i dati crittografati.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows, Encryption
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 69c47c8f3cbb405acbef634aa1ebaef8e767f159
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 3%

---

# Gestione dei dati crittografati {#managing-encrypted-data}

## Informazioni sulle fasi di pre-elaborazione {#about-preprocessing-stages}

In alcuni casi, potrebbe essere necessario crittografare i dati che desideri importare dai server Campaign, ad esempio se contengono dati PII.

Per poter crittografare i dati in uscita o decrittografare i dati in arrivo, devi gestire le chiavi GPG utilizzando il [Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=it).

>[!NOTE]
>
>Il Pannello di controllo Campaign è disponibile per tutti i clienti in hosting su AWS (ad eccezione dei clienti che ospitano le loro istanze di marketing on-premise).

Se non sei idoneo a utilizzare il Pannello di controllo Campaign, devi contattare l’Assistenza clienti di Adobe in modo che fornisca all’istanza i comandi di crittografia/decrittografia necessari. A questo scopo, invia una richiesta indicando:

* **label** che verrà visualizzata nell&#39;interfaccia di Campaign per utilizzare il comando. Ad esempio, &quot;Crittografa file&quot;.
* Il **comando** da installare nell&#39;istanza.

Una volta elaborata la richiesta, i comandi di crittografia/decrittografia saranno disponibili nel campo **[!UICONTROL Pre-processing stage]** delle attività **[!UICONTROL Load file]** e **[!UICONTROL Extract file]**. Puoi utilizzarli per decrittografare o crittografare i file che desideri importare o esportare.

![](assets/preprocessing-encryption.png)

**Argomenti correlati:**

* [Carica file](../../automating/using/load-file.md)
* [Estrai file](../../automating/using/extract-file.md)

## Caso di utilizzo: importazione di dati crittografati utilizzando una chiave generata dal Pannello di controllo Campaign {#use-case-gpg-decrypt}

In questo caso d’uso, crea un flusso di lavoro per importare dati che sono stati crittografati in un sistema esterno, utilizzando una chiave generata nel Pannello di controllo Campaign.

![](assets/do-not-localize/how-to-video.png) [Guarda il video su questa funzione](#video)

I passaggi per eseguire questo caso d’uso sono i seguenti:

1. Utilizza il Pannello di controllo Campaign per generare una coppia di chiavi (pubblica/privata). I passaggi dettagliati sono disponibili nella [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=it#decrypting-data).

   * La chiave pubblica verrà condivisa con il sistema esterno, che la utilizzerà per crittografare i dati da inviare a Campaign.
   * Campaign utilizzerà la chiave privata per decrittografare i dati crittografati in arrivo.

   ![](assets/gpg_generate.png)

1. Nel Pannello di controllo Campaign esterno, utilizza la chiave pubblica scaricata dal sistema per crittografare i dati da importare in Campaign Standard.

1. In Campaign Standard, crea un flusso di lavoro per importare i dati crittografati e decrittografarli utilizzando la chiave privata installata tramite il Pannello di controllo Campaign. A questo scopo, crea un flusso di lavoro come segue:

   ![](assets/gpg_workflow.png)

   * Attività **[!UICONTROL Transfer file]**: trasferisce il file da un&#39;origine esterna a Campaign. In questo esempio, vogliamo trasferire il file da un server SFTP.
   * Attività **[!UICONTROL Load file]**: carica i dati dal file nel database e li decrittografa utilizzando la chiave privata generata nel Pannello di controllo Campaign.

1. Apri l&#39;attività **[!UICONTROL Transfer file]** e configurala in base alle tue esigenze. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Nella scheda **[!UICONTROL Protocol]** specificare i dettagli relativi al server sftp e al file .gpg crittografato che si desidera trasferire.

   ![](assets/gpg_transfer.png)

1. Apri l&#39;attività **[!UICONTROL Load file]**, quindi configurala in base alle tue esigenze. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Aggiungi una fase di pre-elaborazione all’attività per decrittografare i dati in arrivo. A tale scopo, selezionare l&#39;opzione **[!UICONTROL Decryption GPG]** dall&#39;elenco.

   >[!NOTE]
   >
   >Non è necessario specificare la chiave privata da utilizzare per decrittografare i dati. La chiave privata viene archiviata nel Pannello di controllo Campaign, che rileva automaticamente la chiave da utilizzare per decrittografare il file.

   ![](assets/gpg_load.png)

1. Fare clic su **[!UICONTROL OK]** per confermare la configurazione dell&#39;attività.

1. Ora puoi eseguire il flusso di lavoro.

## Caso di utilizzo: crittografia ed esportazione di dati tramite una chiave installata sul Pannello di controllo Campaign {#use-case-gpg-encrypt}

In questo caso d’uso, crea un flusso di lavoro per crittografare ed esportare i dati utilizzando una chiave installata sul Pannello di controllo Campaign.

![](assets/do-not-localize/how-to-video.png) [Guarda il video su questa funzione](#video)

I passaggi per eseguire questo caso d’uso sono i seguenti:

1. Genera una coppia di chiavi GPG (pubblica/privata) utilizzando un’utility GPG, quindi installa la chiave pubblica sul Pannello di controllo Campaign. I passaggi dettagliati sono disponibili nella [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=it#encrypting-data).

   ![](assets/gpg_install.png)

1. In Campaign Standard, crea un flusso di lavoro per esportare i dati e crittografarli utilizzando la chiave privata installata tramite il Pannello di controllo Campaign. A questo scopo, crea un flusso di lavoro come segue:

   ![](assets/gpg-workflow-export.png)

   * Attività **[!UICONTROL Query]**: in questo esempio, si desidera eseguire una query per eseguire il targeting dei dati del database che si desidera esportare.
   * Attività **[!UICONTROL Extract file]**: crittografa ed estrae i dati in un file.
   * Attività **[!UICONTROL Transfer file]**: trasferisce il file contenente i dati crittografati a un server SFTP.

1. Configurare l&#39;attività **[!UICONTROL Query]** in modo che esegua il targeting dei dati desiderati dal database. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/query.md).

1. Apri l&#39;attività **[!UICONTROL Extract file]** e configurala in base alle tue esigenze (file di output, colonne, formato, ecc.). I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/extract-file.md).

   Aggiungi una fase di pre-elaborazione all’attività per crittografare i dati da estrarre. A questo scopo, seleziona la chiave GPG di crittografia da utilizzare per crittografare i dati.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >Il valore tra parentesi è il **commento** definito durante la generazione della coppia di chiavi tramite lo strumento di crittografia GPG. Assicurati di selezionare la chiave corrispondente corretta, altrimenti il destinatario non sarà in grado di decrittografare il file.

1. Apri l&#39;attività **[!UICONTROL Transfer file]**, quindi specifica il server SFTP a cui inviare il file. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Ora puoi eseguire il flusso di lavoro. Una volta eseguita, la destinazione dati dalla query verrà esportata sul server SFTP in un file .gpg crittografato.

## Video tutorial {#video}

Questo video mostra come utilizzare una chiave GPG per decrittografare i dati.

>[!VIDEO](https://video.tv.adobe.com/v/41165?quality=12&captions=ita)

Questo video mostra come utilizzare una chiave GPG per crittografare i dati.

>[!VIDEO](https://video.tv.adobe.com/v/41163?quality=12&captions=ita)

Sono disponibili altri video dimostrativi di Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
