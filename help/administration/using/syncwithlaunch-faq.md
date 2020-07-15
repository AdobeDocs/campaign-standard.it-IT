---
title: Informazioni sulla gestione degli accessi
description: Gestire gli operatori  Adobe Campaign utilizzando ruoli, gruppi e unità organizzative.
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
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---


# Domande frequenti sul flusso di lavoro tecnico SyncWithLaunch {#syncwithlaunch-faq}

Il **[!UICONTROL Sync with Launch]** flusso di lavoro consente l’importazione automatica di tutte le proprietà mobili di Adobe Launch nel Adobe Campaign Standard .

Per ulteriori informazioni, consultare questa [pagina](../../administration/using/technical-workflows.md).

>[!NOTE]
>
>Dovrai inviare un ticket all&#39;Assistenza clienti Adobe (direttamente o tramite il contatto Adobe) per far sì che il flusso di lavoro **[!UICONTROL syncWithLaunch]** tecnico sia attivato nell&#39;istanza Campaign.

## Ho creato una proprietà in [!DNL Launch] (non amministratore di Org-unit ALL). L&#39;applicazione è in stato Pronto per la configurazione in  Adobe Campaign, ma non è possibile aprirla/configurarla. {#configuring-property}

Solo l&#39;amministratore dell&#39;unità organizzativa ALL può configurare le applicazioni mobili in  Adobe Campaign Standard. Una volta configurata, solo gli utenti dell&#39;unità organizzativa assegnata possono modificare l&#39;applicazione. Per ulteriori informazioni sull&#39;unità organizzativa, fare riferimento a questa [pagina](../../administration/using/organizational-units.md).

## Non è possibile modificare un&#39;applicazione mobile configurata in  Adobe Campaign Standard e le applicazioni mobili sono in sola lettura. {#read-mode-mobile-app}

Controllare l&#39;unità organizzativa dell&#39;applicazione mobile nella **[!UICONTROL Access Authorization ]** sezione. Solo gli utenti dell&#39;unità organizzativa assegnata possono modificare l&#39;applicazione mobile.

Per ulteriori informazioni sull&#39;unità organizzativa, fare riferimento a questa [pagina](../../administration/using/organizational-units.md).

## Sono un amministratore con l&#39;unità organizzativa ALL nel  Adobe Campaign Standard, ma non posso configurare l&#39;applicazione mobile. {#org-unit-mobile}

Un amministratore con l&#39;unità di organizzazione impostata su ALL deve avere i diritti per tutte le proprietà mobili in [!DNL Launch] per configurare l&#39;applicazione mobile.

Per ulteriori informazioni sull&#39;unità organizzativa, fare riferimento a questa [pagina](../../administration/using/organizational-units.md).

## Ho creato una proprietà mobile in [!DNL Launch] ma la mia proprietà non è visibile in  Adobe Campaign Standard. {#visibility-mobile-property}

1. Verificate che l&#39;estensione dell&#39;Adobe Campaign Standard  sia installata nella proprietà mobile in [!DNL Launch].

1. Verificate che gli endpoint dell&#39;istanza siano configurati correttamente nell&#39;estensione.

1. Verificate che &#39;Launch_URL_Campaign&#39; o &#39;NmsServer_URL&#39; siano corretti.

1. Quindi, verificate che la sincronizzazione tra [!DNL Launch] e  Adobe Campaign sia completata con il flusso di lavoro **[!UICONTROL syncWithLaunch]** tecnico.

## Come verificare se la sincronizzazione tra  Adobe Campaign e Launch è stata completata? {#sync-campaign-launch}

1. In  Adobe Campaign Standard, nel menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Aprire il **[!UICONTROL syncWithLaunch]** flusso di lavoro.

1. Verificate che il flusso di lavoro sia terminato senza errori.

1. Verificate nei registri che la sincronizzazione del flusso di lavoro sia abilitata e completata correttamente.

## Ho reimpostato il tasto per un&#39;applicazione mobile configurata in Launch. Come riconfigurare la chiave in Launch? {#configuring-pkey}

1. Apri la proprietà mobile in Adobe Launch.

1. Impostate un nuovo URL nell’estensione del Adobe Campaign Standard  per il quale è stato reimpostato il PKey.

1. Salvatelo e lasciate sincronizzare il flusso di lavoro tra  Adobe Campaign e [!DNL Launch].

1. Al termine della sincronizzazione, apri la proprietà mobile in [!DNL Launch].

1. Impostate l’URL corretto nell’estensione del Adobe Campaign Standard  per il quale è stato reimpostato PKey.

1. Salvatelo e lasciate che la sincronizzazione del flusso di lavoro venga nuovamente eseguita.

1. Solo in questo caso la proprietà verrà visualizzata nello stato **[!UICONTROL Ready to Configure]** in  Adobe Campaign e ora può essere configurata.

## Voglio configurare una proprietà mobile in  Adobe Campaign. È necessario attendere il flusso di lavoro tecnico per la sincronizzazione tra Adobe Launch e  Adobe Campaign?

Puoi eseguire immediatamente il flusso di lavoro:

1. In  Adobe Campaign Standard, nel menu avanzato, selezionate **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Aprire il **[!UICONTROL syncWithLaunch]** flusso di lavoro.

1. Fate clic sull&#39; **[!UICONTROL Scheduler]** attività e selezionate **[!UICONTROL Immediate execution]**.
