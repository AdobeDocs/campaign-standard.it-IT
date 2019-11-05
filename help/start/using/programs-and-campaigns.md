---
title: Programmi e campagne
description: In Adobe Campaign, i programmi e le campagne consentono di raggruppare e orchestrare le diverse attività di marketing ad essi collegate. I rapporti su programmi e campagne consentono di analizzarne l’impatto.
page-status-flag: mai attivato
uuid: fe2812a8-196f-4aba-a739-fbbfffd754cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: piani di marketing
discoiquuid: 21b84028-d1a7-4ad6-891a-862a9456514
context-tags: campagna,panoramica;campaignExplorer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Programmi e campagne{#programs-and-campaigns}

## Informazioni su piani, programmi e campagne {#about-plans--programs-and-campaigns}

Adobe Campaign consente di pianificare campagne di marketing in cui creare e gestire diversi tipi di attività: e-mail, messaggi SMS, notifiche push, flussi di lavoro, pagine di destinazione. Tali campagne e il relativo contenuto possono essere raccolti in programmi.

I programmi e le campagne consentono di raggruppare e visualizzare le diverse attività di marketing ad essi collegate.

* Un **programma** può contenere altri programmi, campagne, flussi di lavoro e pagine di destinazione. Viene visualizzata nella timeline e aiutate a organizzare le attività di marketing: potete separarli per paese, per marchio, per unità, ecc.
* Una **campagna** consente di raccogliere tutte le attività di marketing di tua scelta in un'unica entità. Una campagna può contenere e-mail, SMS, notifiche push, e-mail dirette, flussi di lavoro e pagine di destinazione.

Per organizzare meglio i piani di marketing, Adobe consiglia di seguire la gerarchia: Programma &gt; Sottoprogrammi &gt; Campagne &gt; Flussi di lavoro &gt; Consegne.

I rapporti su programmi e campagne consentono di analizzarne l’impatto. Ad esempio, puoi creare report a livello di campagna per aggregare i dati su tutte le consegne contenute in quella campagna.

**Argomenti correlati:**

* [Timeline](../../start/using/timeline.md)
* [Informazioni sui report dinamici](../../reporting/using/about-dynamic-reports.md)

## Creazione di un programma {#creating-a-program}

Il programma è il primo livello di organizzazione. Può contenere sottoprogrammi, campagne, flussi di lavoro o pagine di destinazione.

1. Dalla home page di Adobe Campaign, selezionate la **[!UICONTROL Programs & Campaigns]** scheda.
1. Fate clic sul **[!UICONTROL Create]** pulsante.
1. Nella **[!UICONTROL Creation mode]** schermata, selezionare un tipo di programma.

   ![](assets/programs_and_campaigns_2.png)

   I tipi di programma disponibili sono basati su modelli definiti nella sezione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Program templates]** . Per ulteriori informazioni, consulta la sezione [Gestione dei modelli](../../start/using/about-templates.md) .

1. Nella **[!UICONTROL Properties]** schermata, immettete il nome e l’ID del programma.

   ![](assets/programs_and_campaigns_3.png)

1. Selezionare una data di inizio e di fine per il programma. Tali date si applicano solo al programma stesso.

   È possibile creare il programma all'interno di un programma principale. A questo scopo, selezionare il programma padre dai programmi esistenti.

1. Fare clic su **[!UICONTROL Create]** per confermare la creazione del programma.

Il programma viene creato e visualizzato. Utilizzare il **[!UICONTROL Create]** pulsante per aggiungere sottoprogrammi, campagne, flussi di lavoro o pagine di destinazione.

>[!NOTE]
>
>Puoi anche creare un programma dall'elenco delle attività di marketing.

## Creazione di una campagna {#creating-a-campaign}

Nei programmi e sottoprogrammi è possibile aggiungere campagne. Le campagne possono contenere attività di marketing come e-mail, SMS, notifiche push, flussi di lavoro e pagine di destinazione.

1. Dalla home page di Adobe Campaign, seleziona la **[!UICONTROL Programs & Campaigns]** scheda e accedi a un programma o a un sottoprogramma.
1. Fare clic sul **[!UICONTROL Create]** pulsante e selezionare **[!UICONTROL Campaign]**.
1. Nella **[!UICONTROL Creation mode]** schermata, selezionate un tipo di campagna.

   ![](assets/programs_and_campaigns_7.png)

   I tipi di campagna disponibili sono basati su modelli definiti in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Campaign templates]**. Per ulteriori informazioni, consulta la sezione [Gestione dei modelli](../../start/using/about-templates.md) .

1. Nella **[!UICONTROL Properties]** schermata, immettete il nome e l’ID della campagna.
1. Selezionate una data di inizio e una data di fine per la campagna. Queste date si applicano solo alla campagna stessa.

   ![](assets/programs_and_campaigns_8.png)

1. Fate clic su **[!UICONTROL Create]** per confermare la creazione della campagna.

La campagna viene creata e visualizzata. Utilizzate il **[!UICONTROL Create]** pulsante per aggiungere attività di marketing alla campagna.

>[!NOTE]
>
>A seconda del contratto di licenza, potete accedere solo ad alcune di queste attività.

Puoi anche creare una campagna dall'elenco delle attività di marketing. Puoi scegliere di collegare l'attività di marketing a un programma padre o a un sottoprogramma tramite la finestra delle proprietà della campagna.

## Programmi e campagne icone e stati {#programs-and-campaigns-icons-and-statuses}

Ogni programma e ogni campagna presente nell'elenco sono dotati di un simbolo visivo e di un'icona il cui colore indica lo stato di esecuzione. Questo stato dipende dal periodo di validità del programma o della campagna.

* Grigio: il programma/campagna non è ancora iniziato - **[!UICONTROL Editing]** stato.
* Blu: il programma/campagna è in corso - **[!UICONTROL In progress]** stato.
* Verde: il programma/campagna è terminato - **[!UICONTROL Finished]** stato. Per impostazione predefinita, la data corrente viene visualizzata automaticamente come data di inizio validità e la data di fine viene calcolata in base alla data di inizio (**D+186 giorni**). Potete modificare queste date nelle proprietà del programma o della campagna.

![](assets/programs_and_campaigns.png)

