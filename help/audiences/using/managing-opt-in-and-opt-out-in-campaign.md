---
title: Gestione di consenso e rinuncia in Campaign
description: Comprendi come il consenso e la rinuncia vengono gestiti in Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: understanding-opt-in-and-opt-out-processes
feature: Audiences
role: User
level: Intermediate
exl-id: 4aeb90c5-f5b5-4cfe-93fb-2fd01fb8d70e
source-git-commit: 8be43668d1a4610c3388ad27e493a689925dc88c
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 8%

---

# Gestione di consenso e rinuncia in Campaign{#managing-opt-in-and-opt-out-in-campaign}

## Gestione del consenso e del diniego da un profilo {#managing-opt-in-and-opt-out-from-a-profile}

Un operatore può acconsentire o rinunciare agli utenti direttamente dalla scheda del profilo **[!UICONTROL General]**.

Nella sezione **[!UICONTROL No longer contact (on denylist)]**, le caselle di controllo selezionate corrispondono ai canali da cui l&#39;utente ha scelto di rinunciare. Seleziona i canali in base alle esigenze dell’utente.

![](assets/optin_landingpage_3.png)

## Impostazione delle pagine di destinazione di consenso e rinuncia {#setting-up-opt-in-and-opt-out-landing-pages}

Per consentire agli utenti di fornire il consenso o la rinuncia, è necessario creare e pubblicare una pagina di destinazione **[!UICONTROL Profile acquisition]**. Potranno quindi selezionare i canali in base alle loro esigenze. A tale scopo, segui la procedura indicata di seguito.

Puoi anche impostare una pagina di destinazione **[!UICONTROL Denylist]** che consentirà agli utenti di rinunciare a tutte le consegne. Per ulteriori informazioni, consulta [Impostazione di una pagina di destinazione per rifiutare tutte le consegne](#setting-up-a-landing-page-to-opt-out-from-all-deliveries).

>[!NOTE]
>
>Le pagine di destinazione possono essere utilizzate anche per abilitare l’abbonamento ai servizi. Per ulteriori informazioni, consulta [questa pagina](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service).

1. Crea una pagina di destinazione **[!UICONTROL Profile acquisition]** (vedi [questa sezione](../../channels/using/getting-started-with-landing-pages.md)).
1. Aggiungi una casella di controllo nel contenuto della pagina di destinazione per ciascun canale desiderato, quindi collegala al campo corrispondente dal database di Campaign.

   ![](assets/optin_landingpage_1.png)

1. Salva la pagina di destinazione e pubblicala.
1. Nella pagina di destinazione, le caselle di controllo sono già selezionate in base alla scheda del profilo **[!UICONTROL General]**. L’utente può selezionare o deselezionare i canali in base alle proprie esigenze e inviare il modulo.

   ![](assets/optin_landingpage_2.png)

1. Dopo l&#39;invio del modulo, la scheda del profilo **[!UICONTROL General]** viene aggiornata in base alla selezione dell&#39;utente.

   ![](assets/optin_landingpage_3.png)

### Impostazione di una pagina di destinazione per la rinuncia a tutte le consegne {#setting-up-a-landing-page-to-opt-out-from-all-deliveries}

Per consentire agli utenti di rinunciare a tutte le consegne, devi creare e pubblicare una pagina di destinazione **[!UICONTROL Denylist]**. Per ulteriori informazioni sulla creazione di pagine di destinazione, consulta [questa pagina](../../channels/using/getting-started-with-landing-pages.md).

Quando un utente fa clic sul collegamento della pagina di destinazione, l&#39;opzione **[!UICONTROL No longer contact (by any channel)]** nel profilo viene selezionata automaticamente.

![](assets/blocklisting_allchannels.png)
