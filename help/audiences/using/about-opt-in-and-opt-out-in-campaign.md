---
title: Informazioni sul consenso e diniego in Campaign
description: Il rifiuto comporta l'assenza del targeting del profilo per consegna o per consegna da un canale specifico.
page-status-flag: never-activated
uuid: 501d9485-976b-4de7-b242-6886f2814c6c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 2f26ec22-0809-4541-b2a1-e84ff868ba6e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 5%

---


# Informazioni sul consenso e diniego in Campaign{#about-opt-in-and-opt-out-in-campaign}

Il rifiuto comporta l&#39;assenza del targeting del profilo per consegna o per consegna da un canale specifico.

Per offrire ai profili la possibilità di scegliere se aderire o rifiutare, dovete creare una pagina di destinazione dedicata. Per ulteriori informazioni, vedere [Impostazione delle pagine](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)di destinazione di consenso e di rifiuto.

I profili possono anche essere scelti manualmente da un operatore. Per ulteriori informazioni, fare riferimento a [Gestione dell&#39;opt-in e dell&#39;opt-out da un profilo](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

I profili di rifiuto vengono automaticamente esclusi durante l&#39;analisi della consegna per accelerare le consegne (il tasso di errore ha un effetto significativo sulla velocità di consegna).

>[!NOTE]
>
>Il rifiuto si applica ai **profili**, invece della quarantena collegata a un indirizzo **** e-mail o a un numero **di** telefono. L&#39;esclusione di un profilo escluderà quindi dalle consegne tutti gli indirizzi ad esso collegati. Se un utente ha due profili nel database, sarà comunque preso di mira dalle consegne, in quanto solo uno dei suoi profili è l&#39;opzione di rifiuto. Per assicurarsi che tutti i suoi indirizzi siano esclusi, aggiungeteli agli indirizzi delle quarantena. For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Per ulteriori informazioni sulle iscrizioni ai servizi, consultare [questa pagina](../../audiences/using/about-subscriptions.md).
