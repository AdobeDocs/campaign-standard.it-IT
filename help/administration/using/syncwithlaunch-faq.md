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

Puoi importare le proprietà dei tag mobili in Adobe Campaign Standard tramite **[!UICONTROL Sync with Launch]** flusso di lavoro tecnico dedicato. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/technical-workflows.md)

Nella sezione seguente sono elencate le domande più frequenti sulla sincronizzazione.

## Ho creato una proprietà tag (che non è un amministratore di ALL per l’unità organizzativa). La mia applicazione si trova nello stato Pronto per la configurazione in Adobe Campaign, ma non sono in grado di aprirla/configurarla. {#configuring-property}

Solo l’amministratore dell’unità organizzativa ALL può configurare le applicazioni mobili in Adobe Campaign Standard. Una volta configurata, solo gli utenti dell’unità organizzativa assegnata possono modificare l’applicazione. Per ulteriori informazioni sull’unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

## Non sono in grado di modificare un’app mobile configurata in Adobe Campaign Standard e le app mobili sono solo in modalità di lettura. {#read-mode-mobile-app}

Controlla l’unità organizzativa dell’app mobile in **[!UICONTROL Access Authorization]** sezione. Solo gli utenti dell’unità organizzativa assegnata possono modificare l’app mobile.

Per ulteriori informazioni sull’unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

## Sono un amministratore con unità organizzativa ALL in Adobe Campaign Standard, ma non posso configurare l’app mobile. {#org-unit-mobile}

Un amministratore con l’unità organizzativa impostata su ALL deve disporre dei diritti per tutte le proprietà mobili dei tag per configurare l’app mobile.

Per ulteriori informazioni sull’unità organizzativa, consulta questa [pagina](../../administration/using/organizational-units.md).

## Ho creato una proprietà mobile di tag, ma la mia proprietà non è visibile in Adobe Campaign Standard. {#visibility-mobile-property}

1. Verifica che l’estensione Adobe Campaign Standard sia installata nella proprietà mobile nell’interfaccia utente di Data Collection.

1. Verifica che gli endpoint dell&#39;istanza siano configurati correttamente nell&#39;estensione.

1. Verifica che &quot;Launch_URL_Campaign&quot; o &quot;NmsServer_URL&quot; siano corretti.

1. Quindi, verifica che la sincronizzazione sia completata con **[!UICONTROL syncWithLaunch]** flusso di lavoro tecnico.

## Come verificare se la sincronizzazione tra Adobe Campaign e i tag in Adobe Experience Platform è stata completata? {#sync-campaign-launch}

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Apri **[!UICONTROL syncWithLaunch]** flusso di lavoro.

1. Controlla se il flusso di lavoro è terminato senza errori.

1. Controlla nei registri che la sincronizzazione del flusso di lavoro sia abilitata e completata correttamente.

## Reimposta la chiave per un’app mobile con tag configurata. Come riconfigurare la chiave nell’interfaccia utente di Data Collection? {#configuring-pkey}

1. Apri la proprietà mobile nell’interfaccia utente di Data Collection.

1. Imposta un nuovo URL nell’estensione Adobe Campaign Standard per il quale è stata reimpostata la PKey.

1. Salvalo e lascia sincronizzare il flusso di lavoro.

1. Al termine della sincronizzazione, apri la proprietà mobile in nell’interfaccia utente di Data Collection.

1. Imposta l’URL corretto nell’estensione Adobe Campaign Standard per la quale è stato reimpostato PKey.

1. Salva e riesegui la sincronizzazione del flusso di lavoro.

1. Solo allora la proprietà apparirà in **[!UICONTROL Ready to Configure]** in Adobe Campaign e ora può essere configurato.

## Desidero configurare una proprietà mobile in Adobe Campaign. Dovrò attendere che il flusso di lavoro tecnico venga sincronizzato tra i tag in Adobe Experience Platform e Adobe Campaign?

Puoi eseguire l’esecuzione immediata del flusso di lavoro:

1. In Adobe Campaign Standard, dal menu avanzato, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Apri **[!UICONTROL syncWithLaunch]** flusso di lavoro.

1. Fai clic sul pulsante **[!UICONTROL Scheduler]** attività e selezione **[!UICONTROL Immediate execution]**.
