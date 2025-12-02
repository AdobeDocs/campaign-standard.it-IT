---
title: Gestione dei tipi di pubblico di Adobe Experience Platform
description: Scopri come gestire Adobe Experience Platform in Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# Gestione dei tipi di pubblico di Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta, e potrebbe essere soggetto ad aggiornamenti frequenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

## Accesso al pubblico di Adobe Experience Platform

Per accedere al generatore di segmenti di Adobe Experience Platform, accedi alla scheda **[!UICONTROL Audiences]** nella home page di Campaign Standard (o al collegamento **[!UICONTROL Audiences]** nell&#39;intestazione), quindi seleziona l&#39;ambiente **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Verrai innanzitutto indirizzato alla pagina dell’elenco dei segmenti di Adobe Experience Platform, dove è possibile accedere ai segmenti Adobe Experience Platform esistenti per ulteriori modifiche.

Sono disponibili una barra di ricerca e un filtro per individuare il segmento di Adobe Experience Platform desiderato.

![](assets/aep_audiences_list.png)

## Creazione di tipi di pubblico di Adobe Experience Platform

Per creare un pubblico di Adobe Experience Platform direttamente in Campaign Standard, segui questi passaggi:

1. Nella pagina dell&#39;elenco dei segmenti di Adobe Experience Platform fare clic sul pulsante **[!UICONTROL New audience]** nell&#39;angolo destro.

   ![](assets/aep_audiences_creation_create.png)

1. Ora il Generatore di segmenti dovrebbe essere visualizzato nell’area di lavoro. Consente di creare un segmento utilizzando i dati di Adobe Experience Platform che verranno utilizzati per creare il pubblico.

1. Assegna un nome al segmento nel riquadro a destra e immetti una descrizione (facoltativa).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Per creare correttamente un segmento, devi selezionare un **criterio di unione** che corrisponda allo scopo di marketing per questo segmento.

   Nel riquadro delle impostazioni viene selezionato un criterio di unione predefinito di Platform. Per ulteriori informazioni sui criteri di unione, consulta la sezione dedicata della [guida utente di Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=it).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definisci le regole che identificheranno i profili da recuperare nel pubblico.

   A questo scopo, trascina gli attributi e/o gli eventi desiderati dal riquadro di sinistra all&#39;area di lavoro, definisci le regole corrispondenti e fai clic sul pulsante **[!UICONTROL Create segment]** per salvare il segmento (vedi [Utilizzo del Generatore di segmenti](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

Il pubblico è ora pronto per essere attivato, puoi utilizzarlo come destinazione per le campagne (vedi [Destinazione dei tipi di pubblico di Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Modifica dei tipi di pubblico

Per modificare un pubblico, aprirlo e modificare le regole in base alle esigenze nell&#39;interfaccia del Generatore di segmenti (vedi [Utilizzo del Generatore di segmenti](../../integrating/using/aep-using-segment-builder.md)).

Una volta completate le modifiche, fai clic sul pulsante **[!UICONTROL Save segment]** per aggiornare il pubblico.

![](assets/aep_audiences_editing.png)
