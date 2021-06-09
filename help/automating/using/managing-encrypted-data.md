---
solution: Campaign Standard
product: campaign
title: Gestione dei dati crittografati
description: Scopri come gestire i dati crittografati.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Flussi di lavoro
role: Data Architect
level: Experienced
exl-id: 1df1552a-6578-47eb-ba14-fb91cd2a3999
source-git-commit: 05e7de6d59420f532e0095ddb1fd7f158519518b
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 5%

---

# Gestione dei dati crittografati {#managing-encrypted-data}

## Informazioni sulle fasi di pre-elaborazione {#about-preprocessing-stages}

In alcuni casi, i dati che desideri importare dai server Campaign potrebbero dover essere crittografati, ad esempio se contengono dati PII.

Per crittografare i dati in uscita o decrittografare quelli in arrivo, devi gestire le chiavi GPG utilizzando il [Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html?lang=it).

>[!NOTE]
>
>Il Pannello di controllo Campaign è disponibile per tutti i clienti ospitati su AWS (ad eccezione dei clienti che ospitano le loro istanze di marketing on-premise).

Se non sei idoneo all’utilizzo del Pannello di controllo Campaign, devi contattare l’Assistenza clienti di Adobe in modo che fornisca all’istanza i comandi di crittografia/decrittografia necessari. A tal fine, invia una richiesta che indichi:

* L’ **etichetta** che verrà visualizzata nell’interfaccia di Campaign per utilizzare il comando. Ad esempio &quot;Crittografa file&quot;.
* Il **comando** da installare sull&#39;istanza.

Una volta elaborata la richiesta, i comandi di crittografia/decrittografia saranno disponibili nel campo **[!UICONTROL Pre-processing stage]** dalle attività **[!UICONTROL Load file]** e **[!UICONTROL Extract file]**. Puoi utilizzarli per decrittografare o crittografare i file da importare o esportare.

![](assets/preprocessing-encryption.png)

**Argomenti correlati:**

* [Load file](../../automating/using/load-file.md)
* [Extract file](../../automating/using/extract-file.md)

## Caso di utilizzo: Importazione di dati crittografati utilizzando una chiave generata dal Pannello di controllo Campaign {#use-case-gpg-decrypt}

In questo caso d’uso, creeremo un flusso di lavoro per importare i dati crittografati in un sistema esterno, utilizzando una chiave generata nel Pannello di controllo Campaign.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

I passaggi per eseguire questo caso d’uso sono i seguenti:

1. Utilizza il Pannello di controllo Campaign per generare una coppia di chiavi (pubblica/privata). I passaggi dettagliati sono disponibili nella [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#decrypting-data).

   * La chiave pubblica verrà condivisa con il sistema esterno, che lo utilizzerà per crittografare i dati da inviare a Campaign.
   * La chiave privata verrà utilizzata da Campaign per decrittografare i dati crittografati in arrivo.

   ![](assets/gpg_generate.png)

1. Nel sistema esterno, utilizza la chiave pubblica scaricata dal Pannello di controllo Campaign per crittografare i dati da importare in Campaign Standard.

1. In Campaign Standard, crea un flusso di lavoro per importare i dati crittografati e decrittografarli utilizzando la chiave privata installata tramite il Pannello di controllo Campaign. A questo scopo, verrà creato un flusso di lavoro come segue:

   ![](assets/gpg_workflow.png)

   * **[!UICONTROL Transfer file]** attività: Trasferisce il file da un’origine esterna a Campaign. In questo esempio, vogliamo trasferire il file da un server SFTP.
   * **[!UICONTROL Load file]** attività: Carica i dati dal file nel database e decrittografalo utilizzando la chiave privata generata nel Pannello di controllo Campaign.

1. Apri l’attività **[!UICONTROL Transfer file]** e configurala in base alle tue esigenze. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Nella scheda **[!UICONTROL Protocol]** , specifica i dettagli sul server sftp e sul file .gpg crittografato da trasferire.

   ![](assets/gpg_transfer.png)

1. Apri l’attività **[!UICONTROL Load file]** , quindi configurala in base alle tue esigenze. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/load-file.md).

   Aggiungi una fase di pre-elaborazione all’attività per decrittografare i dati in arrivo. A questo scopo, seleziona l’opzione **[!UICONTROL Decryption GPG]** dall’elenco.

   >[!NOTE]
   >
   >Non è necessario specificare la chiave privata da utilizzare per decrittografare i dati. La chiave privata viene memorizzata in Pannelli di controllo Campaign, che rileverà automaticamente la chiave da utilizzare per decrittografare il file.

   ![](assets/gpg_load.png)

