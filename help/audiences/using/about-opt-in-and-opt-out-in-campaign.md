---
title: Informazioni su consenso e rinuncia in Campaign
description: La rinuncia fa sì che un profilo non rientri più nel target di una consegna o di consegne da un canale specifico.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Beginner
exl-id: ccb35aeb-2b32-4444-969b-50021111a0d6
TQID: https://experienceleague.adobe.com/9fzQiPrBRAFlTxX5EKo-Qvph3nYZYoA29kMrm6cXVLs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 10%

---

# Informazioni su consenso e rinuncia in Campaign{#about-opt-in-and-opt-out-in-campaign}

La rinuncia fa sì che un profilo non rientri più nel target di una consegna o di consegne da un canale specifico.

Per consentire ai profili di dare il consenso o la rinuncia, devi creare una pagina di destinazione dedicata. Per ulteriori informazioni, consulta [Impostazione delle pagine di destinazione di consenso e rinuncia](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

I profili possono anche essere inclusi o esclusi manualmente da un operatore. Per ulteriori informazioni, consulta [Gestione del consenso e della rinuncia da un profilo](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

I profili di rinuncia vengono esclusi automaticamente durante l’analisi della consegna per velocizzare le consegne (il tasso di errore ha un effetto significativo sulla velocità di consegna).

>[!NOTE]
>
>La rinuncia si applica a **Profili**, anziché alla quarantena collegata a un **indirizzo e-mail** o **numero di telefono**. La rinuncia a un profilo escluderà dalle consegne tutti gli indirizzi ad esso collegati. Tuttavia, se un utente dispone di due profili nel database, questo sarà ancora oggetto di consegne in quanto solo uno dei suoi profili viene escluso. Per assicurarti che tutti i loro indirizzi siano esclusi, aggiungili agli indirizzi in quarantena. Per ulteriori informazioni, consulta [questa pagina](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

Per ulteriori informazioni sugli abbonamenti ai servizi, consulta [questa pagina](../../audiences/using/about-subscriptions.md).
