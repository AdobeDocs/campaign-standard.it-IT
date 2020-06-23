---
title: Gestione dei tipi di pubblico di Adobe Experience Platform
description: Scoprite come gestire  Adobe Experience Platform in Campaign Standard.
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
source-git-commit: d487600fc4f3004804e93347b83edfe4e01cceeb
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---


# Gestione dei tipi di pubblico di Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service è attualmente in versione beta, che può essere oggetto di aggiornamenti frequenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta l&#39;Assistenza clienti Adobe.

## Accesso ai tipi di pubblico  Adobe Experience Platform

Per accedere al generatore di segmenti di  Adobe Experience Platform, andate alla **[!UICONTROL Audiences]** scheda nella home page di Campaign Standard (o al **[!UICONTROL Audiences]** collegamento nell&#39;intestazione), quindi selezionate l&#39; **[!UICONTROL Adobe Experience Platform]** ambiente.

![](assets/aep_audiences_access.png)

Verrai indirizzato prima alla pagina dell&#39;elenco dei segmenti del Adobe Experience Platform , dove è possibile accedere ai segmenti  Adobe Experience Platform già esistenti per ulteriori modifiche.

Sono disponibili una barra di ricerca e un filtro per individuare il segmento di Adobe Experience Platform  desiderato.

![](assets/aep_audiences_list.png)

## Creazione di audience  Adobe Experience Platform

Per creare un pubblico  Adobe Experience Platform direttamente in Campaign Standard, effettuate le seguenti operazioni:

1. Dalla pagina dell’elenco dei segmenti del Adobe Experience Platform , fate clic sul **[!UICONTROL New audience]** pulsante situato nell’angolo destro.

   ![](assets/aep_audiences_creation_create.png)

1. Il Generatore di segmenti deve ora essere visualizzato nell’area di lavoro. Consente di creare un segmento utilizzando i dati di  Adobe Experience Platform che verranno utilizzati per creare il pubblico.

1. Denominate il segmento nel riquadro a destra e immettete una descrizione (facoltativo).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Per creare correttamente un segmento, devi selezionare un criterio **di** unione che corrisponda allo scopo di marketing per questo segmento.

   Nel riquadro delle impostazioni, è selezionato un criterio di unione predefinito di Platform. Per ulteriori informazioni sui criteri di unione, consulta la sezione dedicata della guida [utente di](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html)Segment Builder.

   ![](assets/aep_audiences_mergepolicy.png)

1. Definite le regole che identificheranno i profili da recuperare nel pubblico.

   A questo scopo, trascina gli attributi e/o gli eventi desiderati dal riquadro a sinistra nell’area di lavoro, definisce le regole corrispondenti, quindi fai clic sul **[!UICONTROL Create segment]** pulsante per salvare il segmento (consulta [Utilizzo del Generatore](../../audiences/using/aep-using-segment-builder.md)di segmenti).

   ![](assets/aep_audiences_creation_query.png)

L&#39;audience è ora pronta per essere attivata e può essere utilizzata come destinazione per le campagne (consultate [Targeting  audience](../../automating/using/aep-targeting-audiences.md)di Adobi Experience Platform).

## Modifica delle audience

Per modificare un&#39;audience, aprirla e modificarne le regole in base alle esigenze all&#39;interno dell&#39;interfaccia di Segment Builder (vedere [Utilizzo di Segment Builder](../../audiences/using/aep-using-segment-builder.md)).

Una volta completate le modifiche, fate clic sul **[!UICONTROL Save segment]** pulsante per aggiornare il pubblico.

![](assets/aep_audiences_editing.png)
