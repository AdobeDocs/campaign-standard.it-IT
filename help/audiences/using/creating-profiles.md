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
TQID: https://experienceleague.adobe.com/STHpDRtsdjT7OMDg3aOtVHdzqLokzOxvM2PI0ho9WLA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 395
ht-degree: 84%

---

# Creazione di profili{#creating-profiles}

In Adobe Campaign, utilizzi profili per impostazione predefinita per definire la destinazione principale dei messaggi.

>[!NOTE]
>
>Puoi creare profili anche tramite l’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/creating-profiles-api.md).

![](assets/do-not-localize/how-to-video.png) [Scopri come importare i profili utilizzando un flusso di lavoro nel video](#video)

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
   * La categoria **[!UICONTROL Access authorization]** indica le unità organizzative del profilo per [gestire le autorizzazioni](../../administration/using/about-access-management.md). Per aggiungere i campi organizzativi ai profili, consulta la sezione [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).
   * La categoria **[!UICONTROL Traceability]** viene aggiornata automaticamente con le informazioni relative all’utente che ha creato o modificato il profilo.

1. Fai clic su **[!UICONTROL Create]** per salvare il profilo.

Il profilo viene ora visualizzato nell’elenco.

>[!NOTE]
>Utilizza il campo della lingua preferita per selezionare la lingua durante l’invio di messaggi multilingue. Per ulteriori informazioni sui messaggi multilingue, [consulta questa pagina](../../channels/using/creating-a-multilingual-email.md).

## Video tutorial {#video}

Questo video mostra come importare i profili con un flusso di lavoro.

>[!VIDEO](https://video.tv.adobe.com/v/329676?captions=ita&quality=12)

Ulteriori video dimostrativi di Campaign Standard sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
