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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f3a668860659e40645ce3e4aab879cae5ad90083
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# Utilizzo di risorse diverse dalle dimensioni di targeting {#using-resources-different-from-targeting-dimensions}

In questi casi di utilizzo viene illustrato come utilizzare una risorsa diversa dalla dimensione di targeting, ad esempio per cercare un record specifico in una tabella lontana.

Per ulteriori informazioni sul targeting delle dimensioni e delle risorse, consulta [questa sezione](../../automating/using/query.md#targeting-dimensions-and-resources)

**Esempio 1: identificare i profili interessati dalla consegna con l&#39;etichetta &quot;Bentornato!&quot;**.

* In questo caso, vogliamo eseguire il targeting dei profili. Imposteremo la dimensione di targeting su **[!UICONTROL Profiles (profile)]**.
* Vogliamo filtrare i profili selezionati in base all&#39;etichetta di consegna. Pertanto, imposteremo la risorsa su **[!UICONTROL Delivery logs]**. In questo modo, filtriamo direttamente nella tabella del registro di consegna, che offrirà prestazioni migliori.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Esempio 2: identificare i profili che non erano interessati dalla consegna con l&#39;etichetta &quot;Bentornato!&quot;**

Nell&#39;esempio precedente, abbiamo utilizzato una risorsa diversa dalla dimensione di targeting. Questa operazione è possibile solo se si desidera trovare un record **presente** nella tabella lontana (log di consegna nel nostro esempio).

Se si desidera trovare un record che non **sia presente** nella tabella lontana (ad esempio, profili non mirati da una consegna specifica), è necessario utilizzare la stessa dimensione di risorsa e targeting, in quanto il record non sarà presente nella tabella lontana (log di consegna).

* In questo caso, vogliamo eseguire il targeting dei profili. Imposteremo la dimensione di targeting su **[!UICONTROL Profiles (profile)]**.
* Vogliamo filtrare i profili selezionati in base all&#39;etichetta di consegna. Non è possibile filtrare direttamente sui registri di consegna perché stiamo cercando un record non presente nella tabella dei registri di consegna. Pertanto, imposteremo la risorsa per **[!UICONTROL Profile (profile)]** e costruiremo la nostra query sulla tabella dei profili.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
