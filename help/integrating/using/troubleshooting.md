---
title: Risoluzione dei problemi
description: Scoprite come risolvere i problemi durante la condivisione delle risorse.
page-status-flag: mai attivato
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: lavoro con campagna e pubblico-manager o persone-servizio di base
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Risoluzione dei problemi{#troubleshooting}

Durante l'integrazione con Audience Manager o con il servizio di base Persone possono verificarsi degli errori.

In questo caso, accertatevi che i seguenti elementi siano configurati correttamente:

* **Account esterni**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, accertatevi che i seguenti account S3 esterni siano configurati correttamente. I server S3 menzionati dovrebbero essere stati configurati durante il provisioning.

   * **[!UICONTROL importSharedAudience]**: Account S3 dedicato all'importazione di audience.
   * **[!UICONTROL exportSharedAudience]**: Account S3 dedicato all'esportazione dei tipi di pubblico.

* **Origini dati condivise**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, verificare che l'origine dati condivisa sia impostata correttamente.

   **[!UICONTROL Priority]** viene utilizzato quando sono definite più origini dati. Priorità decide quale origine dati verrà utilizzata per corrispondere all'alias ricevuto nell'ordine definito. **[!UICONTROL Priority]** è necessaria solo per l'implementazione Triggers.

   Verificare che la chiave di riconciliazione sia corretta. È il valore crittografato o con hash di questo campo utilizzato per esportare e importare audience.

   In caso di hash o cifratura dell'ID dichiarato, verifica che gli stessi parametri/algoritmi di cifratura siano utilizzati sul tuo sito Web.

   È supportato un solo algoritmo di cifratura: AES in modalità CBC con una dimensione chiave di 128, 192 o 256 bit, con la spaziatura PKCS.

   Se è selezionato l'algoritmo di cifratura AES, è necessario impostare correttamente i seguenti campi aggiuntivi:

   * **Chiave** di crittografia per AES
   * **Crittografia IV** (vettore di inizializzazione) per AES
   * **Canale** (E-mail/SMS/Altro): Questo campo consente di decrittografare direttamente indirizzi e-mail e numeri SMS. Assicurarsi che la chiave di riconciliazione corrisponda all'impostazione del campo **Canale** . Se si seleziona "Altro", questa specifica decrittazione non verrà eseguita e la chiave di riconciliazione verrà utilizzata per riconciliare i dati.
   Il pubblico di Experience Cloud potrebbe non essere condiviso perché il flusso di lavoro tecnico è stato interrotto o messo in pausa. Per accedere al **[!UICONTROL Import shared audience]** flusso di lavoro, fai clic direttamente sull' **[!UICONTROL Show ImportShared Audience workflow]** opzione nell'origine dati.

Può accadere che alcuni dati manchino durante la condivisione di un'audience tramite il servizio di base Persone o durante l'importazione di un'audience. Vengono trasferiti solo i record per i quali l'ID ('ID visitatore' o 'ID dichiarato') è stato riconciliato con la dimensione del profilo. Gli ID dai segmenti del servizio di base Persone non riconosciuti da Adobe Campaign non vengono importati.
