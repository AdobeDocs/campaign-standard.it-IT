---
title: Configurazione dell’integrazione di Campaign e Target
description: Scopri come configurare l’integrazione di Adobe Target per iniziare a utilizzare contenuti dinamici in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-target
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: d382bfdd-418d-46c1-98dd-df8626f85cac
TQID: https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 5%

---

# Configurazione dell’integrazione di Campaign e Target{#configuring-the-campaign-target-integration}

L’integrazione tra Adobe Campaign e Adobe Target ti consente di inserire contenuto dinamico nella consegna.

Per utilizzare le funzionalità di integrazione con Adobe Campaign è innanzitutto necessaria una configurazione, che deve essere gestita dall’amministratore funzionale.

Per questa procedura sono necessari i seguenti elementi:

* Un tenant Adobe Experience Cloud
* Un tenant Adobe Target
* Un rawbox Adobe Target specificato per stabilire la connessione con Adobe Campaign

1. Dal menu avanzato, tramite il logo Adobe Campaign nell&#39;angolo in alto a sinistra, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
1. Per configurare le opzioni server e tenant per Adobe Target, compila i campi seguenti di conseguenza:

   * **[!UICONTROL TNT_TenantName]**: nome del tenant Adobe Target. Questo valore corrisponde al nome dell&#39;Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: server Adobe Target utilizzato per l&#39;integrazione. Questa opzione è già fornita per impostazione predefinita. Questo valore corrisponde all&#39;Adobe Target **[!UICONTROL Server Domain]**, seguito dal valore **/m2**. Ad esempio: **tt.omtrdc.net/m2**.

   ![](assets/tar_options.png)

Ora gli utenti possono aggiungere immagini dinamiche in una consegna con Adobe Target.
