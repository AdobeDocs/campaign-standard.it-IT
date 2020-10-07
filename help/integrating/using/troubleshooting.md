---
title: Risoluzione dei problemi
description: Scoprite come risolvere i problemi durante la condivisione delle risorse.
page-status-flag: never-activated
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 1%

---


# Risoluzione dei problemi{#troubleshooting}

È possibile che si verifichino degli errori durante l&#39;utilizzo dell&#39;integrazione con  servizio di base Audience Manager o Persone.

In questo caso, accertatevi che i seguenti elementi siano configurati correttamente:

* **Account esterni**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, accertatevi che i seguenti account S3 esterni siano configurati correttamente. I server S3 menzionati dovrebbero essere stati configurati durante il provisioning.

   * **[!UICONTROL importSharedAudience]**: Account S3 dedicato all&#39;importazione di audience.
   * **[!UICONTROL exportSharedAudience]**: Account S3 dedicato all&#39;esportazione dei tipi di pubblico.

* **Origini dati condivise**

   In **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, verificare che l&#39;origine dati condivisa sia impostata correttamente.

   **[!UICONTROL Priority]** viene utilizzato quando sono definite più origini dati. Priorità decide quale origine dati verrà utilizzata per corrispondere all&#39;alias ricevuto nell&#39;ordine definito. **[!UICONTROL Priority]** è necessaria solo per l&#39;implementazione Triggers.

   Verificare che la chiave di riconciliazione sia corretta. È il valore crittografato o con hash di questo campo utilizzato per esportare e importare i tipi di pubblico.

   In caso di hash o cifratura dell&#39;ID dichiarato, verifica che gli stessi parametri/algoritmi di cifratura siano utilizzati sul tuo sito Web.

   È supportato un solo algoritmo di cifratura: AES in modalità CBC con una dimensione chiave di 128, 192 o 256 bit, con la spaziatura PKCS.

   Se è selezionato l&#39;algoritmo di cifratura AES, è necessario impostare correttamente i seguenti campi aggiuntivi:

   * **Chiave** di crittografia per AES
   * **Crittografia IV** (vettore di inizializzazione) per AES
   * **Canale** (E-mail/SMS/Altro): Questo campo consente di decrittografare direttamente indirizzi e-mail e numeri SMS. Assicurarsi che la chiave di riconciliazione corrisponda all&#39;impostazione del campo **Canale** . Se si seleziona &quot;Altro&quot;, questa specifica decrittazione non verrà eseguita e la chiave di riconciliazione verrà utilizzata per riconciliare i dati.

    pubblico di Experienci Cloud potrebbe non essere condiviso perché il flusso di lavoro tecnico è stato interrotto o messo in pausa. Per accedere al **[!UICONTROL Import shared audience]** flusso di lavoro, fai clic direttamente sull&#39; **[!UICONTROL Show ImportShared Audience workflow]** opzione nell&#39;origine dati.

Può accadere che alcuni dati manchino durante la condivisione di un&#39;audience tramite il servizio di base Persone o durante l&#39;importazione di un&#39;audience. Vengono trasferiti solo i record per i quali l&#39;ID (&#39;ID visitatore&#39; o &#39;ID dichiarato&#39;) è stato riconciliato con la dimensione del profilo. Gli ID dai segmenti del servizio di base Persone che non sono riconosciuti da  Adobe Campaign non vengono importati.
