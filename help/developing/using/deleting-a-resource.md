---
title: Eliminazione di una risorsa
description: Scopri come eliminare una risorsa
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# Eliminazione di una risorsa{#deleting-a-resource}

Per eliminare una risorsa, la risorsa in questione deve essere un **[!UICONTROL Draft]**. La risorsa è nello stato **[!UICONTROL Draft]** se:

* È stato appena creato e non è ancora stato pubblicato.
* Se è già stata pubblicata, la risorsa deve essere riscritta.

>[!IMPORTANT]
>
>La riprogettazione e l’eliminazione di una risorsa personalizzata sono operazioni sensibili che possono influire su altre risorse. Queste azioni devono essere eseguite solo da un utente esperto.

Per rielaborare ed eliminare una risorsa pubblicata:

1. Seleziona la risorsa da riprogettare.
1. Fai clic sul pulsante **[!UICONTROL Re-draft]** nella barra delle azioni.

   ![](assets/schema_extension_uc26.png)

1. Fai clic su **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Questa azione è definitiva: la tabella o le colonne del database della risorsa e i relativi dati verranno eliminati definitivamente quando la modifica viene pubblicata, il che può causare l’interruzione dei collegamenti da altre risorse personalizzate. Solo la definizione della risorsa rimarrà disponibile.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se si reprogetta un&#39;estensione della risorsa predefinita **Profili (profilo)**, è necessario riprogettare anche qualsiasi estensione **Profilo di test (seedMember)** definita. Per ulteriori informazioni sull&#39;estensione della risorsa profilo, consulta [questa sezione](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publish la risorsa. Per i passaggi più dettagliati, consulta [Pubblicazione di una risorsa personalizzata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   La risorsa passa quindi alla modalità **Bozza** e il suo stato di attivazione è **[!UICONTROL Inactive]**.

1. In modalità **[!UICONTROL List]**, controllare la risorsa da eliminare, quindi fare clic sull&#39;icona ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

La risorsa viene eliminata dal modello dati.

>[!NOTE]
>
>Se viene modificato o eliminato un campo di una risorsa personalizzata utilizzata all’interno di un evento, l’evento corrispondente viene automaticamente annullato. Vedi [Annullamento della pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
