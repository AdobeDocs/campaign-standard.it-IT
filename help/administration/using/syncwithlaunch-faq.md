---
title: Domande frequenti sulla sincronizzazione con il flusso di lavoro tecnico di Launch
description: Domande comuni sul flusso di lavoro tecnico di Adobe Launch
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 1%

---

# Domande frequenti sulla sincronizzazione dei tag in Adobe Experience Platform {#syncwithlaunch-faq}

Puoi importare le proprietà dei tag mobile in Adobe Campaign Standard tramite **[!UICONTROL Sync with Launch]** flusso di lavoro tecnico dedicato. Per ulteriori informazioni, consulta [page](../../administration/using/technical-workflows.md)

La sezione seguente elenca le domande comuni relative a questa sincronizzazione.

## Ho creato una proprietà tag (non amministratore di Org-unit ALL). La mia applicazione è in stato Pronto per la configurazione in Adobe Campaign ma non è possibile aprirla/configurarla. {#configuring-property}

Solo l&#39;amministratore dell&#39;unità organizzativa ALL può configurare le applicazioni mobili in Adobe Campaign Standard. Una volta configurata, solo gli utenti dell’unità organizzativa assegnata possono modificare l’applicazione. Per ulteriori informazioni sull’unità organizzativa, consulta questo [page](../../administration/using/organizational-units.md).

## Non è possibile modificare un&#39;applicazione mobile configurata in Adobe Campaign Standard e le applicazioni mobili sono in modalità di sola lettura. {#read-mode-mobile-app}

Controlla l’unità organizzativa dell’app mobile nel **[!UICONTROL Access Authorization]** sezione . Solo gli utenti dell’unità organizzativa assegnata possono modificare l’app mobile.

Per ulteriori informazioni sull’unità organizzativa, consulta questo [page](../../administration/using/organizational-units.md).

## Sono un amministratore con l’unità organizzativa ALL in Adobe Campaign Standard ma non posso configurare l’app mobile. {#org-unit-mobile}

Un amministratore con l&#39;unità organizzativa impostata su ALL deve disporre dei diritti per tutte le proprietà di tag mobile per configurare l&#39;applicazione mobile.

Per ulteriori informazioni sull’unità organizzativa, consulta questo [page](../../administration/using/organizational-units.md).

## Ho creato una proprietà tag mobile ma la mia proprietà non è visibile in Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifica che l’estensione Adobe Campaign Standard sia installata nella proprietà mobile nell’interfaccia utente di raccolta dati.

1. Verifica che gli endpoint dell’istanza siano configurati correttamente nell’estensione .

1. Verifica che &#39;Launch_URL_Campaign&#39; o &#39;NmsServer_URL&#39; siano corretti.

1. Quindi, controlla che la sincronizzazione sia completata con il **[!UICONTROL syncWithLaunch]** flusso di lavoro tecnico.

## Come verificare se la sincronizzazione tra Adobe Campaign e Tag in Adobe Experience Platform è stata completata? {#sync-campaign-launch}

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Apri **[!UICONTROL syncWithLaunch]** workflow.

1. Controlla se il flusso di lavoro è terminato senza errori.

1. Controlla nei registri che la sincronizzazione del flusso di lavoro sia abilitata e completata correttamente.

## Ho reimpostato la chiave per un&#39;applicazione mobile tag configurata. Come riconfigurare la chiave nell’interfaccia utente di raccolta dati? {#configuring-pkey}

1. Apri la proprietà mobile nell’interfaccia utente Raccolta dati.

1. Imposta un nuovo URL nell&#39;estensione Adobe Campaign Standard per cui è stato reimpostato il PKey.

1. Salvarlo e lasciare che il flusso di lavoro sia sincronizzato.

1. Al termine della sincronizzazione, apri la proprietà mobile in nell’interfaccia utente Raccolta dati.

1. Imposta l&#39;URL corretto nell&#39;estensione Adobe Campaign Standard per cui è stato reimpostato PKey.

1. Salvarlo e lasciare che la sincronizzazione del flusso di lavoro venga eseguita nuovamente.

1. Solo in questo caso la proprietà verrà visualizzata in **[!UICONTROL Ready to Configure]** in Adobe Campaign e può ora essere configurato.

## Voglio configurare una proprietà mobile in Adobe Campaign. Aspetto il flusso di lavoro tecnico per la sincronizzazione tra Tag in Adobe Experience Platform e Adobe Campaign?

Puoi eseguire immediatamente il flusso di lavoro:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Apri **[!UICONTROL syncWithLaunch]** workflow.

1. Fai clic sul pulsante **[!UICONTROL Scheduler]** e seleziona **[!UICONTROL Immediate execution]**.
