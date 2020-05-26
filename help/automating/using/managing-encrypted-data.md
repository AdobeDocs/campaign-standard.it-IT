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
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---


# Gestione dei dati crittografati {#managing-encrypted-data}

In alcuni casi, i dati da importare sui server delle campagne potrebbero dover essere crittografati, ad esempio se contengono dati PII.

Per importare o esportare file crittografati, è innanzitutto necessario contattare l&#39;Assistenza clienti Adobe in modo che fornisca all&#39;istanza i comandi di cifratura/decrittazione necessari.

A tal fine, inviare una richiesta indicando:

* L&#39; **etichetta** che verrà visualizzata nell&#39;interfaccia di Campaign per utilizzare il comando. Ad esempio &quot;Cifra file&quot;.
* Il **comando** da installare nell’istanza.
Ad esempio, per decifrare un file con PGP, il comando sarà:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Una volta elaborata la richiesta, i comandi di cifratura/decrittazione saranno disponibili nel **[!UICONTROL Pre-processing stage]** campo dalle **[!UICONTROL Load file]** attività e **[!UICONTROL Extract file]** . Potete utilizzarli per decifrare o cifrare i file da importare o esportare.

![](assets/preprocessing-encryption.png)

**Argomenti correlati:**

* [Caricare file](../../automating/using/load-file.md)
* [Estrarre file](../../automating/using/extract-file.md)
