---
title: Creazione di profili
seo-title: Creazione di profili
description: Creazione di profili
seo-description: Scopri come creare profili e raccogliere dati sui tuoi contatti, utilizzando API, funzionalità di importazione, acquisizione online, aggiornamenti automatici o manuali.
page-status-flag: never-activated
uuid: a 5 f 5 a 58 a-e 798-400 f -8648-05 dc 843 d 5557
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audience
content-type: riferimento
topic-tags: managing-profiles
discoiquuid: 4 ab 8 a 984-f 898-4 fff-ad 8 c-ed 8 f 95362 f 96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f883986392f6b739832093e0473591aa39dfcbfe

---


# Creating profiles{#creating-profiles}

In Adobe Campaign, i profili vengono utilizzati per impostazione predefinita per definire il target principale dei messaggi.

Per creare o aggiornare un profilo in Campaign, puoi:

* Import a profile list from a file, via a [workflow](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Collect data online, via [landing pages](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html)
* Create bulk via [REST API](http://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)
* Synchronize profiles from [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* Immettere i dati utilizzando le schermate dell'interfaccia grafica, come illustrato di seguito

Ad esempio, per creare un nuovo profilo direttamente nell'interfaccia utente, segui i passaggi seguenti:

1. From the Adobe Campaign home page, click the **Customer Profiles** card or the **Profiles** tab to access the list of profiles.

   ![](assets/profile_creation_1.png)

1. Then click **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Inserite i dati del profilo.

   ![](assets/profile_creation1.png)

   * The contact information, such as first name, last name, gender, date of birth, photo, preferred language (for [multilingual emails](../../channels/using/creating-a-multilingual-email.md)) helps better personalize deliveries.
   * The profile's **[!UICONTROL Time zone]** is used to send deliveries at the profile's time zone. For more on this, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * The **[!UICONTROL Channels]** category, which contains the email address, mobile phone number, opt-out information, lets you know on which channel the profile is reachable.
   * The **[!UICONTROL No longer contact]** category is updated as soon as the profile unsubscribe to a channel.
   * The **[!UICONTROL Address]** category contains the postal address that needs to be filled along with the **[!UICONTROL Address specified]** option to send [direct mail](../../channels/using/about-direct-mail.md) to this profile. If the **[!UICONTROL Address specified]** option is not checked, this profile will be excluded from every direct mail delivery.
   * The **[!UICONTROL Access authorization]** category indicates the profile's organizational units (to [manage permissions](../../administration/using/about-access-management.md)). See also [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * The **[!UICONTROL Traceability]** category automatically updates with information concerning the user who created or modified the profile.

1. Click **[!UICONTROL Create]** to save the profile.

Il profilo viene ora visualizzato nell'elenco.

>[!NOTE]
>
>La creazione dei profili è possibile anche tramite l'API standard di Adobe Campaign. For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#creating-profiles) .

I profili possono essere suddivisi anche in base alle unità organizzative. To add the organizational fields to your profiles, refer to the [Partitioning profiles](../../administration/using/organizational-units.md#partitioning-profiles) section.

>[!NOTE]
>
>Il campo lingua preferito viene usato per selezionare la lingua quando si inviano messaggi in più lingue. For more information about the multilingual messages [refer to this page](../../channels/using/creating-a-multilingual-email.md).

**Argomenti correlati:**

* [Creazione di una guida passo-passo per una pagina](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_CreateLandingPage.html) di destinazione
* [Importazione di profili](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

