---
solution: Campaign Standard
product: campaign
title: Domande frequenti sulla sincronizzazione con il flusso di lavoro tecnico di Launch
description: Domande comuni sul flusso di lavoro tecnico Launch.
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '487'
ht-degree: 0%

---


# Domande frequenti sulla sincronizzazione di Adobe Launch {#syncwithlaunch-faq}

Puoi importare le proprietà mobili di Adobe Launch in Adobe Campaign Standard tramite il **[!UICONTROL Sync with Launch]** flusso di lavoro tecnico dedicato. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/technical-workflows.md)

La sezione seguente elenca le domande comuni relative a questa sincronizzazione.

## Ho creato una proprietà in [!DNL Launch] (non amministratore di Org-unit ALL). La mia applicazione è in stato Pronto per la configurazione in Adobe Campaign ma non è possibile aprirla/configurarla. {#configuring-property}

Solo l&#39;amministratore dell&#39;unità organizzativa ALL può configurare le applicazioni mobili in Adobe Campaign Standard. Una volta configurata, solo gli utenti dell’unità organizzativa assegnata possono modificare il
applicazione. Per ulteriori informazioni sull&#39;unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

## Non è possibile modificare un&#39;applicazione mobile configurata in Adobe Campaign Standard e le applicazioni mobili sono in modalità di sola lettura. {#read-mode-mobile-app}

Controlla l’unità organizzativa dell’app mobile nella sezione **[!UICONTROL Access Authorization]** . Solo gli utenti dell’unità organizzativa assegnata possono modificare l’app mobile.

Per ulteriori informazioni sull&#39;unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

## Sono un amministratore con l’unità organizzativa ALL in Adobe Campaign Standard ma non posso configurare l’app mobile. {#org-unit-mobile}

Un amministratore con l&#39;unità organizzativa impostata su ALL deve disporre dei diritti per tutte le proprietà mobili in [!DNL Launch] per configurare l&#39;applicazione mobile.

Per ulteriori informazioni sull&#39;unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

## Ho creato una proprietà mobile in [!DNL Launch] ma la mia proprietà non è visibile in Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifica che l’estensione Adobe Campaign Standard sia installata nella proprietà mobile in [!DNL Launch].

1. Verifica che gli endpoint dell’istanza siano configurati correttamente nell’estensione .

1. Verifica che &#39;Launch_URL_Campaign&#39; o &#39;NmsServer_URL&#39; siano corretti.

1. Quindi, controlla che la sincronizzazione tra [!DNL Launch] e Adobe Campaign sia completata con il flusso di lavoro tecnico **[!UICONTROL syncWithLaunch]** .

## Come verificare se la sincronizzazione tra Adobe Campaign e Launch è stata completata? {#sync-campaign-launch}

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Apri il flusso di lavoro **[!UICONTROL syncWithLaunch]** .

1. Controlla se il flusso di lavoro è terminato senza errori.

1. Controlla nei registri che la sincronizzazione del flusso di lavoro sia abilitata e completata correttamente.

## Ho reimpostato la chiave per un&#39;applicazione mobile configurata in Launch. Come riconfigurare la chiave in Launch? {#configuring-pkey}

1. Apri la proprietà mobile in Adobe Launch.

1. Imposta un nuovo URL nell&#39;estensione Adobe Campaign Standard per cui è stato reimpostato il PKey.

1. Salva e lascia sincronizzare il flusso di lavoro tra Adobe Campaign e [!DNL Launch].

1. Al termine della sincronizzazione, apri la proprietà mobile in [!DNL Launch].

1. Imposta l&#39;URL corretto nell&#39;estensione Adobe Campaign Standard per cui è stato reimpostato PKey.

1. Salvarlo e lasciare che la sincronizzazione del flusso di lavoro venga eseguita nuovamente.

1. Solo in questo caso la proprietà verrà visualizzata in **[!UICONTROL Ready to Configure]** stato in Adobe Campaign e può essere configurata.

## Voglio configurare una proprietà mobile in Adobe Campaign. Attenderò la sincronizzazione del flusso di lavoro tecnico tra Adobe Launch e Adobe Campaign?

Puoi eseguire immediatamente il flusso di lavoro:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Apri il flusso di lavoro **[!UICONTROL syncWithLaunch]** .

1. Fai clic sull’attività **[!UICONTROL Scheduler]** e seleziona **[!UICONTROL Immediate execution]**.
