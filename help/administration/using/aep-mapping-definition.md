---
title: Definizione mappature
description: Scopri come mappare un campo Campaign Standard con un campo Experience Data Model (XDM).
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 327d0e4f862b39c60fb3943d1128f4f42828bc0d

---


# Definizione mappature {#mapping-definition}

>[!IMPORTANT]
>
>Campaign Standard Data Service è attualmente in versione beta, che potrebbe essere oggetto di aggiornamenti frequenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta l&#39;Assistenza clienti Adobe.

In questa sezione scoprirai come mappare un campo Campaign Standard con un campo Experience Data Model (XDM).

Per eseguire questa attività, i prerequisiti sono:

* una definizione dello schema XDM tramite l&#39;interfaccia o utilizzando l&#39;API REST associata a XDM
* creazione di set di dati in base alla definizione dello schema XDM

1. Vai a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** e scegli la **[!UICONTROL Data mappings]** voce.

1. Fate clic su **[!UICONTROL Create]** per avviare una nuova mappatura XDM.

   ![](assets/aep_createmapping.png)

1. Completa i campi obbligatori e seleziona:

   * una dimensione **di** targeting: schema Campaign Standard da mappare
   * un **set di dati**: si tratta del pacchetto di dati associato a uno schema XDM in Adobe Experience Platform.

>[!NOTE]
>
>Affinché un batch venga assimilato in Real-time Customer Profile o Identity Service, il set di dati deve essere [abilitato per il Real-time Customer Profile](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html).
>
>Se il set di dati selezionato è già utilizzato in una mappatura dati esistente, viene visualizzato un avviso per informare l&#39;utente che i dati potrebbero essere sovrascritti in Adobe Experience Platform. Ciò può accadere quando alcuni destinatari comuni nelle mappature dati utilizzano lo stesso set di dati.

Nella schermata seguente viene visualizzata la **[!UICONTROL Field mappings]** sezione in cui è possibile creare una nuova mappatura per ciascun campo nello schema Campaign Standard.

![](assets/aep_fieldmappings.png)

Il **[!UICONTROL Create new field mapping]** pulsante consente di selezionare il campo Campaign Standard e l&#39;espressione del percorso del campo corrispondente nello schema XDM.

Se non è possibile trovare un campo Campaign Standard, è possibile utilizzare il campo di ricerca per cercare il campo. Attualmente, la ricerca funziona solo per i campi aperti nella gerarchia.

![](assets/aep_mapfield.png)

Le risorse estese definite in Campaign Standard sono mappate su tutti i campi nativi. Sono definiti nell&#39;estensione _customer/default in XDM.

![](assets/aep_fieldscusmapping.png)

Potete personalizzare l&#39;estensione XDM tramite l&#39;API e definire la vostra estensione per un migliore controllo sulla mappatura.

Per ulteriori informazioni sull&#39;API XDM, consultate l&#39;esercitazione [API del Registro di sistema dello](https://docs.adobe.com/content/help/en/experience-platform/xdm/api/getting-started.html) schema.

Per mappare un campo di enumerazione, è necessario utilizzare l&#39;editor di espressioni per definire ogni valore di enumerazione corrispondente al valore XDM. Ad esempio, postalAdressfield deve essere definito come:

![](assets/aep_enummapping.png)

Se il valore XDM è definito come enumerazione nello schema XDM, è possibile utilizzare la funzione EXDM nativa che sostituirà automaticamente la sintassi **del ciclo di vita** .

![](assets/aep_enummappingexdm.png)

Per modificare una mappatura XDM, apritela, modificate le informazioni desiderate e salvatela.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Per il momento, se si modifica un valore nella **[!UICONTROL Field mappings]** sezione e si fa clic all&#39;esterno del campo, la modifica non viene visualizzata nell&#39;interfaccia finché non si fa clic sul **[!UICONTROL Save]** pulsante. Questo comportamento si verifica solo una volta, quando la modifica **[!UICONTROL Field Mappings]** è la prima modifica sulla pagina.
