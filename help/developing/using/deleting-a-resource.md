---
solution: Campaign Standard
product: campaign
title: Eliminazione di una risorsa
description: 'Scopri come eliminare una risorsa '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: a51943e4da04f5d19aaecdfcf956f5c4f3d804c8
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---


# Eliminazione di una risorsa{#deleting-a-resource}

Per eliminare una risorsa, la risorsa in questione deve essere un **[!UICONTROL Draft]**. La risorsa è nello stato **[!UICONTROL Draft]** se:

* È appena stato creato e non è ancora stato pubblicato.
* Se è già stata pubblicata, la risorsa deve essere rielaborata.

>[!IMPORTANT]
>
>La ridefinizione e l&#39;eliminazione di una risorsa personalizzata sono operazioni sensibili che possono avere un impatto su altre risorse. Queste azioni devono essere eseguite solo da un utente esperto.

Per ridisegnare ed eliminare una risorsa pubblicata:

1. Selezionate la risorsa da ridisegnare.
1. Fai clic sul pulsante **[!UICONTROL Re-draft]** nella barra delle azioni.

   ![](assets/schema_extension_uc26.png)

1. Fai clic su **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Il presente ricorso è definitivo: la tabella o le colonne del database della risorsa e i relativi dati verranno eliminati definitivamente al momento della pubblicazione della modifica, con possibili collegamenti interrotti da altre risorse personalizzate. Rimarrà disponibile solo la definizione di risorsa.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se si riprogetta un&#39;estensione della risorsa **Profili (profilo)** out-of-the-box, è inoltre necessario ridisegnare qualsiasi estensione **Test profile (seedMember)** definita. Per ulteriori informazioni sull&#39;estensione della risorsa del profilo, vedere [questa sezione](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Pubblicate la risorsa. Per ulteriori dettagli, vedere [Pubblicazione di una risorsa personalizzata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   La risorsa quindi entra in modalità **Bozza** e il suo stato di attivazione è **[!UICONTROL Inactive]**.

1. In modalità **[!UICONTROL List]**, selezionare la risorsa da eliminare, quindi fare clic sull&#39;icona ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

La risorsa viene eliminata dal modello dati.

>[!NOTE]
>
>Se viene modificato o eliminato un campo di una risorsa personalizzata utilizzata all’interno di un evento, l’evento corrispondente viene automaticamente annullato. Vedere [Annullamento della pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
