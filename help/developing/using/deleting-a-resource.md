---
title: Eliminazione di una risorsa
description: 'Scopri come eliminare una risorsa '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# Eliminazione di una risorsa{#deleting-a-resource}

Per eliminare una risorsa, la risorsa in questione deve essere una **[!UICONTROL Draft]**. La risorsa è nello**[!UICONTROL Draft]** stato se:

* È appena stato creato e non è ancora stato pubblicato.
* Se è già stata pubblicata, la risorsa deve essere rielaborata.

>[!CAUTION]
>
>La ridefinizione e l&#39;eliminazione di una risorsa personalizzata sono operazioni sensibili che possono avere un impatto su altre risorse. Queste azioni devono essere eseguite solo da un utente esperto.

Per ridisegnare ed eliminare una risorsa pubblicata:

1. Selezionate la risorsa da ridisegnare.
1. Fate clic sul **[!UICONTROL Re-draft]**pulsante nella barra delle azioni.

   ![](assets/schema_extension_uc26.png)

1. Clic **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Tale azione è definitiva: la tabella o le colonne del database della risorsa e i relativi dati verranno eliminati definitivamente al momento della pubblicazione della modifica, con possibili collegamenti interrotti da altre risorse personalizzate. Rimarrà disponibile solo la definizione di risorsa.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Se si riprogetta un&#39;estensione della risorsa **Profili out-of-the-box (profilo)** , è inoltre necessario ridisegnare qualsiasi estensione del profilo di **test (seedMember)** eventualmente definita. Per ulteriori informazioni sull&#39;estensione della risorsa del profilo, consulta [questa sezione](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Pubblicate la risorsa. Per ulteriori dettagli, consultate [Pubblicazione di una risorsa](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizzata.

   La risorsa passa quindi alla modalità **Bozza** e il suo stato di attivazione è **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** modalità selezionare la risorsa da eliminare, quindi fare clic sull’![](assets/delete_darkgrey-24px.png)icona **[!UICONTROL Delete element]** .

   ![](assets/schema_extension_uc28.png)

La risorsa viene eliminata dal modello dati.

>[!NOTE]
>
>Se un campo di una risorsa personalizzata utilizzata in un evento viene modificato o eliminato, l&#39;evento corrispondente viene automaticamente annullato. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

