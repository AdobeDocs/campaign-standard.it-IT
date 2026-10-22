---
title: Utilizzo di risorse diverse dalle dimensioni targeting
description: Scopri come utilizzare una risorsa diversa dalla dimensione di targeting.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
TQID: 'https://experienceleague.adobe.com/tGVP20eQpo7EuB1xluX2AQHHMZ-IM-q6JmgFGp6Iwk4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 76%
---
# Utilizzo di risorse diverse dalle dimensioni targeting {#using-resources-different-from-targeting-dimensions}

In questi casi d’uso viene illustrato come utilizzare una risorsa diversa dalla dimensione di targeting, ad esempio, per cercare un record specifico in una tabella lontana.

Per ulteriori informazioni sulle dimensioni di targeting e sulle risorse, consulta [questa sezione](../../automating/using/query.md#targeting-dimensions-and-resources)

**Esempio 1: identificazione dei profili target interessati dalla consegna con l’etichetta “Bentornato”**.

* In questo caso, desideri eseguire il targeting dei profili. Imposta la dimensione targeting su **[!UICONTROL Profiles (profile)]**.
* Desideri filtrare i profili selezionati in base all’etichetta di consegna. Pertanto, imposta la risorsa su **[!UICONTROL Delivery logs]**. In questo modo, filtra direttamente nella tabella dei registri di consegna, che offrirà prestazioni migliori.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Esempio 2: identificazione dei profili target non interessati dalla consegna con l’etichetta “Bentornato”**

Nell’esempio precedente, hai utilizzato una risorsa diversa dalla dimensione targeting. Puoi eseguire questa operazione solo se desideri trovare un record **presente** nella tabella lontana (log di consegna nell’esempio).

Se desideri trovare un record **non presente** nella tabella lontana (ad esempio profili non interessati da una consegna specifica), devi utilizzare la stessa risorsa e la stessa dimensione targeting, in quanto il record non risulta presente nella tabella lontana (log di consegna).

* In questo caso, desideri eseguire il targeting dei profili. Imposta la dimensione targeting su **[!UICONTROL Profiles (profile)]**.
* Desideri filtrare i profili selezionati in base all’etichetta di consegna. Non puoi filtrare direttamente sui log di consegna perché stai cercando un record non presente in questa tabella. Pertanto, imposta la risorsa su **[!UICONTROL Profile (profile)]** e crea la query sulla tabella dei profili.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
