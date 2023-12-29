---
title: Creazione di profili
description: Scopri come creare profili e raccogliere dati sui contatti tramite API, funzionalità di importazione, acquisizione online, aggiornamenti automatici o manuali.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Beginner
exl-id: 827df9f6-070c-466a-890c-e363de6b129b
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 84%

---

# Creazione di profili{#creating-profiles}

In Adobe Campaign, utilizzi profili per impostazione predefinita per definire la destinazione principale dei messaggi.

>[!NOTE]
>
>Puoi creare profili anche tramite l’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/creating-profiles-api.md).

![](assets/do-not-localize/how-to-video.png) [Scopri come importare profili utilizzando un flusso di lavoro nel video](#video)

Per creare o aggiornare un profilo in Campaign, puoi:

* importare un elenco di profili da un file tramite un [flusso di lavoro](../../automating/using/creating-import-workflow-templates.md);
* raccogliere dati online tramite [pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md);
* creare in massa tramite [API REST](../../api/using/get-started-apis.md);
* sincronizzare profili da [Microsoft Dynamics](../../integrating/using/d365-acs-get-started.md);
* Immetti i dati utilizzando l’interfaccia utente, come spiegato di seguito

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

     >[!NOTE]
     > I numeri di telefono cellulare devono essere sempre in formato internazionale (`+<country><number>`) nella tabella dei profili.

   * La categoria **[!UICONTROL No longer contact]** viene aggiornata dopo che il profilo ha annullato l’abbonamento a un canale.
   * La categoria **[!UICONTROL Address]** contiene l’indirizzo postale che deve essere compilato insieme all’opzione **[!UICONTROL Address specified]** per inviare [direct mailing](../../channels/using/about-direct-mail.md) a questo profilo. Se l’opzione **[!UICONTROL Address specified]** non è selezionata, questo profilo viene escluso da tutte le consegne di direct mailing.
   * Il **[!UICONTROL Access authorization]** categoria indica le unità organizzative del profilo a cui [gestire le autorizzazioni](../../administration/using/about-access-management.md). Per aggiungere i campi organizzativi ai profili, consulta la sezione [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).
   * La categoria **[!UICONTROL Traceability]** viene aggiornata automaticamente con le informazioni relative all’utente che ha creato o modificato il profilo.

1. Fai clic su **[!UICONTROL Create]** per salvare il profilo.

Il profilo viene ora visualizzato nell’elenco.

>[!NOTE]
>Utilizza il campo della lingua preferita per selezionare la lingua durante l’invio di messaggi multilingue. Per ulteriori informazioni sui messaggi multilingue, [consulta questa pagina](../../channels/using/creating-a-multilingual-email.md).

## Video tutorial {#video}

Questo video mostra come importare i profili con un flusso di lavoro.

>[!VIDEO](https://video.tv.adobe.com/v/24993?quality=12)

Sono disponibili altri video dimostrativi sui Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
