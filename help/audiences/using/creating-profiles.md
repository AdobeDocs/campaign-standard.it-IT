---
title: Creazione di profili
description: Scopri come creare profili e raccogliere dati sui tuoi contatti utilizzando API, funzionalità di importazione, acquisizione online, aggiornamenti automatici o manuali.
page-status-flag: mai attivato
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profile
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creazione di profili{#creating-profiles}

In Adobe Campaign, i profili sono utilizzati per impostazione predefinita per definire la destinazione principale dei messaggi.

Per creare o aggiornare un profilo in Campaign, puoi:

* Importazione di un elenco di profili da un file tramite un [flusso di lavoro](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Raccolta di dati online tramite pagine di [destinazione](../../channels/using/about-landing-pages.md)
* Creazione in massa tramite API [REST](http://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)
* Sincronizzare i profili da [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* Inserire i dati utilizzando le schermate dell'interfaccia grafica, come illustrato di seguito

Ad esempio, per creare un nuovo profilo direttamente nell’interfaccia utente, effettuate le seguenti operazioni:

1. Dalla home page di Adobe Campaign, fai clic sulla scheda Profili **** cliente o sulla scheda **Profili** per accedere all'elenco dei profili.

   ![](assets/profile_creation_1.png)

1. Quindi fate clic **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Immettete i dati del profilo.

   ![](assets/profile_creation1.png)

   * Le informazioni di contatto, come nome, cognome, sesso, data di nascita, foto, lingua preferita (per le e-mail [](../../channels/using/creating-a-multilingual-email.md)multilingue) consentono di personalizzare meglio le consegne.
   * Il profilo **[!UICONTROL Time zone]** viene utilizzato per inviare le consegne al fuso orario del profilo. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La **[!UICONTROL Channels]** categoria, che contiene l'indirizzo e-mail, il numero di telefono cellulare, le informazioni di rifiuto, vi consente di sapere su quale canale il profilo è raggiungibile.
   * La **[!UICONTROL No longer contact]** categoria viene aggiornata non appena il profilo annulla la sottoscrizione a un canale.
   * La **[!UICONTROL Address]** categoria contiene l'indirizzo postale che deve essere compilato insieme all' **[!UICONTROL Address specified]** opzione per inviare la posta [](../../channels/using/about-direct-mail.md) diretta a questo profilo. Se l' **[!UICONTROL Address specified]** opzione non è selezionata, questo profilo verrà escluso da ogni consegna diretta per posta.
   * La **[!UICONTROL Access authorization]** categoria indica le unità organizzative del profilo (per [gestire le autorizzazioni](../../administration/using/about-access-management.md)). Consultate anche [Profili](../../administration/using/organizational-units.md#partitioning-profiles)di partizionamento.
   * La **[!UICONTROL Traceability]** categoria si aggiorna automaticamente con le informazioni relative all'utente che ha creato o modificato il profilo.

1. Fate clic **[!UICONTROL Create]** per salvare il profilo.

Il profilo verrà ora visualizzato nell'elenco.

>[!NOTE]
>
>La creazione di profili è possibile anche tramite l'API Adobe Campaign Standard. Per ulteriori informazioni, consulta la documentazione [](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#creating-profiles) dedicata.

I profili possono essere suddivisi in base alle unità organizzative. Per aggiungere i campi organizzativi ai profili, fare riferimento alla sezione Profili [](../../administration/using/organizational-units.md#partitioning-profiles) partizionamento.

>[!NOTE]
>
>Il campo della lingua preferita viene utilizzato per selezionare la lingua durante l'invio di messaggi in più lingue. Per ulteriori informazioni sui messaggi multilingue, [fare riferimento a questa pagina](../../channels/using/creating-a-multilingual-email.md).

**Argomenti correlati:**

* [Informazioni sulle pagine](../../channels/using/about-landing-pages.md) di destinazione guida dettagliata
* [Importazione di profili](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

