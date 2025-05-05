---
title: Definizione mappature
description: Scopri come mappare un campo Campaign Standard con un campo Experience Data Model (XDM).
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 6383ddbe-922a-4363-a1da-166cf717b0dd
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 0%

---

# Definizione mappature {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Contatta l’Assistenza clienti di Adobe se desideri accedervi.

In questa sezione scoprirai come mappare un campo Campaign Standard con un campo Experience Data Model (XDM).

Per eseguire questa attività, i prerequisiti sono:

* una definizione dello schema XDM tramite l’interfaccia o utilizzando l’API REST associata a XDM
* una creazione di set di dati basata sulla definizione dello schema XDM

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** e scegli la voce **[!UICONTROL Data mappings]**.

1. Fai clic su **[!UICONTROL Create]** per avviare una nuova mappatura XDM.

   ![](assets/aep_createmapping.png)

1. Compila i campi obbligatori e seleziona:

   * una **dimensione di targeting**: questo è lo schema Campaign Standard da mappare
   * un **set di dati**: questo è il pacchetto di dati associato a uno schema XDM in Adobe Experience Platform.

>[!NOTE]
>
>Affinché un batch possa essere acquisito in Real-time Customer Profile o Identity Service, il set di dati deve essere [abilitato per Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html?lang=it).
>
>Se il set di dati selezionato è già utilizzato in una mappatura dati esistente, viene visualizzato un avviso per informare che i dati potrebbero essere sovrascritti in Adobe Experience Platform. Ciò può verificarsi quando sono presenti alcuni destinatari comuni nei mapping dei dati che utilizzano lo stesso set di dati.

La schermata seguente presenta la sezione **[!UICONTROL Field mappings]** in cui è possibile creare una nuova mappatura per ogni campo nello schema Campaign Standard.

![](assets/aep_fieldmappings.png)

Il pulsante **[!UICONTROL Create new field mapping]** consente di selezionare il campo Campaign Standard e l&#39;espressione del percorso del campo corrispondente nello schema XDM.

Se non riesci a trovare un campo Adobe Campaign Standard, puoi utilizzarlo per cercare il campo. Attualmente, la ricerca funziona solo per i campi aperti nella gerarchia.

![](assets/aep_mapfield.png)

Le risorse estese definite in Campaign Standard vengono mappate come tutti i campi nativi. Sono definite nell’estensione _customer/default in XDM.

![](assets/aep_fieldscusmapping.png)

Puoi personalizzare l’estensione XDM tramite l’API e definire una tua estensione che ti consenta di controllare meglio la mappatura.

Per ulteriori dettagli sull&#39;API XDM, consulta l&#39;[esercitazione sull&#39;API del Registro di schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=it).

Per mappare un campo di enumerazione, è necessario utilizzare l’editor di espressioni per definire ogni valore di enumerazione corrispondente al valore XDM. Ad esempio, il campo postaladdressfield deve essere definito come:

![](assets/aep_enummapping.png)

Se il valore XDM è definito come enumerazione nello schema XDM, puoi utilizzare la funzione EXDM nativa che sostituirà automaticamente la sintassi **lif**.

![](assets/aep_enummappingexdm.png)

Per modificare una mappatura XDM, aprila, modifica le informazioni desiderate, quindi salvala.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Per il momento, se modifichi un valore nella sezione **[!UICONTROL Field mappings]** e fai clic all&#39;esterno del campo, la modifica non viene visualizzata nell&#39;interfaccia finché non fai clic sul pulsante **[!UICONTROL Save]**. Questo comportamento si verifica una sola volta, quando la modifica su **[!UICONTROL Field Mappings]** è la prima modifica sulla pagina.
