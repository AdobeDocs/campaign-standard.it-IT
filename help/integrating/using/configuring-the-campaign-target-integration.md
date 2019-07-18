---
title: Configurazione dell'integrazione con Campaign-Target
seo-title: Configurazione dell'integrazione con Campaign-Target
description: Configurazione dell'integrazione con Campaign-Target
seo-description: Scopri come configurare l'integrazione di Adobe Target per iniziare a utilizzare il contenuto dinamico in Adobe Campaign.
page-status-flag: never-activated
uuid: 0 df 5701 c-dc 26-4 c 30-9 af 9-ebf 92815 d 90 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-target
discoiquuid: f 7 fb 2084-dd 6 f -4 aa 2-940 f-e 48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Configuring the Campaign-Target integration{#configuring-the-campaign-target-integration}

L'integrazione tra Adobe Campaign e Adobe Target consente di inserire contenuto dinamico nella distribuzione.

In Adobe Campaign è necessario innanzi tutto una configurazione per utilizzare le funzionalità di integrazione con Adobe Target e deve essere gestito dall'amministratore funzionale.

Per questa procedura sono necessari i seguenti elementi:

* Un tenant Adobe Experience Cloud
* Un tenant di Adobe Target
* Una rawbox di Adobe Target specificata per stabilire la connessione con Adobe Campaign

1. From the advanced menu, via the Adobe Campaign logo in the top left corner, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Per configurare il server e le opzioni tenant per Adobe Target, compila i campi seguenti:

   * **[!UICONTROL TNT_TenantName]**: del tenant di Adobe Target. This value corresponds to the name of the Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Server Adobe Target utilizzato per l'integrazione. Questa opzione è già disponibile per impostazione predefinita. This value corresponds to the Adobe Target **[!UICONTROL Server Domain]**, followed by the **/m2** value. For example: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Gli utenti possono ora aggiungere immagini dinamiche in una consegna con Adobe Target.
