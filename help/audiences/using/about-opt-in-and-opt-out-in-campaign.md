---
title: Informazioni su consenso e rinuncia in Campaign
description: La rinuncia comporta la mancata destinazione di un profilo da parte di una consegna o di consegne da un canale specifico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---

# Informazioni su consenso e rinuncia in Campaign{#about-opt-in-and-opt-out-in-campaign}

La rinuncia comporta la mancata destinazione di un profilo da parte di una consegna o di consegne da un canale specifico.

Per consentire ai profili di dare il consenso o la rinuncia, devi creare una pagina di destinazione dedicata. Per ulteriori informazioni, consulta [Impostazione delle pagine di destinazione di consenso e rinuncia](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

Un operatore può anche effettuare il consenso o la rinuncia manuale ai profili. Per ulteriori informazioni, consulta [Gestione dell&#39;opt-in e della rinuncia da un profilo](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

I profili di rinuncia vengono automaticamente esclusi durante l’analisi della consegna per velocizzare le consegne (il tasso di errore ha un effetto significativo sulla velocità di consegna).

>[!NOTE]
>
>La rinuncia si applica a **Profili**, invece della quarantena collegata a un **indirizzo e-mail** o a **numero di telefono**. La rinuncia a un profilo esclude quindi dalle consegne tutti gli indirizzi ad esso collegati. Tuttavia, se un utente ha due profili nel database, sarà comunque oggetto di targeting per le consegne in quanto viene escluso solo uno dei profili. Per escludere tutti i suoi indirizzi, aggiungili agli indirizzi messi in quarantena. Per ulteriori informazioni, consulta [questa pagina](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Per ulteriori informazioni sugli abbonamenti ai servizi, consulta [questa pagina](../../audiences/using/about-subscriptions.md).
