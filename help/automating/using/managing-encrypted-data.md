---
solution: Campaign Standard
product: campaign
title: Gestione dei dati crittografati
description: Scopri come gestire i dati crittografati.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 5%

---


# Gestione dei dati crittografati {#managing-encrypted-data}

## Informazioni sulle fasi di pre-elaborazione {#about-preprocessing-stages}

In alcuni casi, i dati da importare sui server delle campagne potrebbero dover essere crittografati, ad esempio se contengono dati PII.

Per poter crittografare i dati in uscita o decrittografare quelli in arrivo, è necessario gestire le chiavi GPG utilizzando il [Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/instances-settings/gpg-keys-management.html).

>[!NOTE]
>
>Il Pannello di controllo Campaign è disponibile per tutti i clienti ospitati su AWS (ad eccezione dei clienti che ospitano le proprie istanze di marketing in sede).

Se non siete autorizzati a utilizzare il Pannello di controllo Campaign, dovete contattare  Assistenza clienti di Adobe in modo che forniscano all&#39;istanza i comandi di cifratura/decrittazione necessari. A tal fine, inviare una richiesta indicando:

* L&#39; **etichetta** che verrà visualizzata nell&#39;interfaccia di Campaign per utilizzare il comando. Ad esempio &quot;Cifra file&quot;.
* Il **comando** da installare nell&#39;istanza.

Una volta elaborata la richiesta, i comandi di cifratura/decrittazione saranno disponibili nel campo **[!UICONTROL Pre-processing stage]** dalle attività **[!UICONTROL Load file]** e **[!UICONTROL Extract file]**. Potete utilizzarli per decifrare o cifrare i file da importare o esportare.

![](assets/preprocessing-encryption.png)

**Argomenti correlati:**

* [Load file](../../automating/using/load-file.md)
* [Extract file](../../automating/using/extract-file.md)

## Caso di utilizzo: Importazione di dati crittografati con una chiave generata dal Pannello di controllo Campaign {#use-case-gpg-decrypt}

In questo caso, verrà creato un flusso di lavoro per importare i dati crittografati in un sistema esterno, utilizzando una chiave generata nel Pannello di controllo Campaign.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

Le operazioni da eseguire per questo caso di utilizzo sono le seguenti:

1. Utilizzate il Pannello di controllo Campaign per generare una coppia di chiavi (pubblica/privata). I passaggi dettagliati sono disponibili nella [documentazione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * La chiave pubblica verrà condivisa con il sistema esterno, che la utilizzerà per crittografare i dati da inviare a Campaign.
   * La chiave privata verrà utilizzata da Campaign per decifrare i dati crittografati in arrivo.

   ![](assets/gpg_generate.png)

1. Nel sistema esterno, utilizzare la chiave pubblica scaricata dal Pannello di controllo Campaign per cifrare i dati da importare in Campaign Standard.

1. In Campaign Standard, creare un flusso di lavoro per importare i dati crittografati e decifrarlo utilizzando la chiave privata installata tramite il Pannello di controllo Campaign. A tal fine, verrà creato un flusso di lavoro come segue:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** activity: Trasferisce il file da un&#39;origine esterna a Campaign. In questo esempio, vogliamo trasferire il file da un server SFTP.
   * **[!UICONTROL Load file]** activity: Carica i dati dal file nel database e decrittografalo utilizzando la chiave privata generata nel Pannello di controllo Campaign.

1. Apri l&#39;attività **[!UICONTROL Transfer file]**, quindi configurala in base alle tue esigenze. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Nella scheda **[!UICONTROL Protocol]**, specificate i dettagli sul server sftp e sul file .gpg crittografato da trasferire.

   ![](assets/gpg_transfer.png)

1. Apri l&#39;attività **[!UICONTROL Load file]**, quindi configurala in base alle tue esigenze. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Aggiungete una fase di pre-elaborazione all&#39;attività, per decifrare i dati in arrivo. A questo scopo, selezionare l&#39;opzione **[!UICONTROL Decryption GPG]** dall&#39;elenco.

   >[!NOTE]
   >
   >Non è necessario specificare la chiave privata da utilizzare per decrittografare i dati. La chiave privata è memorizzata nel Pannello di controllo Campaign, che rileverà automaticamente la chiave da utilizzare per decrittografare il file.

   ![](assets/gpg_load.png)

1. Fate clic su **[!UICONTROL OK]** per confermare la configurazione dell&#39;attività.

1. Ora puoi eseguire il flusso di lavoro.

## Caso di utilizzo: Cifratura ed esportazione di dati utilizzando una chiave installata nel Pannello di controllo Campaign {#use-case-gpg-encrypt}

In questo caso, verrà creato un flusso di lavoro per la cifratura e l&#39;esportazione dei dati tramite una chiave installata sul Pannello di controllo Campaign.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

Le operazioni da eseguire per questo caso di utilizzo sono le seguenti:

1. Generate una coppia di chiavi GPG (pubblica/privata) utilizzando un&#39;utility GPG, quindi installate la chiave pubblica sul Pannello di controllo Campaign. I passaggi dettagliati sono disponibili nella [documentazione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. In Campaign Standard, creare un flusso di lavoro per esportare i dati e cifrarlo utilizzando la chiave privata installata tramite il Pannello di controllo Campaign. A tal fine, verrà creato un flusso di lavoro come segue:

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** activity: In questo esempio, si desidera eseguire una query per eseguire il targeting dei dati del database che si desidera esportare.
   * **[!UICONTROL Extract file]** activity: Cifra ed estrae i dati in un file.
   * **[!UICONTROL Transfer file]** activity: Trasferisce il file contenente i dati crittografati a un server SFTP.

1. Configurate l&#39;attività **[!UICONTROL Query]** per eseguire il targeting dei dati desiderati dal database. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/query.md).

1. Aprite l&#39;attività **[!UICONTROL Extract file]**, quindi configuratela in base alle vostre esigenze (file di output, colonne, formato, ecc.). I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/extract-file.md).

   Aggiungete un passaggio di pre-elaborazione all&#39;attività, per cifrare i dati da estrarre. A tal fine, selezionare la chiave GPG di crittografia da utilizzare per cifrare i dati.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >Il valore tra parentesi è il **commento** definito durante la generazione della coppia di chiavi con lo strumento di cifratura GPG. Assicurarsi di selezionare la chiave di corrispondenza corretta, altrimenti il destinatario non sarà in grado di decifrare il file.

1. Aprite l&#39;attività **[!UICONTROL Transfer file]**, quindi specificate il server SFTP al quale desiderate inviare il file. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Ora puoi eseguire il flusso di lavoro. Una volta eseguita, la destinazione dei dati dalla query verrà esportata nel server SFTP in un file .gpg crittografato.

## Video tutorial {#video}

In questo video viene illustrato come utilizzare un codice GPG per decrittografare i dati.

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

Questo video mostra come utilizzare una chiave GPG per cifrare i dati.

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

Ulteriori video dimostrativi sui Campaign Standard sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
