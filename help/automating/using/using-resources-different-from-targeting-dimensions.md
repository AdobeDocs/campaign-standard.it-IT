---
title: Utilizzo di risorse diverse dalle dimensioni di targeting
description: Scoprite come utilizzare una risorsa diversa dalla dimensione di targeting.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 81%

---


# Utilizzo di risorse diverse dalle dimensioni di targeting {#using-resources-different-from-targeting-dimensions}

In questi casi di utilizzo viene illustrato come utilizzare una risorsa diversa dalla dimensione di targeting, ad esempio per cercare un record specifico in una tabella lontana.

Per ulteriori informazioni sul targeting delle dimensioni e delle risorse, consulta [questa sezione](../../automating/using/query.md#targeting-dimensions-and-resources)

**Esempio 1: identificazione dei profili target interessati dalla consegna con l’etichetta “Bentornato”**.

* In questo caso, desideri eseguire il targeting dei profili. Imposta la dimensione di targeting su **[!UICONTROL Profiles (profile)]**.
* Desideri filtrare i profili selezionati in base all’etichetta di consegna. Pertanto, imposta la risorsa su **[!UICONTROL Delivery logs]**. In questo modo filtri direttamente nella tabella dei registri di consegna, che offre prestazioni migliori.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Esempio 2: identificazione dei profili target non interessati dalla consegna con l’etichetta “Bentornato”**

Nell’esempio precedente, hai utilizzato una risorsa diversa dalla dimensione di targeting. Puoi eseguire questa operazione solo se desideri trovare un record **presente** nella tabella lontana (log di consegna nell’esempio).

Se desideri trovare un record **non presente** nella tabella lontana (ad esempio profili non interessati da una consegna specifica), devi utilizzare la stessa risorsa e la stessa dimensione di targeting, in quanto il record non risulta presente nella tabella lontana (log di consegna).

* In questo caso, desideri eseguire il targeting dei profili. Imposta la dimensione di targeting su **[!UICONTROL Profiles (profile)]**.
* Desideri filtrare i profili selezionati in base all’etichetta di consegna. Non puoi filtrare direttamente sui log di consegna perché stai cercando un record non presente in questa tabella. Pertanto, imposta la risorsa su **[!UICONTROL Profile (profile)]** e crea la query sulla tabella dei profili.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
