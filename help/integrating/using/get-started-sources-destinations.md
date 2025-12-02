---
title: Guida introduttiva a origini e destinazioni
description: Ulteriori informazioni su origini e destinazioni di Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 13%

---

# Guida introduttiva a origini e destinazioni {#rtcdp}

## Informazioni su origini e destinazioni

Con Adobe Experience Platform puoi condividere i dati tra Campaign Standard e Adobe Real-time Customer Data Platform (RTCDP). Questo consente di indirizzare l’attività ai tipi di pubblico di Adobe Experience Platform nei flussi di lavoro di Campaign e quindi di inviare ad Adobe Real-time Customer Data Platform i dati relativi a tali tipi di pubblico, ad esempio invii, aperture e clic.

* Con **Destinazioni**, acquisisci il pubblico da Adobe Experience Platform in Campaign Standard. Questo ti consente di attivare i dati noti e sconosciuti per le campagne di marketing.
* Con **Origini**, esporta i dati di Campaign Standard (ad esempio invii, aperture, clic) in Adobe Experience Platform. Questo consente di centralizzare i dati raccolti da origini diverse in un’unica posizione e di utilizzare le informazioni acquisite per fare di più.


>[!IMPORTANT]
>
>Tieni presenti i limiti di archiviazione SFTP, i limiti di archiviazione del database e i limiti del profilo attivo in base al tuo contratto Adobe Campaign durante l’esecuzione di questa integrazione.

Per una panoramica più dettagliata di Adobe Real-time Customer Data Platform, Destinations and Sources, consulta queste pagine:

* [Adobe Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/overview.html?lang=it)
* [Documentazione sulle destinazioni](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=it)
* [Documentazione sulle origini](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=it)

## Collegare Campaign Standard a Adobe Experience Platform

Per condividere i dati tra Adobe Experience Platform e Campaign Standard, devi innanzitutto connettere Adobe Campaign come **Destinazione** e il percorso di archiviazione BLOB di AWS S3 o Azure come **Source** in Adobe Experience Platform.

Una volta configurati i connettori, puoi impostare un’importazione o un’esportazione di dati in Campaign Standard utilizzando i flussi di lavoro.

![](assets/rtcdp-schema.png)

Per ulteriori informazioni su come impostare questi processi di importazione ed esportazione, consulta le sezioni seguenti:

* [Inserire il pubblico di Adobe Experience Platform in Campaign](../../integrating/using/ingest-aep-data.md)
* [Esportare dati da Campaign ad Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
