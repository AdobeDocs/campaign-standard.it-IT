---
title: Utilizzo di risorse diverse dalle dimensioni di targeting
description: Scopri come utilizzare una risorsa diversa dalla dimensione di targeting.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 76%

---

# Utilizzo di risorse diverse dalle dimensioni di targeting {#using-resources-different-from-targeting-dimensions}

In questi casi d’uso viene illustrato come utilizzare una risorsa diversa dalla dimensione di targeting, ad esempio, per cercare un record specifico in una tabella lontana.

Per ulteriori informazioni sulle dimensioni di targeting e sulle risorse, consulta [questa sezione](../../automating/using/query.md#targeting-dimensions-and-resources)

**Esempio 1: identificazione dei profili target interessati dalla consegna con l’etichetta “Bentornato”**.

* In questo caso, desideri eseguire il targeting dei profili. Imposta la dimensione di targeting su **[!UICONTROL Profiles (profile)]**.
* Desideri filtrare i profili selezionati in base all’etichetta di consegna. Pertanto, imposta la risorsa su **[!UICONTROL Delivery logs]**. In questo modo, filtra direttamente nella tabella dei registri di consegna, che offrirà prestazioni migliori.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Esempio 2: identificazione dei profili target non interessati dalla consegna con l’etichetta “Bentornato”**

Nell’esempio precedente, hai utilizzato una risorsa diversa dalla dimensione di targeting. Puoi eseguire questa operazione solo se desideri trovare un record **presente** nella tabella lontana (log di consegna nell’esempio).

Se desideri trovare un record **non presente** nella tabella lontana (ad esempio profili non interessati da una consegna specifica), devi utilizzare la stessa risorsa e la stessa dimensione di targeting, in quanto il record non risulta presente nella tabella lontana (log di consegna).

* In questo caso, desideri eseguire il targeting dei profili. Imposta la dimensione di targeting su **[!UICONTROL Profiles (profile)]**.
* Desideri filtrare i profili selezionati in base all’etichetta di consegna. Non puoi filtrare direttamente sui log di consegna perché stai cercando un record non presente in questa tabella. Pertanto, imposta la risorsa su **[!UICONTROL Profile (profile)]** e crea la query sulla tabella dei profili.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
