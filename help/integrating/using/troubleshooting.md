---
title: Risoluzione dei problemi di integrazione
description: Scopri come risolvere i problemi durante la condivisione delle risorse.
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

È possibile che si verifichino errori durante l’utilizzo dell’integrazione con il servizio di base Audienci Manager o People.

In questo caso, assicurati che i seguenti elementi siano configurati correttamente:

* **Account esterni**

  In entrata **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, assicurati che i seguenti account S3 esterni siano configurati correttamente. I server S3 menzionati avrebbero dovuto essere configurati durante il provisioning.

   * **[!UICONTROL importSharedAudience]**: account S3 dedicato all’importazione di tipi di pubblico.
   * **[!UICONTROL exportSharedAudience]**: account S3 dedicato all’esportazione dei tipi di pubblico.

* **Origini dati condivise**

  In entrata **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, verificare che l&#39;origine dati condivisa sia impostata correttamente.

  **[!UICONTROL Priority]** viene utilizzato quando sono definite più origini dati. La priorità determina l’origine dati da utilizzare per la corrispondenza con l’alias ricevuto nell’ordine definito. **[!UICONTROL Priority]** è necessario solo per l’implementazione di Triggers.

  Verifica che la chiave di riconciliazione sia corretta. È il valore con hash/crittografato di questo campo che viene utilizzato per esportare e importare i tipi di pubblico.

  In caso di hashing o crittografia dell’ID dichiarato, verifica che gli stessi parametri/algoritmi di crittografia siano utilizzati sul sito web.

  È supportato un solo algoritmo di crittografia: AES in modalità CBC con chiave di 128, 192 o 256 bit, con spaziatura PKCS.

  Se è selezionato l&#39;algoritmo di crittografia AES, è necessario impostare correttamente i campi aggiuntivi seguenti:

   * **Chiave di crittografia** per AES
   * **Crittografia IV** (vettore di inizializzazione) per AES
   * **Canale** (E-mail/SMS/Altro): questo campo consente di decrittografare direttamente gli indirizzi e-mail e i numeri SMS. Assicurati che la chiave di riconciliazione corrisponda all’impostazione della **Canale** campo. Se selezioni &quot;Altro&quot;, questa decrittografia specifica non verrà eseguita e la chiave di riconciliazione verrà utilizzata per riconciliare i dati.

  I tipi di pubblico di Experience Cloud potrebbero non essere condivisi perché il flusso di lavoro tecnico è stato interrotto o sospeso. Accedere a **[!UICONTROL Import shared audience]** flusso di lavoro facendo direttamente clic sul pulsante **[!UICONTROL Show ImportShared Audience workflow]** nell&#39;origine dati.

Alcuni dati possono mancare quando si condivide un pubblico tramite il servizio core People o quando si importa un pubblico. Vengono trasferiti solo i record per i quali l’ID (&quot;ID visitatore&quot; o &quot;ID dichiarato&quot;) è stato riconciliato con la dimensione del profilo. Gli ID dei segmenti del servizio core People che non sono riconosciuti da Adobe Campaign non vengono importati.
