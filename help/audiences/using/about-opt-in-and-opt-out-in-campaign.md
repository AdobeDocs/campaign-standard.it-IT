---
title: Informazioni sulla rinuncia e la rinuncia in Campaign
seo-title: Informazioni sulla rinuncia e la rinuncia in Campaign
description: Informazioni sulla rinuncia e la rinuncia in Campaign
seo-description: La rinuncia (blacklist) restituisce un profilo non più destinato ad alcun tipo di consegna o da consegne di un canale specifico.
page-status-flag: never-activated
uuid: 501 d 9485-976 b -4 de 7-b 242-6886 f 2814 c 6 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audience
content-type: riferimento
topic-tags: understanding-opt-in-and-opt-out
discoiquuid: 2 f 26 ec 22-0809-4541-b 2 a 1-e 84 ff 868 ba 6 e
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About opt-in and opt-out in Campaign{#about-opt-in-and-opt-out-in-campaign}

La rinuncia (blacklist) restituisce un profilo non più destinato ad alcun tipo di consegna o da consegne di un canale specifico.

Per concedere ai profili la capacità di rifiutare o rifiutare, dovete creare una pagina di destinazione dedicata. For more on this, refer to [Setting up opt-in and opt-out landing pages](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages).

I profili possono anche essere attivati o disattivati manualmente da un operatore. For more on this, refer to [Managing opt-in and opt-out from a profile](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#managing-opt-in-and-opt-out-from-a-profile).

I profili di rinuncia vengono esclusi automaticamente durante l'analisi della distribuzione per velocizzare le consegne (il tasso di errore ha un effetto significativo sulla velocità di consegna).

>[!NOTE]
>
>Opt-out applies to **Profiles**, as opposed to quarantine which is linked to an **email address** or **phone number**. La scelta di un profilo, pertanto, escluderà dall'invio tutti gli indirizzi associati. Se un utente dispone di due profili nel database, sarà comunque indirizzato dalle consegne in quanto la rinuncia di uno solo dei profili è consentita. Per essere certi che tutti i suoi indirizzi siano esclusi, aggiungerli alle relative posizioni. For more on this, refer to [this page](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).

For more on services subscriptions, refer to [this page](../../audiences/using/about-subscriptions.md).
