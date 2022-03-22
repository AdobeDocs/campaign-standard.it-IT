---
title: Risoluzione dei problemi di integrazione
description: Scopri come risolvere i problemi relativi alla condivisione delle risorse.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---

# Risoluzione dei problemi{#troubleshooting}

È possibile che si verifichino errori durante l’utilizzo dell’integrazione con il servizio core Audience Manager o People.

In questo caso, assicurati che i seguenti elementi siano configurati correttamente:

* **Account esterni**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, assicurati che i seguenti account S3 esterni siano configurati correttamente. I server S3 menzionati avrebbero dovuto essere configurati durante il provisioning.

   * **[!UICONTROL importSharedAudience]**: Account S3 dedicato all’importazione di tipi di pubblico.
   * **[!UICONTROL exportSharedAudience]**: Account S3 dedicato all’esportazione di tipi di pubblico.

* **Origini dati condivise**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, controlla che l&#39;origine dati condivisa sia impostata correttamente.

   **[!UICONTROL Priority]** viene utilizzato quando sono definite più origini dati. Priorità decide quale origine dati verrà utilizzata per corrispondere all’alias ricevuto nell’ordine definito. **[!UICONTROL Priority]** è necessario solo per l&#39;implementazione di Triggers.

   Verifica che la chiave di riconciliazione sia corretta. Il valore crittografato o con hash di questo campo viene utilizzato per esportare e importare i tipi di pubblico.

   In caso di hashing o crittografia dell’ID dichiarato, verifica che gli stessi parametri/algoritmi di crittografia siano utilizzati sul tuo sito web.

   È supportato un solo algoritmo di crittografia: AES in modalità CBC con una dimensione chiave di 128, 192 o 256 bit, con imbottitura PKCS.

   Se è selezionato l’algoritmo di crittografia AES, è necessario impostare correttamente i campi aggiuntivi seguenti:

   * **Chiave di crittografia** per AES
   * **Crittografia IV** (vettore di inizializzazione) per AES
   * **Canale** (E-mail/SMS/Altro): Questo campo consente di decrittografare direttamente gli indirizzi e-mail e i numeri SMS. Assicurati che la chiave di riconciliazione corrisponda all&#39;impostazione della **Canale** campo . Se selezioni &quot;Altro&quot;, questa decrittografia specifica non verrà eseguita e la chiave di riconciliazione verrà utilizzata per riconciliare i dati.

   È possibile che il pubblico di Experience Cloud non sia condiviso perché il flusso di lavoro tecnico è stato arrestato o messo in pausa. Accedere al **[!UICONTROL Import shared audience]** facendo clic direttamente sul pulsante **[!UICONTROL Show ImportShared Audience workflow]** nella tua origine dati.

È possibile che alcuni dati manchino durante la condivisione di un pubblico tramite il servizio core Persone o durante l’importazione di un pubblico. Vengono trasferiti solo i record di cui è stato possibile riconciliare l’ID (&quot;ID visitatore&quot; o &quot;ID dichiarato&quot;) con la dimensione del profilo. Gli ID dei segmenti del servizio core Persone che non sono riconosciuti da Adobe Campaign non vengono importati.