1. Fai clic su **[!UICONTROL OK]** per confermare la configurazione dell’attività.

1. Ora puoi eseguire il flusso di lavoro.

## Caso di utilizzo: Cifratura ed esportazione di dati utilizzando una chiave installata sul Pannello di controllo Campaign {#use-case-gpg-encrypt}

In questo caso d’uso, creeremo un flusso di lavoro per crittografare ed esportare i dati utilizzando una chiave installata sul Pannello di controllo Campaign.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#video)

I passaggi per eseguire questo caso d’uso sono i seguenti:

1. Genera una coppia di chiavi GPG (pubblica/privata) utilizzando un&#39;utility GPG, quindi installa la chiave pubblica sul Pannello di controllo Campaign. I passaggi dettagliati sono disponibili nella [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/instances-settings/gpg-keys-management.html#encrypting-data).

   ![](assets/gpg_install.png)

1. In Campaign Standard, crea un flusso di lavoro per esportare i dati e cifrarli utilizzando la chiave privata installata tramite il Pannello di controllo Campaign. A questo scopo, verrà creato un flusso di lavoro come segue:

   ![](assets/gpg-workflow-export.png)

   * **[!UICONTROL Query]** attività: In questo esempio, si desidera eseguire una query per eseguire il targeting dei dati del database che si desidera esportare.
   * **[!UICONTROL Extract file]** attività: Cifra ed estrae i dati in un file.
   * **[!UICONTROL Transfer file]** attività: Trasferisce il file contenente i dati crittografati a un server SFTP.

1. Configura l’attività **[!UICONTROL Query]** per eseguire il targeting dei dati desiderati dal database. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/query.md).

1. Apri l’attività **[!UICONTROL Extract file]** e configurala in base alle tue esigenze (file di output, colonne, formato, ecc.). I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/extract-file.md).

   Aggiungi una fase di pre-elaborazione all’attività per crittografare i dati da estrarre. A questo scopo, seleziona la chiave GPG di crittografia da utilizzare per crittografare i dati.

   ![](assets/gpg-extract-stage.png)

   >[!NOTE]
   >
   >Il valore tra parentesi è il **commento** definito durante la generazione della coppia di chiavi utilizzando lo strumento di crittografia GPG. Assicurati di selezionare la chiave di corrispondenza corretta, altrimenti il destinatario non sarà in grado di decrittografare il file.

1. Apri l’attività **[!UICONTROL Transfer file]** , quindi specifica il server SFTP al quale vuoi inviare il file. I concetti globali su come configurare l&#39;attività sono disponibili in [questa sezione](../../automating/using/transfer-file.md).

   ![](assets/gpg-transfer-encrypt.png)

1. Ora puoi eseguire il flusso di lavoro. Una volta eseguito, il target dei dati dalla query verrà esportato nel server SFTP in un file .gpg crittografato.

## Video tutorial {#video}

Questo video mostra come utilizzare una chiave GPG per decrittografare i dati.

>[!VIDEO](https://video.tv.adobe.com/v/35753?quality=12)

Questo video mostra come utilizzare una chiave GPG per crittografare i dati.

>[!VIDEO](https://video.tv.adobe.com/v/36380?quality=12)

Sono disponibili ulteriori video dimostrativi su Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
