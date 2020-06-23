---
title: Gestione dei dati crittografati
description: Scopri come gestire i dati crittografati.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: adc5e92183b891a70cac4aa7a6ed96148d104a20
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 2%

---


# Gestione dei dati crittografati {#managing-encrypted-data}

## Informazioni sulle fasi di pre-elaborazione {#about-preprocessing-stages}

In alcuni casi, i dati da importare sui server delle campagne potrebbero dover essere crittografati, ad esempio se contengono dati PII.

Per importare o esportare file crittografati, è innanzitutto necessario contattare l&#39;Assistenza clienti Adobe in modo che fornisca all&#39;istanza i comandi di cifratura/decrittazione necessari.

A tal fine, inviare una richiesta indicando:

* L&#39; **etichetta** che verrà visualizzata nell&#39;interfaccia di Campaign per utilizzare il comando. Ad esempio &quot;Cifra file&quot;.
* Il **comando** da installare nell’istanza.

Una volta elaborata la richiesta, i comandi di cifratura/decrittazione saranno disponibili nel **[!UICONTROL Pre-processing stage]** campo dalle **[!UICONTROL Load file]** attività e **[!UICONTROL Extract file]** . Potete utilizzarli per decifrare o cifrare i file da importare o esportare.

![](assets/preprocessing-encryption.png)

>[!NOTE]
>
>Si noti che le chiavi GPG possono essere aggiunte all&#39;istanza utilizzando il Pannello di controllo, disponibile per tutti i clienti ospitati su AWS (ad eccezione dei clienti che ospitano le proprie istanze di marketing in sede).
>
>Per ulteriori informazioni, consultare la documentazione [del Pannello di](https://docs.adobe.com/content/help/it-IT/control-panel/using/control-panel-home.html)controllo.

**Argomenti correlati:**

* [Caricare file](../../automating/using/load-file.md)
* [Estrarre file](../../automating/using/extract-file.md)

## Caso di utilizzo: Importazione di dati crittografati con una chiave generata dal Pannello di controllo {#use-case-gpg-decrypt}

In questo caso, verrà creato un flusso di lavoro per importare i dati crittografati in un sistema esterno, utilizzando una chiave generata nel Pannello di controllo.

Le operazioni da eseguire per questo caso di utilizzo sono le seguenti:

1. Usate il Pannello di controllo per generare una coppia di chiavi (pubblica/privata). I passaggi dettagliati sono disponibili nella documentazione [del Pannello di](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data)controllo.

   * La chiave pubblica verrà condivisa con il sistema esterno, che la utilizzerà per crittografare i dati da inviare a Campaign.
   * La chiave privata verrà utilizzata da Campaign per decifrare i dati crittografati in arrivo.
   ![](assets/gpg_generate.png)

1. Nel sistema esterno, utilizzare la chiave pubblica scaricata dal Pannello di controllo per cifrare i dati da importare in Campaign Standard.

   ![](assets/gpg_external.png)

1. In Campaign Standard, creare un flusso di lavoro per importare i dati crittografati e decifrarlo utilizzando la chiave privata installata tramite il Pannello di controllo. A tal fine, verrà creato un flusso di lavoro come segue:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** activity: Trasferisce il file da un&#39;origine esterna a Campaign. In questo esempio, vogliamo trasferire il file da un server SFTP.
   * **[!UICONTROL Load file]** activity: Carica i dati dal file nel database e decrittografalo utilizzando la chiave privata generata nel Pannello di controllo.

1. Aprite l&#39; **[!UICONTROL Transfer file]** attività e configuratela in base alle vostre esigenze. Concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Nella **[!UICONTROL Protocol]** scheda, specificate i dettagli relativi al server sftp e al file .gpg cifrato che desiderate trasferire.

   ![](assets/gpg_transfer.png)

1. Aprite l&#39; **[!UICONTROL Load file]** attività, quindi configuratela in base alle vostre esigenze. Concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Aggiungete una fase di pre-elaborazione all&#39;attività, per decifrare i dati in arrivo. A tale scopo, selezionare l&#39; **[!UICONTROL Decryption GPG]** opzione dall&#39;elenco.

   >[!NOTE]
   >
   >Non è necessario specificare la chiave privata da utilizzare per decrittografare i dati. La chiave privata è memorizzata nel Pannello di controllo, che rileverà automaticamente la chiave da utilizzare per decrittografare il file.

   ![](assets/gpg_load.png)

1. Fate clic **[!UICONTROL OK]** per confermare la configurazione dell&#39;attività.

1. Ora puoi eseguire il flusso di lavoro.

## Caso di utilizzo: Cifratura ed esportazione dei dati tramite una chiave installata nel Pannello di controllo {#use-case-gpg-encrypt}

In questo caso, verrà creato un flusso di lavoro per la cifratura e l&#39;esportazione dei dati tramite una chiave installata nel Pannello di controllo.

Le operazioni da eseguire per questo caso di utilizzo sono le seguenti:

1. Generare una coppia di chiavi GPG (pubblica/privata) utilizzando un&#39;utility GPG, quindi installare la chiave pubblica nel Pannello di controllo. I passaggi dettagliati sono disponibili nella documentazione [del Pannello di](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data)controllo.

   ![](assets/gpg_install.png)

1. In Campaign Standard, creare un flusso di lavoro per esportare i dati ed esportarli utilizzando la chiave privata installata tramite il Pannello di controllo. A tal fine, verrà creato un flusso di lavoro come segue:

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** activity: In questo esempio, si desidera eseguire una query per eseguire il targeting dei dati del database che si desidera esportare.
   * **[!UICONTROL Extract file]** activity: Cifra ed estrae i dati in un file.
   * **[!UICONTROL Transfer file]** activity: Trasferisce il file contenente i dati crittografati a un server SFTP.

1. Configurate l&#39; **[!UICONTROL Query]** attività per eseguire il targeting dei dati desiderati dal database. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/query.md).

1. Aprite l&#39; **[!UICONTROL Extract file]** attività e configuratela in base alle vostre esigenze (file di output, colonne, formato, ecc.). Concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/extract-file.md).

   Aggiungete un passaggio di pre-elaborazione all&#39;attività, per cifrare i dati da estrarre. A tal fine, selezionare la chiave GPG di crittografia da utilizzare per cifrare i dati.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >Il valore tra parentesi è il **commento** definito durante la generazione della coppia di chiavi con lo strumento di cifratura GPG. Assicurarsi di selezionare la chiave di corrispondenza corretta, altrimenti il destinatario non sarà in grado di decifrare il file.

1. Aprite l&#39; **[!UICONTROL Transfer file]** attività, quindi specificate il server SFTP al quale desiderate inviare il file. Concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Ora puoi eseguire il flusso di lavoro. Una volta eseguita, la destinazione dei dati dalla query verrà esportata nel server SFTP in un file .gpg crittografato.

   ![](assets/gpg-sftp-encrypt.png)
