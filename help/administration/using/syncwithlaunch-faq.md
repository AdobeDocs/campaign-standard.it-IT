---
title: Domande frequenti sul flusso di lavoro tecnico Launch
description: Domande comuni sul flusso di lavoro tecnico di Launch.
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95a7397092f6e07c84967d90908469f630f7a170
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---


# Domande frequenti sulla sincronizzazione del lancio  Adobe {#syncwithlaunch-faq}

È possibile importare  proprietà di Launch mobile Adobe in  Adobe Campaign Standard attraverso il flusso di lavoro tecnico **[!UICONTROL Sync with Launch]** dedicato. For more information, refer to this [page](../../administration/using/technical-workflows.md)

La sezione seguente elenca le domande comuni su questa sincronizzazione.

>[!NOTE]
>
>You will need to submit a ticket to Adobe Customer Care (either directly or through your Adobe contact) to have the **[!UICONTROL syncWithLaunch]** technical workflow enabled in your Campaign instance.

## Ho creato una proprietà in [!DNL Launch] (non amministratore di Org-unit ALL). L&#39;applicazione è in stato Pronto per la configurazione in  Adobe Campaign, ma non è possibile aprirla/configurarla. {#configuring-property}

Solo l&#39;amministratore dell&#39;unità organizzativa ALL può configurare le applicazioni mobili in  Adobe Campaign Standard. Una volta configurata, solo gli utenti dell&#39;unità organizzativa assegnata possono modificare l&#39;applicazione. For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Non è possibile modificare un&#39;applicazione mobile configurata in  Adobe Campaign Standard e le applicazioni mobili sono in sola lettura. {#read-mode-mobile-app}

Controllare l&#39;unità organizzativa dell&#39;applicazione mobile nella **[!UICONTROL Access Authorization ]** sezione. Solo gli utenti dell&#39;unità organizzativa assegnata possono modificare l&#39;applicazione mobile.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Sono un amministratore con l&#39;unità organizzativa ALL in  Adobe Campaign Standard, ma non posso configurare l&#39;applicazione mobile. {#org-unit-mobile}

Un amministratore con l&#39;unità di organizzazione impostata su ALL deve avere i diritti per tutte le proprietà mobili in [!DNL Launch] per configurare l&#39;applicazione mobile.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Ho creato una proprietà mobile in [!DNL Launch] ma la mia proprietà non è visibile in  Adobe Campaign Standard. {#visibility-mobile-property}

1. Verificate che l&#39;estensione Adobe Campaign Standard  sia installata nella proprietà mobile in [!DNL Launch].

1. Verificate che gli endpoint dell&#39;istanza siano configurati correttamente nell&#39;estensione.

1. Verificate che &#39;Launch_URL_Campaign&#39; o &#39;NmsServer_URL&#39; siano corretti.

1. Quindi, controllate che la sincronizzazione tra [!DNL Launch] e  Adobe Campaign sia completata con il flusso di lavoro **[!UICONTROL syncWithLaunch]** tecnico.

## Come verificare se la sincronizzazione tra  Adobe Campaign e Launch è stata completata? {#sync-campaign-launch}

1. In  Adobe Campaign Standard, dal menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Aprire il **[!UICONTROL syncWithLaunch]** flusso di lavoro.

1. Verificate che il flusso di lavoro sia terminato senza errori.

1. Verificate nei registri che la sincronizzazione del flusso di lavoro sia abilitata e completata correttamente.

## Ho reimpostato il tasto per un&#39;applicazione mobile configurata in Launch. Come riconfigurare la chiave in Launch? {#configuring-pkey}

1. Apri la proprietà mobile in  Adobe Launch.

1. Impostate un nuovo URL nell’estensione Adobe Campaign Standard  per la quale è stato reimpostato il PKey.

1. Salvatelo e lasciate sincronizzare il flusso di lavoro tra  Adobe Campaign e [!DNL Launch].

1. Al termine della sincronizzazione, apri la proprietà mobile in [!DNL Launch].

1. Impostate l’URL corretto nell’estensione Adobe Campaign Standard  per la quale è stato reimpostato PKey.

1. Salvatelo e lasciate che la sincronizzazione del flusso di lavoro venga nuovamente eseguita.

1. Solo in questo caso la proprietà verrà visualizzata nello **[!UICONTROL Ready to Configure]** stato in  Adobe Campaign e ora può essere configurata.

## Voglio configurare una proprietà mobile in  Adobe Campaign. È necessario attendere la sincronizzazione del flusso di lavoro tecnico tra  Adobe Launch e  Adobe Campaign?

Puoi eseguire immediatamente il flusso di lavoro:

1. In  Adobe Campaign Standard, dal menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Aprire il **[!UICONTROL syncWithLaunch]** flusso di lavoro.

1. Click on the **[!UICONTROL Scheduler]** activity and select **[!UICONTROL Immediate execution]**.
