---
title: Configurazione dell’integrazione Campaign-Target
description: Scopri come configurare l'integrazione di Adobe Target per iniziare a utilizzare il contenuto dinamico in Adobe Campaign.
page-status-flag: mai attivato
uuid: 0df5701c-dc26-4c30-9af9-ebf92815d90c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: con campagna e destinazione
discoiquuid: f7fb2084-dd6f-4aa2-940f-e48713146635
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configurazione dell’integrazione Campaign-Target{#configuring-the-campaign-target-integration}

L'integrazione tra Adobe Campaign e Adobe Target consente di inserire nella distribuzione contenuti dinamici.

Per utilizzare le funzionalità di integrazione con Adobe Target è innanzitutto necessario disporre di una configurazione in Adobe Campaign, che deve essere gestita dall'amministratore funzionale.

Per questa procedura sono necessari i seguenti elementi:

* Un tenant Adobe Experience Cloud
* Un tenant Adobe Target
* Una rawbox di Adobe Target specificata per stabilire la connessione con Adobe Campaign

1. Dal menu avanzato, utilizzando il logo Adobe Campaign nell'angolo in alto a sinistra, seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
1. Per configurare le opzioni server e tenant per Adobe Target, compila i seguenti campi di conseguenza:

   * **[!UICONTROL TNT_TenantName]**: nome del tenant di Adobe Target. Questo valore corrisponde al nome di Adobe Target **[!UICONTROL Client]**.
   * **[!UICONTROL TNT_EdgeServer]**: Server Adobe Target utilizzato per l'integrazione. Questa opzione è già disponibile per impostazione predefinita. Questo valore corrisponde ad Adobe Target **[!UICONTROL Server Domain]**, seguito dal valore **/m2** . Ad esempio: **tt.omtrdc.net/m2**.
   ![](assets/tar_options.png)

Gli utenti possono ora aggiungere immagini dinamiche in una distribuzione con Adobe Target.
