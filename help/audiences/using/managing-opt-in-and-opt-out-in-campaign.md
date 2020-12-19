---
solution: Campaign Standard
product: campaign
title: Gestione del consenso e del diniego in Campaign
description: Comprendere in che modo le opzioni di opt-in e opt-out vengono gestite in  Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---


# Gestione del consenso e del diniego in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gestione del consenso e del rifiuto da un profilo {#managing-opt-in-and-opt-out-from-a-profile}

Gli utenti possono essere inclusi o disabilitati da un operatore direttamente dalla scheda **[!UICONTROL General]** del profilo.

Nella sezione **[!UICONTROL No longer contact (on denylist)]**, le caselle di controllo selezionate corrispondono ai canali da cui l&#39;utente ha scelto di rifiutare. Selezionate i canali in base alle esigenze dell&#39;utente.

![](assets/optin_landingpage_3.png)

## Impostazione delle pagine di destinazione di consenso e di rifiuto {#setting-up-opt-in-and-opt-out-landing-pages}

Per consentire agli utenti di scegliere se aderire o rifiutare, è necessario creare e pubblicare una pagina di destinazione **[!UICONTROL Profile acquisition]**. Essi potranno quindi selezionare i canali in base alle loro esigenze. Per farlo, segui la procedura indicata di seguito.

Potete anche impostare una pagina di destinazione **[!UICONTROL Denylist]** che consenta agli utenti di rifiutare tutte le consegne. Per ulteriori informazioni, vedere [Impostazione di una pagina di destinazione per rifiutare tutte le consegne](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Le pagine di destinazione possono essere utilizzate anche per abilitare l&#39;iscrizione ai servizi. Per ulteriori informazioni, consulta [questa pagina](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Creare una pagina di destinazione **[!UICONTROL Profile acquisition]** (vedere [questa sezione](../../channels/using/getting-started-with-landing-pages.md)).
1. Aggiungi una casella di controllo nel contenuto della pagina di destinazione per ciascun canale desiderato, quindi collegala al campo corrispondente dal database Campaign.

   ![](assets/optin_landingpage_1.png)

1. Salvate la pagina di destinazione e pubblicatela.
1. Nella pagina di destinazione, le caselle di controllo sono già selezionate in base alla scheda del profilo **[!UICONTROL General]**. L&#39;utente può selezionare o deselezionare i canali in base alle proprie esigenze e inviare il modulo.

   ![](assets/optin_landingpage_2.png)

1. Una volta inviato il modulo, la scheda del profilo **[!UICONTROL General]** viene aggiornata in base alla selezione dell&#39;utente.

   ![](assets/optin_landingpage_3.png)

### Impostazione di una pagina di destinazione per rifiutare tutte le consegne {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Per consentire agli utenti di rifiutare tutte le consegne, è necessario creare e pubblicare una pagina di destinazione **[!UICONTROL Denylist]**. Per ulteriori informazioni sulla creazione delle pagine di destinazione, vedere [questa pagina](../../channels/using/getting-started-with-landing-pages.md).

Quando un utente fa clic sul collegamento della pagina di destinazione, l&#39;opzione **[!UICONTROL No longer contact (by any channel)]** nel profilo viene automaticamente selezionata.

![](assets/blocklisting_allchannels.png)

