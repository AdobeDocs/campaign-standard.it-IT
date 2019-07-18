---
title: Eliminazione di una risorsa
seo-title: Eliminazione di una risorsa
description: Eliminazione di una risorsa
seo-description: 'Come eliminare una risorsa '
page-status-flag: never-activated
uuid: 5 de 27589-6 fa 5-412 c -8 e 5 a-a 4976 de 05715
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: sviluppo
content-type: riferimento
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733 d -4 e 3 f -40 cd-b 959-56381 f 2 c 8 f 44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Deleting a resource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* È stato appena creato e non è ancora stato pubblicato.
* Se è già stato pubblicato, la risorsa deve essere rielaborata.

>[!CAUTION]
>
>La riprogettazione e l'eliminazione di una risorsa personalizzata sono operazioni sensibili che possono influenzare altre risorse. Queste azioni devono essere eseguite solo da un utente esperto.

Per riproporre ed eliminare una risorsa pubblicata:

1. Selezionate la risorsa da riproporre.
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >Questa azione è definitiva: la tabella o le colonne del database della risorsa verranno eliminate definitivamente quando la modifica viene pubblicata, il che può causare collegamenti interrotti da altre risorse personalizzate. Resta disponibile solo la definizione delle risorse.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >If you re-draft an extension of the out-of-the-box **Profiles (profile)** resource, you must also re-draft any **Test profile (seedMember)** extension you may have defined. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Pubblicate la risorsa. For more detailed steps, refer to [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** mode, check the resource to delete then click the ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** icon.

   ![](assets/schema_extension_uc28.png)

La risorsa viene eliminata dal modello dati.

>[!NOTE]
>
>Se un campo di una risorsa personalizzata utilizzato in un evento viene modificato o eliminato, l'evento corrispondente verrà automaticamente non pubblicato. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

