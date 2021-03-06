---
title: Gestione dei tipi di pubblico di Adobe Experience Platform
description: Scopri come gestire Adobe Experience Platform in Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# Gestione dei tipi di pubblico di Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta e potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

## Accesso ai tipi di pubblico di Adobe Experience Platform

Per accedere al generatore di segmenti di Adobe Experience Platform, passa alla **[!UICONTROL Audiences]** scheda nella home page di Campaign Standard (o **[!UICONTROL Audiences]** nell&#39;intestazione), quindi seleziona il **[!UICONTROL Adobe Experience Platform]** ambiente.

![](assets/aep_audiences_access.png)

Verrai prima indirizzato alla pagina dell’elenco dei segmenti Adobe Experience Platform, dove è possibile accedere ai segmenti Adobe Experience Platform già esistenti per ulteriori modifiche.

Sono disponibili una barra di ricerca e un filtro per aiutarti a trovare il segmento Adobe Experience Platform desiderato.

![](assets/aep_audiences_list.png)

## Creazione di tipi di pubblico Adobe Experience Platform

Per creare un pubblico Adobe Experience Platform direttamente in Campaign Standard, effettua le seguenti operazioni:

1. Dalla pagina dell’elenco dei segmenti di Adobe Experience Platform, fai clic sul pulsante **[!UICONTROL New audience]** nell&#39;angolo a destra.

   ![](assets/aep_audiences_creation_create.png)

1. Il Generatore di segmenti dovrebbe ora essere visualizzato nell’area di lavoro. Ti consente di creare un segmento utilizzando i dati di Adobe Experience Platform che verranno utilizzati per creare il pubblico.

1. Assegna un nome al segmento nel riquadro di destra e immetti una descrizione (facoltativa).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Per creare correttamente un segmento, devi selezionare un **criterio di unione** che corrisponde allo scopo di marketing per questo segmento.

   Nel riquadro delle impostazioni, viene selezionato un criterio di unione predefinito della piattaforma. Per ulteriori informazioni sui criteri di unione, consulta la sezione dedicata dalla sezione [Guida utente di Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Definisci le regole che identificheranno i profili da recuperare nel pubblico.

   A questo scopo, trascina gli attributi e/o gli eventi desiderati dal riquadro di sinistra nell’area di lavoro, definisci le regole corrispondenti e fai clic sul pulsante **[!UICONTROL Create segment]** per salvare il segmento (vedi [Utilizzo del Generatore di segmenti](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

Il pubblico è ora pronto per essere attivato e può essere utilizzato come destinazione per le campagne (consulta [Targeting dei tipi di pubblico di Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Modifica di tipi di pubblico

Per modificare un pubblico, aprilo e modifica le regole in base alle esigenze all’interno dell’interfaccia di Segment Builder (consulta [Utilizzo del Generatore di segmenti](../../integrating/using/aep-using-segment-builder.md)).

Una volta completate le modifiche, fai clic sul pulsante **[!UICONTROL Save segment]** per aggiornare il pubblico.

![](assets/aep_audiences_editing.png)
