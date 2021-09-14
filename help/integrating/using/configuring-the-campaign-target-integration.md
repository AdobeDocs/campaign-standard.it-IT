---
title: Configurazione dell’integrazione di Campaign e Target
description: Scopri come configurare l’integrazione Adobe Target per iniziare a utilizzare il contenuto dinamico in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---

# Configurazione dell’integrazione di Campaign e Target{#configuring-the-campaign-target-integration}

L’integrazione tra Adobe Campaign e Adobe Target consente di inserire contenuto dinamico nella consegna.

Per utilizzare le funzionalità di integrazione con Adobe Target è innanzitutto necessaria una configurazione in Adobe Campaign e deve essere gestita dall’amministratore funzionale.

Per questa procedura sono necessari i seguenti elementi:

* Un tenant Adobe Experience Cloud
* Un tenant Adobe Target
* Una rawbox Adobe Target specificata per stabilire la connessione con Adobe Campaign

1. Dal menu avanzato, tramite il logo Adobe Campaign nell’angolo in alto a sinistra, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Per configurare le opzioni server e tenant per Adobe Target, compila i campi seguenti di conseguenza:

   * **[!UICONTROL TNT_TenantName]**: nome del tenant Adobe Target. Questo valore corrisponde al nome dell&#39;Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Server Adobe Target utilizzato per l’integrazione. Questa opzione è già fornita per impostazione predefinita. Questo valore corrisponde all&#39;Adobe Target **[!UICONTROL Server Domain]**, seguito dal valore **/m2**. Ad esempio: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Gli utenti possono ora aggiungere immagini dinamiche in una consegna con Adobe Target.
