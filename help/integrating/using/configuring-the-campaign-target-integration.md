---
title: Configurazione dell’integrazione di Campaign e Target
description: Scopri come configurare l’integrazione di Adobe Target per iniziare a utilizzare contenuti dinamici in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 4%

---

# Configurazione dell’integrazione di Campaign e Target{#configuring-the-campaign-target-integration}

L’integrazione tra Adobe Campaign e Adobe Target ti consente di inserire contenuto dinamico nella consegna.

Per utilizzare le funzionalità di integrazione con Adobe Campaign Adobe Target è innanzitutto necessaria una configurazione, che deve essere gestita dall’amministratore funzionale.

Per questa procedura sono necessari i seguenti elementi:

* Un tenant Adobe Experience Cloud
* Un tenant Adobe Target
* Un rawbox Adobe Target specificato per stabilire la connessione con Adobe Campaign

1. Dal menu avanzato, tramite il logo Adobe Campaign in alto a sinistra, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Per configurare le opzioni server e tenant per Adobe Target, compila i campi seguenti di conseguenza:

   * **[!UICONTROL TNT_TenantName]**: nome del tenant Adobe Target. Questo valore corrisponde al nome dell’Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: server Adobe Target utilizzato per l’integrazione. Questa opzione è già fornita per impostazione predefinita. Questo valore corrisponde all’Adobe Target **[!UICONTROL Server Domain]**, seguito da **/m2** valore. Ad esempio: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Ora gli utenti possono aggiungere immagini dinamiche in una consegna con Adobe Target.
