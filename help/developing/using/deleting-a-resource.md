---
title: Eliminazione di una risorsa
description: 'Scopri come eliminare una risorsa '
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

Per eliminare una risorsa, la risorsa in questione deve essere **[!UICONTROL Draft]**. La risorsa è in **[!UICONTROL Draft]** se:

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
   >Se riprogetti un&#39;estensione di **Profili (profilo)** risorsa, devi anche ridisegnare qualsiasi **Profilo di prova (seedMember)** estensione definita. Per ulteriori informazioni sull’estensione della risorsa profilo, consulta [questa sezione](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Pubblica la risorsa. Per passaggi più dettagliati, consulta [Pubblicazione di una risorsa personalizzata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   La risorsa viene quindi inserita in **Bozza** e il relativo stato di attivazione è **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** , controlla la risorsa da eliminare e fai clic sul pulsante ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** icona.

   ![](assets/schema_extension_uc28.png)

La risorsa viene eliminata dal modello dati.

>[!NOTE]
>
>Se viene modificato o eliminato un campo di una risorsa personalizzata utilizzata all’interno di un evento, l’evento corrispondente viene automaticamente annullato. Vedi [Annullamento della pubblicazione di un evento sulle transazioni](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
