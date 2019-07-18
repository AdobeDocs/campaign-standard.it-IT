---
title: Risoluzione dei problemi
seo-title: Risoluzione dei problemi
description: Risoluzione dei problemi
seo-description: Scoprite come risolvere i problemi durante la condivisione delle risorse.
page-status-flag: never-activated
uuid: 1 c 764 dd 8-e 09 f -4 e 8 e -9 ccd -88 ab 3 d 714284
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c 28 e 1 d 90-8074-4127-a 6 fc-ed 39 d 69 cdb 19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Troubleshooting{#troubleshooting}

Potrebbero verificarsi errori durante l'utilizzo dell'integrazione con Audience Manager o con il servizio di base Persone.

In questo caso, accertatevi che i seguenti elementi siano correttamente configurati:

* **Account esterni**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. I server S 3 indicati dovrebbero essere stati configurati durante il provisioning.

   * **[!UICONTROL importSharedAudience]**: Account S 3 dedicato all'importazione di audience.
   * **[!UICONTROL exportSharedAudience]**: Account S 3 dedicato all'esportazione di audience.

* **Origini dati condivise**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** è utilizzato quando sono definite più origini dati. La priorità determina quale sorgente dati verrà utilizzata per corrispondere all'alias ricevuto nell'ordine definito. **[!UICONTROL Priority]** è necessario solo per l'implementazione Triggers.

   Verificate che la chiave di riconciliazione sia corretta. È il valore crittografato/crittografato di questo campo utilizzato per esportare e importare audience.

   Nel caso di hash o cifratura dell'ID dichiarato, controllate che gli stessi parametri/algoritmi di cifratura siano utilizzati nel sito Web.

   È supportato un solo algoritmo di cifratura: AES in modalità CBC con una dimensione chiave pari a 128, 192 o 256 bit, con la spaziatura PKCS.

   Se l'algoritmo di cifratura AES è selezionato, i seguenti campi aggiuntivi devono essere impostati correttamente:

   * **Chiave** di crittografia per AES
   * **Cifratura IV** (vettoriale inizializzazione) per AES
   * **Canale** (e-mail/SMS/Altro): Questo campo consente di decrittografare direttamente indirizzi e-mail e numeri SMS. Make sure that the reconciliation key matches the setting of the **Channel** field. Se selezionate "Altro", questa decrittazione specifica non si verifica e la chiave di riconciliazione sarà utilizzata per riconciliare i dati.
   L'audience Experience Cloud potrebbe non essere condivisa perché il flusso di lavoro tecnico è stato interrotto o messo in pausa. Access the **[!UICONTROL Import shared audience]** workflow by clicking directly the **[!UICONTROL Show ImportShared Audience workflow]** option in your Data source.

Potrebbe verificarsi la mancanza di alcuni dati durante la condivisione di un'audience tramite il servizio di base Persone o durante l'importazione di un'audience. Vengono trasferiti solo i record per i quali l'ID ('Visitor ID'o'Dichiarato ID ') è stato in grado di riconciliare con la dimensione del profilo. Gli ID dai segmenti di servizio di base Persone non riconosciuti da Adobe Campaign non vengono importati.
