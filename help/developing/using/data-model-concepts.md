---
solution: Campaign Standard
product: campaign
title: Concetti del modello dati
description: Scopri il modello dati di Adobe Campaign e come modificarlo.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 79%

---


# Concetti del modello dati{#data-model-concepts}

Adobe Campaign viene fornito con un modello dati predefinito. Gli [amministratori](../../administration/using/users-management.md#functional-administrators) possono modificare questo modello dati e aggiungere nuove risorse o estensioni alle risorse esistenti.

>[!CAUTION]
>
>La creazione e la modifica di risorse sono operazioni delicate che devono essere eseguite solo da utenti esperti.

Il menu **[!UICONTROL Administration]** > **[!UICONTROL Development]**, accessibile tramite il logo Adobe Campaign, ti dà la possibilità di gestire le **risorse personalizzate**, **pubblicarle** e **accedere agli strumenti diagnostici**.

I dati utilizzati da Adobe Campaign sono definiti tramite risorse diverse. Puoi **arricchire il modello dati** fornito creando risorse personalizzate, ad esempio tabelle di acquisto o di prodotti.

Non puoi modificare le risorse incorporate (come campagne, e-mail o tipi di pubblico). Tuttavia, puoi estendere le risorse personalizzate per aggiungere nuovi campi.

I campi di estensione vengono generati con un prefisso in modo che non entrino mai in conflitto con i campi incorporati.

>[!NOTE]
>
>È possibile trovare una rappresentazione del modello di dati per le risorse integrate in [questa pagina](../../developing/using/datamodel-introduction.md).

Puoi anche [configurare la navigazione](configuring-the-screen-definition.md) nelle schermate corrispondenti alla risorsa creata.

Puoi **esportare e importare** risorse personalizzate, ad esempio da un ambiente di sviluppo a uno di produzione. Per ulteriori informazioni, consulta questo [caso di utilizzo passo per passo](../../automating/using/exporting-importing-custom-resources.md).

>[!CAUTION]
>
>Solo gli amministratori [funzionali](../../administration/using/users-management.md#functional-administrators), con il ruolo **[!UICONTROL Administration]** e l&#39;accesso alle unità **All** possono accedere ai registri di invio, ai log dei messaggi, ai registri di monitoraggio, ai registri di esclusione o ai registri di iscrizione. Un utente non amministratore può eseguire il targeting di questi registri ma iniziare da una tabella collegata (profili, consegna).
