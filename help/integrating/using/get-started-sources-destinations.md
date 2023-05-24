---
title: Guida introduttiva a origini e destinazioni
description: Ulteriori informazioni su origini e destinazioni di Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 17%

---

# Guida introduttiva a origini e destinazioni {#rtcdp}

## Informazioni su origini e destinazioni

Con Adobe Experience Platform, puoi condividere i dati tra Campaign Standard e Adobe Real-time Customer Data Platform (RTCDP). Questo ti consente di indirizzare l’attività ai tipi di pubblico di Adobe Experience Platform nei flussi di lavoro di Campaign e di inviarli nuovamente ad Adobe Real-time Customer Data Platform, con dati relativi a tali tipi di pubblico, ad esempio invii, aperture e clic.

* Con **Destinazioni**, inserisci i tipi di pubblico da Adobe Experience Platform a Campaign Standard. Questo ti consente di attivare i dati noti e sconosciuti per le campagne di marketing.
* Con **Sorgenti**, esporta i dati di Campaign Standard (ad esempio invii, aperture, clic) in Adobe Experience Platform. Questo consente di centralizzare i dati raccolti da origini diverse in un’unica posizione e di utilizzare le informazioni acquisite per fare di più.


>[!IMPORTANT]
>
>Tieni presenti i limiti di archiviazione SFTP, i limiti di archiviazione del database e i limiti del profilo attivo in base al tuo contratto Adobe Campaign durante l’esecuzione di questa integrazione.

Per una panoramica più dettagliata di Adobe Real-time Customer Data Platform, Destinazioni e Origini, consulta queste pagine:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=it)
* [Documentazione sulle destinazioni](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=it)
* [Documentazione sulle origini](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it)

## Collegare Campaign Standard a Adobe Experience Platform

Per poter condividere i dati tra Adobe Experience Platform e Campaign Standard, devi innanzitutto collegare Adobe Campaign as a **Destinazione**, e connettere il percorso di archiviazione BLOB di AWS S3 o Azure come **Sorgente** in Adobe experience Platform.

Una volta configurati i connettori, puoi impostare un’importazione o un’esportazione di dati in Campaign Standard utilizzando i flussi di lavoro.

![](assets/rtcdp-schema.png)

Per ulteriori informazioni su come impostare questi processi di importazione ed esportazione, consulta le sezioni seguenti:

* [Inserire il pubblico di Adobe Experience Platform in Campaign](../../integrating/using/ingest-aep-data.md)
* [Esportare dati da Campaign ad Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
