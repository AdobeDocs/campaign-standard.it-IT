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
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 0%

---

# Definizione mappature {#mapping-definition}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

In questa sezione viene illustrato come mappare un campo Campaign Standard con un campo Experience Data Model (XDM).

Per eseguire questa attività, i prerequisiti sono i seguenti:

* una definizione dello schema XDM tramite l’interfaccia o utilizzando l’API REST associata a XDM
* creazione di un set di dati in base alla definizione dello schema XDM

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** e scegli la voce **[!UICONTROL Data mappings]**.

1. Fai clic su **[!UICONTROL Create]** per avviare una nuova mappatura XDM.

   ![](assets/aep_createmapping.png)

1. Compila i campi obbligatori e seleziona:

   * a **dimensione di targeting**: schema Campaign Standard da mappare
   * a **set di dati**: si tratta del pacchetto di dati associato a uno schema XDM in Adobe Experience Platform.

>[!NOTE]
>
>Affinché un batch possa essere acquisito in Profilo cliente o servizio Identity in tempo reale, il set di dati deve essere [abilitato per Profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/intro/get-started.html).
>
>Se il set di dati selezionato è già in uso in una mappatura dati esistente, viene visualizzato un avviso per informare l’utente che i dati potrebbero essere sovrascritti in Adobe Experience Platform. Questo può accadere quando ci sono alcuni destinatari comuni nelle mappature dati che utilizzano uno stesso set di dati.

La schermata seguente presenta la sezione **[!UICONTROL Field mappings]** in cui è possibile creare una nuova mappatura per ciascun campo nello schema di Campaign Standard.

![](assets/aep_fieldmappings.png)

Il pulsante **[!UICONTROL Create new field mapping]** ti consente di selezionare il campo Campaign Standard e l’espressione del percorso del campo corrispondente nello schema XDM.

Se non riesci a trovare un campo Adobe Campaign Standard, puoi utilizzare il campo di ricerca per cercare il campo. Attualmente, la ricerca funziona solo per i campi aperti nella gerarchia.

![](assets/aep_mapfield.png)

Le risorse estese definite in Campaign Standard sono mappate con tutti i campi nativi. Vengono definite nell&#39;estensione _customer/default in XDM.

![](assets/aep_fieldscusmapping.png)

Puoi personalizzare l’estensione XDM tramite l’API e definire la tua estensione per un migliore controllo sulla mappatura.

Per ulteriori informazioni sull’API XDM, consulta l’ [esercitazione sull’API del Registro di sistema dello schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) .

Per mappare un campo di enumerazione, devi utilizzare l’editor di espressioni per definire ogni valore di enumerazione corrispondente al valore XDM. Ad esempio, il campo postaladdressfield deve essere definito come:

![](assets/aep_enummapping.png)

Se il valore XDM è definito come enumerazione nello schema XDM, è possibile utilizzare la funzione nativa EXDM che sostituirà automaticamente la sintassi **lif**.

![](assets/aep_enummappingexdm.png)

Per modificare una mappatura XDM, aprilo, modifica le informazioni desiderate e salvalo.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Per il momento, se modifichi un valore nella sezione **[!UICONTROL Field mappings]** e fai clic all’esterno del campo, la modifica non viene visualizzata nell’interfaccia finché non fai clic sul pulsante **[!UICONTROL Save]** . Questo comportamento si verifica una sola volta, quando la modifica su **[!UICONTROL Field Mappings]** è la prima modifica sulla pagina.
