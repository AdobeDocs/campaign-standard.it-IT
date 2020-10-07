---
title: Creazione di profili
description: Scopri come creare profili e raccogliere dati sui contatti tramite API, funzionalità di importazione, acquisizione online, aggiornamenti automatici o manuali.
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 97%

---


# Creazione di profili{#creating-profiles}

In Adobe Campaign, utilizzi profili per impostazione predefinita per definire la destinazione principale dei messaggi.

>[!NOTE]
>
>Puoi creare profili anche tramite l’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/creating-profiles.md).

Per creare o aggiornare un profilo in Campaign, puoi:

* importare un elenco di profili da un file tramite un [flusso di lavoro](../../automating/using/creating-import-workflow-templates.md);
* raccogliere dati online tramite [pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md);
* creare in massa tramite [API REST](../../api/using/get-started-apis.md);
* sincronizzare profili da [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md);
* inserire dati grazie alle schermate dell’interfaccia grafica, come spiegato di seguito.

Ad esempio, per creare un nuovo profilo direttamente dall’interfaccia utente, segui i passaggi qui sotto:

1. Dalla pagina Home di Adobe Campaign, fai clic sulla scheda **Customer Profiles** o su **Profiles** per accedere al relativo elenco.

   ![](assets/profile_creation_1.png)

1. Fai clic su **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Immetti i dati del profilo.

   ![](assets/profile_creation1.png)

   * Le informazioni di contatto, come nome, cognome, genere, data di nascita, foto, lingua preferita (per [e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)) consentono di personalizzare meglio le consegne.
   * Il **[!UICONTROL Time zone]** del profilo viene utilizzato per inviare consegne secondo il relativo fuso orario. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La categoria **[!UICONTROL Channels]**, che contiene l’indirizzo e-mail, il numero di telefono cellulare, le informazioni di rinuncia (opt-out), ti informa su quale canale puoi raggiungere il profilo.
   * La categoria **[!UICONTROL No longer contact]** viene aggiornata dopo che il profilo ha annullato l’abbonamento a un canale.
   * La categoria **[!UICONTROL Address]** contiene l’indirizzo postale che deve essere compilato insieme all’opzione **[!UICONTROL Address specified]** per inviare [direct mailing](../../channels/using/about-direct-mail.md) a questo profilo. Se l’opzione **[!UICONTROL Address specified]** non è selezionata, questo profilo viene escluso da tutte le consegne di direct mailing.
   * The **[!UICONTROL Access authorization]** category indicates the profile&#39;s organizational units to [manage permissions](../../administration/using/about-access-management.md). Per aggiungere i campi organizzativi ai profili, consulta la sezione [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).
   * La categoria **[!UICONTROL Traceability]** viene aggiornata automaticamente con le informazioni relative all’utente che ha creato o modificato il profilo.

1. Fai clic su **[!UICONTROL Create]** per salvare il profilo.

Il profilo viene ora visualizzato nell’elenco.

>[!NOTE]
>Utilizza il campo della lingua preferita per selezionare la lingua durante l’invio di messaggi multilingue. Per ulteriori informazioni sui messaggi multilingue, [consulta questa pagina](../../channels/using/creating-a-multilingual-email.md).

**Argomenti correlati:**

* Guida dettagliata [Informazioni sulle pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md)
* Video sull’[importazione di profili](https://video.tv.adobe.com/v/24993?captions=ita)
