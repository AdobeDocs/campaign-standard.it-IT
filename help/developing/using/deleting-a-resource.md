---
solution: Campaign Standard
product: campaign
title: Eliminazione di una risorsa
description: 'Scopri come eliminare una risorsa '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Modello dati
role: Sviluppatore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 14%

---


# Eliminazione di una risorsa{#deleting-a-resource}

Per eliminare una risorsa, la risorsa in questione deve essere un **[!UICONTROL Draft]**. La risorsa è nello stato **[!UICONTROL Draft]** se:

* È stata appena creata e non è ancora stata pubblicata.
* Se è già stata pubblicata, la risorsa deve essere rielaborata.

>[!IMPORTANT]
>
>La riprogettazione e l’eliminazione di una risorsa personalizzata sono operazioni sensibili che possono avere un impatto su altre risorse. Queste azioni devono essere eseguite solo da un utente esperto.

Per ridisegnare ed eliminare una risorsa pubblicata:

1. Seleziona la risorsa da ridisegnare.
1. Fai clic sul pulsante **[!UICONTROL Re-draft]** nella barra delle azioni.

   ![](assets/schema_extension_uc26.png)

1. Fai clic su **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >La presente azione è definitiva: la tabella o le colonne del database della risorsa e i relativi dati verranno eliminati definitivamente al momento della pubblicazione della modifica, il che può causare l’interruzione dei collegamenti da altre risorse personalizzate. Sarà disponibile solo la definizione della risorsa.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se riprogetti un&#39;estensione della risorsa preconfigurata **Profili (profilo)** , devi anche ridisegnare qualsiasi estensione **Profilo di test (seedMember)** che potresti aver definito. Per ulteriori informazioni sull’estensione della risorsa profilo, consulta [questa sezione](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Pubblica la risorsa. Per passaggi più dettagliati, consulta [Pubblicazione di una risorsa personalizzata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   La risorsa passa quindi alla modalità **Bozza** e il suo stato di attivazione è **[!UICONTROL Inactive]**.

1. In modalità **[!UICONTROL List]** , seleziona la risorsa da eliminare, quindi fai clic sull’icona ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** .

   ![](assets/schema_extension_uc28.png)

La risorsa viene eliminata dal modello dati.

>[!NOTE]
>
>Se viene modificato o eliminato un campo di una risorsa personalizzata utilizzata all’interno di un evento, l’evento corrispondente viene automaticamente annullato. Consulta [Annullamento della pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
