---
title: Guida introduttiva a origini e destinazioni
description: Ulteriori informazioni su origini e destinazioni di Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ba6205fa-dbcf-497a-882f-f15c00f12e68
TQID: https://experienceleague.adobe.com/r1rASYXuo-xeKH80eZVYG-jUhxy93GuTa8CIDyouSNY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 314
ht-degree: 18%

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

Per condividere i dati tra Adobe Experience Platform e Campaign Standard, devi innanzitutto connettere Adobe Campaign come **Destinazione** e il percorso di archiviazione BLOB AWS S3 o Azure come **Source** in Adobe Experience Platform.

Una volta configurati i connettori, puoi impostare un’importazione o un’esportazione di dati in Campaign Standard utilizzando i flussi di lavoro.

![](assets/rtcdp-schema.png)

Per ulteriori informazioni su come impostare questi processi di importazione ed esportazione, consulta le sezioni seguenti:

* [Inserire il pubblico di Adobe Experience Platform in Campaign](../../integrating/using/ingest-aep-data.md)
* [Esportare dati da Campaign ad Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
