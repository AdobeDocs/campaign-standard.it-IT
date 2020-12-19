---
solution: Campaign Standard
product: campaign
title: Gestione dei tipi di pubblico di Adobe Experience Platform
description: Scopri come gestire Adobe Experience Platform all'interno di Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# Gestione dei tipi di pubblico di Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service è attualmente in versione beta, che può essere oggetto di aggiornamenti frequenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.

## Accesso ai tipi di pubblico Adobe Experience Platform

Per accedere al generatore di segmenti Adobe Experience Platform, andate alla scheda **[!UICONTROL Audiences]** nella home page del Campaign Standard (o al collegamento **[!UICONTROL Audiences]** nell&#39;intestazione), quindi selezionate l&#39;ambiente **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Verrai indirizzato prima alla pagina dell&#39;elenco dei segmenti Adobe Experience Platform, dove è possibile accedere ai segmenti Adobe Experience Platform già esistenti per ulteriori modifiche.

Sono disponibili una barra di ricerca e un filtro per trovare il segmento Adobe Experience Platform desiderato.

![](assets/aep_audiences_list.png)

## Creazione di audience Adobe Experience Platform

Per creare un pubblico Adobe Experience Platform direttamente in Campaign Standard, attenetevi alla procedura seguente:

1. Dalla pagina dell&#39;elenco dei segmenti di Adobe Experience Platform, fate clic sul pulsante **[!UICONTROL New audience]** situato nell&#39;angolo destro.

   ![](assets/aep_audiences_creation_create.png)

1. Il Generatore di segmenti deve ora essere visualizzato nell’area di lavoro. Consente di creare un segmento utilizzando i dati di Adobe Experience Platform che verranno utilizzati per creare il pubblico.

1. Denominate il segmento nel riquadro a destra e immettete una descrizione (facoltativo).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Per creare correttamente un segmento, è necessario selezionare un **criterio di unione** che corrisponda allo scopo di marketing per questo segmento.

   Nel riquadro delle impostazioni, è selezionato un criterio di unione predefinito per la piattaforma. Per ulteriori informazioni sui criteri di unione, fare riferimento alla sezione dedicata della [Guida utente di Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definite le regole che identificheranno i profili da recuperare nel pubblico.

   A questo scopo, trascina gli attributi e/o gli eventi desiderati dal riquadro a sinistra nell&#39;area di lavoro, definisce le regole corrispondenti, quindi fai clic sul pulsante **[!UICONTROL Create segment]** per salvare il segmento (vedere [Utilizzo del Generatore di segmenti](../../audiences/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

L&#39;audience è ora pronta per essere attivata e può essere utilizzata come destinazione per le campagne (vedere [Targeting Adobe Experience Platform audiences](../../automating/using/aep-targeting-audiences.md)).

## Modifica di tipi di pubblico

Per modificare un&#39;audience, aprirla e modificarne le regole in base alle esigenze all&#39;interno dell&#39;interfaccia di Segment Builder (vedere [Using the Segment Builder](../../audiences/using/aep-using-segment-builder.md)).

Una volta completate le modifiche, fate clic sul pulsante **[!UICONTROL Save segment]** per aggiornare il pubblico.

![](assets/aep_audiences_editing.png)
