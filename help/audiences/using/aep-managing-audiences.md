---
title: Gestione dell’audience
description: Scopri come gestire Adobe Experience Platform in Campaign Standard.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 19b22fa0780a0bf7c4b7a559270d7c8b32d89e38

---


# Gestione dell’audience {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service è attualmente in versione beta, che può essere oggetto di aggiornamenti frequenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta l&#39;Assistenza clienti Adobe.

## Accesso ai tipi di pubblico

Per accedere ai tipi di pubblico di Adobe Experience Platform, seleziona la **[!UICONTROL Audiences]**scheda nella home page di Campaign Standard oppure il**[!UICONTROL Audiences]** collegamento, quindi seleziona **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Vengono visualizzati tutti i tipi di pubblico creati con Adobe Experience Platform. Sono disponibili una barra di ricerca e dei filtri che consentono di trovare il pubblico desiderato.

![](assets/aep_audiences_list.png)

## Creazione di audience

Le audience vengono create direttamente dall&#39;elenco dei tipi di pubblico di Adobe Experience Platform. A questo scopo, effettuate le seguenti operazioni:

1. Vai all&#39;elenco delle audience, quindi fai clic sul **[!UICONTROL New audience]**pulsante.

   ![](assets/aep_audiences_creation_create.png)

1. Il Generatore di segmenti unificato deve ora essere visualizzato nell&#39;area di lavoro. Consente di creare un segmento utilizzando i dati di Adobe Experience Platform, che verranno utilizzati per creare il pubblico.

1. Denominate il segmento nel riquadro a destra e immettete una descrizione (facoltativo).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Per creare correttamente un segmento, devi selezionare un criterio **di** unione che corrisponda allo scopo di marketing per questo segmento.

   Nel riquadro delle impostazioni, è selezionato un criterio di unione predefinito per la piattaforma. Per ulteriori informazioni sui criteri di unione, consulta la sezione dedicata della guida utente di [Segment Builder](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

   ![](assets/aep_audiences_mergepolicy.png)

1. Definite le regole che identificheranno i profili da recuperare nel pubblico.

   A questo scopo, trascina gli attributi e/o gli eventi desiderati dal riquadro a sinistra nell&#39;area di lavoro, definisce le regole corrispondenti, quindi fai clic sul **[!UICONTROL Create segment]**pulsante per salvare il segmento (consulta[Utilizzo di Unified Segment Builder](../../audiences/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

L&#39;audience è ora pronta per essere attivata e può essere utilizzata come destinazione per le campagne (consultate [Targeting Adobe Experience Platform Audiences](../../automating/using/aep-targeting-audiences.md)).

## Modifica delle audience

Per modificare un&#39;audience, aprirla e modificarne le regole in base alle esigenze all&#39;interno dell&#39;interfaccia Unified Segment Builder (vedere [Utilizzo di Unified Segment Builder](../../audiences/using/aep-using-segment-builder.md)).

Una volta completate le modifiche, fate clic sul **[!UICONTROL Save segment]**pulsante per aggiornare il pubblico.

![](assets/aep_audiences_editing.png)
