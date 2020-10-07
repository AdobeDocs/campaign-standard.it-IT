---
title: Gestione del consenso e del diniego in Campaign
description: Comprendere in che modo le opzioni di opt-in e opt-out vengono gestite in  Adobe Campaign.
page-status-flag: never-activated
uuid: aa1801ec-562b-420e-8d79-c07d066b7b1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
discoiquuid: 6b5680f2-bba9-453e-a0d5-8ca69dd02001
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# Gestione del consenso e del diniego in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gestione del consenso e del rifiuto da un profilo {#managing-opt-in-and-opt-out-from-a-profile}

Gli utenti possono essere ammessi o disabilitati da un operatore direttamente dalla **[!UICONTROL General]** scheda del profilo.

Nella **[!UICONTROL No longer contact (on denylist)]** sezione, le caselle selezionate corrispondono ai canali da cui l&#39;utente ha scelto di rifiutare. Selezionate i canali in base alle esigenze dell&#39;utente.

![](assets/optin_landingpage_3.png)

## Impostazione delle pagine di destinazione di consenso e rinuncia {#setting-up-opt-in-and-opt-out-landing-pages}

Per consentire agli utenti di scegliere se aderire o rifiutare, dovete creare e pubblicare una pagina di **[!UICONTROL Profile acquisition]** destinazione. Essi potranno quindi selezionare i canali in base alle loro esigenze. Per farlo, segui la procedura indicata di seguito.

Potete anche impostare una **[!UICONTROL Denylist]** pagina di destinazione che consenta agli utenti di rifiutare tutte le consegne. Per ulteriori informazioni, vedere [Impostazione di una pagina di destinazione per rifiutare tutte le consegne](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Le pagine di destinazione possono essere utilizzate anche per abilitare l&#39;iscrizione ai servizi. Per ulteriori informazioni, consulta [questa pagina](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Creare una **[!UICONTROL Profile acquisition]** pagina di destinazione (vedere [questa sezione](../../channels/using/getting-started-with-landing-pages.md)).
1. Aggiungi una casella di controllo nel contenuto della pagina di destinazione per ciascun canale desiderato, quindi collegala al campo corrispondente dal database Campaign.

   ![](assets/optin_landingpage_1.png)

1. Salvate la pagina di destinazione e pubblicatela.
1. Nella pagina di destinazione, le caselle di controllo sono già selezionate in base alla **[!UICONTROL General]** scheda del profilo. L&#39;utente può selezionare o deselezionare i canali in base alle proprie esigenze e inviare il modulo.

   ![](assets/optin_landingpage_2.png)

1. Una volta inviato il modulo, la **[!UICONTROL General]** scheda del profilo viene aggiornata in base alla selezione dell&#39;utente.

   ![](assets/optin_landingpage_3.png)

### Impostazione di una pagina di destinazione per rifiutare tutte le consegne {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Per consentire agli utenti di rifiutare tutte le consegne, dovete creare e pubblicare una pagina di **[!UICONTROL Denylist]** destinazione. Per ulteriori informazioni sulla creazione delle pagine di destinazione, consulta [questa pagina](../../channels/using/getting-started-with-landing-pages.md).

Quando un utente fa clic sul collegamento della pagina di destinazione, l&#39; **[!UICONTROL No longer contact (by any channel)]** opzione nel profilo viene automaticamente selezionata.

![](assets/blocklisting_allchannels.png)

