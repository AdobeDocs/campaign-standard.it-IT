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
TQID: 'https://experienceleague.adobe.com/trfuEp6pEd2jFADsK6NMw6tx8ASi86ZFur56AjwnpWQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '184'
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
