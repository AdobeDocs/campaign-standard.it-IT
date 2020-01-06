---
title: Informazioni sui modelli
description: '"I modelli di Adobe Campaign consentono di preconfigurare i parametri in base alle esigenze: i modelli possono contenere una configurazione completa o parziale dell''attività di marketing, per semplificare l''utilizzo di Adobe Campaign per gli utenti finali non tecnici."'
page-status-flag: never-activated
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb5cc55c431cbe6050699a35ef2fff270f869dee

---


# Modelli di attività di marketing {#marketing-activity-templates}

## Informazioni sui modelli {#about-templates}

Quando crei una nuova attività di marketing, nella prima schermata della procedura guidata viene richiesto di selezionare un tipo o un modello. I modelli consentono di preconfigurare alcuni parametri in base alle esigenze. Il modello può contenere una configurazione completa o parziale dell&#39;attività di marketing. La gestione dei modelli viene eseguita dall&#39;amministratore funzionale.

L&#39;utente finale ha un&#39;interfaccia semplificata. Quando crei una nuova attività di marketing, devi solo selezionare il modello da utilizzare. Non c&#39;è bisogno di preoccuparsi di configurazioni tecniche. Questo è già stato preconfigurato dall&#39;amministratore funzionale nel modello.

Ad esempio, nel caso di un modello e-mail, potete precompilare il contenuto HTML, il pubblico e qualsiasi altro parametro per la distribuzione: pianificazione, profili di test, proprietà generali della consegna, parametri avanzati, ecc. Questo consente di risparmiare tempo durante la creazione di una nuova attività.

![](assets/template_1.png)

Per ogni tipo di attività di marketing, sono disponibili uno o più modelli out-of-the-box con una configurazione minima. Non è possibile modificare o eliminare questi modelli predefiniti.

I modelli sono disponibili per le seguenti attività di marketing:

* Programmi
* Campagne
* Consegne e-mail
* Consegne mediante SMS
* Notifiche push
* Pagine di destinazione
* Flussi di lavoro
* Servizi
* Importa
* Messaggi transazionali

## Creazione di un nuovo modello {#creating-a-new-template}

I modelli di messaggio possono essere gestiti dall&#39;amministratore funzionale della piattaforma, nel **[!UICONTROL Resources > Templates]**menu. I modelli forniti non possono essere modificati o eliminati. Per creare un nuovo modello, dovete duplicarne uno esistente.

1. Selezionate un modello esistente. Nel nostro esempio, abbiamo scelto un **[!UICONTROL Delivery template]**.

   ![](assets/template_2.png)

1. Passate il puntatore del mouse su di esso, quindi selezionate l&#39; **[!UICONTROL Duplicate element]**opzione.

   ![](assets/template_3.png)

1. Configura le impostazioni desiderate, esattamente come faresti per [creare una nuova attività](../../start/using/marketing-activities.md#creating-a-marketing-activity) di marketing da zero.

   ![](assets/template_4.png)

I modelli creati possono quindi essere selezionati dall&#39;utente standard nella prima schermata della procedura guidata durante la creazione di un&#39;attività di marketing.

## Utilizzo di un modello {#using-a-template}

Adesso vedremo come utilizzare un modello creato nella sezione precedente.

>[!NOTE]
>
>La creazione di un&#39;attività di marketing basata su un modello viene generalmente eseguita da un profilo di tipo utente standard.

1. Crea una nuova attività di marketing.

   ![](assets/template_5.png)

1. Nella prima schermata della procedura guidata, selezionate il modello da utilizzare.

   ![](assets/template_6.png)

   L&#39;attività di marketing è preconfigurata con i parametri definiti nel modello.

   ![](assets/template_7.png)
